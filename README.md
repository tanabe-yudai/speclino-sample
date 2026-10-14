# SpecLino の見本リポジトリ（注文サービス）

[SpecLino](https://github.com/tanabe-yudai/speclino) の PR ゲートを、自分のリポジトリで試すための見本です。
審査員向けデモ手順の「第 2 部」の任意の手順 A で使います。

- `examples/shop/app/`: 注文の確定・出荷・取消を行う小さな Python のコード。仕様 `shop-order` に適合しています
- `.speclino/bindings.yaml`: 仕様の図の名前（`OrderService.place_order` など）と、コードの関数の対応
- `.speclino/domain.yaml`: 仕様の変数（`order.status` など）の型
- `docs/shop-order.md`: SpecLino に登録する仕様の本文（手順書の手順 15 と同じもの）。検査に使うのは SpecLino で承認した改訂で、このファイルではありません

## 試し方

1. このリポジトリの右上の「Use this template」→「Create a new repository」で、自分のアカウントにリポジトリを作ります
2. SpecLino の自分のワークスペースで、作ったリポジトリを登録します（設定 → リポジトリ）
3. `examples/shop/app/service.py` の `self.payment.charge(order.id)` の行を消す PR を作ります
4. PR の Check「SpecLino / gate」が失敗し、決済を呼ばずに注文を確定する経路が、反例つきの違反として示されます

ライセンス: AGPL-3.0（SpecLino の `examples/shop` から作成）
