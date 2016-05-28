# Route 53の基本操作

## Hosted Zoneの作成

### マネジメントコンソールの場合

* サービス: Route 53
* 概要: `DNS Management`を`Get Started Now`から`Create Hosted Zone`

Domain Nameに取得したドメインを、Commentに管理用のコメントを入れる。TypeはPublic Hosted Zoneで。

また、Route 53はリージョンに関係なく設定が可能なサービスのため、メニュー右上のリージョン名が`グローバル`になっている

ひとまずこれで無事にHosted Zoneの登録は完了。簡単！

## Record Setの作成

次にRecord Setを作成して実際に名前からIPアドレスが解決できるようにしていく。

### サポートされているレコードタイプ

|レコードタイプ|説明|
|---|---|
|A(Address Record)|ホスト名とIPv4のIPアドレスのマッピング|
|AAAA(IPv6 Address Record)|ホスト名とIPv6のIPアドレスのマッピング|
|CNAME(Cannonical NAME Record)|他のDNS名の別名を設定|
|MX(Mail eXchange Record)|メールサーバ名のリストを設定|
|NS(Name Server Record)|ドメインの移譲されているネームサーバ(権威DNSサーバ)名を設定|
|PTR(PoinTeR Record)|逆引き(IPアドレスからDNS名へのマッピング)を行う。実際にはIPアドレスを直接していしない。|
|SOA(Start Of Authority Record)|ゾーンに関する情報を指定。プライマリネームサーバ、ドメイン管理者のEメール、シリアルナンバー、更新間隔、キャッシュの有効期間など。|
|SPF(Sender Policy Framework Record)|IPアドレスによる電子メールの送信ドメイン認証技術であるSPFに関する記述を行う。|
|SRV(SeRVice locator Record)|そのドメインで提供されているサービスの詳細な情報を記述|
|TXT(Text Record)|テキスト情報を提供するためのレコード。Routes 53では255文字を超えるTXTレコードを1レコードとして記述する場合は注意が必要|

以上10種類。
