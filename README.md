# Fieldnet
Weather station integration
{
    "$schema": "http://json-schema.org/draft-07/schema#",
    "$id": "https://docs.api.myfieldnet.com/schema/v2/weather-station-dashboard.json",
    "type": "object",
    "title": "Weather Station Dashboard",
    "description": "A single weather station entity",
    "required": [
        "name",
        "latitude",
        "longitude",
        "organization_id",
        "manufacturer",
        "model"
    ],
    "properties": {
        "id": {
            "type": "string",
            "pattern": "^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$",
            "description": "Unique identifier for the weather station",
            "readOnly": true
        },
        "application_id": {
            "type": "string",
            "pattern": "^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$",
            "description": "Unique identifier for the application that created this weather station",
            "readOnly": true
        },
        "group_id": {
            "type": [
                "string",
                "null"
            ],
            "pattern": "^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$",
            "description": "Optional unique identifier for the group this equipment is attached to",
            "readOnly": true
        },
        "organization_id": {
            "type": "string",
            "pattern": "^[0-9a-f]{8}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{4}-[0-9a-f]{12}$",
            "description": "Unique identifier for owner organization of this weather station, can only be set on the initial POST"
        },
        "name": {
            "type": "string",
            "description": "Name of the weather station"
        },
        "manufacturer": {
            "type": "string",
            "description": "The name of the manufacturer of this weather station hardware"
        },
        "model": {
            "type": "string",
            "description": "The model name of this weather station hardware"
        },
        "latitude": {
            "type": [
                "number"
            ],
            "minimum": -90,
            "maximum": 90,
            "description": "WGS84 latitude of this weather station"
        },
        "longitude": {
            "type": [
                "number"
            ],
            "minimum": -180,
            "maximum": 180,
            "description": "WGS84 longitude of this weather station"
        },
        "elevation": {
            "type": [
                "number",
                "null"
            ],
            "description": "Elevation of the weather station in metres"
        },
        "last_observation": {
            "type": [
                "string",
                "null"
            ],
            "format": "date-time",
            "description": "ISO8601 timestamp representing when the last observation occurred",
            "readOnly": true
        },
        "temperature": {
            "type": [
                "number",
                "null"
            ],
            "description": "Last known temperature reading in celsius",
            "readOnly": true
        },
        "precipitation_6_hours": {
            "type": [
                "number",
                "null"
            ],
            "description": "Sum of precipitation recorded over the past 6 hours in millimetres",
            "readOnly": true,
            "minimum": 0
        },
        "precipitation_24_hours": {
            "type": [
                "number",
                "null"
            ],
            "description": "Sum of precipitation recorded over the past 24 hours in millimetres",
            "readOnly": true,
            "minimum": 0
        },
        "wind_speed_average": {
            "type": [
                "number",
                "null"
            ],
            "description": "Average windspeed, measured in m/s",
            "readOnly": true,
            "minimum": 0
        },
        "wind_speed_gust": {
            "type": [
                "number",
                "null"
            ],
            "description": "Gusting windspeed, measured in m/s",
            "readOnly": true,
            "minimum": 0
        },
        "wind_direction": {
            "type": [
                "number",
                "null"
            ],
            "description": "Wind direction, measured in degrees from north",
            "readOnly": true,
            "minimum": 0,
            "exclusiveMaximum": 360
        },
        "relative_humidity": {
            "type": [
                "number",
                "null"
            ],
            "description": "Relative humidity, measured as a percentage of air saturation",
            "readOnly": true,
            "minimum": 0,
            "maximum": 100
        },
        "solar_radiation": {
            "type": [
                "number",
                "null"
            ],
            "description": "Solar radiation, measured in W/m^2",
            "readOnly": true,
            "minimum": 0
        },
        "time_zone": {
            "type": [
                "string",
                "null"
            ],
            "description": "IANA time zone string for the weather station",
            "readOnly": true
        }
    }
}
