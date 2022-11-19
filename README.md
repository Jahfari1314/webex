mport requests
import json
from getpass import getpass
from pprint import pprint

TOKEN = getpass('Paste your token: ')

BASEURL = "https://webexapis.com"
room = "/v1/rooms"

body = {}

bodyJSON = json.dumps(body)

headers = {
    'Authorization': 'Bearer ' + TOKEN,
    'Accept': 'application/json'

}

getRoom = BASEURL + room

response = requests.get(getRoom, headers=headers, data=body)

responseJSON = response.json()

pprint(responseJSON)
