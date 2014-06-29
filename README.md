# tournament-db #
Crowd-sourced database of Planetary Annihilation tournaments

## JSON Schema ##
All entries must adhere to the following JSON schema:

```json
{
  "$schema": "http://json-schema.org/schema#",
  "title": "Tournament",
  "description": "A Planetary Annihilation tournament",
  "type": "object",

  "properties":
  {
    "title":
    {
      "type": "string",
      "description": "The tournament's title/name"
    },

    "date":
    {
      "type": "string",
      "pattern": "^[0-9]{4}-[0-9]{2}-[0-9]{2}T[0-9]{2}:[0-9]{2}:[0-9]{2}$"
      "description": "ISO 8601 formatted UTC date and time the tournament is scheduled for"
    },

    "mode":
    {
      "type": "string",
      "description": "The tournament's format"
    },

    "url":
    {
      "type": "string",
      "description": "A URL pointing to additional information/signup"
    }

    "winner":
    {
      "oneOf": 
      [
        {"type": "null"},
        {"type": "string"}
      ]
      "description": "The tournament's winner(s) or null if none has been determined yet"
    }
  },

  "required": ["title", "date", "mode", "url", "winner"]
}
```
