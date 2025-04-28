---
{"dg-publish":true,"更新日期":"2024-04-26","permalink":"/知识共享/Markdown图表展示/","dgPassFrontmatter":true}
---
# 

这个页面展示了Markdown中各种图表的渲染效果，可以作为图表语法参考。

## 1. Mermaid图表

### 流程图
```mermaid
flowchart TD
    A[开始] --> B{是否有问题?}
    B -->|是| C[解决问题]
    B -->|否| D[继续前进]
    C --> E[结束]
    D --> E
```

### 思维导图
```mermaid
mindmap
  root((核心概念))
    A[概念A]
      A1[子概念A1]
      A2[子概念A2]
    B[概念B]
      B1[子概念B1]
      B2[子概念B2]
    C[概念C]
```

### 时序图
```mermaid
sequenceDiagram
    参与者A->>参与者B: 你好，B!
    参与者B->>参与者A: 你好，A!
    参与者A->>参与者C: 你好，C!
    参与者C->>参与者A: 你好，A!
```

## 2. PlantUML

需要PlantUML插件支持。

```plantuml
@startuml
用户 -> 认证中心: 登录请求
认证中心 -> 用户: 认证结果

用户 -> 权限系统: 权限请求
权限系统 -> 用户: 权限结果
@enduml
```

## 3. Graphviz (Dot)

需要Graphviz插件支持。

```dot
digraph G {
  rankdir=LR;
  
  数据收集 -> 数据处理;
  数据处理 -> 数据分析;
  数据分析 -> 数据可视化;
  数据分析 -> 结果输出;
  
  数据收集 [shape=box, style=filled, color=lightblue];
  数据处理 [shape=box, style=filled, color=lightgreen];
  数据分析 [shape=box, style=filled, color=lightyellow];
  数据可视化 [shape=box, style=filled, color=lightpink];
  结果输出 [shape=box, style=filled, color=lightgrey];
}
```

## 4. Vega/Vega-Lite

需要Vega插件支持。

```vega
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "description": "简单柱状图",
  "data": {
    "values": [
      {"类别": "A", "数值": 28},
      {"类别": "B", "数值": 55},
      {"类别": "C", "数值": 43},
      {"类别": "D", "数值": 91},
      {"类别": "E", "数值": 81},
      {"类别": "F", "数值": 53}
    ]
  },
  "mark": "bar",
  "encoding": {
    "x": {"field": "类别", "type": "nominal"},
    "y": {"field": "数值", "type": "quantitative"}
  }
}
```

## 5. ASCII艺术图

```
+-------------+         +--------------+
|   模块 A    |-------->|    模块 B    |
+-------------+         +--------------+
       |                        |
       |                        |
       v                        v
+-------------+         +--------------+
|   模块 C    |<--------|    模块 D    |
+-------------+         +--------------+
```

## 6. MathJax/LaTeX

### 行内公式: $E = mc^2$

### 块级公式:
$$
\frac{d}{dx}\left( \int_{a}^{x} f(u)\,du\right)=f(x)
$$

$$
\begin{bmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{bmatrix}
$$

## 7. Chart.js

需要Chart.js插件支持。

```chart
type: bar
labels: [一季度, 二季度, 三季度, 四季度]
series:
  - title: 收入
    data: [500, 650, 750, 800]
  - title: 支出
    data: [400, 500, 650, 700]
options:
  title:
    display: true
    text: 年度财务状况
```

## 8. Gantt图表

通过Mermaid实现:

```mermaid
gantt
    title 项目计划Gantt图
    dateFormat  YYYY-MM-DD
    section 规划阶段
    需求分析       :a1, 2023-06-01, 15d
    系统设计       :after a1, 20d
    section 开发阶段
    编码实现       :2023-07-05, 30d
    测试          :2023-08-05, 20d
    section 部署阶段
    系统上线       :2023-08-25, 5d
    用户培训       :2023-08-30, 10d
```

## 9. 饼图 (使用Mermaid)

```mermaid
pie
    title 市场份额分布
    "产品A" : 45
    "产品B" : 30
    "产品C" : 15
    "其他" : 10
```

## 10. Er图 (实体关系图)

```mermaid
erDiagram
    用户 ||--o{ 订单 : 下单
    订单 ||--|{ 订单项 : 包含
    产品 ||--o{ 订单项 : 购买
```

---

注意：某些图表类型可能需要Obsidian相关插件支持才能正常渲染。如果图表未能正确显示，请检查是否需要安装相应的插件。 