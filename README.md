問題1. Nothing but the Truth ;; 真実のみ

問題はclojure形式です。下線の部分に値を入れて、評価結果がtrueになるようにして下さい。
```
(= __ true)
```
解答
```clojure
true
```

問題2. Simple Math ;; 簡単な算数

ポーランド記法とか知っている人なら簡単かも。

今回はひと桁の数字です。
```
(= (- 10 (* 2 3)) __)
```

解答
```clojure
4
```

問題3. Intro to Strings ;; 文字列入門

clojureの文字列はJavaの文字列です。Javaの文字列メソッドはすべて使えます。

```
(= __ (.toUpperCase "hello world"))
```

解答
```clojure
"HELLO WORLD"
```

問題4. Intro to Lists ;; リスト入門

関数でリストを作る方法と、引用符で作る方法があります。

```
(= (list __) '(:a :b :c))
```

解答
```clojure
:a :b :c
```

問題5. Lists: conj ;; リストの関数conj

リストの関数conj(conjoin)はリストの先頭にアイテムを付け加えます。

```
(= __ (conj '(2 3 4) 1))

(= __ (conj '(3 4) 2 1))
```

解答
```clojure
'(1 2 3 4)
```

問題6. Intro to Vectors ;; ベクトル入門

ベクトルはカギ括弧で囲む方法などいろいろな方法で作ることができます。

```
(= [__] (list :a :b :c) (vec '(:a :b :c)) (vector :a :b :c))
```

解答
```clojure
:a :b :c
```

質問

(list :a :b :c)もベクトルと=であるのが納得がいきません。

問題7. Vectors: conj ;; ヴェクトルの関数conj

関数conjはベクトルの場合は後ろにアイテムを付け加えます。

```
(= __ (conj [1 2 3] 4))

(= __ (conj [1 2] 3 4))
```

解答
```clojure
[1 2 3 4]
```

問題8. Intro to Sets ;; 集合入門

セットはユニークな（重複なしの）値のコレクションです。

```
(= __ (set '(:a :a :b :c :c :c :c :d :d)))

(= __ (clojure.set/union #{:a :b :c} #{:b :c :d}))
```

解答
```clojure
#{:a :b :c :d}
```

問題9. Sets: conj ;; 関数conjはセットの場合、新たなアイテムを付け加えます。

```
(= #{1 2 3 4} (conj #{1 4 3} __))
```

解答
```clojure
2
```

問題10. Intro to Maps ;; マップ(連想配列)入門

マップは連想配列とかハッシュテーブルとか呼ばれるものと同じで、キーワードと値のペアを格納します。カンマは任意です（あってもなくてもよい）。

キーワードはそのままでlookup関数として使えます。

```
(= __ ((hash-map :a 10, :b 20, :c 30) :b))

(= __ (:b {:a 10, :b 20, :c 30}))
```

解答
```clojure
20
```

問題11. Maps: conj ;; マップ(連想配列)の関数conj

関数conjはマップの場合key-valueペアを加えます。

```
(= {:a 1, :b 2, :c 3} (conj {:a 1} __ [:c 3]))
```

解答
```clojure
{:b 2}
```

問題12. Intro to Sequences ;; シーケンス入門

Clojureのコレクションはシーケンス機能があり、シーケンス関数であるところ、first, second, lastが使えます。

```
(= __ (first '(3 2 1)))

(= __ (second [2 3 4]))

(= __ (last (list 1 2 3)))
```

解答
```clojure
3
```

問題13. Sequences: rest ;; シーケンス関数rest

関数restはシーケンスのfirst以外の要素を返します。

```
(= __ (rest [10 20 30 40]))
```

解答
```clojure
[20 30 40]
```

問題14. Intro to Functions ;; 関数入門

Clojureはいろんな方法で関数を作れます。

```
(= __ ((fn add-five [x] (+ x 5)) 3))

(= __ ((fn [x] (+ x 5)) 3))

(= __ (#(+ % 5) 3))

(= __ ((partial + 5) 3))
```

解答
```clojure
8
```

問題15. Double Down ;; 倍返し

数を倍にして返す関数を作る。

```
(= (__ 2) 4)

(= (__ 3) 6)

(= (__ 11) 22)

(= (__ 7) 14)
```

解答
```clojure
#(* 2 %)

* 2
```

問題16. Hello World ;; ハローワールド

名前にハローをつけて返す関数を作る。

```
(= (__ "Dave") "Hello, Dave!")

(= (__ "Jenn") "Hello, Jenn!")

(= (__ "Rhea") "Hello, Rhea!")
```

解答
```clojure
#(str "Hello, " % "!")

(fn [name] (str "Hello, " name "!"))
```

問題17. Sequences: map ;; map関数

関数mapは引数が2個で1つめは関数fで2つめはシーケンスです。

シーケンスの各要素に関数fを作用させた返り値が要素となったシーケンスを返します。

データ構造のmapと混同しないこと。

```
(= __ (map #(+ % 5) '(1 2 3)))
```

解答
```clojure
'(6 7 8)
```

問題18. Sequences: filter ;; シーケンスのfilter関数

関数filterは引数が2個で1つめは真偽判定関数fで2つめはシーケンスです。

シーケンスの要素にfを当てはめて真を返す値が要素となったシーケンスを返します。

```
(= __ (filter #(> % 5) '(3 4 5 6 7)))
```

解答
```clojure
'(6 7)
```


問題19. Last Element ;; 最後の要素

シーケンスの最後の要素を返す関数を作る。

使わない関数: last

```
(= (__ [1 2 3 4 5]) 5)

(= (__ '(5 4 3)) 3)

(= (__ ["b" "c" "d"]) "d")
```

解答
```clojure
#(nth % (dec (count %)))
```

問題20. Penultimate Element ;; 最後から2番目の要素

シーケンスの後から2番目の要素を返す関数を作る。

```
(= (__ (list 1 2 3 4 5)) 4)

(= (__ ["a" "b" "c"]) "b")

(= (__ [[1 2] [3 4]]) [1 2])
```

解答
```clojure
(fn [coll] (first (reverse (vec coll))))

(comp second reverse)
```

問題21. Nth Element ;; N番目の要素

シーケンスのN番目の要素を返す関数を作る。

使わない関数: nth

```
(= (__ '(4 5 6 7) 2) 6)

(= (__ [:a :b :c] 0) :a)

(= (__ [1 2 3 4] 1) 2)

(= (__ '([1 2] [3 4] [5 6]) 2) [5 6])
```

解答
```clojure
(fn [coll n] (first (drop n coll)))
```


問題22. Count a Sequence ;; シーケンスの要素数を数える

シーケンスの要素数を返す関数を作る。

使わない関数: count

```
(= (__ '(1 2 3 3 1)) 5)

(= (__ "Hello World") 11)

(= (__ [[1 2] [3 4] [5 6]]) 3)

(= (__ '(13)) 1)

(= (__ '(:a :b :c)) 3)
```

解答
```clojure
#(reduce + (map (constantly 1) %))

(fn [coll] (reduce + (map (constantly 1) coll)))
```

問題23. Reverse a Sequence ;; シーケンスの逆順

シーケンスを逆順にして返す関数を作る。

使わない関数: reverse rseq

```
(= (__ [1 2 3 4 5]) [5 4 3 2 1])

(= (__ (sorted-set 5 7 2 7)) '(7 5 2))

(= (__ [[1 2][3 4][5 6]]) [[5 6][3 4][1 2]])
```

解答
```clojure
#(reduce conj () %)

(fn [coll] (reduce conj () coll))
```


問題24. Sum It All Up ;; 合計(sum)

数字のシーケンスの合計を返す関数を作る。

```
(= (__ [1 2 3]) 6)

(= (__ (list 0 -2 5 5)) 8)

(= (__ #{4 2 1}) 7)

(= (__ '(0 0 -1)) -1)

(= (__ '(1 10 3)) 14)
```

解答
```clojure
#(reduce + %)

(fn [coll] (reduce + coll))
```


問題25. Find the odd numbers ;; 奇数

シーケンスの要素から奇数だけ抜き出して返す関数を作る。

```
(= (__ #{1 2 3 4 5}) '(1 3 5))

(= (__ [4 2 1 6]) '(1))

(= (__ [2 2 4 6]) '())

(= (__ [1 1 1 3]) '(1 1 1 3))
```

解答
```clojure
#(filter odd? %)
```


問題26. Fibonacci Sequence ;; フィボナッチ数列

X個のフィボナッチ数を返す関数を作る。

```
(= (__ 3) '(1 1 2))

(= (__ 6) '(1 1 2 3 5 8))

(= (__ 8) '(1 1 2 3 5 8 13 21))
```

解答
```clojure
#(take % (map first (iterate (fn [[a b]] [b (+ a b)]) [1 1])))
```

問題27. Palindrome Detector ;; 回文発見器

与えられたシーケンスが回文かどうかを判定する関数を作る。

ヒント: "racecar"は'(\r \a \c \e \c \a \r)ではない。

```
(false? (__ '(1 2 3 4 5)))

(true? (__ "racecar"))

(true? (__ [:foo :bar :foo]))

(true? (__ '(1 1 3 3 1 1)))

(false? (__ '(:a :b :c)))
```

解答
```clojure
#(= (seq %) (reverse (seq %)))
```


問題28. Flatten a Sequence ;; シーケンスのフラット化

ネストしたリストなどのシーケンスをフラット化する関数を作る。

使わない関数: flatten

```
(= (__ '((1 2) 3 [4 [5 6]])) '(1 2 3 4 5 6))

(= (__ ["a" ["b"] "c"]) '("a" "b" "c"))

(= (__ '((((:a))))) '(:a))
```

解答
```clojure
#(filter (complement sequential?) (rest (tree-seq sequential? seq %)))
```


問題29. Get the Caps ;; 大文字だけ

文字列から大文字だけ抜き出して新たな文字列を返す関数を作る。

```
(= (__ "HeLlO, WoRlD!") "HLOWRD")

(empty? (__ "nothing"))

(= (__ "$#A(*&987Zf") "AZ")
```

解答
```clojure
#(apply str (re-seq #"[A-Z]+" %))
```


問題30. Compress a Sequence ;; シーケンスの圧縮

シーケンスから連続した値を取り除く関数を作る。

```
(= (apply str (__ "Leeeeeerrroyyy")) "Leroy")

(= (__ [1 1 2 3 3 2 2 3]) '(1 2 3 2 3))

(= (__ [[1 2] [1 2] [3 4] [1 2]]) '([1 2] [3 4] [1 2]))
```

解答
```clojure
#(map first (partition-by identity %))
```


問題31. Pack a Sequence ;; シーケンスをパック

シーケンスの連続した値をサブリストにしてパックする。

```
(= (__ [1 1 2 1 1 1 3 3]) '((1 1) (2) (1 1 1) (3 3)))

(= (__ [:a :a :b :b :c]) '((:a :a) (:b :b) (:c)))

(= (__ [[1 2] [1 2] [3 4]]) '(([1 2] [1 2]) ([3 4])))
```

解答
```clojure
partition-by identity
```

問題32. Duplicate a Sequence ;; シーケンスの二重化

シーケンスの要素を二重にする関数を作る。

```
(= (__ [1 2 3]) '(1 1 2 2 3 3))

(= (__ [:a :a :b :b]) '(:a :a :a :a :b :b :b :b))

(= (__ [[1 2] [3 4]]) '([1 2] [1 2] [3 4] [3 4]))

(= (__ [[1 2] [3 4]]) '([1 2] [1 2] [3 4] [3 4]))
```

解答
```clojure
mapcat #(list % %)
```

問題33. Replicate a Sequence ;; シーケンスのレプリケイト

シーケンスの要素を指定した回数繰り返す関数。

```
(= (__ [1 2 3] 2) '(1 1 2 2 3 3))

(= (__ [:a :b] 4) '(:a :a :a :a :b :b :b :b))

(= (__ [4 5 6] 1) '(4 5 6))

(= (__ [[1 2] [3 4]] 2) '([1 2] [1 2] [3 4] [3 4]))

(= (__ [44 33] 2) [44 44 33 33])
```

解答
```clojure
(fn [s n] (mapcat #(repeat n %) s))
```


問題34. Implement range ;; range関数の実装

ある範囲の整数のリストを返す関数を作る。

```
(= (__ 1 4) '(1 2 3))

(= (__ -2 2) '(-2 -1 0 1))

(= (__ 5 8) '(5 6 7))
```


解答
```clojure
#(take (- %2 %1) (iterate inc %1))
```

問題35. Local bindings ;; ローカル・バインディング

Clojureはローカルな名前付きの変数をletというスペシャル・フォームで扱うことができます。

```
(= __ (let [x 5] (+ 2 x)))

(= __ (let [x 3, y 10] (- y x)))

(= __ (let [x 21] (let [y 3] (/ x y))))
```

解答
```clojure
7
```


問題36. Let it Be ;; レット・イット・ビー

以下のテストの結果がすべて真になるようにx, y, zをバインドすることができますか。

```
(= 10 (let __ (+ x y)))

(= 4 (let __ (+ y z)))

(= 1 (let __ z))
```

解答
```clojure
[z 1 y 3 x 7]
```

問題37. Regular Expressions ;; 正規表現

Regexパターンにはスペシャル・マクロのreaderがあります。

```
(= __ (apply str (re-seq #"[A-Z]+" "bA1B3Ce ")))
```


解答
```clojure
"ABC"
```

問題38. Maximum value ;; 最大値

引数の数の引数の中から最大値を返す関数を作る。

```
(= (__ 1 8 3 4) 8)

(= (__ 30 20) 30)

(= (__ 45 67 11) 67)
```

解答
```clojure
#(last (sort %&))
```

問題39. Interleave Two Seqs ;; 2つのシーケンスの交互合成

2つのシーケンスから交互に要素をとりだして新しいシーケンスを返す関数を作る。

使わない関数: interleave

```
(= (__ [1 2 3] [:a :b :c]) '(1 :a 2 :b 3 :c))

(= (__ [1 2] [3 4 5 6]) '(1 3 2 4))

(= (__ [1 2 3 4] [5]) [1 5])

(= (__ [30 20] [25 15]) [30 25 20 15])
```

解答
```clojure
#(mapcat vector %1 %2)
```

問題40. Interpose a Seq ;; 区切り要素の挿入

シーケンスの要素の間に任意の要素を挿入する関数を作る。

使わない関数: interpose

```
(= (__ 0 [1 2 3]) [1 0 2 0 3])

(= (apply str (__ ", " ["one" "two" "three"])) "one, two, three")

(= (__ :z [:a :b :c :d]) [:a :z :b :z :c :z :d])
```

解答
```clojure
(fn [v coll] (butlast (mapcat #(vector % v) coll)))
```

問題41. Drop Every Nth Item ;; N番目ごとの要素をすてる

シーケンスからN番目ごとの要素をなくしたシーケンスを返す関数を作る。

```
(= (__ [1 2 3 4 5 6 7 8] 3) [1 2 4 5 7 8])

(= (__ [:a :b :c :d :e :f] 2) [:a :c :e])

(= (__ [1 2 3 4 5 6] 4) [1 2 3 5 6])
```

解答
```clojure
#(apply concat (partition-all (dec %2) %2 %))
```

問題42. Factorial Fun ;; 階乗の喜び

階乗を計算して返す関数を作る。

```
(= (__ 1) 1)

(= (__ 3) 6)

(= (__ 5) 120)

(= (__ 8) 40320)
```


解答
```clojure
#(apply * (range 1 (inc %)))
```


問題43. Reverse Interleave ;; 逆交互合成

交互合成の逆で、1つのシーケンスを任意の数のシーケンスにする関数を作る。

```
(= (__ [1 2 3 4 5 6] 2) '((1 3 5) (2 4 6)))

(= (__ (range 9) 3) '((0 3 6) (1 4 7) (2 5 8)))

(= (__ (range 10) 5) '((0 5) (1 6) (2 7) (3 8) (4 9)))
```

解答
```clojure
(fn deinterleave [coll n]
  (for [i (range n)] (take-nth n (drop i coll))))
```

問題44. Rotate Sequence ;; シーケンスの回転

シーケンスを任意の方向、数、だけ回転(rotate)する関数を作る。
```
(= (__ 2 [1 2 3 4 5]) '(3 4 5 1 2))

(= (__ -2 [1 2 3 4 5]) '(4 5 1 2 3))

(= (__ 6 [1 2 3 4 5]) '(2 3 4 5 1))

(= (__ 1 '(:a :b :c)) '(:b :c :a))

(= (__ -4 '(:a :b :c)) '(:c :a :b))
```

解答
```clojure
(fn [n coll]
  (take (count coll) (drop (mod n (count coll)) (cycle coll))))
```

問題45. Intro to Iterate ;; イテレート入門

iterate関数を用いて遅延評価の無限シーケンスが作成できる。

```
(= __ (take 5 (iterate #(+ 3 %) 1)))
```

解答
```clojure
[1 4 7 10 13]
```

問題46. Flipping out ;; 引数交換

高階関数を用いて、引数の順序を反転した関数を返す関数を作る。
```
(= 3 ((__ nth) 2 [1 2 3 4 5]))

(= true ((__ >) 7 8))

(= 4 ((__ quot) 2 8))

(= [1 2 3] ((__ take) [1 2 3 4 5] 3))
```

解答
```clojure
(fn [f]
  (fn [& args] (apply f (reverse args))))
```

問題47. Contain Yourself ;; 範囲内属性確認

関数contains?はKEYがコレクションにあるかどうかを調べるものです。ベクトルやリストのインデクスとは別物です。

```
(contains? #{4 5 6} __)

(contains? [1 1 1 1 1] __)

(contains? {4 :a 2 :b} __)

(not (contains? [1 2 4] __))
```

解答
```clojure
4
```

問題48. Intro to some ;; some入門

関数someは真偽判定関数とコレクションを引数にとり、真偽判定関数が真になる最初の値を返します。

```
(= __ (some #{2 7 6} [5 6 7 8]))

(= __ (some #(when (even? %) %) [5 6 7 8]))
```

解答
```clojure
6
```

問題49. Split a sequence ;; シーケンスのスプリット

シーケンスを2つのパートに分割する関数を作る。

使わない関数: split-at

```
(= (__ 3 [1 2 3 4 5 6]) [[1 2 3] [4 5 6]])

(= (__ 1 [:a :b :c :d]) [[:a] [:b :c :d]])

(= (__ 2 [[1 2] [3 4] [5 6]]) [[[1 2] [3 4]] [[5 6]]])
```

解答
```clojure
(fn [n coll]
  [(take n coll) (drop n coll)])
```

問題50. Split by Type ;; 型による分割

型の混在したシーケンスを型ごとのシーケンスに分割する関数を作る。サブシーケンスの中の順序は元の順序を維持するが、サブシーケンス自体の順序は保証しない。(テストケースに集合がある理由である。)

```
(= (set (__ [1 :a 2 :b 3 :c])) #{[1 2 3] [:a :b :c]})

(= (set (__ [:a "foo"  "bar" :b])) #{[:a :b] ["foo" "bar"]})

(= (set (__ [[1 2] :a [3 4] 5 6 :b])) #{[[1 2] [3 4]] [:a :b] [5 6]})
```

解答
```clojure
(comp vals (partial group-by type))
```

問題51. Advanced Destructuring ;; 高度なシーケンス分解

つぎはより洗練されたシーケンス分解です。

```
(= [1 2 [3 4 5] [1 2 3 4 5]] (let [[a b & c :as d] __] [a b c d]))
```

解答
```clojure
(range 1 6)
```

問題52. Intro to Destructuring ;; シーケンス分解入門

let束縛と関数の媒介変数はシーケンス分解に使えます。
Let bindings and function parameter lists support destructuring.

```
(= [2 4] (let [[a b c d e] [0 1 2 3 4]] __))
```

解答
```clojure
[c e]
```

問題53. Longest Increasing Sub-Seq ;; サブシーケンスをみつける

整数のベクトルを与えられてその中にある連続した漸増するサブシーケンスの最長のものをみつける。同じ長さのものだったら最初のもの。サブシーケンスは最低でも長さ2とする。

```
(= (__ [1 0 1 2 3 0 4 5]) [0 1 2 3])

(= (__ [5 6 1 3 2 7]) [5 6])

(= (__ [2 3 3 4 5]) [3 4 5])

(= (__ [7 6 5 4]) [])
```

解答
```clojure
(fn longest-subseq [coll]
  (let [take-seq (fn [n pred coll]
                   (let [hits (count (take-while #(apply pred %) (partition n 1 coll)))]
                     (take (+ n hits -1) coll)))
        chop (fn [coll] (for [n (range (count coll))] (drop n coll)))
        parts (chop coll)
        seqs (map (partial take-seq 2 #(= (inc %1) %2)) parts)
        longest (apply max-key count seqs)]
    (if (< (count longest) 2)
      []
      longest)))
```

問題54. Partition a Sequence ;; シーケンスの単位分割

シーケンスの要素をx個ごとに分割する。x個以下の要素は捨てられる。

```
(= (__ 3 (range 9)) '((0 1 2) (3 4 5) (6 7 8)))

(= (__ 2 (range 8)) '((0 1) (2 3) (4 5) (6 7)))

(= (__ 3 (range 8)) '((0 1 2) (3 4 5)))
```

解答
```clojure
(fn p [n c] (when (and (seq c) (>= (count c) n)) (cons (take n c) (p n (drop n c)))))
```

問題55. Count Occurrences ;; 出現回数カウント

シーケンスの要素ごとに出現回数をマップ(連想配列)にして返す関数を作る。

使わない関数: frequencies

```
(= (__ [1 1 2 3 2 1 1]) {1 4, 2 2, 3 1})

(= (__ [:b :a :b :a :b]) {:a 2, :b 3})

(= (__ '([1 2] [1 3] [1 3])) {[1 2] 1, [1 3] 2})
```

解答
```clojure
#(apply merge-with + (for [e %] {e 1}))
```

問題56. Find Distinct Items ;; ディスティンクト(ユニーク)

シーケンスから重複を削除する関数を作る。もとの出現順序は維持される。

使わない関数: distinct

```
(= (__ [1 2 1 3 1 2 4]) [1 2 3 4])

(= (__ [:a :a :b :b :c :c]) [:a :b :c])

(= (__ '([2 4] [1 2] [1 3] [1 3])) '([2 4] [1 2] [1 3]))

(= (__ (range 50)) (range 50))
```

解答
```clojure
reduce #(if ((set %1) %2) %1 (conj %1 %2)) []
```

問題57. Simple Recursion ;; 簡単な再帰

再帰関数は自分自身を呼び出す関数です。

```
(= __ ((fn foo [x] (when (> x 0) (conj (foo (dec x)) x))) 5))
```

解答
```clojure
[5 4 3 2 1]
```

問題58. Function Composition ;; 関数の構築

複数の関数を右から左に適用する関数を作る。

使わない関数: comp

```
(= [3 2 1] ((__ rest reverse) [1 2 3 4]))

(= 5 ((__ (partial + 3) second) [1 2 3 4]))

(= true ((__ zero? #(mod % 8) +) 3 5 7 9))

(= "HELLO" ((__ #(.toUpperCase %) #(apply str %) take) 5 "hello world"))

```
解答
```clojure
(fn [& fs] (reduce (fn [f g] #(f (apply g %&))) fs))
```

問題59. Juxtaposition ;; 並置

複数の関数を引数としてとり、返される新たな関数は、それぞれの関数を適用した結果が左から右に並置されたベクトルとなるような関数を作る。

使わない関数: juxt

```
(= [21 6 1] ((__ + max min) 2 3 5 1 6 4))

(= ["HELLO" 5] ((__ #(.toUpperCase %) count) "hello"))

(= ["HELLO" 5] ((__ #(.toUpperCase %) count) "hello"))
```

解答
```clojure
(fn [& fs]
  (fn [& as] (map #(apply % as) fs)))
```

問題60. Sequence Reductions ;; シーケンス・リダクション

reduce関数と似た関数で、途中の結果を返す関数を作る。2個か3個の引数をとって返されるシーケンスは遅延評価とする。

使わない関数: reductions

```
(= (take 5 (__ + (range))) [0 1 3 6 10])

(= (__ conj [1] [2 3 4]) [[1] [1 2] [1 2 3] [1 2 3 4]])

(= (last (__ * 2 [3 4 5])) (reduce * 2 [3 4 5]) 120)
```

解答
```clojure
(fn reduce-
  ([f coll]
    (reduce- f (first coll) (next coll)))
  ([f init [h & t :as coll]]
    (cons init
      (lazy-seq
        (if (seq coll)
          (reduce- f (f init h) t))))))
```

問題61. Map Construction ;; マップ(連想配列)作成

キーのベクトルと値のベクトルを引数としてマップを作成する関数を作る。

使わない関数: zipmap

```
(= (__ [:a :b :c] [1 2 3]) {:a 1, :b 2, :c 3})

(= (__ [1 2 3 4] ["one" "two" "three"]) {1 "one", 2 "two", 3 "three"})

(= (__ [:foo :bar] ["foo" "bar" "baz"]) {:foo "foo", :bar "bar"})
```

解答
```clojure
#(apply hash-map (interleave %1 %2))
```

問題62. Re-implement Iterate ;; イテレートの実装

副作用のない関数fと初期値xを引数としてとり、x, (f x), (f (f x)), (f (f (f x))), etc.という無限遅延シーケンスを返す関数を作る。

使わない関数: iterate

```
(= (take 5 (__ #(* 2 %) 1)) [1 2 4 8 16])

(= (take 100 (__ inc 0)) (take 100 (range)))

(= (take 9 (__ #(inc (mod % 3)) 1)) (take 9 (cycle [1 2 3])))
```

解答
```clojure
(fn iterate- [f init]
  (cons init
    (lazy-seq
      (iterate- f (f init)))))
```

問題63. Group a Sequence ;; シーケンスのグループ化

関数fとシーケンスを引数とし、マップ(連想配列)を返す関数を作る。マップのキーとなるのは、fをシーケンスに適用した結果である。値はベクトルで元のシーケンスの順序を維持する。

使わない関数: group-by

```
(= (__ #(> % 5) [1 3 6 8]) {false [1 3], true [6 8]})

(= (__ #(apply / %) [[1 2] [2 4] [4 6] [3 6]])
   {1/2 [[1 2] [2 4] [3 6]], 2/3 [[4 6]]})

(= (__ count [[1] [1 2] [3] [1 2 3] [2 3]])
   {1 [[1] [3]], 2 [[1 2] [2 3]], 3 [[1 2 3]]})
```

解答
```clojure
#(apply merge-with into (for [v %2] {(% v) [v]}))
```

問題64. Intro to Reduce ;; reduce関数入門

reduce関数は引数として関数とオプショナルな初期値をとる。次にreduce関数はシーケンスの最初の2つの要素(もしくは初期値と最初の1つの要素)に関数を適用する。次のイテレーションでは前回の返り値と次の要素に関数を適用し、結果としてコレクション全体を1つの値に縮小(reduce)する。

複雑そうに聞こえるかもしれないが、それほどでもない。

```
(= 15 (reduce __ [1 2 3 4 5]))

(=  0 (reduce __ []))

(=  6 (reduce __ 1 [2 3]))
```

解答
```clojure
+
```

問題65. Black Box Testing ;; ブラックボックステスト

Clojureにたくさんのシーケンス型があり、それぞれ違いがあります。シーケンス型に作用する関数は対象を単一のシーケンス型に変換してから作用するのが典型的ですが、それぞれの型の違いを認識することも大切です。

コレクションを引数としてとり、型(:map, :set, :list, or :vector)を判断して返す関数を作る。list?などの真偽判定関数は使わずに対象の動作から判断すること。

使わない関数: class type Class vector?  sequential?  list?  seq?  map?  set?  instance?  getClass

```
(= :map (__ {:a 1, :b 2}))

(= :list (__ (range (rand-int 20))))

(= :vector (__ [1 2 3 4 5 6]))

(= :set (__ #{10 (rand-int 5)}))

(= [:map :set :vector :list] (map __ [{} #{} [] ()]))
```

解答
```clojure
(fn [c]
  (cond
    (= (get (conj c [:t "t"]) :t) "t") :map
    (= (get (conj c :t) :t) :t) :set
    (= (first (conj (conj c :a) :b)) :b) :list
    (= (last (conj (conj c :a) :b)) :b) :vector))
```


問題66. Greatest Common Divisor ;; 最大公約数

2つの整数から最大公約数を返す関数を作る。

```
(= (__ 2 4) 2)

(= (__ 10 5) 5)

(= (__ 5 7) 1)

(= (__ 1023 858) 33)
```

解答
```clojure
(fn gcd [a b] (if (zero? b) a (recur b (mod a b))))
```

問題67. Prime Numbers ;; 素数

最初のx個の素数を返す関数を作る。

```
(= (__ 2) [2 3])

(= (__ 5) [2 3 5 7 11])

(= (last (__ 100)) 541)
```

解答
```clojure
(fn prime-gen [cnt]
  (let [prime? (fn [n]
                 (not (some #(and
                               (not= n %)
                               (zero? (mod n %)))
                            (range 2 (inc (Math/sqrt n))))))]
    (take cnt (filter prime? (iterate inc 2)))))
```

問題68. Recurring Theme ;; recur関数

Clojureのループ構造はスタック1つを使うrecur関数しかない。関数の中で使うにしろloopの中で使うにしろ、recurは与えられた値を再帰ポイントとして再束縛する。recurは最後の位置に置かれ、それ以外の場所に置かれるとエラーになる。

```
(= __
  (loop [x 5
         result []]
    (if (> x 0)
      (recur (dec x) (conj result (+ 2 x)))
      result)))
```

解答
```clojure
[7 6 5 4 3]
```

問題69. Merge with a Function ;; マージ関数

関数fと複数のマップ(連想配列)を引数とし、最初のマップに残りのマップを合成したものを返す関数を作る。キーが重複した場合、あとの方の値を結果の値と関数fで合成する(f val-in-result val-in-latter)。

使わない関数: merge-with

```
(= (__ * {:a 2, :b 3, :c 4} {:a 2} {:b 2} {:c 5}) {:a 4, :b 6, :c 20})

(= (__ - {1 10, 2 20} {1 3, 2 10, 3 15}) {1 7, 2 10, 3 15})

(= (__ concat {:a [3], :b [6]} {:a [4 5], :c [8 9]} {:b [7]}) {:a [3 4 5], :b [6 7], :c [8 9]})
```

解答
```clojure
(fn [f & ms]
  (reduce (fn [m1 m2]
            (reduce (fn [m [k v]]
                      (if (contains? m k)
                        (update-in m [k] f v)
                        (assoc m k v)))
                    m1 m2))
          ms))
```

問題70. Word Sorting ;; 単語のソート

文を単語に区切り、ソートした結果を返す関数を作る。大文字小文字はソートに影響しない。句読点は無視する。

```
(= (__  "Have a nice day.") ["a" "day" "Have" "nice"])

(= (__  "Clojure is a fun language!") ["a" "Clojure" "fun" "is" "language"])

(= (__  "Fools fall for foolish follies.") ["fall" "follies" "foolish" "Fools" "for"])
```

解答
```clojure
(fn [s]
  (sort-by clojure.string/lower-case
    (re-seq #"[A-Za-z]+" s)))
```

問題71. Rearranging Code: -> ;; スレッドマクロ

macro(->)は式xを順次フォームの中に挿入していきます。まず最初のフォームの2番目要素として挿入し、リストにします。次に最初のフォームを2番目のフォームの2番目の要素として挿入し、リストにします。これを最後のフォームまで繰り返します。

```
(= (__ (sort (rest (reverse [2 5 4 1 3 6])))) (-> [2 5 4 1 3 6] (reverse) (rest) (sort) (__)) 5)
```

解答
```clojure
last
```

問題72. Rearranging Code: ->> ;; スレッドラストマクロ

macro(->>)は式xを順次フォームの中に挿入していきます。まず最初のフォームの最後の要素として挿入し、リストにします。次に最初のフォームを2番目のフォームの最後の要素として挿入し、リストにします。これを最後のフォームまで繰り返します。

```
(= (__ (map inc (take 3 (drop 2 [2 5 4 1 3 6])))) (->> [2 5 4 1 3 6] (drop 2) (take 3) (map inc) (__)) 11)
```

解答
```clojure
reduce +
```

問題73. Analyze a Tic-Tac-Toe Board ;; マルバツゲームの分析

マルバツゲームは2次元のベクトルとして表現できます。Xを:x、Oを:o、空を:eとして表現する。競技者は3つのXか3つのOを縦、横または斜めに置くことにより勝利します。マルバツゲームの盤面を分析し、Xが勝っていれば:x、Oが勝っていれば:o、どちらも勝っていなければnilを返す関数を作る。

```
(= nil (__ [[:e :e :e]
            [:e :e :e]
            [:e :e :e]]))

(= :x (__ [[:x :e :o]
           [:x :e :e]
           [:x :e :o]]))

(= :o (__ [[:e :x :e]
           [:o :o :o]
           [:x :e :x]]))

(= nil (__ [[:x :e :o]
            [:x :x :e]
            [:o :x :o]]))

(= :x (__ [[:x :e :e]
           [:o :x :e]
           [:o :e :x]]))

(= :o (__ [[:x :e :o]
           [:x :o :e]
           [:o :e :x]]))

(= nil (__ [[:x :o :x]
            [:x :o :x]
            [:o :x :o]]))
```

解答
```clojure
(fn tic-tac-toe [board]
  (let [same? (fn [sec] (if (apply = sec) (first sec) nil))
        rows (map same? board)
        cols (map same? (apply map vector board))
        diag1 (same? (map get board (range 3)))
        diag2 (same? (map get board (range 2 -1 -1)))]
    (some #{:x :o} (concat rows cols [diag1] [diag2]))))
```

問題74. Filter Perfect Squares ;; 完全平方フィルター

コンマで区切られた整数の文字列を与えられて、その中から完全平方数だけを抜き出して、コンマで区切られた文字列にして返す関数を作る。

```
(= (__ "4,5,6,7,8,9") "4,9")

(= (__ "15,16,25,36,37") "16,25,36")
```

解答
```clojure
(fn [s]
  (let [nums (map #(Integer/parseInt %) (clojure.string/split s #","))
        psquare? (fn [n] (let [sqrt (Math/sqrt n)] (= (Math/floor sqrt) sqrt)))
        perfect (filter psquare? nums)]
    (apply str (interpose "," perfect))))
```

問題75. Euler's Totient Function ;; オイラーのトーシェント関数(ファイ関数)

2つの数の最大公約数が1のとき互いに素である。オイラーのトーシェント関数f(x)はx以下のxと素な正の整数の数と定義される。f(1)は特別に1と定義する。オイラーのトーシェント関数計算する関数を作れ。

```
(= (__ 1) 1)

(= (__ 10) (count '(1 3 7 9)) 4)

(= (__ 40) 16)

(= (__ 99) 60)
```

解答
```clojure
(fn [n]
  (if (= n 1)
    1
    (let [gcd (fn [a b] (if (zero? b) a (recur b (mod a b))))]
      (count (filter #{1} (map (partial gcd n) (range 1 n)))))))
```


問題76. Intro to Trampoline ;; トランポリン入門

trampoline関数は関数fと複数のパラメーターを引数にとり、fをパラメーターに適用します。もしfが関数を返してきたら、trampolineはその関数を引数なしに実行します。返り値が関数でなくなるまで繰り返し、trampolineはその値を返します。trampolineはスタックを消費することなく互いに再帰するアルゴリズムを実行するのに役立ちます。

```
(= __
   (letfn
     [(foo [x y] #(bar (conj x y) y))
      (bar [x y] (if (> (last x) 10)
                   x
                   #(foo x (+ 2 y))))]
     (trampoline foo [] 1)))
```

解答
```clojure
(range 1 12 2)
```


問題77. Anagram Finder ;; アナグラム発見器

単語のベクトルからアナグラムをさがす関数を作る。単語xの文字を並べ替えて単語yになる場合、単語xは単語yのアナグラムです。返り値は集合の集合で、サブセットは互いにアナグラムである単語の集合とする。サブセットは最低2単語からできていて、アナグラムのない単語は返り値には含まれない。

```
(= (__ ["meat" "mat" "team" "mate" "eat"])
   #{#{"meat" "team" "mate"}})

(= (__ ["veer" "lake" "item" "kale" "mite" "ever"])
   #{#{"veer" "ever"} #{"lake" "kale"} #{"mite" "item"}})
```

解答
```clojure
(fn [ws]
  (set (map (comp set val)
            (remove (comp #{1} count val) (group-by frequencies ws)))))
```


問題78. Reimplement Trampoline ;; トランポリンの実装

"Intro to Trampoline"で紹介した関数を作る。

使わない関数: trampoline

```
(= (letfn [(triple [x] #(sub-two (* 3 x)))
          (sub-two [x] #(stop?(- x 2)))
          (stop? [x] (if (> x 50) x #(triple x)))]
    (__ triple 2))
  82)

(= (letfn [(my-even? [x] (if (zero? x) true #(my-odd? (dec x))))
          (my-odd? [x] (if (zero? x) false #(my-even? (dec x))))]
    (map (partial __ my-even?) (range 6)))
  [true false true false true false])
```

解答
```clojure
(fn [f & args] (loop [f (apply f args)] (if (fn? f) (recur (f)) f)))
```

問題79. Triangle Minimal Path ;; 三角形の最短経路

三角形の最短経路を探索する関数を書く。三角形はベクトルのコレクションとして表現される。経路は三角形の頂点からはじまり、次の行の接している番号を通り、最終行まで行く。

```
(= 7 (__ '([1]
          [2 4]
         [5 1 4]
        [2 3 4 5]))) ; 1->2->1->3

(= 20 (__ '([3]
           [2 4]
          [1 9 3]
         [9 9 2 4]
        [4 6 6 7 8]
       [5 7 3 5 1 4]))) ; 3->4->3->2->7->1
```

解答
```clojure
(fn collapse [p] (let [combine (fn [a b] (map + (map #(apply min %) (partition 2 1 a)) b))] (first (reduce combine (reverse p)))))
```

問題80. Perfect Numbers ;; 完全数

約数の合計がその数と一致するとき完全数と言う。6は1+2+3=6なので完全数です。完全数かどうかを判定する関数を作る。

```
(= (__ 6) true)

(= (__ 7) false)

(= (__ 496) true)

(= (__ 500) false)

(= (__ 8128) true)
```

解答
```clojure
(fn [n]
  (= n (reduce +
    (filter
      #(zero? (mod n %))
      (range 1 n)))))
```

問題81. Set Intersection ;; 集合の共通

集合の共通部分をもとめる関数を作る。共通部分とはそれぞれの集合に共通する要素を元とするサブセットです。

使わない関数: intersection

```
(= (__ #{0 1 2 3} #{2 3 4 5}) #{2 3})

(= (__ #{0 1 2} #{3 4 5}) #{})

(= (__ #{:a :b :c :d} #{:c :e :a :f :d}) #{:a :c :d})
```


解答
```clojure
(fn [a b] (set (filter #(contains? b %) a)))
```

問題82. Word Chains ;; 単語の鎖

ワードチェーンは、単語が一文字ずつ変化するように並べられたものです。一文字は挿入でも削除でも置換でもかまいません。以下に例をあげます。

cat -> cot -> coat -> oat -> hat -> hot -> hog -> dog

単語のシーケンスをとり、単語の鎖に並べられるものだったら真、そうでなかったら偽を返す関数を作る。

```
(= true (__ #{"hat" "coat" "dog" "cat" "oat" "cot" "hot" "hog"}))

(= false (__ #{"cot" "hot" "bat" "fat"}))

(= false (__ #{"to" "top" "stop" "tops" "toss"}))

(= true (__ #{"spout" "do" "pot" "pout" "spot" "dot"}))

(= true (__ #{"share" "hares" "shares" "hare" "are"}))

(= false (__ #{"share" "hares" "hare" "are"}))
```

解答
```clojure
(fn find-chain [words]
  (let [lev (fn lev [s1 s2]
              (cond (empty? s1) (count s2)
                    (empty? s2) (count s1)
                    (= (first s1) (first s2)) (lev (rest s1) (rest s2))
                    :else (inc (min (lev (rest s1) s2)
                                    (lev s1 (rest s2))
                                    (lev (rest s1) (rest s2))))))
        neighbors (fn [words word] (filter #(= (lev word %) 1) words))
        chain (fn chain [graph visited root]
                (let [visited (conj visited root)
                      neigh (remove visited (graph root))]
                  (if (= visited words)
                    true
                    (some (partial chain graph visited) neigh))))
        graph (into {} (for [w words] [w (neighbors words w)]))]
    (true? (some (partial chain graph #{}) words))))
```

問題83. A Half-Truth ;; 半分真実

複数の真偽値を引数にとる関数を作る。引数が真を含む場合真を返すが、全てが真の場合は偽を返す。それ以外は偽を返す。

```
(= false (__ false false))

(= true (__ true false))

(= false (__ true))

(= true (__ false true false))

(= false (__ true true true))

(= true (__ true true true false))
```

解答
```clojure
not=
```

問題84. Transitive Closure ;; 推移閉包

二項関係の推移閉包を生成する関数を作る。関係は2要素のベクトルの集合で表される。

```
(let [divides #{[8 4] [9 3] [4 2] [27 9]}]
  (= (__ divides) #{[4 2] [8 4] [8 2] [9 3] [27 9] [27 3]}))

(let [more-legs
      #{["cat" "man"] ["man" "snake"] ["spider" "cat"]}]
  (= (__ more-legs)
     #{["cat" "man"] ["cat" "snake"] ["man" "snake"]
       ["spider" "cat"] ["spider" "man"] ["spider" "snake"]}))

(let [progeny
      #{["father" "son"] ["uncle" "cousin"] ["son" "grandson"]}]
  (= (__ progeny)
     #{["father" "son"] ["father" "grandson"]
       ["uncle" "cousin"] ["son" "grandson"]}))
```

解答
```clojure
(fn [rel]
  (let [roots (into {} (for [[k v] (group-by first rel)] [k (mapv second v)]))
        children (fn children [rels e]
                   (let [cs (get rels e [])]
                     (cons e (mapcat #(children rels %) cs))))]
    (set (mapcat #(map vector (repeat %) (rest (children roots %))) (keys roots)))))
```


問題85. Power Set ;; 冪集合

集合の冪集合を返す関数を作る。冪集合とは、与えられた集合から、その部分集合の全体として新たに作り出される集合のことである。空集合ともとの集合自身を含みます。

```
(= (__ #{1 :a}) #{#{1 :a} #{:a} #{} #{1}})

(= (__ #{}) #{#{}})

(= (__ #{1 2 3})
   #{#{} #{1} #{2} #{3} #{1 2} #{1 3} #{2 3} #{1 2 3}})

(= (count (__ (into #{} (range 10)))) 1024)
```

解答
```clojure
(fn powerset [s]
  (reduce #(into % (for [subset %] (conj subset %2))) #{#{}} s))
```

問題86. Happy numbers ;; ハッピー数

ハッピー数とは次のような計算を

ある数について各位の数字を自乗して足してあたらしい数を作ることを繰り返して最終的に1になる場合、その数をハッピー数と言います。無限に続いてしまう場合、アンハッピーもしくはサッド数です。数値についてハッピーかどうかを判定する関数を作る。

```
(= (__ 7) true)

(= (__ 986543210) true)

(= (__ 2) false)

(= (__ 3) false)
```

解答
```clojure
(fn happy? [n]
  (letfn [(digits [n]
            (map #(Integer/parseInt (str %)) (str n)))
          (sum-of-squares [n]
            (reduce + (map #(* % %) (digits n))))]
    (boolean (some #{1} (take 100 (iterate sum-of-squares n))))))
```

問題88. Symmetric Difference ;; 対称差

2つの集合のどちらかに属し、両方には属さないものの集合を返す関数を作る。

```
(= (__ #{1 2 3 4 5 6} #{1 3 5 7}) #{2 4 6 7})

(= (__ #{:a :b :c} #{}) #{:a :b :c})

(= (__ #{} #{4 5 6}) #{4 5 6})

(= (__ #{[1 2] [2 3]} #{[2 3] [3 4]}) #{[1 2] [3 4]})
```

解答
```clojure
#(clojure.set/union (clojure.set/difference %1 %2) (clojure.set/difference %2 %1))
```


問題89. Graph Tour ;; グラフツアー

グラフ理論の問題です。グラフを与えられて、全ての辺を一回だけ通る経路がある場合真、そうでない場合偽を返す関数を作る。タプルのベクトルを与えられる。タプル一つ一つがグラフの頂点/ノードを表す。

経路探索のルールは以下の通り。

どのノードから始めてもよい。

辺は必ず1回だけ通る。

辺は無向である。

```
(= true (__ [[:a :b]]))

(= false (__ [[:a :a] [:b :b]]))

(= false (__ [[:a :b] [:a :b] [:a :c] [:c :a]
               [:a :d] [:b :d] [:c :d]]))

(= true (__ [[1 2] [2 3] [3 4] [4 1]]))

(= true (__ [[:a :b] [:a :c] [:c :b] [:a :e]
              [:b :e] [:a :d] [:b :d] [:c :e]
              [:d :e] [:c :f] [:d :f]]))

(= false (__ [[1 2] [2 3] [2 4] [2 5]]))
```

解答
```clojure
(fn eulerian [edges]
  (let [degrees (fn [edges]
                  (apply merge-with + {} (for [[a b] edges
                                               :when (not= a b)]
                                           {a 1 b 1})))
        gdeg (degrees edges)]
    (and
     (not (empty? gdeg))
     (->> (vals gdeg) (filter odd?) count (>= 2)))))
```

問題90. Cartesian Product ;; 直積集合

2つの集合の直積集合を計算する関数を作る。

```
(= (__ #{"ace" "king" "queen"} #{"♠" "♥" "♦" "♣"})
   #{["ace"   "♠"] ["ace"   "♥"] ["ace"   "♦"] ["ace"   "♣"]
     ["king"  "♠"] ["king"  "♥"] ["king"  "♦"] ["king"  "♣"]
     ["queen" "♠"] ["queen" "♥"] ["queen" "♦"] ["queen" "♣"]})

(= (__ #{1 2 3} #{4 5})
   #{[1 4] [2 4] [3 4] [1 5] [2 5] [3 5]})

(= 300 (count (__ (into #{} (range 10))
                  (into #{} (range 30)))))
```


解答
```clojure
#(set (for [a (vec %1) b (vec %2)] [a b]))
```


問題91. Graph Connectivity ;; グラフの連結

グラフ理論で言うところのグラフについて、グラフが連結しているかどうかを判定する関数を作る。グラフが連結している、とはどのノードをとっても経路が存在する、ということである。

グラフが連結している場合、真を、そうでない場合は偽を返す関数を作る。タプルの集合を与えられる。タプル一つ一つがグラフの頂点/ノードを表す。辺は無向(どちらの方向にもすすめる)である。

```
(= true (__ #{[:a :a]}))

(= true (__ #{[:a :b]}))

(= false (__ #{[1 2] [2 3] [3 1]
               [4 5] [5 6] [6 4]}))

(= true (__ #{[1 2] [2 3] [3 1]
              [4 5] [5 6] [6 4] [3 4]}))

(= false (__ #{[:a :b] [:b :c] [:c :d]
               [:x :y] [:d :a] [:b :e]}))

(= true (__ #{[:a :b] [:b :c] [:c :d]
              [:x :y] [:d :a] [:b :e] [:x :a]}))
```

解答
```clojure
(fn fully-connected? [graph]
  (let [nodes (set (apply concat graph))
        full-graph (set (mapcat (fn [[a b :as n]] [n [b a]]) graph))
        children (into {} (for [[k v] (group-by first full-graph)] [k (set (map second v))]))
        connections (fn [node]
                      (->> (iterate #(into % (mapcat children %)) #{node})
                           (partition 2 1)
                           (drop-while #(apply not= %))
                           first first))]
    (every? #(= % nodes) (map connections nodes))))
```

問題92. Read Roman numerals ;; ローマ数字を読む

ローマ数字を文字列で読み込み、意味するところの数字を返す関数を作る。入力されるローマ数字はルールに則っていて、大文字で、減算則である。普通の文字で表される最大の数MMMCMXCIX(3999)以上については考慮しないでよい。

```
(= 14 (__ "XIV"))

(= 827 (__ "DCCCXXVII"))

(= 3999 (__ "MMMCMXCIX"))

(= 48 (__ "XLVIII"))
```

解答
```clojure
(fn read-roman [s]
  (let [numerals {\M 1000 \D 500 \C 100 \L 50 \X 10 \V 5 \I 1}
        nums (partition 2 1 (concat (map numerals s) [0]))]
    (reduce (fn [sum [a b]] ((if (< a b) - +) sum a)) 0 nums)))
```


問題93. Partially Flatten a Sequence ;; シーケンスの部分フラット化

シーケンス(リスト、ベクトル、等)のシーケンスのネストしたコンビネーションをフラット化する関数を作る。最下層のシーケンスは維持する。結果としてネストが1層だけのシーケンスのシーケンスが返される。

```
(= (__ [["Do"] ["Nothing"]])
   [["Do"] ["Nothing"]])

(= (__ [[[[:a :b]]] [[:c :d]] [:e :f]])
   [[:a :b] [:c :d] [:e :f]])

(= (__ '((1 2)((3 4)((((5 6)))))))
   '((1 2)(3 4)(5 6)))
```

解答
```clojure
(fn pflatten [tree]
  (if (every? sequential? tree)
    (mapcat pflatten tree)
    [tree]))
```


問題94. Game of Life ;; ライフゲーム

ライフゲームは数学者john conwayによって発案されたセルオートマトンである。

ボードは生きている(#)セルと死んだ( )セルからできている。セルは周り(横、縦、斜め)の隣接するセルの状態によって次のステージに変化する。ルールは以下のとおりである。

1) 生きているセルで隣接する生きているセルが2個以下のものは死ぬ。過疎によって死ぬようなイメージ。

2) 生きているセルで隣接する生きているセルが2個もしくは3個の場合、生き続ける。

3) 生きているセッるで隣接する生きているセルが3個以上のものは死ぬ。過密によって死ぬイメージ。

4) 死んでいるセルで隣接する行きているセルがちょうど3個のものは生きる。再生によって生きるイメージ。

ボードを与えられ、セルのつぎの世代を表すボードを返す関数を作る。

```
(= (__ ["      "
        " ##   "
        " ##   "
        "   ## "
        "   ## "
        "      "])
   ["      "
    " ##   "
    " #    "
    "    # "
    "   ## "
    "      "])

(= (__ ["     "
        "     "
        " ### "
        "     "
        "     "])
   ["     "
    "  #  "
    "  #  "
    "  #  "
    "     "])

(= (__ ["      "
        "      "
        "  ### "
        " ###  "
        "      "
        "      "])
   ["      "
    "   #  "
    " #  # "
    " #  # "
    "  #   "
    "      "])
```


解答
```clojure
(fn conway [board]
  (let [cells (set (for [y (range (count board))
                         x (range (count (get board y)))
                         :when (not= \space (get-in board [y x]))]
                     [x y]))
        width (count (first board))
        height (count board)
        neighbors (fn [[x y]]
                    (for [dx [-1 0 1] dy (if (zero? dx) [-1 1] [-1 0 1])]
                      [(+ x dx) (+ y dy)]))
        step (fn [cells]
               (set (for [[loc n] (frequencies (mapcat neighbors cells))
                          :when (or (= n 3) (and (= n 2) (cells loc)))]
                      loc)))
        serialize (fn [alive]
                    (mapv #(apply str %)
                          (partition width
                                     (for [y (range height) x (range width)
                                           :let [sym (if (alive [x y]) \# \space)]]
                                       sym))))]
    (-> cells step serialize)))
```


問題95. To Tree, or not to Tree ;; ツリー判定

シーケンスが二分木かどうかを判定する関数を作る。二分木では、それぞれのノードが値と左の子と右の子を持つ。

```
(= (__ '(:a (:b nil nil) nil))
   true)

(= (__ '(:a (:b nil nil)))
   false)

(= (__ [1 nil [2 [3 nil nil] [4 nil nil]]])
   true)

(= (__ [1 [2 nil nil] [3 nil nil] [4 nil nil]])
   false)

(= (__ [1 [2 [3 [4 nil nil] nil] nil] nil])
   true)

(= (__ [1 [2 [3 [4 false nil] nil] nil] nil])
   false)

(= (__ '(:a nil ()))
   false)
```

解答
```clojure
(fn tree? [coll]
  (cond
    (or (seq? coll) (vector? coll))
      (and (= 3 (count coll)) (tree? (nth coll 1)) (tree? (nth coll 2)))
    (nil? coll) true
    :else false))
```




問題96. Beauty is Symmetry ;; 対称性に美あり

二分木の左半分が右半分の鏡像のとき、対称であると定義しよう。与えられた二分木が対称かどうかを判定する関数を作る。前に作った二分木判定(ツリー判定)関数を利用する。

```
(= (__ '(:a (:b nil nil) (:b nil nil))) true)

(= (__ '(:a (:b nil nil) nil)) false)

(= (__ '(:a (:b nil nil) (:c nil nil))) false)

(= (__ [1 [2 nil [3 [4 [5 nil nil] [6 nil nil]] nil]]
          [2 [3 nil [4 [6 nil nil] [5 nil nil]]] nil]])
   true)

(= (__ [1 [2 nil [3 [4 [5 nil nil] [6 nil nil]] nil]]
          [2 [3 nil [4 [5 nil nil] [6 nil nil]]] nil]])
   false)

(= (__ [1 [2 nil [3 [4 [5 nil nil] [6 nil nil]] nil]]
          [2 [3 nil [4 [6 nil nil] nil]] nil]])
   false)
```

解答
```clojure
#(= ((fn mirror [[n l r :as tree]] (when tree [n (mirror r) (mirror l)])) %) %)
```


問題97. Pascal's Triangle ;; パスカルの三角形

パスカルの3角形とは1行目は1、次からの行は上の行の隣り合う番号の合計で、最初と最後は1を足す。

パスカルの三角形の行を返す関数を作る。


Pascal's triangle is a triangle of numbers computed using the following rules:
- The first row is 1.
- Each successive row is computed by adding together adjacent numbers in the row above, and adding a 1 to the beginning and end of the row.

Write a function which returns the nth row of Pascal's Triangle. 

```
(= (__ 1) [1])

(= (map __ (range 1 6))
   [     [1]
        [1 1]
       [1 2 1]
      [1 3 3 1]
     [1 4 6 4 1]])

(= (__ 11)
   [1 10 45 120 210 252 210 120 45 10 1])
```

解答
```clojure
(fn [n]
  (last (take n (iterate #(map +' `(0 ~@%) `(~@% 0)) [1]))))
```


問題98. Equivalence Classes ;; 同値関係クラス

ドメインDにおいて定義された関数fはDについて同値関係を作り出します。すなわちaは(f a)が(f b)に同値ならばbと同値である。fとDを引数にとり、fについてDの同値関係クラスを計算する関数を作る。

```
(= (__ #(* % %) #{-2 -1 0 1 2})
   #{#{0} #{1 -1} #{2 -2}})

(= (__ #(rem % 3) #{0 1 2 3 4 5 })
   #{#{0 3} #{1 4} #{2 5}})

(= (__ identity #{0 1 2 3 4})
   #{#{0} #{1} #{2} #{3} #{4}})

(= (__ (constantly true) #{0 1 2 3 4})
   #{#{0 1 2 3 4}})
```

解答
```clojure
(fn [f coll] (into #{} (map set (vals (group-by f coll)))))
```


問題99. Product Digits ;; 積の位ごとの数

2つの数を掛けてその結果を位ごとの数のシーケンスとして返す関数を作る。

```
(= (__ 1 1) [1])

(= (__ 99 9) [8 9 1])

(= (__ 999 99) [9 8 9 0 1])
```

解答
```clojure
(fn [a b] (mapv #(Integer/parseInt (str %)) (str (* a b))))
```


問題100. Least Common Multiple ;; 最小公倍数

複数の正の整数か分数を引数にとり、最小公倍数を計算する関数を作る。

```
(== (__ 2 3) 6)

(== (__ 5 3 7) 105)

(== (__ 1/3 2/5) 2)

(== (__ 3/4 1/6) 3/2)

(== (__ 7 5/7 2 3/5) 210)
```

解答
```clojure
(fn [& args]
  (let [gcd (fn [a b] (if (zero? b) a (recur b (mod a b))))]
    (/ (reduce * args) (reduce gcd args))))
```


問題101. Levenshtein Distance ;; レーベンシュタイン距離

2つのシーケンスxとyを与えられ、xとyの間のレーベンシュタイン距離を計算する。レーベンシュタイン距離とはxをyに変換するのに必要な最短の編集回数のことである。許される編集は以下の通り。

- 要素を1つ挿入する

- 要素を1つ削除する

- 要素を1つほかの要素で置換する

注意: テストケースのいくつかは効率の悪い解法ではタイムアウトします。

```
(= (__ "kitten" "sitting") 3)

(= (__ "closure" "clojure") (__ "clojure" "closure") 1)

(= (__ "xyx" "xyyyx") 2)

(= (__ "" "123456") 6)

(= (__ "Clojure" "Clojure") (__ "" "") (__ [] []) 0)

(= (__ [1 2 3 4] [0 2 3 4 5]) 2)

(= (__ '(:a :b :c :d) '(:a :d)) 2)

(= (__ "ttttattttctg" "tcaaccctaccat") 10)

(= (__ "gaattctaatctc" "caaacaaaaaattt") 9)
```

解答
```clojure
(memoize
  (fn lev [s1 s2]
    (cond
      (zero? (count s1)) (count s2)
      (zero? (count s2)) (count s1)
      (= (first s1) (first s2)) (lev (rest s1) (rest s2))
      :else (inc (min (lev (rest s1) s2)
                      (lev s1 (rest s2))
                      (lev (rest s1) (rest s2)))))))
```

問題102. intoCamelCase ;; キャメルケース変換

Javaではオブジェクトの名前はキャメルケースでfirldsLikeThisというような形になります。一方、clojureのハッシュマップ(連想配列)では:keys-like-thisというような書き方をします。さて、小文字でハイフンでつながれた文字列をキャメルケースの文字列に変換する関数を作りましょう。

```
(= (__ "something") "something")

(= (__ "multi-word-key") "multiWordKey")

(= (__ "leaveMeAlone") "leaveMeAlone")
```

解答
```clojure
#(let [words (clojure.string/split % #"-")] 
    (str (first words) 
         (apply str (map clojure.string/capitalize (drop 1 words)))))
```


問題103. Generating k-combinations ;; k個の組合せ(二項係数)

n個の要素からなるシーケンスsからすべてのk個の組合せを生成する。sの要素からなるすべての可能なk個の要素からなる集合の集合である。シーケンスのk個の組合せの数は二項係数と一致する。

```
(= (__ 1 #{4 5 6}) #{#{4} #{5} #{6}})

(= (__ 10 #{4 5 6}) #{})

(= (__ 2 #{0 1 2}) #{#{0 1} #{0 2} #{1 2}})

(= (__ 3 #{0 1 2 3 4}) #{#{0 1 2} #{0 1 3} #{0 1 4} #{0 2 3} #{0 2 4}
                         #{0 3 4} #{1 2 3} #{1 2 4} #{1 3 4} #{2 3 4}})

(= (__ 4 #{[1 2 3] :a "abc" "efg"}) #{#{[1 2 3] :a "abc" "efg"}})

(= (__ 2 #{[1 2 3] :a "abc" "efg"}) #{#{[1 2 3] :a} #{[1 2 3] "abc"} #{[1 2 3] "efg"}
                                    #{:a "abc"} #{:a "efg"} #{"abc" "efg"}})
```

解答
```clojure
(fn combinations [k s]
  (cond
    (zero? k) #{#{}}
    (empty? s) #{}
    :else (set (clojure.set/union
                 (map #(conj % (first s)) (combinations (dec k) (rest s)))
                 (combinations k (rest s))))))
```

問題104. Write Roman Numerals ;; ローマ数字を書く

ローマ数字を読む問題の逆であるが、ずっとやさしい。4000以下の数字を与えられ、対応するローマ数字を大文字で減算則で表す。

```
(= "I" (__ 1))

(= "XXX" (__ 30))

(= "IV" (__ 4))

(= "CXL" (__ 140))

(= "DCCCXXVII" (__ 827))

(= "MMMCMXCIX" (__ 3999))

(= "XLVIII" (__ 48))
```

解答
```clojure
(fn [n]
  (let [numerals {"M" 1000 "CM" 900 "D" 500 "CD" 400 "C" 100 "XC" 90 "L" 50 "XL" 40 "X" 10 "IX" 9 "V" 5 "IV" 4 "I" 1}
        dec->roman (fn [n]
                     (loop [n n [[c v] & nums :as all] (reverse (sort-by val numerals)) acc []]
                       (cond
                         (zero? n) (apply str acc)
                         (> v n) (recur n nums acc)
                         :else (recur (- n v) all (conj acc c)))))]
    (dec->roman n)))
```


問題105. Identify keys and values ;; キーと値の識別

キーワードと数字のシーケンスから、マップのキーがキーワードで、値は次のキーワードまでの数字のシーケンスとなるようなマップを返す関数を作る。

```
(= {} (__ []))

(= {:a [1]} (__ [:a 1]))

(= {:a [1], :b [2]} (__ [:a 1, :b 2]))

(= {:a [1 2 3], :b [], :c [4]} (__ [:a 1 2 3 :b :c 4]))
```

解答
```clojure
(fn kv [acc k [v & vs]]
  (cond (nil? v) acc
        (keyword? v) (kv (assoc acc v []) v vs)
        :e (kv (update-in acc [k] conj v) k vs))) {} *
```

問題106. Number Maze ;; 数の迷路

2つの数(ペア)を与えられる。それぞれの数はスタートとエンドである。以下のルールで3回のオペレーションでスタートからエンドへの経路を探す。

倍にする

半分にする(奇数は半分にはできない)

2を足す

"迷路"の最短の経路を見つける。最短経路はいくつもあるので、パスそのものではなく、最短経路を返す。

```
(= 1 (__ 1 1))  ; 1

(= 3 (__ 3 12)) ; 3 6 12

(= 3 (__ 12 3)) ; 12 6 3

(= 3 (__ 5 9))  ; 5 7 9

(= 9 (__ 9 2))  ; 9 18 20 10 12 6 8 4 2

(= 5 (__ 9 12)) ; 9 11 22 24 12
```

解答
```clojure
(fn find-path [s e]
  (loop [opts [s] depth 1]
    (if (some #{e} opts)
      depth
      (letfn [(solutions [n]
                (concat
                  [(* n 2) (+ n 2)]
                  (if (even? n) [(/ n 2)] [])))]
        (recur (mapcat solutions opts) (inc depth))))))
```

問題107. Simple closures ;; 簡単なクロージャー

静的(レキシカル)スコープと第一級関数はClojureのような関数型言語の基礎となる概念です。この2つを一緒にすると強力なレキシカルクロージャー(closure)ができあがります。これらを利用することにより変数の束縛をコントロールできるようになり、いま動いているコードが終了後も変数を保持することが可能になります。

抽象的にはわかりにくいので、簡単なクロージャー(closure)を作りましょう。正の整数nが与えられ、$x^n$を計算する関数(f x)を返す関数を作ります。nの値が保持されれて定義されたスコープの外で使われることを認識して下さい。

```
(= 256 ((__ 2) 16), ((__ 8) 2))

(= [1 8 27 64] (map (__ 3) [1 2 3 4]))

(= [1 2 4 8 16] (map #((__ %) 2) [0 1 2 3 4]))
```

解答
```clojure
(fn [n] (fn [b] (int (Math/pow b n))))
```

問題108. Lazy Searching ;; 遅延検索

複数のソートされたシーケンスの中からすべてのシーケンスのなかで一番小さい数を探す。シーケンスは無限の可能性もあるので、検索は遅延であること。

```
(= 3 (__ [3 4 5]))

(= 4 (__ [1 2 3 4 5 6 7] [0.5 3/2 4 19]))

(= 7 (__ (range) (range 0 100 7/6) [2 3 5 7 11 13]))

(= 64 (__ (map #(* % % %) (range)) ;; perfect cubes
          (filter #(zero? (bit-and % (dec %))) (range)) ;; powers of 2
          (iterate inc 20))) ;; at least as large as 20
```

解答
```clojure
(fn lazy-search [& colls]
  (if (= 1 (count colls))
    (first (first colls))
    (let [heads (map first colls) largest (apply max heads)]
      (if (apply = heads)
        largest
        (recur (map (fn [c] (drop-while #(< % largest) c)) colls))))))
```

問題110. Sequence of pronunciations ;; 発音のシーケンス

数の発音の遅延シーケンスを返す関数を作る。数の反復回数と数そのものがシーケンスの内容である。たとえば[1 1]は[2 1]と発音される。「2つの1」、これはさらに[1 2 1 1]と発音さる。すなわち「1つの2と1つの1」である。

作る関数は初期の数のシーケンスを与えられ、発音の無限の遅延シーケンスを返す。それぞれの要素はその直前の要素の発音である。

```
(= [[1 1] [2 1] [1 2 1 1]] (take 3 (__ [1])))

(= [3 1 2 4] (first (__ [1 1 1 4 4])))

(= [1 1 1 3 2 1 3 2 1 1] (nth (__ [1]) 6))

(= 338 (count (nth (__ [3 2]) 15)))
```

解答
```clojure
#(rest (iterate (fn [coll] (mapcat (juxt count first) (partition-by identity coll))) %))

```
問題111. Crossword Puzzle ;; クロスワードパズル

部分的に埋められたクロスワードパズル盤と文字列を受け取り、その文字列がボードに当てはめられるかを判定する関数を作る。

クロスワードパズル盤は部分的に埋められた行のコレクションから成る。空白のスペースはアンダースコア(_)、使わないスペースはハッシュ記号(#)、すでに埋められたスペースはその文字が書かれている。ホワイトスペースは読みやすくするためのものなので無視する。

単語が正しく収まるためのルールは以下の通りです。

空白(アンダースコア)を使う。

すでに埋められている文字と衝突しない。

使ってはいけないスペース(ハッシュ)は使えない。

単語の前後に空白(アンダースコア)や余分な文字があってはならない。使ってはいけないすスペースはあってよい。

文字は大文字小文字は関係ない。

単語は縦(上から下)にも横(左から右)に置ける。

```
(= true  (__ "the" ["_ # _ _ e"]))

(= false (__ "the" ["c _ _ _"
                    "d _ # e"
                    "r y _ _"]))

(= true  (__ "joy" ["c _ _ _"
                    "d _ # e"
                    "r y _ _"]))

(= false (__ "joy" ["c o n j"
                    "_ _ y _"
                    "r _ _ #"]))

(= true  (__ "clojure" ["_ _ _ # j o y"
                        "_ _ o _ _ _ _"
                        "_ _ f _ # _ _"]))
```

解答
```clojure
(fn [w p]
  (let [sm (map #(replace {\space "" \_ \.} %) p)
        co (apply map list sm)
        pl (mapcat #(take-nth 2 (partition-by #{\#} %)) (concat sm co))]
    (boolean (some #(re-matches (re-pattern (apply str %)) w) pl))))
```


問題112. Sequs Horribilis  ;; 恐ろしいシーケンス

整数とネストした整数のコレクションを引数にとり、要素を分析してネスト構造は維持し、最初からの要素の合計が与えられた整数以下であるようなシーケンスを返す関数を作る。

```
(=  (__ 10 [1 2 [3 [4 5] 6] 7])
   '(1 2 (3 (4))))

(=  (__ 30 [1 2 [3 [4 [5 [6 [7 8]] 9]] 10] 11])
   '(1 2 (3 (4 (5 (6 (7)))))))

(=  (__ 9 (range))
   '(0 1 2 3))

(=  (__ 1 [[[[[1]]]]])
   '(((((1))))))

(=  (__ 0 [1 2 [3 [4 5] 6] 7])
   '())

(=  (__ 0 [0 0 [0 [0]]])
   '(0 0 (0 (0))))

(=  (__ 1 [-10 [1 [2 3 [4 5 [6 7 [8]]]]]])
   '(-10 (1 (2 3 (4)))))
```

解答
```clojure
(fn [n s]
  (second
   ((fn sequs [n s]
      (loop [cnt 0 acc [] [x & xs] s]
        (cond
         (or (nil? x) (< n cnt)) [cnt acc]
         (coll? x) (let [[c r] (sequs (- n cnt) x)
                         coll (if (empty? r) acc (conj acc r))]
                     (recur (+ c cnt) coll xs))
         :else (recur (+ x cnt) (if (< n (+ cnt x)) acc (conj acc x)) xs)))) 
    n s)))
```

問題113. Making Data Dance ;;

複数の整数の引数をとる関数を作る。出力が文字列に変換される場合、コンマとスペースで区切らた小さい順にソートされた文字列を返す。出力がシーケンスに変換される場合、入力データのままの順序で重複のないユニークな要素のシーケンスを返す。

使わない関数: proxy

```
(= "1, 2, 3" (str (__ 2 1 3)))

(= '(2 1 3) (seq (__ 2 1 3)))

(= '(2 1 3) (seq (__ 2 1 3 3 1 2)))

(= '(1) (seq (apply __ (repeat 5 1))))

(= "1, 1, 1, 1, 1" (str (apply __ (repeat 5 1))))

(and (= nil (seq (__)))
     (=  "" (str (__))))
```

解答
```clojure
#(when %&
   (reify
     clojure.lang.ISeq
     (seq [_] (distinct %&))
     (toString [_] (apply str (interpose ", " (sort %&))))))
```

問題114. Global take-while ;; グローバルなtake-while

take-while関数はシーケンスをフィルターするのに大変有効ですが、限界があります。シーケンスの要素を1つずつしか調べられません。もしシーケンスのある状態を追いかけたいときににはどうしますか。

整数nと真偽判定関数pとシーケンスを引数にとり、pを満足させるn番目以下(n番目を含まない)遅延シーケンスを返す関数を作る。

```
(= [2 3 5 7 11 13]
   (__ 4 #(= 2 (mod % 3))
         [2 3 5 7 11 13 17 19 23]))

(= ["this" "is" "a" "sentence"]
   (__ 3 #(some #{\i} %)
         ["this" "is" "a" "sentence" "i" "wrote"]))

(= ["this" "is"]
   (__ 1 #{"a"}
         ["this" "is" "a" "sentence" "i" "wrote"]))
```

解答
```clojure
(fn gtw [n f [h & t]]
  (when-not (or (zero? n) (and (= n 1) (f h)))
    (cons h (gtw (if (f h) (dec n) n) f t))))
```

問題115. The Balance of N ;; 平衡数

平衡数とは各位の数の右半分の合計が左半分の合計と一致する数です。整数nについてバランスしているかどうかを判定する関数を作る。

```
(= true (__ 11))

(= true (__ 121))

(= false (__ 123))

(= true (__ 0))

(= false (__ 88099))

(= true (__ 89098))

(= true (__ 89089))

(= (take 20 (filter __ (range)))
   [0 1 2 3 4 5 6 7 8 9 11 22 33 44 55 66 77 88 99 101])
```

解答
```clojure
(fn [n]
  (let [digits (map #(Integer/parseInt (str %)) (str n))
        size (int (/ (count digits) 2))
        f (take size digits)
        l (take-last size digits)]
    (= (reduce + f) (reduce + l))))
```

問題116. Prime Sandwich ;; 平衡素数

平衡素数とは、素数であって1つ前の素数と1つ後の素数の算術平均に等しいものを言う。整数nについて平衡素数かどうかを判定する関数を作る。

```
(= false (__ 4))

(= true (__ 563))

(= 1103 (nth (filter __ (range)) 15))
```

解答
```clojure
(fn balanced-prime? [n]
  (let [factors (cons 2 (iterate (partial + 2) 3))
        prime? (fn [n] (not-any? #(zero? (mod n %))
                                 (take-while #(<= % (inc (Math/sqrt n))) factors)))
        prime-step (fn [n s] (first (drop-while (complement prime?) (rest (iterate (partial + s) n)))))]
    (and (> n 3)
         (prime? n)
         (= n (/ (+ (prime-step n 2) (prime-step n -2)) 2)))))
```

問題117. For Science! ;; 科学のために

マッドサイエンティストが迷路のネズミを記録する実験をしています。ランダムに生成された迷路について、ネズミがチーズ目標にうたどり着ける迷路かどうか判断する必要があります。迷路は行のコレクションで、それぞれの行はスペースがネズミがあるける部分、ハッシュ(#)が壁を表し、ネズミはあるけません。Mがネズミの最初の位置。Cが目的地(チーズ)を表します。ネズミは斜めには歩けず、上、下、左、右にいけます。迷路の端から逃げることはできません。迷路がネズミに解ける迷路かどうかを判断する関数を作る。

```
(= true  (__ ["M   C"]))

(= false (__ ["M # C"]))

(= true  (__ ["#######"
              "#     #"
              "#  #  #"
              "#M # C#"
              "#######"]))

(= false (__ ["########"
              "#M  #  #"
              "#   #  #"
              "# # #  #"
              "#   #  #"
              "#  #   #"
              "#  # # #"
              "#  #   #"
              "#  #  C#"
              "########"]))

(= false (__ ["M     "
              "      "
              "      "
              "      "
              "    ##"
              "    #C"]))

(= true  (__ ["C######"
              " #     "
              " #   # "
              " #   #M"
              "     # "]))

(= true  (__ ["C# # # #"
              "        "
              "# # # # "
              "        "
              " # # # #"
              "        "
              "# # # #M"]))
```

解答
```clojure
(fn cat-n-mouse [grid]
  (let [neighbors (fn [[x y]] [[(inc x) y] [(dec x) y] [x (inc y)] [x (dec y)]])
        parts (for [y (range (count grid))
                    x (range (count (nth grid y)))
                    :let [e (get-in grid [y x])]]
                {({\C :cat \M :mouse \# :wall \space :space} e) [x y]})
        game (apply merge-with conj {:wall [] :space []} parts)
        spaces (conj (set (:space game)) (:mouse game))]
    (loop [open [(:cat game)] visited #{}]
      (cond
        (empty? open) false
        (= (first open) (:mouse game)) true
        :else (let [visited (conj visited (first open))
                    neigh (filter spaces (neighbors (first open)))
                    neigh (remove visited neigh)
                    open (concat (rest open) (remove visited neigh))]
                (recur open visited))))))
```

問題118. Re-implement Map ;; マップ(連想配列)の実装

マップは関数型プログラミングの核となる要素の1つです。関数fとシーケンスを与えられて、(f x)の遅延シーケンスを返す関数を作る。

使わない関数: map map-indexed mapcat for

```
(= [3 4 5 6 7]
   (__ inc [2 3 4 5 6]))

(= (repeat 10 nil)
   (__ (fn [_] nil) (range 10)))

(= [1000000 1000001]
   (->> (__ inc (range))
        (drop (dec 1000000))
        (take 2)))
```

解答
```clojure
(fn map- [f coll]
  (lazy-seq
    (when-let [s (seq coll)]
      (cons (f (first s)) (map- f (rest s))))))
```


問題119. Win at Tic-Tac-Toe ;; マルバツゲームに勝つ

問題73と同様に、マルバツゲームの盤面を2次元のベクトルとして表現します。Xを:x、Oを:o、空を:eで表します。マルバツゲームの盤面を受け取り、勝つ指し手を全て集合として(空集合も可)返す関数を作る。

```
(= (__ :x [[:o :e :e]
           [:o :x :o]
           [:x :x :e]])
   #{[2 2] [0 1] [0 2]})

(= (__ :x [[:x :o :o]
           [:x :x :e]
           [:e :o :e]])
   #{[2 2] [1 2] [2 0]})

(= (__ :x [[:x :e :x]
           [:o :x :o]
           [:e :o :e]])
   #{[2 2] [0 1] [2 0]})

(= (__ :x [[:x :x :o]
           [:e :e :e]
           [:e :e :e]])
   #{})

(= (__ :o [[:x :x :o]
           [:o :e :o]
           [:x :e :e]])
   #{[2 2] [1 1]})
```

解答
```clojure
(fn ttt-win [p b]
  (let [win? (fn [board]
               (let [same? (fn [sec] (if (apply = sec) (first sec) nil))
                     rows (map same? board)
                     cols (map same? (apply map vector board))
                     diag1 (same? (map get board [0 1 2]))
                     diag2 (same? (map get board [2 1 0]))]
                 (some #{:x :o} (concat rows cols [diag1] [diag2]))))
        free (for [y (range 3)
                   x (range 3)
                   :when (= :e (get-in b [y x]))]
               [y x])]
    (set (filter #(= p (win? (assoc-in b % p))) free))))
```

問題120. Sum of square of digits ;; 位の数の自乗の合計

整数のコレクションを引数にとり、位の数の自乗の合計より少ない整数の数を返す関数を作る。たとえば10は1の自乗と0の合計より大きいからダメで、15は1と5の自乗の合計より小さいのでオーケーとする。

```
(= 8 (__ (range 10)))

(= 19 (__ (range 30)))

(= 50 (__ (range 100)))

(= 50 (__ (range 1000)))
```

解答
```clojure
(fn sum-square [coll]
  (let [digits (fn [n] (map #(- (int %) 48) (str n)))
        square #(* % %)
        sum-digits (fn [n] (reduce + (map square (digits n))))]
    (count (filter #(< % (sum-digits %)) coll))))
```

問題121. Universal Computation Engine ;; ユニバーサル計算エンジン

前置記法の数式を与えられて、数式を計算する関数を返す。数式は四則演算を用い、入れ子と変数の存在を許す。返された関数は変数と値のマップを含む1パラメーターを受け入れるものとする。

使わない関数: eval resolve

```
(= 2 ((__ '(/ a b))
      '{b 8 a 16}))

(= 8 ((__ '(+ a b 2))
      '{a 2 b 4}))

(= [6 0 -4]
     (map (__ '(* (+ 2 a)
                  (- 10 b)))
            '[{a 1 b 8}
              {b 5 a -2}
              {a 2 b 11}]))

(= 1 ((__ '(/ (+ x 2)
              (* 3 (+ y 1))))
      '{x 4 y 1}))
```


解答
```clojure
(fn [form]
  (fn [values]
    (let [env (merge {'+ + '- - '* * '/ /} values)]
      ((fn eval- [f]
         (if (seq? f)
           (let [[op & args] f]
             (apply (env op) (map eval- args)))
           (get env f f)))
         form))))
```

問題122. Read a binary number ;; 2進数の変換

文字列で表された2進数を数値に変換する。

```
(= 0     (__ "0"))

(= 7     (__ "111"))

(= 8     (__ "1000"))

(= 9     (__ "1001"))

(= 255   (__ "11111111"))

(= 1365  (__ "10101010101"))

(= 65535 (__ "1111111111111111"))
```

解答
```clojure
#(Integer/parseInt % 2)
```

問題124. Analyze Reversi ;; オセロ分析

オセロは通常8x8の盤面でプレーされます。この問題では、4x4の盤面が2次元のベクトルとして表現されます。ここでは黒、白、空白がそれぞれ`b, `w, `eで表されます。ゲーム盤と色を引数として、その色の次の可能な指し手をマップ(連想配列)の形で返す関数を作る。キーは可能な指し手の座標で、値はその指し手によってひっくり返される駒の座標とする。

盤面の座標はゼロベースで[0 1]は一番上の行の2番目の列である。

```
(= {[1 3] #{[1 2]}, [0 2] #{[1 2]}, [3 1] #{[2 1]}, [2 0] #{[2 1]}}
   (__ '[[e e e e]
         [e w b e]
         [e b w e]
         [e e e e]] 'w))

(= {[3 2] #{[2 2]}, [3 0] #{[2 1]}, [1 0] #{[1 1]}}
   (__ '[[e e e e]
         [e w b e]
         [w w w e]
         [e e e e]] 'b))

(= {[0 3] #{[1 2]}, [1 3] #{[1 2]}, [3 3] #{[2 2]}, [2 3] #{[2 2]}}
   (__ '[[e e e e]
         [e w b e]
         [w w b e]
         [e e b e]] 'w))

(= {[0 3] #{[2 1] [1 2]}, [1 3] #{[1 2]}, [2 3] #{[2 1] [2 2]}}
   (__ '[[e e w e]
         [b b w e]
         [b w w e]
         [b w w w]] 'b))
```

解答
```clojure
(fn reversi [board p]
  (let [o '{b w w b}
        d (for [y [-1 0 1] x (if (= 0 y) [-1 1] [-1 0 1])] [y x])
        b (into {} (for [y (range 4) x (range 4)] [[y x] (get-in board [y x])]))
        e (map key (filter #(= 'e (val %)) b))
        wk (fn [st off] (take-while b (rest (iterate #(map + % off) st))))
        vl (fn [pth] (let [s (apply str (map b pth)) r (re-pattern (str (o p) "+" p))]
                       (if (re-seq r s) (take-while #(not= p (b %)) pth))))

        mv (fn [st] (set (apply concat (keep vl (map #(wk st %) d)))))]
    (into {} (for [st e :let [mvs (mv st)] :when (not-empty mvs)] [st mvs]))))
```

問題125. Gus' Quinundrum ;; グスの難問(クワイン)

引数を取らず、その関数自身の完全なコピーである文字列を返す関数を作る。

行き詰まったら、ウィキペディアのQuine(computing)が参考になる。この問題はみかけよりだいぶむずかしいが、できれば自分で解く価値はある。

グスは4Clojureのドラゴンの名前です。

```
(= (str '__) (__))
```

解答
```clojure
;; The most common quine
(fn [x] (str x x)) '(fn [x] (str x x))
```

問題126. Through the Looking Class ;; クラスの国のアリス

次の式を満足させる値はなにか。

```
(let [x __]
  (and (= (class x) x) x))
```

解答
```clojure
Class
```


問題128. Recognize Playing Cards ;; トランプ認識

標準のアメリカのトランプは、4つのスート(スペード、ハート、ダイヤ、クラブ)と13のカードがあります。2が最低のランクでその後に10までの数字とジャック、クイーン、キング、エースの順です。

ハートの5とダイヤのクイーンをH5とかDQのようにスートとランクのペアで表現すると人間にはわかりやすいですが、プログラマーには不便です。カードゲームのためにはインプットを意味のある部分にパースする必要があります。

ランクの値を0(2)から12(エース)とし、たとえば"SJ"という文字列を{:suit :space, :rank 9*というようなマップ(連想配列)に変換する関数を作ります。10は"10"ではなく"T"という一文字にします。

```
(= {:suit :diamond :rank 10} (__ "DQ"))

(= {:suit :heart :rank 3} (__ "H5"))

(= {:suit :club :rank 12} (__ "CA"))

(= (range 13) (map (comp :rank __ str)
                   '[S2 S3 S4 S5 S6 S7
                     S8 S9 ST SJ SQ SK SA]))
```

解答
```clojure
(fn card [[s r]]
  (let [suits (zipmap (map str "SHCD") [:spade :heart :club :diamond])
        ranks (zipmap (map str (concat (range 2 10) "TJQKA")) (range 13))]
    {:suit (suits (str s)) :rank (ranks (str r))}))
```



問題131. Sum Some Set Subsets ;; サブセットのサム

複数の整数の集合を与えられ、それらのサブセットがサムをとると同じ値のものが含まれている場合にtrue、それ以外はfalseを返す関数を作る。

```
(= true  (__ #{-1 1 99}
             #{-2 2 888}
             #{-3 3 7777})) ; ex. all sets have a subset which sums to zero

(= false (__ #{1}
             #{2}
             #{3}
             #{4}))

(= true  (__ #{1}))

(= false (__ #{1 -3 51 9}
             #{0}
             #{9 2 81 33}))

(= true  (__ #{1 3 5}
             #{9 11 4}
             #{-3 12 3}
             #{-3 4 -2 10}))

(= false (__ #{-1 -2 -3 -4 -5 -6}
             #{1 2 3 4 5 6 7 8 9}))

(= true  (__ #{1 3 5 7}
             #{2 4 6 8}))

(= true  (__ #{-1 3 -5 7 -9 11 -13 15}
             #{1 -3 5 -7 9 -11 13 -15}
             #{1 -1 2 -2 4 -4 8 -8}))

(= true  (__ #{-10 9 -8 7 -6 5 -4 3 -2 1}
             #{10 -9 8 -7 6 -5 4 -3 2 -1}))
```

解答
```clojure
(fn sum-subsets [& s]
  (let [ps (fn powerset [s]
             (reduce (fn [acc e] 
                       (into acc (map conj acc (repeat e))))
                     #{#{}}
                     s))
        pss (map #(disj (ps %) #{}) s)
        sums (map (fn [p] (set (map #(apply + %) p))) pss)]
    (not (empty? (apply clojure.set/intersection sums)))))
```

問題132. Insert between two items ;; 要素の間に挿入

2個の引数をとる真偽判定関数と、値と、シーケンスを引数にとり、真偽判定関数を満足させる要素の間に値が挿入されたあらたなコレクションを返す関数を作る。

```
(= '(1 :less 6 :less 7 4 3) (__ < :less [1 6 7 4 3]))

(= '(2) (__ > :more [2]))

(= [0 1 :x 2 :x 3 :x 4]  (__ #(and (pos? %) (< % %2)) :x (range 5)))

(empty? (__ > :more ()))

(= [0 1 :same 1 2 3 :same 5 8 13 :same 21]
   (take 12 (->> [0 1]
                 (iterate (fn [[a b]] [b (+ a b)]))
                 (map first) ; fibonacci numbers
                 (__ (fn [a b] ; both even or both odd
                       (= (mod a 2) (mod b 2)))
                     :same))))
```

解答
```clojure
(fn [c v s]
  (mapcat (fn [[a b]] (if (and a b (c a b)) (list a v) (list a)))
          (partition-all 2 1 s)))
```

問題134. A nil key ;; nilキー

キーとマップを与えられ、マップにキーがあって、さらにその値がnilのときに限って真を返す関数を作る。

```
(true?  (__ :a {:a nil :b 2}))

(false? (__ :b {:a nil :b 2}))

(false? (__ :c {:a nil :b 2}))
```

解答
```clojure
(fn [k m]
  (if (contains? m k)
    (= (m k) nil)
    false))
```

問題135. Infix Calculator ;; 中置記法計算機

友達のジョーはLispの数学の前置記法が不満です。彼に中置記法で計算をする関数を作ってあげて下さい。数字と演算子が複数ならんだ式を受け取って、演算子の優先順序は考えずに左から右へ計算する単純な計算機を作ります。演算子は、+, -, *, /とします。

```
(= 7  (__ 2 + 5))

(= 42 (__ 38 + 48 - 2 / 2))

(= 8  (__ 10 / 2 - 1 * 2))

(= 72 (__ 20 / 2 + 2 + 4 + 8 - 6 - 10 * 9))
```

解答
```clojure
(fn calc [& exp]
  (reduce #(if (fn? %1) (%1 %2) (partial %2 %1)) identity exp))
```

問題137. Digits and bases ;; 数字とナンバーベース(基数)

非負の整数と基数を引数として、数のシーケンスを返す関数を作る。数は整数で表現され、例えば15は10進数では[1 5]、2進数では[1 1 1 1]、16進数では[15]と表すものとする。

```
(= [1 2 3 4 5 0 1] (__ 1234501 10))

(= [0] (__ 0 11))

(= [1 0 0 1] (__ 9 2))

(= [1 0] (let [n (rand-int 100000)](__ n n)))

(= [16 18 5 24 15 1] (__ Integer/MAX_VALUE 42))
```

解答
```clojure
(fn to-base [n b]
  (loop [n n num ()]
    (if (zero? n)
      (if (empty? num) '(0) num)
      (recur (int (/ n b)) (conj num (mod n b))))))
```

問題141. Tricky card games ;; カードゲームのトリック

ブリッジのようなトリックを取り合うゲームでは、それぞれのプレーヤーが順番にカードを1枚ずつ出します。最初のプレーヤーがトリックをリードして、全員が出し終わった時点でどれかのカードがトリックを勝ったことになります。ルールはゲームによって違いますが、一般的にはそのスートで一番強いカードを出した人が勝者です。時に、ゲームによってですが、あるスートがトランプ(切り札)とされていてトランプが切られるとそのトリックのリードにかかわらずトランプの最強のカードが勝者になります。

今回作る関数はどのカードがトリックの勝者か判定する関数です。トランプスートありのルールで関数は勝ったカードを返します。カードの表示はハッシュマップで:suitと:rankで表します。:rankは数字が大きいほど強い。

```
(let [notrump (__ nil)]
  (and (= {:suit :club :rank 9}  (notrump [{:suit :club :rank 4}
                                           {:suit :club :rank 9}]))
       (= {:suit :spade :rank 2} (notrump [{:suit :spade :rank 2}
                                           {:suit :club :rank 10}]))))

(= {:suit :club :rank 10} ((__ :club) [{:suit :spade :rank 2}
                                       {:suit :club :rank 10}]))
(= {:suit :heart :rank 8}
   ((__ :heart) [{:suit :heart :rank 6} {:suit :heart :rank 8}
                 {:suit :diamond :rank 10} {:suit :heart :rank 4}]))
```

解答
```clojure
(fn [trump]
  (fn [hand]
    (let [by-suit (group-by :suit hand)
          win-suit (or trump (:suit (first hand)))]
      (last (sort-by :rank (win-suit by-suit))))))
```

問題143. dot product ;; ドット積

ドット積を計算する関数を作る。ベクトルは同じ長さと考えてよい。

```
(= 0 (__ [0 1 0] [1 0 0]))

(= 3 (__ [1 1 1] [1 1 1]))

(= 32 (__ [1 2 3] [4 5 6]))

(= 256 (__ [2 5 6] [100 10 1])
```

解答
```clojure
#(reduce + (map * %1 %2))
```

問題144. Oscilrate ;; 振動反復

振動反復関数を作る。初期値と複数の関数を引数とする。関数を順番に適用していき、遅延評価する。終わりまで行ったら最初に戻る。

```
(= (take 3 (__ 3.14 int double)) [3.14 3 3.0])

(= (take 5 (__ 3 #(- % 3) #(+ 5 %))) [3 0 5 2 7])

(= (take 12 (__ 0 inc dec inc dec inc)) [0 1 0 1 0 1 2 1 2 1 2 3])
```

解答
```clojure
(fn [x & fs]
  (reductions #(%2 %1) x (cycle fs)))
```

問題145. For the win ;; 勝利の一撃

Clojureの`for`マクロはシーケンスをベースにシーケンスを作り出す驚くほど多様なメカニズムです。ちゃんと使うにはしばらくかかりますが、努力は無駄にはならず、明瞭で簡潔なシーケンス扱いができるようになります。ということを頭に置いて、以下の式を読み、なぜ同じ結果になるのかを考える。

```
(= __ (for [x (range 40)
            :when (= 1 (rem x 4))]
        x))

(= __ (for [x (iterate #(+ 4 %) 0)
            :let [z (inc x)]
            :while (< z 40)]
        z))

(= __ (for [[x y] (partition 2 (range 20))]
        (+ x y)))
```

解答
```clojure
(range 1 40 4)
```


問題146. Trees into tables ;; ツリーをテーブルに変換

Clojureの`for`マクロは複数のシーケンスをネストされた方法で"歩く"ことができるので、いろんなシーケンスを変換するのに向いている。もし、最終結果としてシーケンスでなくたとえばマップが欲しい場合も、シーケンスを作ってマップにすればいいだけなのでやはり`for`が最適な場合が多いだろう。

この問題では、目的はマップのマップをフラット化することである。最終マップのキーは元のマップの値にたどり着くための"パス"であるべきなので、たとえば{1 {2 3}}は結果として{[1 2] 3}になる。つまり(get-in original [k1 k2])は(get result [k1 k2])と同じになる。フラット化は1レベルでよくて、値がマップの場合はそのままでよい。

```
(= (__ '{a {p 1, q 2}
         b {m 3, n 4}})
   '{[a p] 1, [a q] 2
     [b m] 3, [b n] 4})

(= (__ '{[1] {a b c d}
         [2] {q r s t u v w x}})
   '{[[1] a] b, [[1] c] d,
     [[2] q] r, [[2] s] t,
     [[2] u] v, [[2] w] x})

(= (__ '{m {1 [a b c] 3 nil}})
   '{[m 1] [a b c], [m 3] nil})
```

解答
```clojure
#(into {} (for [[k v] % [k2 v2] v] [[k k2] v2]))
```


問題147. Pascal's Trapezoid ;; パスカルの台形

数字のベクトルについて、パスカルの三角形と同様なルールで次のベクトルをつくる。例としては[3 1 2]の次の行は[3 4 3 2]になる。このようなベクトルの無限シーケンスを返す関数を作る。
算術オーバーフローに注意する。+のような算術演算子を使うばあい結果が64ビット数に収まらなくなるとエラーになる。+'を使えば遅くなるが、オーバーフローは任意制度のbigintが使われる。

```
(= (second (__ [2 3 2])) [2 5 5 2])

(= (take 5 (__ [1])) [[1] [1 1] [1 2 1] [1 3 3 1] [1 4 6 4 1]])

(= (take 2 (__ [3 1 2])) [[3 1 2] [3 4 3 2]])

(= (take 100 (__ [2 4 2])) (rest (take 101 (__ [2 2]))))
```

解答
```clojure
(fn [row]
  (iterate #(map +' `(0 ~@%) `(~@% 0)) row))
```

問題148. The Big Divide ;; 大きな分割

3個の引数をとる。1つ目の引数n以下の自然数のうち、残りの引数aまたはbで割り切れる数の合計を返す関数を作る。aとbは互いに素とする。

テストケースのnは大きな数なので単純な解法では時間がかかりすぎタイムリミットをオーバーします。

```
(= 0 (__ 3 17 11))

(= 23 (__ 10 3 5))

(= 233168 (__ 1000 3 5))

(= "2333333316666668" (str (__ 100000000 3 5)))

(= "110389610389889610389610"
  (str (__ (* 10000 10000 10000) 7 11)))

(= "1277732511922987429116"
  (str (__ (* 10000 10000 10000) 757 809)))

(= "4530161696788274281"
  (str (__ (* 10000 10000 1000) 1597 3571)))
```

解答
```clojure
(fn [n a b]
  (let [f #(quot (dec n) %)
        g #(/ (*' % (f %) (inc (f %))) 2)]
    (- (+ (g a) (g b)) (g (* a b)))))
```

問題150. Palindromic Numbers ;; 回文数

回文数とは書かれたとき前からも後ろからも同じ数になるもので、例としては3, 99, 14341があります。整数nを与えられ、n以上のすべての回文数を遅延シーケンスで返す関数を作る。簡単な解決方法ではタイムリミットを簡単に超えてしまいます。

```
(= (take 26 (__ 0))
   [0 1 2 3 4 5 6 7 8 9 
    11 22 33 44 55 66 77 88 99 
    101 111 121 131 141 151 161])

(= (take 16 (__ 162))
   [171 181 191 202 
    212 222 232 242 
    252 262 272 282 
    292 303 313 323])

(= (take 6 (__ 1234550000))
   [1234554321 1234664321 1234774321 
    1234884321 1234994321 1235005321])

(= (first (__ (* 111111111 111111111)))
   (* 111111111 111111111))

(= (set (take 199 (__ 0)))
   (set (map #(first (__ %)) (range 0 10000))))

(= true
   (apply < (take 6666 (__ 9999999))))

(= (nth (__ 0) 10101)
   9102019)
```

解答
```clojure
(let [nextp (fn [n]
              (let [p #(Long. %)
                    s (str n)
                    l (count s)
                    m (subs s 0 (Math/ceil (/ l 2)))
                    h (str (inc (p m)))
                    f (fn [s] (p (str s (subs (clojure.string/reverse s) (if (even? l) 0 1)))))
                    [a b] (map f [m h])]
                (if (>= a n) a b)))]
  #(iterate (comp nextp inc) (nextp %)))
```

問題153. Pairwise Disjoint Sets ;; 互いに素な集合

集合の集合を与えられて、どの集合どうしも互いに素であるかどうかを判定する関数を作る。互いに素はpairwise disjointもしくはmutually disjointと言う。テストケースはトリッキーなものもあるので注意すること。


```
(= (__ #{#{\U} #{\s} #{\e \R \E} #{\P \L} #{\.}})
   true)

(= (__ #{#{:a :b :c :d :e}
         #{:a :b :c :d}
         #{:a :b :c}
         #{:a :b}
         #{:a}})
   false)

(= (__ #{#{[1 2 3] [4 5]}
         #{[1 2] [3 4 5]}
         #{[1] [2] 3 4 5}
         #{1 2 [3 4] [5]}})
   true)

(= (__ #{#{'a 'b}
         #{'c 'd 'e}
         #{'f 'g 'h 'i}
         #{''a ''c ''f}})
   true)

(= (__ #{#{'(:x :y :z) '(:x :y) '(:z) '()}
         #{#{:x :y :z} #{:x :y} #{:z} #{}}
         #{'[:x :y :z] [:x :y] [:z] [] {}}})
   false)

(= (__ #{#{(= "true") false}
         #{:yes :no}
         #{(class 1) 0}
         #{(symbol "true") 'false}
         #{(keyword "yes") ::no}
         #{(class '1) (int \0)}})
   false)

(= (__ #{#{distinct?}
         #{#(-> %) #(-> %)}
         #{#(-> %) #(-> %) #(-> %)}
         #{#(-> %) #(-> %) #(-> %)}})
   true)

(= (__ #{#{(#(-> *)) + (quote mapcat) #_ nil}
         #{'+ '* mapcat (comment mapcat)}
         #{(do) set contains? nil?}
         #{, , , #_, , empty?}})
   false)

(= (__ #{#{(#(-> *)) + (quote mapcat) #_ nil}
         #{'+ '* mapcat (comment mapcat)}
         #{(do) set contains? nil?}
         #{, , , #_, , empty?}})
   false)
```

解答
```clojure
(fn [sets]
  (= (reduce + (map count sets))
     (count (reduce clojure.set/union sets))))
```


問題156. Map Defaults ;; マップ(連想配列)のデフォルト値

マップから値を取り出すとき、もしキーが見つからなかった場合のデフォルト値を指定することができます。

```
(= 2 (:foo {:bar 0, :baz 1} 2))
```

もし、マップ自体にデフォルト値を設定したい場合の関数を作る。引数はデフォルト値とキーのシーケンスとします。

```
(= (__ 0 [:a :b :c]) {:a 0 :b 0 :c 0})

(= (__ "x" [1 2 3]) {1 "x" 2 "x" 3 "x"})

(= (__ [:a :b] [:foo :bar]) {:foo [:a :b] :bar [:a :b]})
```

解答
```clojure
#(apply hash-map (interleave %2 (repeat %1)))
```


問題157. Indexing Sequences ;; シーケンスにインデクスをつける

シーケンスをシーケンスの元の要素とインデクスのペアのシーケンスにする。

```
(= (__ [:a :b :c]) [[:a 0] [:b 1] [:c 2]])

(= (__ [0 1 3]) '((0 0) (1 1) (3 2)))

(= (__ [[:foo] {:bar :baz}]) [[[:foo] 0] [{:bar :baz} 1]])
```

解答
```clojure
#(map vector % (range))
```


問題158. Decurry ;; 反カレー化

カレー化された未知のアリティnの関数を受け取り、引数nの同等の関数を返す関数を作る。カレー化については英語のCurryingのWikipediaを参照すること。

```
(= 10 ((__ (fn [a]
             (fn [b]
               (fn [c]
                 (fn [d]
                   (+ a b c d))))))
       1 2 3 4))

(= 24 ((__ (fn [a]
             (fn [b]
               (fn [c]
                 (fn [d]
                   (* a b c d))))))
       1 2 3 4))

(= 25 ((__ (fn [a]
             (fn [b]
               (* a b))))
       5 5))
```

解答
```clojure
(fn [f] (fn [& args] (reduce #(apply %1 (vector %2)) f args)))
```


問題161. Subset and Superset ;; サブセットとスーパーセット

もし集合Aが集合Bに属するのなら、集合Aは集合Bのサブセットである。集合Bは集合Aのスーパーセットである。AとBが同じでもかまわない。

```
(clojure.set/superset? __ #{2})

(clojure.set/subset? #{1} __)

(clojure.set/superset? __ #{1 2})

(clojure.set/subset? #{1 2} __)
```

解答
```clojure
#{1 2}
```


問題162. Logical falsity and truth ;; 論理真偽

clojureではnilとfalseだげが条件テストにおいて論理偽になります。それ以外はすべて真です。

```
(= __ (if-not false 1 0))

(= __ (if-not nil 1 0))

(= __ (if true 1 0))

(= __ (if [] 1 0))

(= __ (if [0] 1 0))

(= __ (if 0 1 0))

(= __ (if 1 1 0))
```



解答
```clojure
1
```


問題164. Language of a DFA ;; 決定性有限オートマトン言語

決定性有限オートマトン(deterministic finite: DFA)は抽象的なマシンで正規言語regular languageを認識する。通常DFAは5つのタプルで定義されるが、ここでは5つのキーのマップを用いる。

:statesはDFAの状態の集合である。

:alphabetはDFAに認識されるシンボルの集合である。

:startはDFAの開始状態である。

:acceptsはDFAの開始状態である。

:transitionsはDFAの繊維関数であり、mapping :states ⨯ :alphabet を:states にマップする。

上記のDFA定義を受け取り、DFAで認識できる言語のすべてのシーケンスを返す関数を作る。

注意: DFAそのものは有限で有限の文字列しか認識できないが、それでも有限の長さの文字列の無限の集合を認識できる。スタックスペースは有限なので、結果を出さない無限ループに陥らないことを確認すること。

```
(= #{"a" "ab" "abc"}
   (set (__ '{:states #{q0 q1 q2 q3}
              :alphabet #{a b c}
              :start q0
              :accepts #{q1 q2 q3}
              :transitions {q0 {a q1}
                            q1 {b q2}
                            q2 {c q3}}})))

(= #{"hi" "hey" "hello"}
   (set (__ '{:states #{q0 q1 q2 q3 q4 q5 q6 q7}
              :alphabet #{e h i l o y}
              :start q0
              :accepts #{q2 q4 q7}
              :transitions {q0 {h q1}
                            q1 {i q2, e q3}
                            q3 {l q5, y q4}
                            q5 {l q6}
                            q6 {o q7}}})))

(= (set (let [ss "vwxyz"] (for [i ss, j ss, k ss, l ss] (str i j k l))))
   (set (__ '{:states #{q0 q1 q2 q3 q4}
              :alphabet #{v w x y z}
              :start q0
              :accepts #{q4}
              :transitions {q0 {v q1, w q1, x q1, y q1, z q1}
                            q1 {v q2, w q2, x q2, y q2, z q2}
                            q2 {v q3, w q3, x q3, y q3, z q3}
                            q3 {v q4, w q4, x q4, y q4, z q4}}})))

(let [res (take 2000 (__ '{:states #{q0 q1}
                           :alphabet #{0 1}
                           :start q0
                           :accepts #{q0}
                           :transitions {q0 {0 q0, 1 q1}
                                         q1 {0 q1, 1 q0}}}))]
  (and (every? (partial re-matches #"0*(?:10*10*)*") res)
       (= res (distinct res))))

(let [res (take 2000 (__ '{:states #{q0 q1}
                           :alphabet #{n m}
                           :start q0
                           :accepts #{q1}
                           :transitions {q0 {n q0, m q1}}}))]
  (and (every? (partial re-matches #"n*m") res)
       (= res (distinct res))))

(let [res (take 2000 (__ '{:states #{q0 q1 q2 q3 q4 q5 q6 q7 q8 q9}
                           :alphabet #{i l o m p t}
                           :start q0
                           :accepts #{q5 q8}
                           :transitions {q0 {l q1}
                                         q1 {i q2, o q6}
                                         q2 {m q3}
                                         q3 {i q4}
                                         q4 {t q5}
                                         q6 {o q7}
                                         q7 {p q8}
                                         q8 {l q9}
                                         q9 {o q6}}}))]
  (and (every? (partial re-matches #"limit|(?:loop)+") res)
       (= res (distinct res))))

```

解答
```clojure
(fn run* [dfa]
  (let [run1 (fn [[s acc]] (for [[c n] ((:transitions dfa) s)] [n (str acc c)]))
        accepted (fn [[s acc]] (when ((:accepts dfa) s) acc))]
    (mapcat #(keep accepted %) (take-while not-empty (iterate #(mapcat run1 %) (run1 [(:start dfa) ""]))))))

```
問題166. Comparisons ;; 比較演算子

順序付けできるデータについて=と≠以外の演算子を1つだけ使って基本的な比較(<, ≤, =, ≠, ≥, >)を行うことができます。小なり演算子(<)と2つの比較したいデータを引数として2つのデータの関係を示すキーワードを返す関数を作る。xとyの関係を表すキーワードは次のようなものである。

```
x = y => :eq
x > y => :gt
x < y => :lt
```
```
(= :gt (__ < 5 1))

(= :eq (__ (fn [x y] (< (count x) (count y))) "pear" "plum"))

(= :lt (__ (fn [x y] (< (mod x 5) (mod y 5))) 21 3))

(= :gt (__ > 0 2))
```

解答
```clojure
(fn [f a b]
  (cond
    (f a b) :lt
    (f b a) :gt
    :else :eq))
```


問題168. Infinite Matrix ;; 無限マトリックス

以下では、m, n, s, t は非負整数を表し、関数fは2個の非負整数を引数に取ります。

数学で無限マトリックスは無限の行と無限の列を表すのに省略記号を使います。Clojureでは行を表す遅延シーケンスの遅延シーケンスで表します。

引数が1と3と5の関数を作ります。

引数が関数fだけのとき、関数はi行j列の要素がf(i, j)であるような無限マトリックスAを返します。

引数がf, m, nのとき、関数はAから最初のm行とn列を除いた無限マトリックスBを返します。

引数がf, m, n, s, tのとき、関数は関数Bから最初のs行とt列を取ってきたsかけるtのマトリックスを返します。

使わない関数: for range iterate repeat cycle drop

```
(= (take 5 (map #(take 6 %) (__ str)))
   [["00" "01" "02" "03" "04" "05"]
    ["10" "11" "12" "13" "14" "15"]
    ["20" "21" "22" "23" "24" "25"]
    ["30" "31" "32" "33" "34" "35"]
    ["40" "41" "42" "43" "44" "45"]])

(= (take 6 (map #(take 5 %) (__ str 3 2)))
   [["32" "33" "34" "35" "36"]
    ["42" "43" "44" "45" "46"]
    ["52" "53" "54" "55" "56"]
    ["62" "63" "64" "65" "66"]
    ["72" "73" "74" "75" "76"]
    ["82" "83" "84" "85" "86"]])

(= (__ * 3 5 5 7)
   [[15 18 21 24 27 30 33]
    [20 24 28 32 36 40 44]
    [25 30 35 40 45 50 55]
    [30 36 42 48 54 60 66]
    [35 42 49 56 63 70 77]])

(= (__ #(/ % (inc %2)) 1 0 6 4)
   [[1/1 1/2 1/3 1/4]
    [2/1 2/2 2/3 1/2]
    [3/1 3/2 3/3 3/4]
    [4/1 4/2 4/3 4/4]
    [5/1 5/2 5/3 5/4]
    [6/1 6/2 6/3 6/4]])

(= (class (__ (juxt bit-or bit-xor)))
   (class (__ (juxt quot mod) 13 21))
   (class (lazy-seq)))

(= (class (nth (__ (constantly 10946)) 34))
   (class (nth (__ (constantly 0) 5 8) 55))
   (class (lazy-seq)))

(= (let [m 377 n 610 w 987
         check (fn [f s] (every? true? (map-indexed f s)))
         row (take w (nth (__ vector) m))
         column (take w (map first (__ vector m n)))
         diagonal (map-indexed #(nth %2 %) (__ vector m n w w))]
     (and (check #(= %2 [m %]) row)
          (check #(= %2 [(+ m %) n]) column)
          (check #(= %2 [(+ m %) (+ n %)]) diagonal)))
   true)
```




解答
```clojure
(fn imat
  ([f] (imat f 0 0))
  ([f r c] (imat f r c -1 -1))
  ([f r c h w]
   (letfn [(row [st wd]
             (lazy-seq
               (when-not (zero? wd)
                 (cons st (row (inc st) (dec wd))))))]
     (map #(map (partial f %) (row c w)) (row r h)))))
```

問題171. Intervals ;; インターバル

整数のシーケンスを受け取り、インターバルのシーケンスを返す関数を作る。インターバルは2つの整数、スタートとエンドからなるベクトルで、元のすべての整数がその中に入るようなもの。

```
(= (__ [1 2 3]) [[1 3]])

(= (__ [10 9 8 1 2 3]) [[1 3] [8 10]])

(= (__ [1 1 1 1 1 1 1]) [[1 1]])

(= (__ []) [])

(= (__ [19 4 17 1 3 10 2 13 13 2 16 4 2 15 13 9 6 14 2 11])
       [[1 4] [6 6] [9 11] [13 17] [19 19]])
```

解答
```clojure
(fn intervals [s]
  (reduce (fn [memo e]
            (let [memo (if (empty? memo) [[e e]] memo)
                  [l h] (nth memo (dec (count memo)))]
              (cond
               (= e h) memo
               (= e (inc h)) (assoc-in memo [(dec (count memo)) 1] e)
               :else (conj memo [e e]))))
          [] (distinct (sort s))))
```

問題173. Intro to Destructuring 2 ;; シーケンス分解入門2

シーケンス分解はシーケンスのそれぞれを(let [bindings* ] exprs*)という方法でシンボルに束縛することができます。下記のアンダーラインを埋めてすべてが3になるようにして下さい。

```
(= 3
  (let [[__] [+ (range 3)]] (apply __))
  (let [[[__] b] [[+ 1] 2]] (__ b))
  (let [[__] [inc 2]] (__)))
```

解答
```clojure
f vs
```

問題177. Balancing Brackets ;; カッコのバランス

プログラムコードをパースするとき、カッコがすべて対応しているかどうかのサニティ・チェックを行うのはいい考えです。文字列を読み込み、カギ括弧[ ]、丸括弧( )、波括弧{ }がすべてペアになっていて、正しくネストされていることを確認し、真偽を返す関数を作る。

```
(__ "This string has no brackets.")

(__ "class Test {
      public static void main(String[] args) {
        System.out.println(\"Hello world.\");
      }
    }")

(not (__ "(start, end]"))

(not (__ "())"))

(not (__ "[ { ] } "))

(__ "([]([(()){()}(()(()))(([[]]({}()))())]((((()()))))))")

(not (__ "([]([(()){()}(()(()))(([[]]({}([)))())]((((()()))))))"))

(not (__ "["))
```

解答
```clojure
(fn balanced? [s]
  (let [p {\( \) \[ \] \{ \}}
        a (set "()[]{}")]
    (empty?
      (reduce (fn [[t & b :as stack] s]
                (cond (= (p t) s) b
                      (a s) (conj stack s)
                      :else stack))
              () s))))
```


問題178. Best Hand ;; ポーカーの手役

トランプの認識(Recognize Playing Cards)の方式に従って、5枚のカードでできるベストな手役を決める。ポーカーの手役のランキングは参考のために以下に記す。

ストレートフラッシュ: 全てのカードが同じスートでシーケンスである。

フォーカード: カードのうち4枚が同じランクである。

フルハウス: 3枚の同じランクのカードと、あと2枚の違うランクの同じランク。

フラッシュ: すべてのカードが同じスート。

ストレート: すべてのカードがシーケンス(エースは高位か低位を選べる)。

スリーカード: 3枚の同じランクのカード。

ツーペア: 2枚のカードが同じランクのペアが2つ。

ペア: 2枚カードが同じランク。

ハイ: 上記のどの条件も当てはまらない場合。

```
(= :high-card (__ ["HA" "D2" "H3" "C9" "DJ"]))

(= :pair (__ ["HA" "HQ" "SJ" "DA" "HT"]))

(= :two-pair (__ ["HA" "DA" "HQ" "SQ" "HT"]))

(= :three-of-a-kind (__ ["HA" "DA" "CA" "HJ" "HT"]))

(= :straight (__ ["HA" "DK" "HQ" "HJ" "HT"]))

(= :straight (__ ["HA" "H2" "S3" "D4" "C5"]))

(= :flush (__ ["HA" "HK" "H2" "H4" "HT"]))

(= :full-house (__ ["HA" "DA" "CA" "HJ" "DJ"]))

(= :four-of-a-kind (__ ["HA" "DA" "CA" "SA" "DJ"]))

(= :straight-flush (__ ["HA" "HK" "HQ" "HJ" "HT"]))
```

解答
```clojure
(fn [h]
  (let [[s r] (apply map list h)
        rs (set (map frequencies (partition 5 1 "A23456789TJQKA")))
        s? (rs (frequencies r))
        f? (apply = s)
        g (frequencies (vals (frequencies r)))]
    (cond
     (and s? f?) :straight-flush
     (g 4) :four-of-a-kind
     (and (g 2) (g 3)) :full-house
     f? :flush
     s? :straight
     (g 3) :three-of-a-kind
     (= 2 (g 2)) :two-pair
     (g 2) :pair
     :else :high-card)))
```

問題195 Parentheses... Again;; 括弧再び

リスプ系の言語ではバランスしたカッコが特徴的です。よいことにこの区切り以外はLispはほとんど文法がありません。通常の役に立つプログラミング言語という意味では文法と呼ぶに値しない。

正しく使われたカッコの組合せを見つけるという課題はもしNペアと限定されるなら難しくはありません。例えば2ペアとすると可能性のある組合せは"()()"と"(())"です。その他の長さNの組合せは不正です。なぜだかわかりますか？

長さ2n(nペアのカッコ)の正しいカッコの組合せを生成する関数を作ります。この問題では'('と')'だけを扱いますが、'{}'でも'[]'でも同じです。

数におもしろいパターンがありますよ！

```
(= [#{""} #{"()"} #{"()()" "(())"}] (map (fn [n] (__ n)) [0 1 2]))

(= #{"((()))" "()()()" "()(())" "(())()" "(()())"} (__ 3))

(= 16796 (count (__ 10)))

(= (nth (sort (filter #(.contains ^String % "(()()()())") (__ 9))) 6) "(((()()()())(())))")

(= (nth (sort (__ 12)) 5000) "(((((()()()()()))))(()))")

```

解答
```clojure
(fn gen-parens
  ([n] (if (= 0 n) #{""} (set (gen-parens n 0))))
  ([n open]
   (if (= 0 n)
     (vector (apply str (repeat open ")")))
     (if (= 0 open)
       (map #(str "(" %) (gen-parens (dec n) 1))
       (concat
         (map #(str ")" %) (gen-parens n (dec open)))
         (map #(str "(" %) (gen-parens (dec n) (inc open))))))))
```

問題130 Tree reparenting;;

ツリーのノードはその子とその親に繋がっている。ツリーのノードを引っ張っルートポジションに持っていき、その他の連結はまったくかわらないと想像して見て下さい。

```
       a
   b---+---i
 c-+-f   j-+-m
d+e g+h k+l n+o
=>
   c
   +
d--e--b
      |
   f--+--a
  g+h    i
       j-+-m
      k+l n+o
```

もう二分木ではなくなっていることに注意して下さい。Cは3個の連結を持っています。2つの子と1つの親です。ノードをベクトルとして表し、最小でも自分自身の名前を表す要素が1つあります。その後の要素は子を表します。子は順序付けられているので返されるツリーは子の順序を維持することと古い親のノードがあれば右側にアペンドされることは重要な点です。関数は2つの引数が与えられます。1つは新たにルートになるノード、で2つめは変換されるツリーです。

```
(= '(n)
   (__ 'n '(n)))

(= '(n)
   (__ 'n '(n)))

(= '(a (t (e)))
   (__ 'a '(t (e) (a))))

(= '(e (t (a)))
   (__ 'e '(a (t (e)))))

(= '(a (b (c)))
   (__ 'a '(c (b (a)))))

(= '(d
      (b
        (c)
        (e)
        (a
          (f
            (g)
            (h)))))
  (__ 'd '(a
            (b
              (c)
              (d)
              (e))
            (f
              (g)
              (h)))))

(= '(c
      (d)
      (e)
      (b
        (f
          (g)
          (h))
        (a
          (i
          (j
            (k)
            (l))
          (m
            (n)
            (o))))))
   (__ 'c '(a
             (b
               (c
                 (d)
                 (e))
               (f
                 (g)
                 (h)))
             (i
               (j
                 (k)
                 (l))
               (m
                 (n)
                 (o))))))

(= '(c
      (d)
      (e)
      (b
        (f
          (g)
          (h))
        (a
          (i
          (j
            (k)
            (l))
          (m
            (n)
            (o))))))
   (__ 'c '(a
             (b
               (c
                 (d)
                 (e))
               (f
                 (g)
                 (h)))
             (i
               (j
                 (k)
                 (l))
               (m
                 (n)
                 (o))))))
```

解答
```clojure
(fn [root tree]
  (letfn [(find-parent [r t]
            (if (> (count t) 1)
              (let [sub-tree (filter #(some #{r} %) (next t))]
                (if (seq sub-tree)
                  [(first t)]
                  (apply concat (map #(find-parent r %) (next t)))))))
          (find-children [r t]
            (if (= r (first t))
              (map first (next t))
              (apply concat (map #(find-children r %) (next t)))))
          (step [r t s]
            (let [filtered-children (filter #(nil? (s %)) (concat (find-children r t) (find-parent r t)))]
              (cons r (map #(step % t (into s filtered-children)) filtered-children))))]
    (step root tree #{root})))
```

問題140 Veitch, Please! ;; カルノー図またはベイチ図

集合の集合の形のブール代数関数を受け取る関数を作る。内側の集合は関数を満足させるブール変数のシンボルに対応する。内側の集合は互いに素ではなく、集合そのものは互いに素であり、canonical mintermsとも呼ばれる)。大文字のシンボルは真を表し、小文字のシンボルはインプットの否定を表す。作る関数は入力と論理的に同等のミニマルな関数を返す。

先に進む前に、WikipediaのK-Mapsを読むといいかもしれない。

```
(= (__ #{#{'a 'B 'C 'd}
         #{'A 'b 'c 'd}
         #{'A 'b 'c 'D}
         #{'A 'b 'C 'd}
         #{'A 'b 'C 'D}
         #{'A 'B 'c 'd}
         #{'A 'B 'c 'D}
         #{'A 'B 'C 'd}})
   #{#{'A 'c}
     #{'A 'b}
     #{'B 'C 'd}})

(= (__ #{#{'A 'B 'C 'D}
         #{'A 'B 'C 'd}})
   #{#{'A 'B 'C}})

(= (__ #{#{'a 'b 'c 'd}
         #{'a 'B 'c 'd}
         #{'a 'b 'c 'D}
         #{'a 'B 'c 'D}
         #{'A 'B 'C 'd}
         #{'A 'B 'C 'D}
         #{'A 'b 'C 'd}
         #{'A 'b 'C 'D}})
   #{#{'a 'c}
     #{'A 'C}})

(= (__ #{#{'a 'b 'c}
         #{'a 'B 'c}
         #{'a 'b 'C}
         #{'a 'B 'C}})
   #{#{'a}})

(= (__ #{#{'a 'B 'c 'd}
         #{'A 'B 'c 'D}
         #{'A 'b 'C 'D}
         #{'a 'b 'c 'D}
         #{'a 'B 'C 'D}
         #{'A 'B 'C 'd}})
   #{#{'a 'B 'c 'd}
     #{'A 'B 'c 'D}
     #{'A 'b 'C 'D}
     #{'a 'b 'c 'D}
     #{'a 'B 'C 'D}
     #{'A 'B 'C 'd}})

(= (__ #{#{'a 'b 'c 'd}
         #{'a 'B 'c 'd}
         #{'A 'B 'c 'd}
         #{'a 'b 'c 'D}
         #{'a 'B 'c 'D}
         #{'A 'B 'c 'D}})
   #{#{'a 'c}
     #{'B 'c}})

(= (__ #{#{'a 'B 'c 'd}
         #{'A 'B 'c 'd}
         #{'a 'b 'c 'D}
         #{'a 'b 'C 'D}
         #{'A 'b 'c 'D}
         #{'A 'b 'C 'D}
         #{'a 'B 'C 'd}
         #{'A 'B 'C 'd}})
   #{#{'B 'd}
     #{'b 'D}})

(= (__ #{#{'a 'b 'c 'd}
         #{'A 'b 'c 'd}
         #{'a 'B 'c 'D}
         #{'A 'B 'c 'D}
         #{'a 'B 'C 'D}
         #{'A 'B 'C 'D}
         #{'a 'b 'C 'd}
         #{'A 'b 'C 'd}})
   #{#{'B 'D}
     #{'b 'd}})
```

解答
```clojure
(fn veitch-pls [table]
  (let [size (count (first table))
        pow-2 (fn [n] (first (drop n (iterate #(* % 2) 1))))
        to-letter-codes (fn [minterm]
                          (for [i (range 0 size)
                                :when (not= ((vec minterm) i) 'x)]
                            (get-in [['a 'A] ['b 'B] ['c 'C] ['d 'D]] [i ((vec minterm) i)])))
        values (into {}
                (map (fn [l n] (vector l n))
                    '(A B C D)
                    (->>
                      (iterate #(* % 2) 1)
                      (take size)
                      reverse)))
        val    (fn [f] (reduce + (keep values f)))
        masks  (fn masks [n k] ; n-long masks where k bits are set
                  (cond
                    (zero? k) [(repeat n 'x)]
                    (= 1 n) [[0] [1]]
                    :else
                      (let [m' (masks (dec n) (dec k))]
                        (concat
                          (map #(cons 0 %) m')
                          (map #(cons 1 %) m')
                          (when (> n k)
                            (map #(cons 'x %) (masks (dec n) k)))))))
        k-comb (fn k-comb [k S]
                  (if
                    (zero? k) #{#{}}
                    (set
                      (mapcat
                        (fn [e]
                          (map
                            (fn [t] (conj t e))
                            (k-comb (dec k) (disj S e))))
                        S))))
        to-bindigits (fn bd [x n]
                      (let [pow2 (first (drop (dec n) (iterate #(* % 2) 1))) ; why (dec n)?
                            d (quot x pow2)]
                          (cond
                            (zero? n) '()
                            (= d 0) (cons 0 (bd x (dec n)))
                            :else   (cons 1 (bd (- x pow2) (dec n))))))
        ones  (map #(to-bindigits % size) (map val table))
        matches? (fn [t mask]
                   (every? identity
                           (map (fn [bit mask-bit] (or (= 'x mask-bit) (= mask-bit bit)))
                                t mask)))
        covers-less? (fn [m1 m2]
                       (and
                         (< (->> m1 (filter #(= % 'x)) count)
                            (->> m2 (filter #(= % 'x)) count))
                         (reduce (fn [res [b1 b2]]
                                   (and res
                                     (if (not= 'x b2) (= b1 b2) true)))
                                 true
                                 (partition 2 (interleave m1 m2)))))
        eligible-masks (for [k (range 1 (inc size))
                             mask (masks size k)
                             :let [matching-ones (filter #(matches? % mask) ones)]
                             :when (= (count matching-ones) (pow-2 (- size k)))]
                             [k mask (set matching-ones)])
        final-masks (reduce
                         (fn [ms [k m matching]]
                           (let [k-masks (get ms k {})]
                             (assoc ms k
                               (assoc k-masks m (set matching)))))
                          {}
                          (remove (fn [[_ m1 _]]
                                    (some (fn [[_ m2 _]] (covers-less? m1 m2)) eligible-masks))
                                  eligible-masks))
        masks-with-at-most-k-fixed (fn [masks k]
                                     (reduce (fn [h k-masks] (reduce merge h k-masks))
                                             {}
                                             (keep (fn [[n v]] (when (<= n k) v)) masks)))]
      (->>
        (mapcat
          #(let [possible-masks (masks-with-at-most-k-fixed final-masks %)]
              (for [l (range 1 (inc (count possible-masks)))
                    chosen-masks (k-comb l (set (keys possible-masks)))
                    :let [covered-minterms (reduce into (map possible-masks chosen-masks))]]
                 [chosen-masks covered-minterms]))
           (range 1 (inc size)))
        (filter
          (fn [[masks covered-minterms]] (= covered-minterms (set ones))))
        first
        first
        (map #(set (to-letter-codes %)))
        (into #{}))))
```

問題138. Squares Squared ;; 自乗の正方形

2つの整数(それぞれスタートとエンド)を引数とし、文字列のベクトルを作成する関数を作る。文字列のベクトルは45度回転した正方形で数字はスタートの数字からエンドの数字までが含まれる。自乗の結果の桁上がりについてはそれぞれの桁の数字を並べる。数字の足りない部分はアステリスクで埋める。描画の方向は時計回りで、最初の方向は右下である。

```
(= (__ 2 2) ["2"])

(= (__ 2 4) [" 2 "
             "* 4"
             " * "])

(= (__ 3 81) [" 3 "
              "1 9"
              " 8 "])

(= (__ 4 20) [" 4 "
              "* 1"
              " 6 "])

(= (__ 2 256) ["  6  "
               " 5 * "
               "2 2 *"
               " 6 4 "
               "  1  "])

(= (__ 10 10000) ["   0   "
                  "  1 0  "
                  " 0 1 0 "
                  "* 0 0 0"
                  " * 1 * "
                  "  * *  "
                  "   *   "])
```

解答
```clojure
(fn sqsq [p q]
  (let [dirs (mapcat
               #(repeat %2 %) (cycle [[1 1] [1 -1] [-1 -1] [-1 1]])
               (cons 1 (mapcat #(repeat % %) (iterate inc 1))))
        digits (apply str (take-while #(<= % q) (iterate #(* % %) p)))
        [max-digits sq-size]
                   (first
                     (drop-while
                       (fn [[d s]] (> (count digits) d))
                       (map #(vector %1 %2)
                            (map #(* % %) (iterate inc 2))
                            (iterate #(+ % 2) 3))))
        spiral ((fn [digits dirs]
                 (let [digits-in-center (inc (quot sq-size 2))
                       center-piece (if (zero? (rem digits-in-center 2))
                                      (dec (quot sq-size 2))
                                      (quot sq-size 2))
                       first-pos [center-piece (quot sq-size 2)]]
                   ; could have used reductions here
                   (loop [[fdig & ndig] (next digits),
                          [fd & nd] dirs,
                          pos first-pos,
                          sp {first-pos (first digits)}]
                     (if (nil? fdig)
                       sp
                       (recur ndig nd (map + pos fd) (assoc sp (map + pos fd) fdig))
                      ))))
                  (concat digits (repeat (- max-digits (count digits)) "*")) dirs)]
    (if (= 1 (count digits))
      [digits]
      (into []
        (for [y (range 0 sq-size)]
          (reduce str
             (for [x (range 0 sq-size)]
               (get spiral [y x] \space))))))))
```

問題127. Love Triangle ;; 愛の三角形

みんな三角形が大好きです。素敵に対称だからです。(不等辺三角形は除く。あれはダメ)

三角形愛が昂じてあなたは坑夫になりました。(同時にパートタイムClojureプログラマーです。) 露天掘りの鉱山で岩から二等辺三角形の形をしたミネラルを掘り出しています。あまりに岩の数が多いのでプログラムを作って、どの岩が最大のミネラルを含んでいるか判定することになりました。

すでにコンピューターによる映像処理システムがあって、それぞれの岩の断面をミネラル(1)と岩(0)の濃度のビットマップにしてくれます。

今回作る関数は、整数のコレクションを受け取ります。整数は2進法になおすと岩のビット表現で1がミネラル、0が無価値の不等辺三角形のような岩です。次のような方法で最大のミネラルが取れる断面を返します。

ミネラルは岩の断面を縦、もしくは水平に切ったときにだけ滑らかな面を示します。

鉱山は二等辺三角形の収穫にだけ興味があるので、1つか2つの辺が切断されます。

ミネラルの一面だけ切断されるとき、向かい合う頂点はポイントであり、滑らかな面は奇数長です。同じ長さの辺は45度の角度で切断面と交差します。つまりこれらの面は斜めに同じ長さに切られなければなりません。

収穫されたミネラルは岩を含んでいてはいけない。

ミネラルは平面にどんな向きであってもかまわない。

面積はミネラルを構成する1の数の合計です。

ミネラルは最低3の面積が必要です。

もし岩からミネラルが取れない場合、関数はnilを返します。

```
(= 10 (__ [15 15 15 15 15]))
; 1111      1111
; 1111      *111
; 1111  ->  **11
; 1111      ***1
; 1111      ****

(= 15 (__ [1 3 7 15 31]))
; 00001      0000*
; 00011      000**
; 00111  ->  00***
; 01111      0****
; 11111      *****

(= 3 (__ [3 3]))
; 11      *1
; 11  ->  **

(= 4 (__ [7 3]))
; 111      ***
; 011  ->  0*1

(= 6 (__ [17 22 6 14 22]))
; 10001      10001
; 10110      101*0
; 00110  ->  00**0
; 01110      0***0
; 10110      10110

(= 9 (__ [18 7 14 14 6 3]))
; 10010      10010
; 00111      001*0
; 01110      01**0
; 01110  ->  0***0
; 00110      00**0
; 00011      000*1

(= nil (__ [21 10 21 10]))
; 10101      10101
; 01010      01010
; 10101  ->  10101
; 01010      01010

(= nil (__ [0 31 0 31 0]))
; 00000      00000
; 11111      11111
; 00000  ->  00000
; 11111      11111
; 00000      00000
```

解答
```clojure
(fn [coll]
  (let [binary-str (map #(Integer/toBinaryString %) coll)
        board (mapv #(vec (concat (repeat (- (apply max (map count binary-str)) (count %)) \0) %)) binary-str)]
    (letfn [(count-one [s e g]
              (let [points (if (zero? (first g))
                             (map #(vec [(first s) %]) (range (second s) (inc (second e))))
                             (map #(vec [% (second s)]) (range (first s) (inc (first e)))))]
                (if (every? #(= % \1) (map #(get-in board %) points))
                  (count points)
                  0)))
            (step [s e m n g r]
              (let [one-count (count-one s e g)]
                (if (zero? one-count)
                  r
                  (step (map #(+ %1 %2) s m) (map #(+ %1 %2) e n) m n g (+ r one-count)))))]
      (let [result (apply max
                     (mapcat
                       #(map
                          (fn [m n g] (step % % m n g 0))
                          [[-1 -1] [-1 0] [-1 -1] [-1 1] [0 1] [-1 1] [1 -1] [1 0] [1 -1] [-1 -1] [0 -1] [-1 -1]]
                          [[-1 0] [-1 1] [-1 1] [0 1] [1 1] [1 1] [1 0] [1 1] [1 1] [0 -1] [1 -1] [1 -1]]
                          [[0 1] [0 1] [0 1] [1 0] [1 0] [1 0] [0 1] [0 1] [0 1] [1 0] [1 0] [1 0]])
                       (filter
                         #(= \1 (get-in board %))
                         (mapcat #(map (fn [x] [x %]) (range 0 (count board))) (range 0 (count board))))))]
        (if (= 1 result)
          nil
          result)))))
```

問題152. Latin Slicing ;; ラテン方格スライシング

ラテン方格とはn次の場合n x nの配列でn種類の要素が行や列で重ならずに入っているもののことです。例えば以下の例では最初の1つだけがラテン方格です。

```
1:
A B C
B C A
C A B

2:
A B C
B C A
C A C

3:
A B C
B D A
C A B
```

Vをそのようなベクトルのベクトルとします。長さは任意です。つらなる行が以下の条件が満たされたとき整列しているとします。

Vの全ての行が使われている。

それぞれの行は1つのベクトルでできている。

Vの順序は維持される。

最長のベクトルは互いに水平に並べられる。

もしベクトルが最長の長さでない場合、要素は最長のベクトルのサブベクトルの要素と並べられる。

Lを2次以上のラテン方格とします。もしVの整列がLと同値のサブスクエアを含むときVはLを含むと言います。例えばVが[[1 2 3][2 3 1 2 1][3 1 2]]のとき9つの整列があります。カギ括弧を省略しました。

```
        1              2              3

      1 2 3          1 2 3          1 2 3
  A   2 3 1 2 1    2 3 1 2 1    2 3 1 2 1
      3 1 2        3 1 2        3 1 2

      1 2 3          1 2 3          1 2 3
  B   2 3 1 2 1    2 3 1 2 1    2 3 1 2 1
        3 1 2        3 1 2        3 1 2

      1 2 3          1 2 3          1 2 3
  C   2 3 1 2 1    2 3 1 2 1    2 3 1 2 1
          3 1 2        3 1 2        3 1 2
```

A1整列はラテン方格[[1 2 3][2 3 1][3 1 2]]を含みます。整列A2, A3, B1, B2, B3はラテン方格を含みません。整列C1, C2, C3は[[2 1][1 2]]を含みます。したがってVは3次のラテン方格1個と2次のラテン方格3個を含みます。

今回の関数はベクトルのベクトルVを引数として受け取り、整数のキーと値のマップを返します。キーはVに含まれるラテン方格の次数で、値はその次数の異なったラテン方格の数です。もしVにラテン方格が含まれない場合、空のマップが返されます。例の場合、正しいアウトプットは{3 1, 2 1}になり、{3 1, 2 3}ではありません。

```
(= (__ '[[A B C D]
         [A C D B]
         [B A D C]
         [D C A B]])
   {})

(= (__ '[[A B C D E F]
         [B C D E F A]
         [C D E F A B]
         [D E F A B C]
         [E F A B C D]
         [F A B C D E]])
   {6 1})

(= (__ '[[A B C D]
         [B A D C]
         [D C B A]
         [C D A B]])
   {4 1, 2 4})

(= (__ '[[B D A C B]
         [D A B C A]
         [A B C A B]
         [B C A B C]
         [A D B C A]])
   {3 3})

(= (__ [  [2 4 6 3]
        [3 4 6 2]
          [6 2 4]  ])
   {})

(= (__ [[1]
        [1 2 1 2]
        [2 1 2 1]
        [1 2 1 2]
        []       ])
   {2 2})

(= (__ [[3 1 2]
        [1 2 3 1 3 4]
        [2 3 1 3]    ])
   {3 1, 2 2})

(= (__ [[8 6 7 3 2 5 1 4]
        [6 8 3 7]
        [7 3 8 6]
        [3 7 6 8 1 4 5 2]
              [1 8 5 2 4]
              [8 1 2 4 5]])
   {4 1, 3 1, 2 7})
```

解答
```clojure
(fn [square]
  (letfn [(rotate [s]
            (if (every? seq s) (cons (map first s) (rotate (map next s)))))
          (is-latin-square? [s]
            (let [eles (set (flatten s))]
              (if (eles \space)
                false
                (if
                  (= (count s) (count eles))
                  (and (every? #(= (set %) eles) s) (every? #(= (set %) eles) (rotate s)))
                  false))))
          (slice [s]
            (set (mapcat
                   (fn [n]
                     (mapcat
                       #(partition n (apply interleave (map (fn [l] (partition n 1 l)) %)))
                       (partition n 1 s)))
                   (range 2 (inc (count s))))))
          (trans [s]
            (let [max-len (apply max (map count s))]
              (letfn [(trans-step [transed-s rest-s]
                        (let [first-line (first rest-s)]
                          (if (seq first-line)
                            (if (= max-len (count first-line))
                              (trans-step (cons first-line transed-s) (next rest-s))
                              (mapcat
                                (fn [pos]
                                  (trans-step
                                    (cons
                                      (concat (concat (repeat pos \space) first-line) (repeat (- max-len (+ pos (count first-line))) \space))
                                      transed-s)
                                    (next rest-s)))
                                (range 0 (inc (- max-len (count first-line))))))
                            transed-s)))]
                (set (partition (count s) (trans-step [] s))))))]
    (apply merge (map
                   (fn [entry]
                     (let [c (count (filter is-latin-square? (val entry)))]
                       (if (pos? c) {(key entry) c} {})))
                   (group-by count (set (mapcat #(slice %) (trans square))))))))
```
