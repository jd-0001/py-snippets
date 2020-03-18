# py-snippets

## Find and replace text from each file in directory
> Module Dependency => re
```python
def find_and_replace_in_dir(find, replace):
    for index, file in enumerate(os.listdir(os.getcwd())):
        with fileinput.FileInput(file, inplace=True, backup='.bak') as f:
            for line in f:
                print(line.replace(find, replace), end='')
```

## Replace text in string insensitively
> Module Dependency => re
```python
def replace_insensitive(find, replace, source):
    return re.compile(re.escape(find), re.IGNORECASE).sub(replace, source)
```

## Split text from Uppercase Characters
> Module Dependency => re
```python
def split_uppercase(source):
    return re.findall('[A-Z][^A-Z]*', source)
```

## Remove string which is start of another string  
```python
# I want to remove starting string 'wp-python' from 'wp-python-my-python-file.py'
remove_starts_with('wp-python-', 'wp-python-my-python-file.py')
```
```python
def remove_starts_with(start, source):
    return source.replace(source, source[len(start):])
```

## For loop with index
```python
arr = ['a', 'b', 'c']

for index, alpha in enumerate(arr):
    print(f"{alpha} is at index {index}")
```
