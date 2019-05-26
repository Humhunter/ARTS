# Algorithm

><https://leetcode.com/problems/valid-parentheses/description/> 

```python3
class Solution:
    def isValid(self, s: str) -> bool:
        if not s:
            return True
        stack = []
        container = {
            '{': '}',
            '[': ']',
            '(': ')'
        }
        
        for matcher in s:
            if matcher in container.keys():
                stack.append(matcher)
            else:
                if stack:
                    left = stack.pop()
                    if matcher != container[left]:
                        return False
                    else:
                        return False
        if stack:
            return False
        else:
            return True
```

**Tips:** 这道题其实已经参考了别人的解题思路，本不该放出来，但是这道题对我个人比较有意义，所以存在这里，因为我最开始审题不严谨，没有看到 Given a string containing **just** the characters ，考虑过于复杂的情况，写的非常繁琐，还用了计数器，后面实在忍不住翻开了别人的代码看了眼，发现了这个新的思路，并吸收，感觉蛮有收获的，记录下



# Review

><https://www.bloomberg.com/opinion/articles/2019-05-20/huawei-supply-freeze-points-to-u-s-china-tech-cold-war>

​		最近一直看华为的文章，所以找一篇关于华为的外刊，技术冷战，不在沉默中爆发就在沉默中灭亡。希望我们会成为最后站立的那个巨人

><https://www.bennettnotes.com/post/making-money-out-of-every-hobby/>

​		昨天看完今天想再看一次就被墙了，只能换一个了。

​		这个文章也蛮有感触的，就是现在做事越来越功利性，做的事情已经完全不是仅仅因为喜欢才去做了，好像这个事情如果不能获利，或者短期很有帮助，做起来的兴趣就很低，看书也并不是真正为了快乐去看，只是想着或许某个时间段我能用的到，如果哪天我能选择做一些事情仅仅是为了兴趣就好了，希望那天能早日到来



# Tips

```python3
# 插入排序
def insert_sort(aList):
    '''
    1、从第一个元素开始，该元素可以认为已经被排序
    2、取出下一个元素，在已经排序的元素序列中从后向前扫描
    3、如果该元素（已排序）大于新元素，将该元素移到下一位置
    4、重复步骤3，直到找到已排序的元素小于或者等于新元素的位置
    5、将新元素插入到该位置中
    6、重复步骤2
    :param aList:
    :return:
    '''
    count = len(aList)
    for i in range(1, count):
        key = aList[i]
        j = i - 1
        while j >= 0:
            if aList[j] > key:
                aList[j + 1] = aList[j]
                aList[j] = key
            j -= 1
    return aList

aList = [28, 32, 14, 12, 53, 42]
print(insert_sort(aList))
```





# Share

><https://www.liriansu.com/windows-dev-env>

如果快速搭建windows的工作环境，给习惯于指令的人