# srt_config
主要用于设置srt相关的配置
- enable: srt服务使能配置,设置为true才可以使用srt功能

*类型*: bool

*值举例*: true

- addr[string]: srt服务监听地址,srt服务监听的是UDP端口

*类型*: string

*值举例*: ":6001"

# rtc_config
主要用于设置rtc相关的配置,目前rtc只实现了WHIP/WHEP,需要配合http_config一起使用
- enable: rtc服务使能配置,设置为true才可以使用rtc功能

*类型*: bool

*值举例*: true

- iceHostNatToIps: rtc服务内穿ip,具体为SDP中的candidate信息,不设置的话,会输出全部网卡的地址

*类型*: []string

*举例*: ["192.168.0.1"]

- iceUdpMuxPort: rtc udp复用端口

*类型*: int

*值举例*: 4888

- iceTcpMuxPort: rtc tcp复用端口

*类型*: int

*值举例*: 4888

# http_config
主要用于设置http相关的配置,依赖http的协议均需要设置,涉及的协议有rtc、http-fmp4、hls(fmp4/llhls)
- http_listen_addr: http服务监听地址

*类型*: string

*值举例*: ":1290"

- enable_https: https使能

*类型*: bool

*值举例*: true

- https_listen_addr: https监听地址

*类型*: string

*值举例*: ":1233"

- https_cert_file: https cert文件路径

*类型*: string

*值举例*: "./conf/cert.pem"

- https_key_file: https key文件路径

*类型*: string

*值举例*: "./conf/key.pem"

# http-fmp4配置
主要用于设置http-fmp4相关的配置,需要配合http_config一起使用
- enable: http-fmp4服务使能配置

*类型*: bool

*值举例*: true

# hls_config
主要用于设置hls-fmp4/llhls相关的配置,需要配合http_config一起使用,hls-ts的能力请使用lal,这里不做过多描述
- enable: hls-fmp4/llhls服务使能配置

*类型*: bool

*值举例*: true

- segmentCount: hls-fmp4 m3u8返回的切片个数,默认为7, llhls默认设置为7个(gohlslib要求)

*类型*: int

*值举例*: 3

- segmentDuration: hls-fmp4 切片时长,默认为1s

*类型*: int

*值举例*: 3

- partDuration:llhls part部分的时长,默认为200ms

*类型*: int

*值举例*: 100

- lowLatency: llhls使能配置,开启此配置后则都走llhls

*类型*: bool

*值举例*: true

# lal_config_path
主要设置lal配置文件的路径