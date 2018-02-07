# path
* filesystem[meta header]
* std::filesystem[meta namespace]
* class[meta id-type]
* cpp17[meta cpp]

```cpp
namespace std::filesystem {
  class path;
}
```

## 概要
`path`は、ファイルシステムのパスを表すクラスである。このクラスは、パスに関して以下のような機能を持つ：

- パスの連結 (`"a"`もしくは`"a/"`ディレクトリと`"b.txt"`ファイル名を連結して`"a/b.txt"`パスとする)
- パスに含まれるディレクトリ、ファイル名、拡張子などの抽出
- 文字コード変換
- パス区切り文字の変換
- その他、文字列レベルのパス変換

このクラス自体は、ファイルシステムを操作しない。


## メンバ関数
### 構築・破棄

| 名前 | 説明 | 対応バージョン |
|------|------|-------|
| [`(constructor)`](path/op_constructor.md.nolink) | コンストラクタ | C++17 |
| [`(destructor)`](path/op_destructor.md.nolink)   | デストラクタ | C++17 |
| [`operator=`](path/op_assign.md.nolink)          | 代入演算子 | C++17 |
| [`assign`](path/assign.md.nolink)                | 代入 | C++17 |


### パスの加算・追加

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`operator/=`](path/op_append_assign.md) | パス要素を加算する | C++17 |
| [`append`](path/append.md) | パス要素を加算する | C++17 |
| [`operator+=`](path/op_plus_assign.md) | パス文字列を加算する | C++17 |
| [`concat`](path/concat.md) | パス文字列を加算する | C++17 |

### パスの変更

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`clear`](path/clear.md) | パスを空にする | C++17 |
| [`make_preferred`](path/make_preferred.md) | ディレクトリの区切り文字を推奨する形式に変換する | C++17 |
| [`remove_filename`](path/remove_filename.md) | パスからファイル名を除去する | C++17 |
| [`replace_filename`](path/replace_filename.md) | パスに含まれるファイル名を置き換える | C++17 |
| [`replace_extension`](path/replace_extension.md) | パスに含まれる拡張子を置き換える | C++17 |
| [`swap`](path/swap.md) | 他の`path`オブジェクトとデータを入れ替える | C++17 |

### 文字コード

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`native`](path/native.md) | システムの文字コードとしてパス文字列を取得する | C++17 |
| `c_str`  | システムの文字コードとしてC言語の文字列表現を取得する | C++17 |
| `operator string_type` | システムの文字コードとして文字列型に変換する | C++17 |
| `string` | システムのマルチバイト文字コードとしてパス文字列を取得する | C++17 |
| `wstring` | システムのワイド文字コードとしてパス文字列を取得する | C++17 |
| `u8string` | UTF-8エンコードとしてパス文字列を取得する | C++17 |
| `u16string` | UTF-16エンコードでパス文字列を取得する | C++17 |
| `u32string` | UTF-32エンコードでパス文字列を首都する | C++17 |

### システム非依存のパスフォーマット

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| `generic_string` | システムのマルチバイト文字コードとして、環境非依存パスフォーマットのパス文字列を取得する | C++17 |
| `generic_wstring` | システムのワイド文字コードとして、環境非依存パスフォーマットのパス文字列を取得する | C++17 |
| `generic_u8string` | UTF-8エンコードで、環境非依存パスフォーマットのパス文字列を取得する | C++17 |
| `generic_u16string` | UTF-16エンコードで、環境非依存パスフォーマットのパス文字列を取得する | C++17 |
| `generic_u32string` | UTF-32エンコードで、環境非依存パスフォーマットのパス文字列を取得する | C++17 |


### 比較

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| `compare` | 他のパスと文字列レベルで比較する | C++17 |


### 抽出

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`root_name`](path/root_name.md) | ルート名を取得する | C++17 |
| [`root_directory`](path/root_directory.md) | ルートディレクトリを取得する | C++17 |
| [`root_path`](path/root_path.md) | ルートパスを取得する | C++17 |
| [`relative_path`](path/relative_path.md) | ルートパスからの相対パスを取得する | C++17 |
| [`parent_path`](path/parent_path.md) | 親のパスを取得する | C++17 |
| [`filename`](path/filename.md) | ファイル名を取得する | C++17 |
| [`stem`](path/stem.md) | 拡張子を除いたファイル名を取得する | C++17 |
| [`extension`](path/extension.md) | 拡張子を取得する | C++17 |

### パス情報の判定

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`empty`](path/empty.md) | パスが空か判定する | C++17 |
| [`has_root_name`](path/has_root_name.md) | ルート名が含まれているか判定する | C++17 |
| [`has_root_directory`](path/has_root_directory.md) | ルートディレクトリが含まれているか判定する | C++17 |
| [`has_root_path`](path/has_root_path.md) | ルートパスが含まれているか判定する | C++17 |
| [`has_relative_path`](path/has_relative_path.md) | ルートパスからの相対パスが含まれているか判定する | C++17 |
| [`has_parent_path`](path/has_parent_path.md) | 親のパスが含まれているか判定する | C++17 |
| [`has_filename`](path/has_filename.md) | ファイル名が含まれているか判定する | C++17 |
| [`has_stem`](path/has_stem.md) | 拡張子を除いたファイル名が含まれているか判定する | C++17 |
| [`has_extension`](path/has_extension.md) | 拡張子が含まれているか判定する | C++17 |
| [`is_absolute`](path/is_absolute.md) | 絶対パスかを判定する | C++17 |
| [`is_relative`](path/is_relative.md) | 相対パスかを判定する | C++17 |

### 文字列レベルのパス生成

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| `lexically_normal` | 文字列レベルで正規化する | C++17 |
| `lexically_relative` | 文字列レベルで相対パスに変換する | C++17 |
| `lexically_proximate` | 文字列レベルで相対パスに変換する | C++17 |

### イテレータ

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`begin`](path/begin.md) | ディレクトリ区切りした各パス要素のうち、先頭要素を指すイテレータを取得する | C++17 |
| [`end`](path/end.md) | ディレクトリ区切りした各パス要素のうち、末尾要素の次を指すイテレータを取得する | C++17 |


## メンバ型

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| `value_type` | パスを表現するシステム依存のエンコード文字型。<br/>POSIXベースのシステムでは`char`<br/> Windowsベースのシステムでは`wchar_t` | C++17 |
| `string_type` | パス文字列型 [`basic_string`](/reference/string/basic_string.md)`<value_type>` | C++17 |
| `format` | パスフォーマットの列挙型 | C++17 |
| [`iterator`](path/iterator.md) | ディレクトリ区切りの要素を走査するイテレータ | C++17 |
| `const_iterator` | `iterator`の別名 | C++17 |


## メンバ定数

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| `static constexpr value_type preferred_separator` | 推奨するディレクトリ区切り文字。<br/> POSIXベースのシステムではスラッシュ (`'/'`) <br/> Windowsベースのシステムではバックスラッシュ (`L'\\'`) | C++17 |


## 非メンバ関数

### 一般関数

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`swap`](path/swap_free.md) | 2つの`path`オブジェクトを入れ替える | C++17 |
| `hash_value` | パスのハッシュ値を取得する | C++17 |

### 比較演算子

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| `operator==` | 等値比較 | C++17 |
| `operator!=` | 非等値比較 | C++17 |
| `operator<` | 左辺が右辺より小さいかの判定を行う | C++17 |
| `operator<=` | 左辺が右辺以下かの判定を行う | C++17 |
| `operator>` | 左辺が右辺より大きいかの判定を行う | C++17 |
| `operator>=` | 左辺が右辺以上かの判定を行う | C++17 |

### パスの連結

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| [`operator/`](path/op_append.md) | 2つのパスを連結する | C++17 |

### 入出力

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| `operator<<` | ストリームへの出力 | C++17 |
| `operator>>` | ストリームからの入力 | C++17 |

### 生成関数

| 名前 | 説明 | 対応バージョン |
|------|------|----------------|
| `u8path` | UTF-8エンコードされた文字列からパスオブジェクトを構築する | C++17 |


## 例
```cpp example
```

### 出力例
```
```

## バージョン
### 言語
- C++17

### 処理系
- [Clang, C++17 mode](/implementation.md#clang): ??
- [GCC, C++17 mode](/implementation.md#gcc): ??
- [ICC](/implementation.md#icc): ??
- [Visual C++](/implementation.md#visual_cpp): ??
