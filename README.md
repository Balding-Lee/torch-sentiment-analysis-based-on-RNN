# torch-sentiment-analysis-based-on-RNN

本项目使用torch做了个基于RNN的情感分析。

代码中没有将数据发送到设备上，如果有需要，将以下代码

```python
model = RNN(128, 300, 2)
```
替换为
```python
model = RNN(128, 300, 2).to(device)
```
将
```python
state = state.detach()
```
替换为
```python
state = state.detach().to(device)
```

并且在
```python
for X, y in train_iter:
```
和
```python
for X, y in test_iter:
```
下面添加上：
```python
X.to(device)
y.to(device)
```
