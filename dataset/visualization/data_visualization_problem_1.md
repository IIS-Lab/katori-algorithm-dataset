# 問題番号1
## 基本情報
- トピック : 尺取り法
- 問題リンク : https://atcoder.jp/contests/abc032/tasks/abc032_c
- 解答リンク : https://atcoder.jp/contests/abc032/submissions/37033493
- 解答人数 : 11
- 解答者ID : 1 2 3 4 5 6 7 8 9 10 11
## ソースコード
```py
1  def two_pointers(arr, x):
2      if 0 in arr:
3          return len(arr)
4      res = 0
5      sum = 1
6      right = 0
7      for left in range(len(arr)):
8          while right < len(arr) and sum * arr[right] <= x:
9              sum *= arr[right]
10             right += 1
11         res = max(res, right - left)
12         if right == left:
13             right += 1
14         else:
15             sum //= arr[left]
16     return res
17 
18 
19 N, K = map(int, input().split())
20 s = []
21 for _ in range(N):
22     s.append(int(input()))
23 
24 print(two_pointers(s, K))
```
## 重要度の結果
★: 1st, ●: 2nd, ▲: 3rd
```py
def two_pointers(arr, x):                                 1  
    if 0 in arr:                                          2  ●●●▲▲▲▲▲
        return len(arr)                                   3  
    res = 0                                               4  
    sum = 1                                               5  
    right = 0                                             6  
    for left in range(len(arr)):                          7  ●●●▲
        while right < len(arr) and sum * arr[right] <= x: 8  ★★★★★★★★★★★
            sum *= arr[right]                             9  
            right += 1                                    10 ●
        res = max(res, right - left)                      11 ●▲
        if right == left:                                 12 ●▲▲
            right += 1                                    13 
        else:                                             14 
            sum //= arr[left]                             15 ●●▲▲
    return res                                            16 
                                                          17 
                                                          18 
N, K = map(int, input().split())                          19 
s = []                                                    20 
for _ in range(N):                                        21 
    s.append(int(input()))                                22 
                                                          23 
print(two_pointers(s, K))                                 24 
```
## 重要な理由の結果
### 1行目
`def two_pointers(arr, x):`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 2行目
`    if 0 in arr:`
#### 1位 0人
#### 2位 3人
- 7 配列に0が含まれている場合をあらかじめ抜いておくことで，例外なパターンを排除でき，メインとなるアルゴリズムを実装できるから．
一番ではない理由としては，これは0を含むという例外的なパターンのみにしか対応せず，基本的なアルゴリズムとは関連が薄いから．
- 8 １つでも０が含まれていたら計算するまでもないという例外処理を行なっているから。あくまで例外処理なので２番とした。
- 11 選択した範囲の積に注目しており，積の特性である一つでも0であれば0になることに気づいているから．基本方針ではないので一番に選びませんでした．
#### 3位 5人
- 1 尺取法の本質部分からは外れるため1番や2番ではないが，問題の性質に起因するコーナーケースを除去する重要な部分であるため．
- 2 配列に0があるときのみコーナーケースとして処理する必要があり、大枠としては関係ないが、問題を解く上では必要である処理だから。
- 3 要素に0が含まれている時の例外処理はこの問題固有のものだから。
- 5 簡単にコーナーケースを処理できており大切だが、なくても解けること・尺取り法と関係ないため１番ではないと思った
- 9 配列の値の中に0があった場合というコーナーケースに対する例外処理を行っており、これがないとコーナーケースに対して正しい値を返さないから。ただし、この部分はメインのアルゴリズム部分ではないため、重要度は先ほどの2つに比べると落ちると考える。
### 3行目
`        return len(arr)`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 4行目
`    res = 0`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 5行目
`    sum = 1`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 6行目
`    right = 0`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 7行目
`    for left in range(len(arr)):`
#### 1位 0人
#### 2位 3人
- 1 尺取法において重要な，条件を満たさなくなったら限り区間の左端を進めるという操作が書かれているため．区間の右端の操作の方が難しいと考えたため2番とした．
- 3 8行目と合わせて尺取り法のコアの部分だが、問題特有の処理はないから。
- 5 8行目に右端を動かしていることのほうが本質的だが、左端を走査していることも本質的だから。
#### 3位 1人
- 6 尺取法の一部である、区間をずらすという処理を行っているから。1 番や 2 番でないと考えたのは、問題によって変わる部分でなく、区間を伸ばす処理に対する従たる処理だから。
### 8行目
`        while right < len(arr) and sum * arr[right] <= x:`
#### 1位 11人
- 1 尺取法において重要な，条件を満たす限り区間の右端を進めるという操作が書かれているため．
- 2 この問題はしゃくとり法を用いて解くことができるが、そのしゃくとり法の繰り返しを行なっている部分であるから。
- 3 尺取り法は特定の連続部分列に対する処理を全探索ではなく、左端と右端を上手くずらすことでO(N)に抑えるアルゴリズムだが、7行目と合わせてコアの部分だから。
- 4 arrを順番に見ていく上で最も重要な判別を行なっていると思うから
- 5 「条件を満たすように範囲を広げる」という、尺取り法を用いた解法を端的に表しているから
- 6 尺取法において、区間を伸ばし続ける条件を記述する行になっているから。
- 7 配列の右側に関してこの行の条件をつけながら探索していくことで，正解を導き出すことができるから．
- 8 rightをひとつずつインクリメントしながらギリギリのところを確かめるという、問題を解く最も本質的なところだと思ったから。
- 9 尺取り法における、範囲を伸ばせる条件を指定しており、この部分の判定が正しいかどうかが、アルゴリズムが正しく動くための核であると考えたから。
- 10 累積がxの値を超えるまで右端を動かしていくことは、とても重要であるから。
- 11 指定された条件を満たす限り，列の中においてみる範囲を増やしていくという方針が表れている箇所だと思ったから
#### 2位 0人
#### 3位 0人
### 9行目
`            sum *= arr[right]`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 10行目
`            right += 1`
#### 1位 0人
#### 2位 1人
- 6 尺取法の一部である、区間を伸ばすという処理を行っているから。1 番でないと考えたのは、問題によって変わる部分ではないから。
#### 3位 0人
### 11行目
`        res = max(res, right - left)`
#### 1位 0人
#### 2位 1人
- 9 答えの値の更新を行っており、これが無いとアルゴリズムが正しい答えを返さないから。ただし、この部分はアルゴリズムの核とは言えないため、1番ではないと考える。
#### 3位 1人
- 4 最終的な答えを更新している部分であるため。ただ誰でも簡単に思いつきそう。
### 12行目
`        if right == left:`
#### 1位 0人
#### 2位 1人
- 2 同じくしゃくとり法のインデックスに関する部分で正しく場合分けしないといけないため重要であると考えられるが、複雑さでいえば8行目より少ないから。
#### 3位 2人
- 10 左端右端が被った時の処理も大切であると思ったため。1番や2番ではない理由は、デバッグで気付きやすいと思ったため。
- 11 列の範囲を拡大していく中でこの処理をする必要がある．毎回ではなく，列の長さが0のときだけの処理なので3番目にしました．
### 13行目
`            right += 1`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 14行目
`        else:`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 15行目
`            sum //= arr[left]`
#### 1位 0人
#### 2位 2人
- 4 前回のsumを利用することで効率化に貢献しているため。ただこの効率化がなくても問題に正解はできる。
- 10 左端を動かすときに、最左端の値で割り忘れないことは重要であるから。1番ではないのは、プログラムを動かすときに気付きやすいと思ったため。
#### 3位 2人
- 7 rightをleftのたびに更新せず，前回のループで計算したものをそのまま利用することで計算量を落とすことが可能となっているから．
1番や2番ではないのは，これは計算量を減らすためであり，この処理がなく，全て計算を行なっても答え自体は導き出せるから．
- 8 左側を右にずらすときの大事な計算だから。8行目の方が本質的だと思ったので３番とした。
### 16行目
`    return res`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 17行目
``
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 18行目
``
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 19行目
`N, K = map(int, input().split())`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 20行目
`s = []`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 21行目
`for _ in range(N):`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 22行目
`    s.append(int(input()))`
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 23行目
``
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 24行目
`print(two_pointers(s, K))`
#### 1位 0人
#### 2位 0人
#### 3位 0人
## 他の重要部分
- 4 : 2, 0の掛け算に対する処理を意外と忘れてしまいそうな気がするから
- 5 : 11行：走査しながらのresの逐次更新は競プロなどでよく使う表現だから
- 6 : 11。最終的に欲しい解答を計算している部分だから。
- 7 : 12: この条件式があることでバグがなくアルゴリズムを実行できるから．
- 9 : 12行目。細かいところではあるが、尺取り法における左のポインタと右のポインタが等しい値を指したときの処理を行っており、アルゴリズムを実装する上では大事な要素となる。
## 自由記述
## 理解度
- とても理解できた。 : 9人, 1 2 3 4 5 6 8 9 11
- まあ理解できた。 : 2人, 7 10
- あまり理解できなかった。 : 0人, 
- まったく理解できなかった。 : 0人, 
