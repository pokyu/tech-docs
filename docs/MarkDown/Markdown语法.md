1、横向流程图源码格式：
```mermaid
graph LR
A[方形] -->B(圆角)
    B --> C{条件a}
    C -->|a=1| D[结果1]
    C -->|a=2| E[结果2]
    F[横向流程图]
```
2、竖向流程图源码格式：
```mermaid
graph TD
A[方形] --> B(圆角)
    B --> C{条件a}
    C --> |a=1| D[结果1]
    C --> |a=2| E[结果2]
    F[竖向流程图]
```
3、标准流程图源码格式：
```flow
st=>start: 开始框
op=>operation: 处理框
cond=>condition: 判断框(是或否?)
sub1=>subroutine: 子流程
io=>inputoutput: 输入输出框
e=>end: 结束框
st->op->cond
cond(yes)->io->e
cond(no)->sub1(right)->op
```
4、标准流程图源码格式（横向）：
```flow
st=>start: 开始框
op=>operation: 处理框
cond=>condition: 判断框(是或否?)
sub1=>subroutine: 子流程
io=>inputoutput: 输入输出框
e=>end: 结束框
st(right)->op(right)->cond
cond(yes)->io(bottom)->e
cond(no)->sub1(right)->op
```
5、UML时序图源码样例：
```sequence
对象A->对象B: 对象B你好吗?（请求）
Note right of 对象B: 对象B的描述
Note left of 对象A: 对象A的描述(提示)
对象B-->对象A: 我很好(响应)
对象A->对象B: 你真的好吗？
```
6、UML时序图源码复杂样例：
```sequence
Title: 标题：复杂使用
对象A->对象B: 对象B你好吗?（请求）
Note right of 对象B: 对象B的描述
Note left of 对象A: 对象A的描述(提示)
对象B-->对象A: 我很好(响应)
对象B->小三: 你好吗
小三-->>对象A: 对象B找我了
对象A->对象B: 你真的好吗？
Note over 小三,对象B: 我们是朋友
participant C
Note right of C: 没人陪我玩
```
7、UML标准时序图样例：
```mermaid
%% 时序图例子,-> 直线，-->虚线，->>实线箭头
  sequenceDiagram
    participant 张三
    participant 李四
    张三->王五: 王五你好吗？
    loop 健康检查
        王五->王五: 与疾病战斗
    end
    Note right of 王五: 合理 食物 <br/>看医生...
    李四-->>张三: 很好!
    王五->李四: 你怎么样?
    李四-->王五: 很好!
```
8、甘特图样例：
```mermaid
%% 语法示例
        gantt
        dateFormat  YYYY-MM-DD
        title 软件开发甘特图
        section 设计
        需求                      :done,    des1, 2014-01-06,2014-01-08
        原型                      :active,  des2, 2014-01-09, 3d
        UI设计                     :         des3, after des2, 5d
    未来任务                     :         des4, after des3, 5d
        section 开发
        学习准备理解需求                      :crit, done, 2014-01-06,24h
        设计框架                             :crit, done, after des2, 2d
        开发                                 :crit, active, 3d
        未来任务                              :crit, 5d
        耍                                   :2d
        section 测试
        功能测试                              :active, a1, after des3, 3d
        压力测试                               :after a1  , 20h
        测试报告                               : 48h
```

```mermaid
graph TD
    A[核心目标: 本地部署DeepSeek-R1实现自动化报告生成] 
    --> B[1. 基础设施层]
    --> C[2. 数据处理层]
    --> D[3. 模型服务层]
    --> E[4. 应用交互层]
    --> F[5. 安全与治理层]
    
    %% 基础设施层
    B --> B1[硬件资源]
    B1 --> B1a[GPU集群]
    B1 --> B1b[高速存储]
    B1 --> B1c[网络隔离]
    
    B --> B2[软件环境]
    B2 --> B2a[Docker/K8s]
    B2 --> B2b[CUDA/PyTorch]
    B2 --> B2c[加密模块]

    %% 数据处理层
    C --> C1[数据接入]
    C1 --> C1a[ETL管道]
    C1 --> C1b[实时流]
    
    C --> C2[数据加工]
    C2 --> C2a[Schema映射]
    C2 --> C2b[向量化]
    C2 --> C2c[缓存]

    %% 模型服务层
    D --> D1[模型部署]
    D1 --> D1a[ONNX优化]
    D1 --> D1b[分布式推理]
    
    D --> D2[模型调优]
    D2 --> D2a[LoRA微调]
    D2 --> D2b[领域词表]

    %% 应用交互层
    E --> E1[前端交互]
    E1 --> E1a[Web界面]
    E1 --> E1b[ChatBot]
    
    E --> E2[报告引擎]
    E2 --> E2a[Prompt模板]
    E2 --> E2b[多模态渲染]

    %% 安全与治理层
    F --> F1[权限控制]
    F1 --> F1a[RBAC]
    F1 --> F1b[动态掩码]
    
    F --> F2[监控审计]
    F2 --> F2a[性能监控]
    F2 --> F2b[日志追踪]
    
    F --> F3[合规灾备]
    F3 --> F3a[GDPR合规]
    F3 --> F3b[异地备份]

    %% 关键依赖关系
    B1c -->|网络隔离| C1a
    C2c -->|缓存加速| D1a
    D2a -->|领域适应| E2a
    F1a -->|权限隔离| E1a
    F2a -->|性能反馈| D1b
```