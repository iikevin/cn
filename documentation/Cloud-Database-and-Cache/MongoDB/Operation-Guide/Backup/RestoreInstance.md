# 数据恢复


云数据库 MongoDB 支持一键将备份数据恢复到原实例，数据恢复功能可以最大程度的减少数据损失。

## 注意事项

- 数据恢复将以备份数据覆盖原数据，此操作不可逆，请谨慎操作。建议操作前先手动创建备份。
- 数据恢复过程请勿对MongoDB 实例做写入操作。
- 数据恢复时间与数据量有关，数据量较大时会花费比较长的时间，请耐性等待。

## 前提条件

- 实例状态为运行，且计费状态正常。

## 操作步骤

1. 登录 [MongoDB 控制台](https://mongodb-console.jdcloud.com/mongodb)。
1. 在实例列表页面，选择目标实例，点击实例名称，进入实例详情页面。
1. 在实例详情页面，点击备份与恢复， 查看备份数据。
1. 选择要使用的备份，在操作项中点击“数据恢复”，打开确认弹窗。

   ![](https://github.com/jdcloudcom/cn/blob/master/image/mongodb/mongo-021.png)

1. 请点击“确定”，确认执行数据恢复，实例状态变更为“恢复中”，请等待数据恢复完成。


## 相关参考

- [手动创建备份](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Operation-Guide/Backup/CreateBackup.md)
- [根据备份创建实例](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Operation-Guide/Backup/CreateInstance2.md)
- [根据时间点创建实例](https://github.com/jdcloudcom/cn/blob/master/documentation/Cloud-Database-and-Cache/MongoDB/Operation-Guide/Backup/CreateInstance3.md)
