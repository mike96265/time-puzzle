# time-puzzle
nginx shows sometimes upstream_response_time larger than request_time
```shell
# start backend-server
cd backend-server
openresty -p `pwd` -c nginx.conf
# start main server
cd ..
openresty -p `pwd` -c nginx.conf
# tracing with systemtap
stap -v -x {main server worker pid} -I tapset stap-scripts/request_time.stp

```
