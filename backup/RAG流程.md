截图来源b站[马克的技术工作坊](https://space.bilibili.com/1815948385/?spm_id_from=333.788.upinfo.detail.click)

RAG（检索增强生成）是一种AI技术，通过检索外部知识库信息来增强大语言模型的生成能力，提高回答准确性和时效性。

有两个流程

- 用户提问前(准备数据阶段):
  1.   将文本内容分片
  2.   而后用Embedding向量化
  3.   之后将向量放入向量数据库中
<img width="676" height="192" alt="Image" src="https://github.com/user-attachments/assets/c3a93963-cb5b-4dbe-b471-3f5936da13ff" />





- 用户提问后(实际使用阶段):
  1.   先将用户提问通过Embedding向量化.
  2.   在向量数据库中召回(也可以叫检索).
<img width="930" height="490" alt="Image" src="https://github.com/user-attachments/assets/67e37d7d-834e-4474-8658-f45cd02d70c8" />




这是召回时,计算向量相似度的方法
<img width="863" height="427" alt="Image" src="https://github.com/user-attachments/assets/49182705-a1bc-4f0a-bd79-6f2c883e7652" />



  3.   后用cross-encoder重排.(召回和重排相当于两层筛选)
<img width="889" height="385" alt="Image" src="https://github.com/user-attachments/assets/fc86e643-ca11-40f3-9f20-6f852f98e720" />




  4.   重排后将找到的数据好用户提问的
<img width="812" height="414" alt="Image" src="https://github.com/user-attachments/assets/55393ec3-3924-44e5-9178-95bbb0b137c0" />