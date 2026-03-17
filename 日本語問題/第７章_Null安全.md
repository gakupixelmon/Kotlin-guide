# Kotlin 重要な構文：Null安全とクラス

プログラムの安全性を高める「Null安全」と、データを構造化する「クラス（オブジェクト指向）」の基礎について解説します。

---

## 1. Null安全 (Null Safety)

多くのプログラミング言語では、「変数に何も入っていない状態（`null`）」にアクセスしようとすると、プログラムがクラッシュします（NullPointerException、通称ぬるぽ）。
Kotlinは、これを**「コンパイル（実行前）の段階で完全に防ぐ」**ように設計されています。



### A. 非Null型 と Null許容型 (Nullable)
Kotlinでは、デフォルトで変数に `null` を入れることができません。`null` を許可するには、型の後ろに `?` をつけます。

```kotlin
// 1. 非Null型 (Non-null type)
var a: String = "Hello"
// a = null // コンパイルエラー！絶対にnullにならないことが保証される

// 2. Null許容型 (Nullable type)
var b: String? = "Hello"
b = null // OK
```

### B. 安全な呼び出し (Safe Call ?.)
null かもしれない変数（Nullable型）のメソッドやプロパティには、直接アクセスできません。?. を使うと、「もしnullでなければ実行し、nullなら全体としてnullを返す」という処理になります。
```
val name: String? = null

// println(name.length) // エラー！nullの可能性があるため直接呼べない
println(name?.length)   // 安全な呼び出し。エラーにならず "null" と出力される
```

### C. エルビス演算子 (Elvis Operator ?:)
「もし左側が null だったら、右側の代わりの値を使う」という演算子です。記号がエルビス・プレスリーの顔文字（時計回りに90度回転）に見えることが由来です。

```
val name: String? = null
// name?.length が null なので、代わりの 0 が代入される
val length = name?.length ?: 0 

println("文字数は $length です") // 文字数は 0 です
```

# 問題
以下のコードを実行したとき、どのような結果になるか、あるいはエラーになるか答えてください。
### 第1問：Null安全の基本
```
fun main() {
    var text: String = "Kotlin"
    // text = null // このコメントを外すとどうなりますか？
    println(text)
}
```

### 第2問: 安全呼び出しとエルビス演算子  
```
fun main() {
    val score: Int? = null
    // score が null なら -1 を返す
    val finalScore = score ?: -1
    println(finalScore)
}
```


