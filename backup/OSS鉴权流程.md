出自[阿里文档](https://help.aliyun.com/zh/oss/user-guide/oss-bucket-policy/?spm=5176.8466032.console-base_help.dexternal.5f9414507gpweO#d4302d7340pfj)

- OSS鉴权遵循显式拒绝优先原则，按以下优先级顺序判断请求：

  - Explicit Deny（最高优先级）：匹配到Deny规则时，请求立即被拒绝。
  
  - Allow：无Deny规则匹配时，若匹配到Allow规则，请求被允许。
 
  - Implicit Deny（默认）：无任何规则匹配时，请求默认被拒绝。

_(引阿里教程中的图片)_
<img width="679" height="838" alt="Image" src="https://github.com/user-attachments/assets/8cca7991-2df8-417f-a73b-af150dcfa3d3" />