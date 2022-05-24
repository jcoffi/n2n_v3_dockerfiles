# n2n v3 edge docker  

This container will create a example config file named */conf/edge.conf.example* at */conf*.  
Then modify the */conf/edge.conf.example* and rename it to */conf/edge.conf*.   
If you already had a config file, just put it into */conf*.    

### Links
- [n2n github](https://github.com/ntop/n2n)  
- [dockerfile(github)](https://github.com/fnMrRice/Dockerfiles/tree/master/n2n_v3_edge)  
- [dockerhub](https://hub.docker.com/r/dorasan/n2n_v3_edge)  

### Usage
```bash
docker run -d --name='n2n_v3_edge' \
              --net='host' \
              -v '/etc/n2n/edge':'/conf':'rw' \
              'dorasan/n2n_v3_edge'
```
