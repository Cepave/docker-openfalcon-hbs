# docker-openfalcon-hbs

## Build

Enter the following command in the repo directory.

```
$sudo docker build --force-rm=true -t openfalcon-hbs .
```

## Run

### Basic Run

Use default mysql account, configuration, and falcon-hbs package.

```
$sudo docker run -dti --name hbs -p 6030:6030 -p 6031:6031 openfalcon-hbs
```

### Advanced Run

+ Self-defined mysql account and configuration

    Replace file **cfg.json** in the volume */config*.  
    For more detail about **cfg.json**, see [Heartbeat Server](http://book.open-falcon.com/zh/install/hbs.html).

+ New falcon-hbs package

    Replace file **falcon-hbs.tar.gz** in the volume */package*.
  
For example, **cfg.json** in /tmp/config and **falcon-hbs.tar.gz** in /tmp/pack,

```
$sudo docker run -dti --name hbs -v /tmp/pack:/package -v /tmp/config/cfg.json:/config/cfg.json -p 6030:6030 -p 6031:6031 openfalcon-hbs
```
