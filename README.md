# pyEliasFano
pyEliasFano offers a **quasi-succinct** represenation for a monotone non-decreasing sequence of n integers from 
the universe [0 . . . m) occupying 2*n+n*ceil(log2(m/n)) bits.

It supports the following operations:
- **select(k)**: nearly constant time access to the k-th element,
- **rank(x)**: access to the index within the structure for given integer x.
- **nextGEQ(x)**: fast access to the smallest integer of the sequence that is greater or equal than a given x
- **nextLEQ(x)**: fast access to the largest integer of the sequence that is smaller or equal than a given x

## Installation
```bash
pip install pyEliasFano
```

## Usage
```python


import pyEliasFano as EF
```
imports the module.

```python
integers = sorted([123, 1343, 2141, 35312, 4343434])
ef = EF.EliasFano(integers)
```
creates an Elias-Fano structure for the sorted ``integers`` list.
```python
ef.select(2)
```
returns the integer stored at index position ``2``.
Here we get ``2141``.    
```python
ef.rank(4343434)
```
returns the index position for the given integer if stored within the Elias-Fano structure. 
Here, we get ``4``.
```python
ef.nextGEQ(1345)
```
returns the smallest integer stored in the Elias-Fano structure that is larger than the given integer. 

```python
ef.nextLEQ(4343420)
```
returns the largest integer stored in the Elias-Fano structure that is smaller than the given integer.
Here, we get ``35312``. 

# Citation
```bibtex

```


# License
<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/80x15.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.