# Assignment1

このproject では正解とtxtファイルで渡される生徒の回答を比較して採点を行い、
その結果をtxtファイルで出力します。

## How to use

pythonの仮想環境下でこのao_okamoto_grade_the_exams.pyを保存します。
他のpython codeと近い場所に保存することを推奨します。
（またはpython passを繋ぐとよいです。）

ao_okamoto_grade_the_exams.pyを開き、実行ボタンを押し、
class number またはclass name(class+number+.txt)を入力します。
すると、そのtxtファイルにアクセスして採点を行い、
結果がclass+ number + grades.txt　として出力されます。

### Examples
```
Enter a file path. ex. C:Users/..../: 
Enter a Class Number(or name). If class1, enter 1: 1
```

## file format
このprojectを問題なく実行するためには生徒の回答が記述されたtxtファイルは
以下の形式に従う必要があります。

1. 生徒はN00000001のような、N+8桁の数字(ID)で識別されます。
2. 回答の数は問題数と一致する必要があります。
3. IDやそれぞれの回答はカンマ(,)区切りで入力される必要があります。


## Description
### answer_key
このproject では問題に対する解答を**answer_key**にリスト形式で渡すことで、
N+8桁のstudent identification に基づいた採点を行うことができます。

#### Examples
```
answer_key = ['B','A','D','D','C','B','D','A','C','C','D','B','A','B','A','C','B']
```

### Allocationpoints
defaultでは正解4点、不正解-1点、空欄0点で採点しますが、
**Allocationpoints**にリスト形式で配点を渡すことで任意の配点に変更できます。

#### Examples
```
Allocationpoints = [4, -1, 0]  #[correct answer, incorrect, empty]
```

### Basic statistic
クラス全体の**基本統計量Basic statistic**もclass+number+describe.txtに保存されます。
必要ない場合は以下の該当するスクリプトをコメントアウトすることで出力させないこともできます。
この出力ファイルには以下の値が含まれます。

回答数
平均点
標準偏差
最低点
25%値
中央値
75%値
最高点


#### Examples
```
S.describe().to_csv(o2,sep=',',header=None)
```


