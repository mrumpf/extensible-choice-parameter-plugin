Extension Choice Parameter plugin
=================================

選択肢をいろんな方法で設定できる選択パラメータを追加するJenkinsプラグイン

これはなに？
------------

Extension Choice Parameter は、「拡張可能な選択」パラメータを追加する [Jenkins](http://jenkins-ci.org/) プラグインです: 

* 標準の選択パラメータと同じように、ビルド時にパラメータの値をドロップダウンで選択します。
* 選択肢の設定方法をいろんな方法で指定できます:
	* テキストエリアで定義する選択肢: 標準の選択パラメータと同様に、テキストエリアに選択肢を記述します。
	* ジョブ共通の選択肢: システムの設定 画面で定義した選択肢を使用します。
* ジョブ共通の選択肢を使えば、複数のジョブで共通の選択肢を使いたい場合に便利です。システムの設定 画面で選択肢を更新すれば、その選択肢を使用しているすべてのジョブで更新内容が反映されます。
* 編集可能にする を設定すれば、ビルド時にパラメータの値として選択肢にない値を指定することもできます。ビルド時に予定外の値を指定する必要がある場合などに便利です。
* 選択肢の設定方法は、[Jenkins の拡張ポイント機能] (https://wiki.jenkins-ci.org/display/JENKINS/Extension+points) を使って拡張することができます。

拡張ポイント
------------

新しい選択肢の設定方法を作る場合は、`ChoiceListProvider` 抽象クラスを拡張し、以下のメソッドをオーバーライドします:

```java
abstract public List<String> ChoiceListProvider::getChoiceList()
```

TODO
----

* [jenkins-ci.orgでプラグインを公開する] (https://wiki.jenkins-ci.org/display/JENKINS/Hosting+Plugins)

