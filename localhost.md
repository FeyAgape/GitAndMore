# Localhost help

## How to force application using localhost:<number> to shut down

`lsof -i :<localhost number i.e 9000>`

`kill <pid>`

repeat untill it doesn't show a list


**For Windows**, you will want to 

run `netstat -ano | findstr :9000` The number to the far right will be the PID of the process you want to kill.
