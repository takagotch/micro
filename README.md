### micro
---
https://github.com/micro/micro

https://micro.mu/docs/toolkit.html

```go
type ChangeSet struct {
  Data []byte
  Checksum string
  Format string
  Source string
  Timestamp time.Time
}

type Host struct {
  Address string `json:"address"`
  Port int `json:"port"`
}

type Config struct {
  Hosts map[string]Host `json:"host"`
}

var conf Config

config.Scan(&conf)

fmt.Println(conf.Hosts["database"].Address, conf.Hosts["database"].Port)


type Host struct {
  Address string `json:"address"`
  Port int `json:"port"`
}

var host host

config.Get("hosts", "database").Scan(&host)

fmt.Println("hosts", "database").Scan(&host)


address := config.Get("hosts", "database", "address").String("localhost")

port := config.Get("hosts", "database", "port").Int(3000)

w, err := config.Watch("hosts", "database")
if err != nil {
}

v, err := w.Next()
if err != nil {
}

var host Host

v.Scan(&host)


config.Load(
  env.NewSource(),
  flag.NewSource(),
  file.NewSource(
    file.WithPath("/tmp/config.json"),
  ),
)

e := yaml.NewEncoder()
s := consul.NewSource(
  source.WithEncoder(e),
)

e := yaml.NewEncoder()

r := json.NewReader(
  reader.WithEncoder(e),
)
```

```sh

```

```
```


