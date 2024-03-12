
一、写一个Bash脚本，**每月的一号** 对 MongoDB 中 test.user_logs 表进行备份、清理
  - 首先备份上个月的数据，备份完成后打包成.gz文件，并传输到 **Backup [bak@bak.ipo.com]** 服务器上;
  - 备份完成后，再对30天之前的数据进行清理: **create_on [2024-01-01 03:33:11]** ;
  - 如果备份失败或者异常，则调用 [https://monitor.ipo.com/webhook/mongodb ];
  - 这个表每日数据量大约在 700w 条

二、现有一台服务器，上面运行了3个docker容器服务，需要通过iptables进行网络配置。请给出命令：
  - 只有Docker_A 与 Docker_B 之间可以相互通信，Docker_C 不能访问其它两个容器;
  - 只允许内网IP为 192.168.1.1 - 192.168.1.30 的内网IP访问所有容器;
  - Docker_A:8080 与 Docker_C:80 对外网提供服务, Docker_B:3316 不对外网提供服务;
  - 所有配置需要固化，重启服务器自动生效;

<img width="556" alt="09050e597247436a86ef57ca5802e5b" src="https://github.com/housesigma/hr-interview/assets/4161489/7f77ad88-406d-4e10-afe8-802cc5366f1a">

三、已知生产环境数据库结构如图所示，因为master服务器偶尔有硬件问题，需要先将slave_01提升为新master, 然后旧master变成slave_01。请给出操作方案和关键命令。
  - 主从数据库服务均处于独立服务器上，有独立的IP;
  - 应用程序写入数据库通过域名[mysql-master.ipo.com]访问;
  - 应用程序读取数据通过**Haproxy**[mysql-slave.ipo.com]访问所有从库[01-04];
  - 尽量平滑处理，不影响生产环境;

```mermaid
graph LR;
    Master-->Slave_01;
    Master-->Slave_02;
    Slave_01-->Slave_03;
    Slave_02-->Slave_04;
```

四、在生产环境中，应用程序是通过Haproxy来读取Slave集群，但是偶尔会产生 **SQLSTATE[HY000]: General error: 2006 MySQL server has gone away** 的错误，现已经排查：
  - 故障发生时，服务器之间防火墙正常，服务器之间可以正常通信;
  - 应用服务查询SQL正常，同时不存在性能问题;
  - 故障频率没有发现特别规律，与服务器负载没有正相关;
  - 查看各服务的日志，只发现了错误信息，但没有发现进一步说明;
  请根据经验，给出一排查方案与可能的方向，与开发一起定位问题

```mermaid
graph LR;
    Service-->Haproxy;
    Haproxy-->Slave_01;
    Haproxy-->Slave_02;
    Haproxy-->Slave_03;
    Haproxy-->Slave_04;
```

