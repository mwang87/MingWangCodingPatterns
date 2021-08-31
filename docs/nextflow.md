## Flags for Command Line

```
script:
def flag = params.ms2_flag == true ? "--ms2_flag" : ''
"""
$flag
"""
```