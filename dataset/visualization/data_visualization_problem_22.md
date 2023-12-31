# 問題番号22
## 基本情報
- トピック : 最小公倍数
- 問題リンク : https://atcoder.jp/contests/abc148/tasks/abc148_c
- 解答リンク : https://atcoder.jp/contests/abc148/submissions/37035141
- 解答人数 : 11
- 解答者ID : 1 2 3 4 5 6 7 8 9 10 11
## ソースコード
```py
1  def gcd(a, b):
2      return a if b == 0 else gcd(b, a % b)
3  
4  
5  a, b = map(int, input().split())
6  print(a * b // gcd(a, b))
```
## 重要度の結果
★: 1st, ●: 2nd, ▲: 3rd
```py
def gcd(a, b):                            1  ▲▲▲▲
    return a if b == 0 else gcd(b, a % b) 2  ★★★★★★●●●●●
                                          3  
                                          4  
a, b = map(int, input().split())          5  ▲▲▲▲▲▲▲
print(a * b // gcd(a, b))                 6  ★★★★★●●●●●●
```
## 重要な理由の結果
### 1行目
`def gcd(a, b):`
#### 1位 0人
#### 2位 0人
#### 3位 4人
- 1 あまり重要とは考えていないが，最大公約数を求める関数を定義しているため，他の行よりは比較的重要と考え，3番目に選択した．
- 4 最大公約数を求めるというのを決定している行だから。具体的な処理については書いていないから。
- 6 最大公約数が二引数の演算であることを示している。1 番や 2 番ではないのは、まあ流石に……
- 9 gcd関数の定義について述べている行であるから。実装上のちょっとしたポイントであるため、1番や2番ではないと考えた。
### 2行目
`    return a if b == 0 else gcd(b, a % b)`
#### 1位 6人
- 1 最大公約数を再帰に求めることを表しており，発想として最も重要かつ難しいところだと考え選択した．
- 5 GCDを再帰を利用して求めるというのは、現実的な計算量で回答を実装するにあたって重要だと考えた。
- 6 ユークリッドの互除法を再帰的に処理するにあたっての本体となる行である。
- 9 最大公約数をユークリッドの互除法を用いて求めている行であるから。最小公倍数を求めるには最大公約数を求める必要があるため、最大公約数を求めることがこのコード内で最も重要だと考えている。
- 10 このプログラムの中で、最大公約数を求める部分が一番重要であると思ったため。
- 11 最大公約数がこのように再帰を使って求められることは重要な事実だと思います．
#### 2位 5人
- 2 最小公倍数を求めるために最大公約数を求める必要があり、それを再帰的に高速に求めている行なので、次に重要。
- 3 最大公約数の求値アルゴリズムそのものがここで式として記述されてるから。
- 4 1番の処理を行うために最大公約数を求める処理を行なっているから。あくまで1番を行うための準備の処理だから。
- 7 最大公約数はユークリッドのの互除法を再帰関数の形で実装することによって効率的に求められるということがこの行から分かるから．
1番でない理由としては，この問題はそもそも最小公倍数を求めるものであるのにも関わらず，この行では最大公約数の求め方となってしまうため，なぜ最大公約数を求める必要があるのかの方が重要だと思ったから．
- 8 再帰を用いて最大公約数を求めるというのもアルゴリズム的に大事だから。答えの求め方の方が重要だと思ったので、こちらは2番にした。
#### 3位 0人
### 3行目
``
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 4行目
``
#### 1位 0人
#### 2位 0人
#### 3位 0人
### 5行目
`a, b = map(int, input().split())`
#### 1位 0人
#### 2位 0人
#### 3位 7人
- 2 アルゴリズムのほうが重要だが、問題の数値の入力ができないと問題は解けないので、残った2行の中ではこっちの方が大切。
- 3 他に選ぶところがないので、まあ入力をとることもプログラミングには大事なことかもしれない。
- 5 mapを用いて入力を受け取るための手法が書かれており、3番めに重要だと考えた。
- 7 すでに選択していない行のうち，関数の定義より入力を受け取る方が重要だと思ったから．
3番目である理由は，この行では入力を受け取っているだけであり，問題の解法には関係ないから．
- 8 特に重要だとは思わなかったが、コードが短いので消去法的に選んだ。
- 10 入力を分割して、intにすることは重要であるが、本質的ではないため、3番目に重要であると思った。
- 11 短いコードなので仕方なく選びました．そんなに重要だとは思っていないです．
### 6行目
`print(a * b // gcd(a, b))`
#### 1位 5人
- 2 この問題の答えが最小公倍数であるという考察、および最小公倍数がA * B / GCD(A, B)でもとまるという知識が両方含まれており、ぶっちぎりで重要な行。
- 3 この問題のコアは最大公約数を使えば計算できることに気付くことなので。
- 4 最大公約数を使って答えを求めるという、計算を行なっている部分だから。
- 7 6行目のような式で最大公約数から最小公倍数を算出することで答えを求められるということが分かるから．
- 8 AとBの最小公倍数が問題の答えであり、それを求めるために最大公約数を用いるという考え方は重要だから。
#### 2位 6人
- 1 2数の最小公倍数が最大公約数を使って求められるという考え方や，問題の考察部分を表していることから選択した．計算量に関係するアルゴリズムの部分を含んでいないため2番目とした．
- 5 LCMを求めるにあたって、a * b / GCD(a,b) を計算するという部分であり、この問題の本質的なところだと感じたため。ただし、問題からGCDを計算するという考え方に至るまでさほど遠くないと考え、2番めに重要だと考えた。
- 6 問題の答えである最小公倍数は、積を最大公約数で割ったものであることを示している。1 番ほど非自明ではない。
- 9 最大公約数を用いて最小公倍数を求めている行であるから。最小公倍数の求め方は最大公約数が求まっていれば簡単な式で求められるため、1番ではないと考えた。
- 10 1番で実装したgcdを用いて、最小公倍数をgcdを用いて、求めることが2番目に重要であるため。
- 11 最大公倍数が積を最大公約数でわると求められることは大事だと思います．gcdを求めるよりも簡単な知識だと感じたので2番目にしました．
#### 3位 0人
## 他の重要部分
## 自由記述
## 理解度
- とても理解できた。 : 9人, 1 2 3 5 6 8 9 10 11
- まあ理解できた。 : 2人, 4 7
- あまり理解できなかった。 : 0人, 
- まったく理解できなかった。 : 0人, 
