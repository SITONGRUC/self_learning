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



## KNN.py

* How to flat a tensor

```python
 x_test.reshape(num_test,-1)
```


* the differenc between torch.cat() and torch.stack()

torch.cat would not add dim while torch.stack() do 


* torch.repeat(), you should pass the arugment to declain that which dim you would like to repeat on . 

* below code should be paid attention 

```python
sum_train = (x_train_flat**2).sum(dim=1, keepdim=True) 
```


* how to write a class

check the code below 

```python

class KnnClassifier:

    def __init__(self, x_train: torch.Tensor, y_train: torch.Tensor):

        self.x_train = x_train
        self.y_train = y_train 

    def predict(self, x_test: torch.Tensor, k: int = 1):

        y_test_pred = None
        dists = compute_distances_no_loops(x_train = self.x_train,x_test = x_test)
        y_test_pred = predict_labels(dists=dists,y_train=self.y_train,k = k)
        return y_test_pred

    def check_accuracy(
        self,
        x_test: torch.Tensor,
        y_test: torch.Tensor,
        k: int = 1,
        quiet: bool = False
    ):

        y_test_pred = self.predict(x_test, k=k)
        num_samples = x_test.shape[0]
        num_correct = (y_test == y_test_pred).sum().item()
        accuracy = 100.0 * num_correct / num_samples
        msg = (
            f"Got {num_correct} / {num_samples} correct; "
            f"accuracy is {accuracy:.2f}%"
        )
        if not quiet:
            print(msg)
        return accuracy


```




* torch.chunk() return a list of tensor



