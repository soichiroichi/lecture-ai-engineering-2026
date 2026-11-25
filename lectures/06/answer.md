# 第6回 解答

## 演習

<!-- [tool call] の行は、表示された行をそのまま貼り付けてください。終わらなかった STEP は、空欄のままでかまいません。 -->

- STEP 1 のツールの名前： [search_materials]/[search_glossary]
- STEP 2 の [tool call]： glossary_search_glossary({'query': '3レベル'})
- STEP 3 の [tool call]： fetch_fetch({'url': 'https://modelcontextprotocol.io/'})
- STEP 4 の [tool call]： aws_aws___search_documentation({'topics': ['general'], 'search_phrase': 'Amazon S3 versioning overview'})
- 気づき・疑問：講義の中でも、MCPだから可能なことは特段ないような印象を受けたが、演習を通して、もしMCPを利用しなければどういった代替の方法があるのか、それと比較してMCP接続にどのようなメリットがあるかというところが気になった。例えば、AWSのMCPサーバはMCP接続用に用意されているように見受けられるが、単にウェブサイトをエージェントがアクセスして必要な情報を取得するよりどう良いのかなど。

## 宿題

<!-- 基礎・実装・発展のどれか1つに取り組めば完了です。 -->

- 取り組んだレベル：基礎
- やったこと： `app/mcp_server.py`に`server.tool()(tools.get_lecture_summary)を追加
- 結果：
    * [tool call]   glossary_get_lecture_summary({'lecture': 2})
    * [tool return] glossary_get_lecture_summary -> # 第2回 ファインチューニングとLoRA
    * 上記テーマの概要が説明された。
- 気づき・疑問：モデルの応答が2回あり、一回目で "第2回では何を学びますか？" という入力文から "{'lecture': 2}のJSON入力が作成され、そのキーと値から"第2回 ファインチューニングとLoRA"が返ってきた。回答の文章の中身は、'data/lectures/06.md' であった。
