# n2n v3 edge docker  
[n2n github](https://github.com/ntop/n2n)  
[dockerfile(github)](https://github.com/fnMrRice/Dockerfiles/tree/master/n2n_v3_edge)  
[dockerhub](https://hub.docker.com/r/dorasan/n2n_v3_edge)  
this container contains a script which can be located at /usr/sbin/start. The script checks wether /conf exists and copy a example conf file into /conf. Just modify the /conf/edge.conf.example and rename it to /conf/edge.conf to let the container work.   
What you need is to mount /conf.

## Usage
```bash
docker run -d --name='n2n_v3_edge' \
              --net='host' \
              -v '/mnt/user/appdata/n2n_v3_edge':'/conf':'rw' \
              'dorasan/n2n_v3_edge'
```
