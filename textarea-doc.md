# Overview

TextArea は、複数行のテキストを表示します。

```KUCComponentRenderer {"id":"_render"}
var component = new TextArea({
  label: 'Fruit',
  visible : true
});
```
---

# Specification

## Property

使用できるプロパティの一覧です。プロパティを指定して値を更新することができます。

| Name | Type | Default | Description | Remark |
| :--- | :--- | :--- | :--- | :--- |
| className | string | "" | コンポーネントの class 名 ||
| error | string | "" | エラーに表示するテキスト | 未指定、あるいは空文字 の場合、error は表示されない |
| id | string | "" | コンポーネントの id 名 ||
| label | string | "" | コンポーネントの説明ラベル | 未指定、あるいは空文字の場合、label は表示されない |
| value | string | "" | 表示されるテキスト ||
| disabled | boolean | false | コンポーネントの編集可/不可設定 ||
| requiredIcon | boolean | false | コンポーネントの必須アイコン表示/非表示設定 ||
| visible | boolean | true | コンポーネントの表示/非表示設定 ||

## Event

指定できるイベントの一覧です。

| Name | Type | Description | Remark |
| :--- | :--- | :--- | :--- |
| change | function | 値が変更された時のイベントハンドラ | 引数には Event の event オブジェクトをとる<br><br>event.detail で以下の値を受け取ることができる<br>event.detail.oldValue : 更新前のvalueの値<br>event.detail.value : 更新後のvalueの値 |
| focus | function | フォーカスされた時のイベントハンドラ | 引数には Event の event オブジェクトをとる<br><br>event.detail で以下の値を受け取ることができる<br>event.detail.value : focus時のvalueの値 |

## Constructor

TextArea(options)  
使用できるコンストラクタの一覧です。

### Parameter
| Name | Type | Default | Description | Remark |
| :--- | :--- | :--- | :--- | :--- |
| options | object | {} | コンポーネントのプロパティを含む JSON オブジェクト | options 内の値は必須でない |

---
# Sample Code

全てのパラメータを指定した場合のサンプルコードです。

```javascript
var space = kintone.app.record.getSpaceElement('space');
var textarea = new kintoneUIComponent.TextArea({
  label: 'Fruit',
  requiredIcon: true,
  value: 'Apple',
  error: 'Error occurred!',
  className: 'options-class',
  id: 'options-id',
  visible: true,
  disabled: false
});
space.appendChild(textarea);

textarea.addEventListener('change', function(event) {
  console.log(event);
});

textarea.addEventListener('focus', function(event) {
  console.log(event);
});
```
