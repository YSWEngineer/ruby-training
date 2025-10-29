<details open><summary>🧩 Ruby基礎演習②：文字列と数値の応用練習</summary>

## 🔹 レベル1：基本メソッドのおさらい
次のコードを実行したときに、出力結果を答えてください。
```ruby
puts "hello".capitalize
puts "ruby".upcase
puts "ChatGPT".downcase
puts "ruby".include?("ru")
puts "ruby".include?("Ra")
```

<details><summary>📍 解答・解説</summary>
  
```ruby
>> puts "hello".capitalize
Hello
=> nil

>> puts "ruby".upcase
RUBY
=> nil

>> puts "ChatGPT".downcase
chatgpt
=> nil

>> puts "ruby".include?("ru")
true
=> nil

>> puts "ruby".include?("Ra")
false
=> nil
```
### capitalize
```ruby
"hello".capitalize #=> "Hello"
```
- 先頭の文字だけを大文字にして、他を小文字にする。
- 文字列`"hello"` → `"Hello"`に変換。

### upcase
```ruby
"ruby".upcase #=> "RUBY"
```
- すべての文字を大文字に変換する。

### downcase
```ruby
"ChatGPT".downcase #=> "chatgpt"
```
- すべての文字を小文字に変換する。

### include?("ru")
```ruby
"ruby".include?("ru") #=> true
```
- `"ru"`という部分文字列が`"ruby"`の中に含まれているかを調べる。含まれているので`true`。

### include?("Ra")
```ruby
"ruby".include?("Ra") #=> false
```
- Ruby の文字列判定は大文字・小文字を区別する。`"Ra"`と`"ra"`は別物なので、結果は`false`。
</details>

---

## 🔹 レベル2：文字列と数値の変換
次のコードの出力結果を答えてください。
```ruby
str = "100"
num = 25

puts str.to_i + num
puts num.to_s + str
puts "10" * 3
puts "10".to_i * 3
```

<details><summary>📍 解答・解説</summary>
  
```ruby
str = "100"
num = 25
```
- `str`は文字列（String型）、`num`は数値（Integer型）。

### puts str.to_i + num
```ruby
"100".to_i + 25 #=> 125
```
- `"100"`は文字列なので、そのままでは数値計算できない。
- `to_i`で整数に変換してから`25`を足す。
- 結果：`125`

### puts num.to_s + str
```ruby
25.to_s + "100" #=> "25100"
```
- `num`を`to_s`で文字列に変換。
- `"25"`と`"100"`を文字列として結合。
- 結果：`"25100"`（数字の計算ではなく、文字列の連結）。

### puts "10" * 3
```ruby
"10" * 3 #=> "101010"
```
- 文字列 × 数値の場合、Ruby は文字列を繰り返す。
- `"10"`を3回繰り返して`"101010"`。

### puts "10".to_i * 3
```ruby
"10".to_i * 3 #=> 30
```
- `"10"`を`to_i`で数値`10`に変換。
- `10 * 3`で計算し、`30`。

</details>

---

### 🔹 レベル3：変数と式の組み合わせ
次のコードの出力を予想してみましょう。
```ruby
name = "Yoshiwo"
age = 30 + 5
puts "#{name}さんは#{age}歳です。"
```

<details><summary>📍 解答・解説</summary>

実行結果：`Yoshiwoさんは35歳です。`
- `puts`は「見やすく出す」ために文字列のクォートを外して出力する。
- `p`は「Rubyオブジェクトをそのまま表示」するため、`"..."`が付く。つまり、コード上でどういうオブジェクトなのかを見せてくれる。
</details>

---

### 🔹 レベル4：自分でコードを書いてみよう
1. 変数 animal に好きな動物の名前を代入してください。
2. その動物の名前を3回繰り返して出力してください。
3. その文字列の長さを表示してください。
（例）
```shell
ねこねこねこ
文字数: 5
```

<details><summary>📍 解答・解説</summary>

```ruby
animal = "まぐろ"
3.times {print animal}
puts
puts animal.length
```
- `times`は同じ処理を指定回数繰り返す。
- `print`は改行しない出力。そのため`"まぐろ"`が横に3回並ぶ。
- `puts`は改行を1回入れて、次の行に進む。これがないと「まぐろまぐろまぐろ3」という表示になってしまう！
- `puts animal.length`で、`"まぐろ"`の文字数（3文字）を出力する。
- `length`は文字数を返すメソッド。
</details>

---

### 🔹 レベル5（挑戦！）
次のように出力されるプログラムを作ってください。
```text
名前を入力してください: （←getsで入力）
こんにちは、〇〇さん！
```
ヒント：gets と chomp を使います。

<details><summary>📍 解答・解説</summary>

```ruby
puts "名前を入力してください:"
name = gets.chomp
puts "こんにちは、#{name}さん！"
```
- `name = gets.chomp`は、ユーザーが入力した文字列を受け取り、改行を削除して変数`name`に代入。もし、`chomp`メソッドがないと以下の表示になる。
```shell
% ruby basics.rb
名前を入力してください:
Yoshiwo
こんにちは、Yoshiwo
さん！
```
</details>


</details>

このセットは「文字列と数値の扱い・出力・入力」に慣れるための演習です。
