# Create timeline from JSONL or CSV file

You can ingest timeline data from a JSONL or CSV file. You can have any number of attributes/columns as you wish but there are some mandatory fields that Timesketch needs in order to render the events in the UI.

**Mandatory fields:**

- `message` String with an informative message of the event
- `datetime` ISO8601 format for example: `2015-07-24T19:01:01+00:00`
- `timestamp_desc` String explaining what type of timestamp it is for example `file created`

## Filename

The filename must end with `.csv / .jsonl` otherwise the import will fail.

## Example CSV file

You need to provide the CSV header with the column names as the first line in the file.

    message,timestamp,datetime,timestamp_desc,extra_field_1,extra_field_2
    A message,1331698658276340,2015-07-24T19:01:01+00:00,Write time,foo,bar
    ...

## Example JSONL file

Unlike JSON files, imports in JSONL format can be streamed from disk, making them far less memory intensive than regular JSON files.

    {"message": "A message","timestamp": 123456789,"datetime": "2015-07-24T19:01:01+00:00","timestamp_desc": "Write time","extra_field_1": "foo"}
    {"message": "Another message","timestamp": 123456790,"datetime": "2015-07-24T19:01:02+00:00","timestamp_desc": "Write time","extra_field_1": "bar"}
    {"message": "Yet more messages","timestamp": 123456791,"datetime": "2015-07-24T19:01:03+00:00","timestamp_desc": "Write time","extra_field_1": "baz"}

## Upload the file to Timesketch

To create a new timeline in Timesketch you need to upload it to the server.

[See here for instructions to do so](/guides/user/upload-data/)
