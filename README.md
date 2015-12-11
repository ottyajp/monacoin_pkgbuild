monacoinをビルドできそうなPKGBUILDを手探りで作ります。

ArchLinuxっていうかantergosで書いてるけどまぁなんとかなるっしょ


`./configure`の次の行から少し設定いじれるようになってますが、`--without-gui`した時には、`package()`のmonacoin-qtな行もコメントアウトするなりしておいてください。（`--without-gui`するとmonacoin-qtはビルドされません）
