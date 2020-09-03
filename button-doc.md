# Overview

Button は、ボタンを表示します。

```KUCComponentRenderer {"id":"_render"}
var component = new Button({
  text: 'Submit',
  type: 'submit',
  visible : true
});
```

---

# Specification

## Property

使用できるプロパティの一覧です。プロパティを指定して値を更新することができます。

| Name | Type | Default | Description | Remark |
| :--- | :--- | :--- | :--- | :--- |
| className | string | "" | コンポーネントの class 名 |  |
| id | string | "" | コンポーネントの id 名 |  |
| text | string | "" | ボタンに表示するテキスト ||
| type | string | "normal" | ボタンのデザインタイプ | 以下を指定できる<br>"normal" : Gray(#f7f9fA)<br>"submit" : Blue(#3498db)<br>"alert" : Red(#e74c3c)<br><br>上記以外（null、”hoge”など）を指定した場合は”normal”となる。 |
| disabled | boolean | false | コンポーネントの編集可/不可設定 ||
| visible | boolean | true | コンポーネントの表示/非表示設定 ||

## Event

指定できるイベントの一覧です。

| Name | Type | Description | Remark |
| :--- | :--- | :--- | :--- |
| click | function | フォーカスされた時のイベントハンドラ | 引数には Event の event オブジェクトをとる |

## Constructor

Button(options)  
使用できるコンストラクタの一覧です。

### Parameter

| Name | Type | Default | Description | Remark |
| :--- | :--- | :--- | :--- | :--- |
| options | object | {} | コンポーネントのプロパティを含む JSON オブジェクト | options 内の値は必須でない |

---

# Sample Code

全てのパラメータを指定した場合のサンプルコードです。

```javascript
var header = kintone.app.getHeaderMenuSpaceElement();
var button = new kintoneUIComponent.Button({
    text: 'Submit',
    type: 'submit',
    className: 'options-class',
    id: 'options-id',
    visible: true,
    disabled: false
});
header.appendChild(button);

button.addEventListener('click', function(event) {
  console.log(event);
});
```
