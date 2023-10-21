# 📶为 小米五 开启 电信Volte

## ❌原因

国内运营商争相关闭 2G 信号，而电信3G又不走通话短信数据，小米官方给米5停更前也不解决好VOLTE问题，导致现在电信卡在米5上无法使用volte,即无电话无短信，仅能上网了。

## ⚒️原理/方法

### 1,关闭系统Volte校验

  拨号输入'*#*#86583#*#*' 看到  volte carrier check was disabled 即可

### 2,将联通volte文件复制到电信目录下

  这是电信的文件`/firmware/image/modem_pr/mcfg/configs/mcfg_sw/mbn/ct/mcfg_sw.mbn`

  备份一份然后把原有的删除`/firmware/image/modem_pr/mcfg/configs/mcfg_sw/mbn/ct/mcfg_sw.mbn.bak`

  ---

  这是联通Volte文件`/firmware/image/modem_pr/mcfg/configs/mcfg_sw/mbn/cu_volte/mcfg_sw.mbn`

  复制到电信目录下`/firmware/image/modem_pr/mcfg/configs/mcfg_sw/mbn/ct`

  ---

  重启手机  设置内将Volte打开即可

## ⚠️可能遇见的问题

### 1,我如何修改这些文件？

  #### 方法1

  Root手机  使用第三方root文件管理器

  （作者手机刷入magisk后不开机，即使用方法2）

  ---

  #### 方法2

  用电脑为手机刷入TWRP，刷后立即进入 防止被系统恢复

  #### TWRP “**挂载**”选项内，为Firmware打勾

  此时Firmware分区为只读，点击 “高级”>"终端"

  输入`mount -o rw,remount /firmware 将firmware`将firmware挂为读写

  之后点击 高级 > 文件管理 自行操作即可

