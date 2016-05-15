# Route 53の概要

## Route 53とは

WebベースのDNSサービス。

SLA100%を掲げている

世界中に展開されているエッジロケーションで提供されていて、もっとも近いロケーションから応答を返すためとても高速かつ高可用でスケーラブル

APIで操作可能なのでコストも安く済む

## Route 53における重要概念

### Hosted Zone

DNSレコードの集合

### Record Set

DNSレコード

* Routing Policy
* Set ID
* ヘルスチェックの設定
* DNSレコード

を合わせた単位

### Routing Policy

Record Setに対してどのようにルーティングを行うかを決定するところ

### Set ID

Routing Policyを用いて複数のRecord Setで同じ名前を設定する場合にそれぞれをユニークにするために設定するID

### ヘルスチェック

転送先ホストの状態をチェックするための設定

HTTP/HTTPS/TCPで可能。
