# Kapacitor Client Module

This package is forked from official client [repo](https://github.com/influxdata/kapacitor/tree/master/client/v1)
I just make it compatible with GoModule.

# Install
> NOTE: You DON'T need manually install this package if GO111MODULE=on.

go get github.com/shaodan/kapacitor-client


## Usage

```
import (
	"fmt"
	"log"

	client "github.com/shaodan/kapacitor-client"
)

k, err := client.New(client.Config{
	URL:                fmt.Sprintf("http://%s:%d", kapacitorHost, kapacitorPort),
	Timeout:            time.Second * time.Duration(kapacitorTimeout),
	InsecureSkipVerify: kapacitorSSL,
})

if err != nil {
	log.Fatal("Unable to connect Kapacitor %s", err)
}

rtt, version, err = k.Ping()

if err != nil {
     log.Println(err)
}

log.Printf("Connected to Kapacitor %s: %dms", version, rtt/time.Millisecond)
```

## Docs

* [GoDoc](https://godoc.org/github.com/influxdata/kapacitor/client/v1)
* [API Docs](https://docs.influxdata.com/kapacitor/latest/api/)
