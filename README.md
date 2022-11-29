```
npm i
sls offline
```


This results in:
```
Running "serverless" from node_modules

Starting Offline at stage dev (us-east-1)

Offline [http for lambda] listening on http://localhost:3002
Function names exposed for local invocation by aws-sdk:
           * MyFun: sls-offline-bug-dev-MyFun
Scheduling [MyFun] cron: [*/1 * * * *]
hello world
✖ Failed to execute scheduled function: [MyFun] Error: Error: Lambda timeout.
Traceback (most recent call last):
  File "/home/tiksa/dev/sls-offline-timeout-bug/node_modules/serverless-offline/src/lambda/handler-runner/python-runner/invoke.py", line 94, in <module>
    input = json.loads(stdin.readline())
  File "/usr/lib/python3.8/json/__init__.py", line 357, in loads
    return _default_decoder.decode(s)
  File "/usr/lib/python3.8/json/decoder.py", line 337, in decode

    obj, end = self.raw_decode(s, idx=_w(s, 0).end())
  File "/usr/lib/python3.8/json/decoder.py", line 355, in raw_decode
    raise JSONDecodeError("Expecting value", s, err.value) from None
json.decoder.JSONDecodeError: Expecting value: line 1 column 1 (char 0)
```


