# n2n v3 supernode docker  

This container will create a example config file named */conf/supernode.conf.example* at */conf*.  
Then modify the */conf/supernode.conf.example* and rename it to */conf/supernode.conf*.   
If you already had a config file, just put it into */conf*.    

### Links
- [n2n github](https://github.com/ntop/n2n)  
- [dockerfile(github)](https://github.com/fnMrRice/Dockerfiles/tree/master/n2n_v3_supernode)  
- [dockerhub](https://hub.docker.com/r/dorasan/n2n_v3_supernode)  

### Usage
```bash
docker run -d --name='n2n_v3_supernode' \
              --net='host' \
              -v '/etc/n2n/supernode':'/conf':'rw' \
              'dorasan/n2n_v3_supernode'
```
