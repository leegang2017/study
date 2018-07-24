http://man.linuxde.net/curl


curl 发送post json请求,设置 header
```sh
curl -l -H "Content-Type:application/json" -H "Accept:application/json" -X POST -d '{"useReady":true,"token":"341634a25cce3cbd5996e056da6a7bc9","url":"http://truck.g7s.huoyunren.com/v2/review/index.html?searchid=8D18D475439D3D660ED0DF626BC9B004&truckpk=8D18D475439D3D660ED0DF626BC9B004&searchtype=truckid&__displayrunner__=gateway&begintime=2018-06-28 18:50&endtime=2018-06-28 20:50"}' http://localhost:3000/common
```