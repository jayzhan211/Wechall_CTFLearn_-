# Problem
Solve Regular expression
## Solution
1. match empty string
`
  /^%/
`
2. match 'wechall'
`
  /^wechall$/
`
  ^匹配前綴, $後綴

3. 匹配以wechall或wechall4 文件名，并以.jpg/.gif/.tiff/.bmp/.png为后缀的文件名
`
/^wechall4?\.(?:jpg|gif|tiff|bmp|png)$/
`
  4? 0~1個 \反特殊字元 (這裡反.) (?:x) 找出x  | or
  
4. 捕获文件名
 `
 /^(wechall4?)\.(?:jpg|gif|tiff|bmp|png)$/
 `
