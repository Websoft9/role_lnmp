Ansible Role: lnmp
=========

本 Role 在CentOS或者Ubuntu服务器上安装和配置 LNMP。

## Requirements

运行本 Role，请确认符合如下的必要条件：

| **Items**      | **Details** |
| ------------------| ------------------|
| Operating system | CentOS7.x Ubuntu18.04 AmazonLinux|
| Python 版本 | Python2  |
| Python 组件 |    |
| Runtime |  |


## Related roles

本 Role 在语法上不依赖其他 role 的变量，但程序运行时需要确保已经运行: nginx, php-fpm。以 LNMP 为例：

```
  roles:
    - {role: role_common, tags: "role_common"}
    - {role: role_cloud, tags: "role_cloud"}
    - {role: role_apache, tags: "role_apache"}
    - {role: role_mysql, tags: "role_mysql"}
    - {role: role_php-fpm, tags: "role_php-fpm"}
    - {role: role_lnmp, tags: "role_lnmp"}
```


## Variables

暂无

## Example

```
- name: LNMP
  hosts: all
  become: yes
  become_method: sudo 
  vars_files:
    - vars/main.yml 

  roles:
    - {role: role_common, tags: "role_common"}
    - {role: role_cloud, tags: "role_cloud"}
    - {role: role_nginx, tags: "role_nginx"}
    - {role: role_redis, tags: "role_redis"}
    - {role: role_mysql, tags: "role_mysql"}
    - {role: role_php-fpm, tags: "role_php-fpm"}
    - {role: role_lnmp, tags: "role_lnmp"}
    - {role: role_phpmyadmin, tags: "role_phpmyadmin"}
    - {role: role_9panel, tags: "role_9panel"}
    - {role: role_inotify_watch, tags: "inotify_watch"}
    - {role: role_init_password, tags: "init_password"}
    - {role: role_preend, tags: "role_preend"}
    - {role: role_end, tags: "role_end"}
```

## FAQ


