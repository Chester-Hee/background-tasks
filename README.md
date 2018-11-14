# background-tasks

Laravel 扩展包，基于 MySQL 后台任务管理工具

- 管理和监控任务执行
- 让后台任务执行更简单
- 支持分布式集群


## Composer 安装

添加仓库源：

```json
"repositories" : [
    {
      "type": "git",
      "url": "https://github.com/Chester-Hee/background-tasks.git"
    }
]
```

添加扩展包：

```bash
composer require chester/background-mission ^1.0.5
```

## MySQL Migration

创建数据表：

```bash
background-tasks/src/2018_11_14_104840_test.php
```

配置 Provider：

```php
 Chester\BackgroundMission\Providers\MissionProvider::class
```

添加 Schedule 任务：

```php
$schedule->command('mission:execute')->everyMinute()->runInBackground();
```

## 命令测试

添加任务：

```markdown
$ php artisan mission:test-add-task
```

查看任务列表：

```markdown
$ php artisan mission:records
+------------------+--------------------------+--------+---------+--------+---------------------------------+
| unique_id        | method                   | type   | state   | params | content                         |
+------------------+--------------------------+--------+---------+--------+---------------------------------+
| bboagxnzbrnxurkx | helloWorld               | system | success | []     | hello world.                    |
| gngkiytndfratiho | helloWorldAfter15Seconds | system | success | []     | after 15 seconds , hello world. |
+------------------+--------------------------+--------+---------+--------+---------------------------------+
```

