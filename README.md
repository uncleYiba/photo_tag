项目说明
=========================================
图片打tag

图片数据存在files下面
但是对应的tag内容等必须存在数据库中

数据库结构
image表   所有的图片表
id
save_name   uuid的name
save_type   保存的文件格式
file_name   文件本身应该叫的名字
status  状态   0正常   1删除
create_time  创建时间
update_time  修改时间

CREATE TABLE IF NOT EXISTS `image`(
   `id` VARCHAR(32) PRIMARY KEY,
   `save_name` VARCHAR(32),
   `save_type` VARCHAR(8),
   `file_name` VARCHAR(64),
   `status` VARCHAR(1),
   `create_time` datetime,
   `update_time` datetime
)DEFAULT CHARSET=utf8;


tag表   所有的tag表
id
tag_name  tag对应的名字
status  状态   0正常   1删除
create_time  创建时间
update_time  修改时间

CREATE TABLE IF NOT EXISTS `tag`(
   `id` VARCHAR(32) PRIMARY KEY,
   `tag_name` VARCHAR(64),
   `status` VARCHAR(1),
   `create_time` datetime,
   `update_time` datetime
)DEFAULT CHARSET=utf8;

image_tag   图片的tag关系，方便整体删除修改等
id 
image_id
tag_id
create_time  创建时间

CREATE TABLE IF NOT EXISTS `image_tag`(
   `id` VARCHAR(32) PRIMARY KEY,
   `image_id` VARCHAR(32),
   `tag_id` VARCHAR(32),
   `create_time` datetime
)DEFAULT CHARSET=utf8;

功能说明
1.tag管理   增删改查 （还可以根据图片查  
2.image管理   增删查   （根据日期，tag两个维度查
3.image-tag管理   
批量打tag   选中一批图片直接为其打上某一个或者几个tag
批量删tag   选中一批图片删除他们的某一个或者几个tag(不含有的则不删)

菜单
1.tag管理
增删改查
2.图片管理
多维度查看，新增删除图片
3.标签设定
图片的标签管理




