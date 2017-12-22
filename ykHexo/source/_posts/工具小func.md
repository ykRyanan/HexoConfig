---
title: 小func
date: 2017-12-19 13:45:33
tags: 工具
---
##### 大小端换位 Data -> int
```
//大小端换位 Data -> int
-(int)convertToLittleEndian:(NSData *)data
{
    Byte *endiaB = (Byte *)[data bytes];
    Byte temp = endiaB[0];
    endiaB[0] = endiaB[1];
    endiaB[1] = temp;
    NSData *resultD = [NSData dataWithBytes:endiaB length:data.length];
    
    int lengthS;
    [resultD getBytes:&lengthS length:sizeof(lengthS)];
    
    return lengthS;
}
```
