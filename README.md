# NetworkMetaModel

最新のメタモデルを更新する。
ファイル名：metamodel_日付　(metamodel_0630)

古いファイルはoldファイルに入れる

属性を追加、削除時はReadMeに変更した属性を追加し、commitメッセージになんの属性を変えたか記入する。


## クラスの説明

### HostName
| 属性名    | 型        | 説明       |
| ------ | -------- | -------- |
| `name` | `String` | ホスト名 |

### EthernetSetting
| 属性名                            | 型         | 説明           |
| ------------------------------ | --------- | ------------ |
| `stack`                        | `String`  | スタック番号       |
| `slot`                         | `String`  | スロット番号       |
| `port`                         | `String`  | ポート番号        |
| `ipAddress`                    | `String`  | IPアドレス       |
| `subnetMask`                   | `String`  | サブネットマスク     |
| `accessVlan`                   | `int`     | アクセスVLAN ID  |
| `nativeVlan`                   | `int`     | ネイティブVLAN ID |
| `allowedVlan`                  | `String`  | 許可されたVLAN一覧  |
| `mode`                         | `String`  | スイッチポートモード   |
| `accessListNumber`             | `int`     | アクセスリスト番号    |
| `accessListName`               | `String`  | アクセスリスト名     |
| `accessListInOrOut`            | `String`  | アクセスリストの方向   |
| `speed`                        | `String`  | 回線速度設定       |
| `duplex`                       | `String`  | デュプレックスモード   |
| `ipVirtualReassembly`          | `Boolean` | IP再構成の有効化    |
| `switchportTrunkEncapsulation` | `String`  | トランクカプセル化    |
| `shutdown`                     | `Boolean` | シャットダウン設定    |
| `mtu`                          | `int`     | MTUサイズ       |

### Vlan 
| 属性名    | 型        | 説明     |
| ------ | -------- | ------ |
| `num`  | `int`    | VLAN番号 |
| `name` | `String` | VLAN名  |

### VlanSetting
| 属性名                   | 型         | 説明             |
| --------------------- | --------- | -------------- |
| `vlanNum`             | `int`     | VLAN番号         |
| `ipAddress`           | `String`  | VLANインターフェースIP |
| `subnetMask`          | `String`  | サブネットマスク       |
| `accessListNumber`    | `int`     | ACL番号          |
| `accessListName`      | `String`  | ACL名           |
| `accessListInOrOut`   | `String`  | ACL適用方向        |
| `ipNatInside`         | `Boolean` | NAT内部有効        |
| `ipTcpAdjustMss`      | `int`     | MSS調整値         |
| `ipVirtualReassembly` | `Boolean` | IP再構成          |
| `shutdown`            | `Boolean` | シャットダウン設定      |

### StpSetting
| 属性名              | 型        | 説明          |
| ---------------- | -------- | ----------- |
| `bridgePriority` | `int`    | ブリッジプライオリティ |
| `vlan`           | `int`    | VLAN番号      |
| `mode`           | `String` | STP動作モード    |
| `macAddress`     | `String` | MACアドレス     |

### IpRoute
| 属性名              | 型        | 説明           |
| ---------------- | -------- | ------------ |
| `ipAddress`      | `String` | 宛先ネットワークアドレス(*注　属性名networkから名前を変更) |
| `subnetMask`     | `String` | サブネットマスク (*注　属性名addressPrefixから名前を変更)    |
| `nextHopAddress` | `String` | ネクストホップのIP   |

### OspfVirtualLink
| 属性名        | 型        | 説明             |
| ---------- | -------- | -------------- |
| `areaId`   | `int`    | エリアID          |
| `routerId` | `String` | 仮想リンク接続先のルータID |

###  OspfInterfaceSetting
| 属性名               | 型         | 説明             |
| ----------------- | --------- | -------------- |
| `ipAddress`       | `String`  | インターフェースIPアドレス |
| `wildcardMask`    | `String`  | ワイルドカードマスク     |
| `areaId`          | `int`     | 所属エリアID        |
| `helloInterval`   | `int`     | Helloパケットの送信間隔 |
| `deadInterval`    | `int`     | ネイバー死活判定時間     |
| `ospdNetworkMode` | `String`  | ネットワークタイプ      |
| `stub`            | `Boolean` | スタブフラグ         |
| `priority`        | `int`     | DR選出優先度        |

### OspfSetting
| 属性名         | 型        | 説明         |
| ----------- | -------- | ---------- |
| `processId` | `int`    | OSPFプロセス番号 |
| `routerId`  | `String` | ルーターID     |

### Client
| 属性名              | 型        | 説明            |
| ---------------- | -------- | ------------- |
| `ipAddress`      | `String` | クライアントIPアドレス  |
| `subnetMask`     | `String` | サブネットマスク      |
| `defaultGateway` | `String` | デフォルトゲートウェイIP |

### EthernetType
| 属性名                 | 型         | 説明                  |
| ------------------- | --------- | ------------------- |
| `fastEthernet`      | `Boolean` | FastEthernet対応有無    |
| `ethernet`          | `Boolean` | Ethernet対応有無        |
| `gigabitEthernet`   | `Boolean` | GigabitEthernet対応有無 |
| `10gigabitEthernet` | `Boolean` | 10G Ethernet対応有無    |

### AccessList
| 属性名                  | 型         | 説明                          |
| -------------------- | --------- | --------------------------- |
| `accessListNumber`   | `int`     | アクセスリスト番号                   |
| `accessListName`     | `String`  | アクセスリストの名前（名前付きACL）         |
| `sequenceNumber`     | `int`     | ルールのシーケンス番号                 |
| `permitOrDeny`       | `String`  | `permit` または `deny` の指定     |
| `protocol`           | `String`  | `ip`, `tcp`, `udp` などのプロトコル |
| `sourceIpAddress`    | `String`  | 送信元IPアドレス                   |
| `sourceWildcardMask` | `String`  | 送信元のワイルドカードマスク              |
| `sourceOperator`     | `String`  | 送信元ポートに対する演算子               |
| `sourcePort`         | `String`  | 送信元ポート番号                    |
| `destIpAddress`      | `String`  | 宛先IPアドレス                    |
| `destWildcardMask`   | `String`  | 宛先のワイルドカードマスク               |
| `destPort`           | `String`  | 宛先ポート番号                     |
| `destOperator`       | `String`  | 宛先ポートに対する演算子                |
| `sourceIsHost`       | `Boolean` | 送信元が単一ホスト指定かどうか             |
| `destIsHost`         | `Boolean` | 宛先が単一ホスト指定かどうか              |
