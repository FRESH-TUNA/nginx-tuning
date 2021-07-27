
# nginx 튜닝

```bash
# 프로세스가 대량의 파일을 읽기 위해 늘려줌
echo 65536 > /proc/sys/fs/file-max 
sysctl -w fs.file-max=65536 

# 재부팅시에도 적용
echo "fs.file-max=65536" >> /etc/sysctl.conf
sysctl -a 
```


```bash
# [/etc/security/limits.conf 수정]
# PAM 사용자 인증 프로세스 갯수, 파일 디스크립터 제한 해제
nginx hard  nproc 10240
nginx soft   nproc 10240
nginx hard  nofile 204800
nginx soft   nofile 204800
```