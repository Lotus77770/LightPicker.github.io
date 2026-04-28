- STS(安全凭证服务)
生成一个临时的访问凭证，授权给临时用户或角色，使其能够在限定时间内访问指定的资源

- RAM(资源允许管理)
管理分配身份和权限等,细化了用户,角色,权限策略

  - [用户](https://help.aliyun.com/zh/ram/user-guide/create-a-ram-user?spm=5176.2020520153.console-base_help.dexternal.3b22336a4FrDDN):实际的一个操作单位,拥有自己密码或密钥.它的权限可以是自身的,也可以切换为角色权限
    - 衍生的场景是一个账号可以有多个角色,这些角色可以通过密码登录.是现实的权限分配.
    - 给程序使用时有AccessKey好AccessID.比如我制作的网站中使用的请求STS临时令牌时需要一个用户. 
  - [角色](https://help.aliyun.com/zh/ram/user-guide/ram-role-overview?spm=5176.2020520153.console-base_help.dexternal.3b22336a4FrDDN):可以获得权限策略,当用户或角色扮演它时权限切换.
    - 可信实体:我的用法是在请求STS时需要一个可信实体(ARM中的用户或角色等),即请求STS时要求的一个用户. 
    - 角色链:当扮演角色后还可以继续扮演其他角色(权限是切换的).用途是通过设置信任策略可以清晰的提升权限.
- 权限策略:一组的权限的集合,可以被角色好用户使用
  - [权限策略语法](https://help.aliyun.com/zh/ram/policy-structure-and-syntax?spm=5176.2020520153.console-base_help.dexternal.3b22336a4FrDDN#concept-srq-fbk-xdb)

- 在使用SDK时([JAVA SDK.V1](https://help.aliyun.com/zh/oss/developer-reference/use-temporary-access-credentials-provided-by-sts-to-access-oss?spm=5176.8465980.console-base_help.dexternal.4e701450no1hN9))
  - 细节上.比如policy中的Resource处<region>是"oss-cn-beijing",要在实际的地域前加上"oss-"
  - JAVA中设置的policy和权限策略是交集关系,如果JAVA中不设置policy则默拥有这个权限策略的所有权限
  - 不设置policy不代表用String的空字符串,而是null.如果用空字符串会提示语法错误

- 实际操作
  

  - 在使用阿里的JAVASDK去获取临时STS令牌时设置的policy就是角色的会话策略,和角色的策略取交集就是实际的策略

<img width="955" height="149" alt="Image" src="https://github.com/user-attachments/assets/058438a5-c775-4c2d-8ec6-dfdbdf723267" />