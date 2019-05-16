# One-liner python code

### The Zen of Python
```bash
$ python -c "import this"
```

### 输出特定字符拼成的心形
```bash
>>> print('\n'.join([''.join([('Love'[(x-y) % len('Love')] if ((x*0.05)**2+(y*0.1)**2-1)**3-(x*0.05)**2*(y*0.1)**3 <= 0 else ' ') for x in range(-30, 30)]) for y in range(30, -30, -1)]))

>>> print'\n'.join([''.join([('Python'[(x-y)%6]if((x*0.05)**2+(y*0.1)**2-1)**3-(x*0.05)**2*(y*0.1)**3<=0 else' ')for x in range(-30,30)])for y in range(15,-15,-1)])
```
### 输出 Mandelbrot 图像
andelbrot 图像中的每个位置都对应于公式 N=x+y*i 中的一个复数
```bash
>>> print('\n'.join([''.join(['*'if abs((lambda a: lambda z, c, n: a(a, z, c, n))(lambda s, z, c, n: z if n == 0 else s(s, z*z+c, c, n-1))(0, 0.02*x+0.05j*y, 40)) < 2 else ' ' for x in range(-80, 20)]) for y in range(-20, 20)]))
```
### 打印九九乘法表
```bash
>>> print('\n'.join([' '.join(['%s*%s=%-2s' % (y, x, x*y) for y in range(1, x+1)]) for x in range(1, 10)]))
```
### 计算出 1-100 之间的素数
```bash
>>> print(' '.join([str(item) for item in filter(lambda x: not [x % i for i in range(2, x) if x % i == 0], range(2, 101))]))

>>> print(' '.join([str(item) for item in filter(lambda x: all(map(lambda p: x % p != 0, range(2, x))), range(2, 101))]))

>>> filter(lambda x: all(map(lambda p: x % p != 0,range(2,x))),range(2,n))
```
### 输出斐波那契数列
```bash
>>> print([x[0] for x in [(a[i][0], a.append([a[i][1], a[i][0]+a[i][1]])) for a in ([[1, 1]], ) for i in range(30)]])
```
### 解决八皇后问题
```bash
>>> _=[__import__('sys').stdout.write('\n'.join('.' * i + 'Q' + '.' * (8-i-1) for i in vec) + "\n========\n") for vec in __import__('itertools').permutations(range(8)) if 8 == len(set(vec[i]+i for i in range(8))) == len(set(vec[i]-i for i in range(8)))]
```
### 求解 2 的 1000 次方的各位数之和
```bash
>>> print(sum(map(int, str(2**1000))))
```
### 解决 FizzBuzz 问题
FizzBuzz 问题：打印数字 1 到 100,3 的倍数打印 "Fizz",5 的倍数打印 "Buzz",既是 3 又是 5 的倍数的打印 "FizzBuzz"
```bash
>>> print(' '.join(["fizz"[x % 3 * 4:]+"buzz"[x % 5 * 4:] or str(x) for x in range(1, 101)]))
```
### 实现数组的 flatten 功能：将多维数组转化为一维
```bash
>>> a = [1, 2, [3, 4], [[5, 6], [7, 8]]]
>>> print(a)
>>> flatten = lambda x: [y for l in x for y in flatten(l)] if type(x) is list else [x]

>>> flatten = lambda x: [y for l in x for y in flatten(l)] if isinstance(x,list) else [x]
>>> print(flatten(a))
```
