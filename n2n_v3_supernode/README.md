# n2n v3 supernode docker  
[n2n github](https://github.com/ntop/n2n)  
[dockerfile(github)](https://github.com/fnMrRice/Dockerfiles/tree/master/n2n_v3_supernode)  
[dockerhub](https://hub.docker.com/r/dorasan/n2n_v3_supernode)  
this container contains a script which can be located at /usr/sbin/start. The script checks wether /conf exists and copy a example conf file into /conf. 
Modify the /conf/supernode.conf.example and rename it to /conf/supernode.conf to let the container work.   

## Usage
```bash
docker run -d --name='n2n_v3_supernode' \
              --net='host' \
              -v '/etc/n2n/supernode':'/conf':'rw' \
              'dorasan/n2n_v3_supernode'
```
