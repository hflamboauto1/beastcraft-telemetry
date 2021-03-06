# InfluxDB (armhf)

### Debian

* [influxdb_0.13.0_armhf.deb](https://s3.eu-central-1.amazonaws.com/belodetech/influxdb_0.13.0_armhf.deb)

### Fedora/CentOS

* [influxdb_0.13.0_armhf.rpm](https://s3.eu-central-1.amazonaws.com/belodetech/influxdb-0.13.0.armhf.rpm)

### Build

```
# get sources
export VERSION=0.13.0
gvm use go1.5
gvm pkgset create influxdb
gvm pkgset use influxdb
cd ~/.gvm/pkgsets/go1.5/influxdb
export GOPATH=`pwd`
go get github.com/influxdata/influxdb || go get -u github.com/influxdata/influxdb
cd $GOPATH/src/github.com/influxdata/influxdb
git checkout $VERSION

# build
./build.py --package --version=$VERSION --arch=armhf
```

### Install (Debian)

```
dpkg -i build/*.deb
```

#### References

* http://www.aymerick.com/2013/09/24/go_language_on_raspberrypi.html
* http://www.aymerick.com/2015/10/07/influxdb-telegraf-grafana-raspberry-pi.html
* http://giatro.me/2015/09/30/install-influxdb-and-grafana-on-raspberry-pi.html
