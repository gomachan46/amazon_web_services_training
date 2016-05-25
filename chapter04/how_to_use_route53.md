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
