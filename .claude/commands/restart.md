---
プロジェクトの途中から再開するコマンド。

使い方：/restart {プロジェクト名}

$ARGUMENTSが空の場合は「プロジェクト名を入力してください。使い方：/restart {プロジェクト名}」と表示して終了する。

$ARGUMENTSが指定されている場合は以下を実行する：
1. projects/$ARGUMENTS/state.jsonを読んで現在の進捗を表示する
2. 現在進行中または最後に実行した工程のprojects/$ARGUMENTS/resume/配下のresumeファイルを読む
3. 以下の形式で進捗を表示する：

=============================
📊 プロジェクト進捗：$ARGUMENTS
=============================
✅ hearing-prep      完了
✅ requirements      完了
🔄 internal-design   進行中（retry: 1）
⏳ implementation    待機中
=============================

【工程内の進捗】
✅ design/backend/auth.md
🔄 design/frontend/README.md
⏳ design/flows/login.md

4. 未完了タスクがある工程エージェントを直接起動する
   指示：「resume-{工程名}.mdを読んで、⏳未着手と🔄生成中のタスクのみ生成すること。✅完了タスクは上書きしない。」
---
