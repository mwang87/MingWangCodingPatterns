## Profiling and creating a visualzaiton

[Link](https://stackoverflow.com/questions/4544784/how-can-you-get-the-call-tree-with-python-profilers). 

Worked well for me. Specifically ```cProfile + gprof2dot + graphViz```. 


```
python -m cProfile -o myLog.profile ./test.py
gprof2dot -f pstats myLog.profile -o callingGraph.dot
dot -Tsvg callingGraph.dot -o callingGraph.svg
```


### Python Utilities

#### Creating chunks of big list

```
# Yield successive n-sized
# chunks from l.
def divide_chunks(l, n):
    # looping till length l
    for i in range(0, len(l), n): 
        yield l[i:i + n]
```