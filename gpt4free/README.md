# gpt4 package

### 这是什么?
Gpt4free是一个python包，它提供了一些语言模型api
### 主要特性
-免费使用
-方便使用
### 安装:

```bash
pip install gpt4free
```

#### 使用:

```python
import gpt4free
from gpt4free import Provider, quora, forefront

# usage You
response = gpt4free.Completion.create(Provider.You, prompt='Write a poem on Lionel Messi')
print(response)

# usage Poe
token = quora.Account.create(logging=False)
response = gpt4free.Completion.create(Provider.Poe, prompt='Write a poem on Lionel Messi', token=token, model='ChatGPT')
print(response)

# usage forefront
token = forefront.Account.create(logging=False)
response = gpt4free.Completion.create(
    Provider.ForeFront, prompt='Write a poem on Lionel Messi', model='gpt-4', token=token
)
print(response)
print(f'END')

# usage theb
response = gpt4free.Completion.create(Provider.Theb, prompt='Write a poem on Lionel Messi')
print(response)

# usage cocalc
response = gpt4free.Completion.create(Provider.CoCalc, prompt='Write a poem on Lionel Messi', cookie_input='')
print(response)

```

### Invocation Arguments

`gpt4free.Completion.create()` method has two required arguments

1. Provider: This is an enum representing different provider
2. prompt: This is the user input

#### Keyword Arguments

Some of the keyword arguments are optional, while others are required.

- You:
    - `safe_search`: boolean - default value is `False`
    - `include_links`: boolean - default value is `False`
    - `detailed`: boolean - default value is `False`
- Quora:
    - `token`: str - this needs to be provided by the user
    - `model`: str - default value is `gpt-4`.
      
  (Available models: `['Sage', 'GPT-4', 'Claude+', 'Claude-instant', 'ChatGPT', 'Dragonfly', 'NeevaAI']`)
- ForeFront:
  - `token`: str - this need to be provided by the user

- Theb:
  (no keyword arguments required)
- CoCalc:
  - `cookie_input`: str - this needs to be provided by user

#### Token generation of quora
```python
from gpt4free import quora

token = quora.Account.create(logging=False)
```

### 令牌生成
```python
from gpt4free import forefront

token = forefront.Account.create(logging=False)
```

## Copyright:

本程序根据获得许可 [GNU GPL v3](https://www.gnu.org/licenses/gpl-3.0.txt)

### 版权声明: <a name="copyright"></a>

```
本程序是自由软件:您可以重新发布和/或修改它
在GNU通用公共许可证的条款下，由
自由软件基金会，或者是许可证的第三版，或者
(根据你的选择)任何以后的版本。
发布这个程序是希望它能有所帮助，
但无任何保证;甚至没有隐含的保证
适销性或适合于某一特定目的。看到
详细信息请参见GNU通用公共许可证。
您应该已经收到了GNU通用公共许可证的副本
和这个节目一起。如果没有，请参见<https://www.gnu.org/licenses/>。
```
