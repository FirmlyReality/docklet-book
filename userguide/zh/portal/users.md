## 用户 ##

用户(Users)页面仅由具有 **管理员(admin)** 权限的用户访问。
该页面提供对docklet中用户信息展示、修改功能。
同时可以添加用户、用户组。

### 注册与激活 ###

目前docklet不支持自由注册，可以使用外部的认证系统登录（如pam）。

第一次使用外部账号认证登录时，账号处于未激活状态，登录之后页面左上角会显示一条待激活的通知，未激活的账号不能使用一些特定功能。

<img src="../images/user_init.png" width="300" alt="user activating">

点击该通知之后会进入激活页面，需要在该页面中填写E-mail、学号/职工号、部门、真实姓名、注册原因，提交申请之后，管理员会在审核该申请并邮件通知用户审核结果。

提交申请表单之后浏览器会自动登出，需要重新登录刷新用户信息。在审核期间docklet页面的左上角会显示等待审核的通知，点击即可关闭。
