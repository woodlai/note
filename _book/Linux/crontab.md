# crontab

定时任务

## edit(编辑工作表)

```
crontab -e
```

命令构成为 时间+动作，其时间有`分、时、日、月、周`五种，操作符有

- `*` 取值范围内的所有数字
- `/` 每过多少个数字
- `-` 从 X 到 Z
- `，`散列数字

### 每小时执行

```
0 */1 * * * /home/sokee/sources/ddns/DdnsOnCloudFlare/updateIpv6.sh
```

## list (列出工作表里的命令)

```
crontab -l
```

## rm (删除工作)

```
crontab -r
```
