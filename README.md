# Backend

# 1. run 
## data flow:
browser -> (post req) -> django page -> (stores file in /tmp/code.py) -> 
docker run -> (execute code) -> (store result in /tmp/code.out) -> 
(response to browser) -> browser callback (update UI)
## docker image && container
We can use: `docker pull python:3.5.2-alpine` as our running image,
and then, use volume to mount `tmp/code.py` on the host with `/tmp/code.py`
in the container. Then, execute, output content to file on host, you can reference:
https://github.com/besnik/simple-python-online-editor/blob/master/run_in_docker.sh