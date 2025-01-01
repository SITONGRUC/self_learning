# Wrap up for A1



## Pytorch101.py

* How to count the elements number in a tensor

```python
tensor.reshape()
# or you could use view
tensor.view()
```

* some function that could be used to create tensor



```python
# below is an exmaple

torch.full(size = (M,N),fill_value = 3.14)

```

* For the index, you could just use what you did index in numpy. They are amlost the same. ( no difference in my mind )

* below code shows that your are index three points
```python
    y = x[[1,0,3],[0,1,2]]
```


* Boolean index is the same with numpy 



* how to pass a tensor to cuda()
```python
w.cuda()
```



