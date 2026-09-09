<!-- machine_translated: true -->

<!-- pre-align:aligned sig=755f913dbd4d -->

<a id="storage-backup-overview"></a>
## Storage > Backup > 概要 { #storage-backup-overview }

バックアップは、セキュリティーの脅威、ユーザーの操作ミス、記憶装置の故障、自然災害などによるデータの損失に備えてコピーを作成し、安全に保管するサービスです。保管したコピーを利用してデータを復旧することができます。

NHN Cloudバックアップサービスは、全体バックアップ方式と増分バックアップ方式を共に使用します。最初の1回はユーザーが登録したパスのデータ全体をバックアップします。以降はデータの重複を削除してバックアップデータを最小化できる可変長の重複削除(variable-length deduplication)技術を利用して増分のみをバックアップします。したがってバックアップ時間が短縮され、ネットワーク使用量も減少します。データは暗号化されて、バックアップストレージに安全に転送されます。

NHN Cloudバックアップサービスは、簡単にバックアップポリシーを登録し、バックアップ履歴を照会して、復旧申請ができるウェブコンソール環境を提供します。バックアップ結果は毎日収集され、メールで報告されます。

<a id="service-features"></a>
## サービスの特徴 { #service-features }
* 様々なオペレーションシステムをサポートします。
* 仮想化環境に最適化されています。
* サービスを中断せずにバックアップできます。
* バックアップ周期とバックアップ時刻、保管周期を設定できるユーザー定義バックアップポリシーを提供します。

<a id="backup-cycle"></a>
### バックアップの周期 { #backup-cycle }
1日間隔、7日間隔を選択できます。

<a id="backup-time"></a>
### バックアップ時刻 { #backup-time }
1時間単位でバックアップ開始時刻を選択できます。ファイル変更が最も少なく、サーバーがアイドル状態の時刻を推奨します。実際のバックアップ開始は、状況に応じて最大1時間ほどの差が生じることがあります。

<a id="retention-cycle"></a>
### バックアップの保管周期 { #retention-cycle }
7日、 14日、 21日、 30日の保管周期を選択できます。

<a id="view-results"></a>
### バックアップ結果の照会 { #view-results }
ユーザーはバックアップ完了時刻から最長30分以内に、ウェブコンソールからバックアップ結果を照会できます。もしバックアップに失敗したら、メールで失敗内容が報告されます。最長3時間バックアップされなければ失敗として記録されます。

バックアップ結果メールは毎日10時に情報が収集され、10時30分に送信されます。10時以前にバックアップスケジュールが実行されていても、10時以降にバックアップスケジュールが完了した場合、当日のバックアップ結果メールが送信されない場合があります。

<a id="supported-operating-systems"></a>
## サポートするオペレーションシステム { #supported-operating-systems }
NHN Cloudでサポートするオペレーションシステムは次のとおりです。

| オペレーションシステム | ハードウェアアーキテクチャ | サポートバージョン | サポート構成 |
| --- | --- | --- | --- |
| CentOS | x64 | 7.8 | ext2, ext3, ext4, xfs |
| Ubuntu | x64 | 18.04 LTS<br/>20.04 LTS | ext2, ext3, ext4 |
| Debian | x64 | 9, 10 | ext2, ext3, ext4 |
| Rocky | x64 | 8.5 | xfs |
| Windows Server | x64 | 2012 R2 STD<br/>2016 STD<br/>2019 STD | NTFS |

<a id="restoration"></a>
## 復元 { #restoration }
復元元のサーバーのバックアップ結果の中から一つを選択して実行します。バックアップされた内容全体を復元することも、一部のパスを選択して復元することも可能です。
復元対象サーバーは、バックアップエージェントがインストールされているサーバーの中から選択でき、復元元のサーバーと同じOS系列（LinuxまたはWindows）のサーバーを選択する必要があります。
保存先のパスは任意のパスを指定することも可能で、入力したパスが存在しない場合は、パスを自動作成した上で復元が実行されます。

<a id="charges"></a>
## 課金 { #charges }
サーバーが登録されると、基本月額料金が課金されます。その後、登録したサーバーの数、ストレージの使用量、復元したデータサイズに応じて追加料金が発生します。基本月額料金の標準仕様は、サーバー2台、ストレージ使用量100GBです。

<a id="reference"></a>
## 参考事項 { #reference }
<a id="backup-software"></a>
### バックアップソフトウェア { #backup-software }
DELL EMC AVAMAR

<a id="backup-program-installation-location"></a>
### バックアッププログラムインストール位置 { #backup-program-installation-location }
* Linux : /usr/local/avamar
* Windows : C:\Program Files\avs

<a id="backup-program-daemon-process-information"></a>
### バックアッププログラムデーモン(プロセス)情報 { #backup-program-daemon-process-information }
* Linux : /usr/local/avamar/bin/avagent.bin
* Windows : Avamar Backup Client
