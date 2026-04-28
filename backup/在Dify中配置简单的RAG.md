Dify中包含可视化AI工作流编排.

<img width="1369" height="456" alt="Image" src="https://github.com/user-attachments/assets/01c11745-7557-4498-bdb5-282f462143b3" />

打开知识检索模块.
<img width="495" height="808" alt="Image" src="https://github.com/user-attachments/assets/85ad6489-985e-443c-a6f8-69b2c1104167" />
在知识库栏添加知识库.或在网页头部的知识库页配置新知识库

<img width="1896" height="79" alt="Image" src="https://github.com/user-attachments/assets/a61d94dc-33d7-438b-87ce-21e5c03d499b" />
进入知识库页后,新建
<img width="1173" height="409" alt="Image" src="https://github.com/user-attachments/assets/33896a13-b068-45b3-9d51-1c7d0c868b54" />
导入文本后,有分段设置好索引方式的选择.

<img width="831" height="400" alt="Image" src="https://github.com/user-attachments/assets/70f154f7-3007-4729-a011-d3f0426defb3" />
我分段是没有设置,因为是测试,实际生产中根据资料情况调整.
之后索引方式有:

  - 高质量(Vector模式):用Embedding 模型将分页或问题向量化,然后重排用的Rerank 模型.
  - 经济(Keyword模式):用的倒排索引,区别于用向量数据库的(即上面的高质量中),不支持语意搜索.

<img width="856" height="170" alt="Image" src="https://github.com/user-attachments/assets/3f6a4a4d-f8ab-4b25-9eb3-479cc98ae447" />

之后保存并处理,等待处理完成就可以添加到工作流的知识检索模块了.
