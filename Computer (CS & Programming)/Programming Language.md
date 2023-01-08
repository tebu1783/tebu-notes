-   エラー
	-   構文エラー
	-   静的型エラー
	-   実行時エラー
		-   算術演算を行おうとしたところ，対象が数値ではなかった
		-   関数呼び出しをしようとしたところ，呼び出し関数を表す式の値が関数でないものだった．
		-   メソッド呼び出しをしようとしたところ，そのメソッドがオブジェクトになかった．
		-   強く型付けされる言語 (strongly typed language)
-   未定義動作 (undefined behaviour)
	-   エラーを検知するためのコストを払いたくない
	-   例えば配列アクセスで添字が大きすぎる場合
	-   不正な領域を読み書きできてしまうことによって発生するセキュリティの問題は深刻である
-   未指定動作 (unspecified behaviour)
	-   例えば C, OCaml, Scheme では，関数呼び出しで実引数が複数ある場合に，それらの評価順序は未指定動作となっていて，どの順番で実行されるかわからない
-   末尾再帰、末尾呼び出し (tail call)
	-   末尾呼び出しの最適化 (tail-call optimization)
	-   末尾呼び出し除去 (tail-call elimination)
	-   f の残りの仕事は g からの返値を f の呼出し元に返すだけなので，多くの場合(OCamlでは必ず)，局所変数の領域はこの時点で必要なくなる
	-   フレームには，局所変数の情報だけでなく，関数から返る際に実行をどこへ戻せばよいかの戻り先情報が書かれているが，末尾呼出しの場合，これも不要になる