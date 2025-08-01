### 1. 逻辑卷扩容

```shell
pvcreate /dev/sdb /dev/sdc /dev/sdd
vgs
vgextend /dev/vg0 /dev/sd{b,c,d}
lvextend -l +100%free /dev/vg0/root
ext4：resize2fs /dev/b92-vg/root
xfs：xfs_growfs /dev/vg0/root
```



### 2. 2T以上硬盘格式化

``` shell
parted /dev/sdx
mklabel gpt
mkpart primary 0% 100%
print
```



###  3. 网络测速命令

```shell
iperf3 -c 107.148.199.113 -t 10 -P 10
```

测试本机到SV6节点2



### 4. 硬盘测速

```shell
(dd if=/dev/zero of=testfile bs=1G count=1 oflag=direct && dd if=testfile of=/dev/null bs=1G count=1 iflag=direct) && rm -f testfile
```



