<p>1．PRODUCT_MASTER(商品情報マスター)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>PRODUCT_CODE</td><td>CHAR(12)</td><td>商品コード (PK)</td></tr>
<tr><td>PRODUCT_NAME</td><td>VARCHAR(30)</td><td>商品名</td></tr>
<tr><td>MAKER_ID</td><td>CHAR(20)</td><td>メーカーID (FK)</td></tr>
<tr><td>CATEGORY_ID</td><td>CHAR(6)</td><td>カテゴリID (FK)</td></tr>
<tr><td>JAN_CODE</td><td>VARCHAR(13)</td><td>JANコード</td></tr>
<tr><td>PRICE</td><td>DECIMAL(14,2)</td><td>価格</td></tr>
<tr><td>COST_PRICE</td><td>DECIMAL(14,2)</td><td>原価</td></tr>
<tr><td>PRODUCT_STATE_ID</td><td>CHAR(2)</td><td>商品状態 (FK)</td></tr>
<tr><td>CREATED_AT</td><td>DATETIME</td><td>登録日時</td></tr>
<tr><td>UPDATED_AT</td><td>DATETIME</td><td>更新日時</td></tr>
<tr><td>WEIGHT_VALUE</td><td>DECIMAL(8,4)</td><td>重量値</td></tr>
<tr><td>WEIGHT_UNIT_ID</td><td>CHAR(2)</td><td>重量単位 (FK)</td></tr>
<tr><td>DELETE_FLAG</td><td>BOOLEAN</td><td>論理削除</td></tr>
</tbody>
</table>
<br>
<p>2．WAREHOUSE_MASTER(倉庫情報マスター)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>WAREHOUSE_ID</td><td>CHAR(3)</td><td>倉庫ID (PK)</td></tr>
<tr><td>LATITUDE</td><td>DECIMAL(10,7)</td><td>緯度</td></tr>
<tr><td>LONGITUDE</td><td>DECIMAL(10,7)</td><td>経度</td></tr>
<tr><td>WAREHOUSE_NAME</td><td>VARCHAR(60)</td><td>倉庫名</td></tr>
<tr><td>POSTAL_CODE</td><td>VARCHAR(12)</td><td>郵便番号</td></tr>
<tr><td>COUNTRY_CODE</td><td>CHAR(2)</td><td>国コード (FK)</td></tr>
<tr><td>PREFECTURE_CODE</td><td>VARCHAR(20)</td><td>県</td></tr>
<tr><td>CITY</td><td>VARCHAR(30)</td><td>市町村</td></tr>
<tr><td>ADDRESS_LINE</td><td>VARCHAR(100)</td><td>町名・番地</td></tr>
<tr><td>WAREHOUSE_TYPE_ID</td><td>CHAR(2)</td><td>倉庫タイプ (FK)</td></tr>
<tr><td>DELETE_FLAG</td><td>BOOLEAN</td><td>論理削除</td></tr>
</tbody>
</table>
<br>
<p>3．INVENTORY(商品在庫管理)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>PRODUCT_CODE</td><td>CHAR(12)</td><td>商品コード (PK)(FK)</td></tr>
<tr><td>WAREHOUSE_ID</td><td>CHAR(3)</td><td>倉庫ID (PK)(FK)</td></tr>
<tr><td>STOCK</td><td>INT</td><td>在庫数</td></tr>
<tr><td>SECTION_NO</td><td>INT</td><td>区画番号</td></tr>
<tr><td>SHELF_NO</td><td>INT</td><td>棚番号</td></tr>
<tr><td>COLUMN_NO</td><td>INT</td><td>列番号</td></tr>
<tr><td>SAFE_STOCK</td><td>INT</td><td>安全在庫数</td></tr>
<tr><td>LOT_NO</td><td>CHAR(20)</td><td>ロット番号</td></tr>
<tr><td>EXPIRATION_DATE</td><td>DATE</td><td>使用期限・賞味期限</td></tr>
</tbody>
  <br>
</table>
<p>4．WAREHOUSE_CONTACT(倉庫連絡先)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>CONTACT_ID</td><td>CHAR(3)</td><td>連絡先ID (PK)</td></tr>
<tr><td>WAREHOUSE_ID</td><td>CHAR(3)</td><td>倉庫ID (FK)</td></tr>
<tr><td>CONTACT_TYPE_ID</td><td>CHAR(2)</td><td>連絡先種別 (FK)</td></tr>
<tr><td>CONTACT_DETAIL</td><td>VARCHAR(60)</td><td>連絡内容</td></tr>
</tbody>
</table>
<br>
<p>5．TRANSACTION_HISTORY(入出庫履歴) </p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>TRANSACTION_ID</td><td>CHAR(12)</td><td>入出庫ID (PK)</td></tr>
<tr><td>EMPLOYEE_ID</td><td>CHAR(12)</td><td>担当者ID (FK)</td></tr>
<tr><td>TRANSACTION_REASON_ID</td><td>CHAR(2)</td><td>理由 (FK)</td></tr>
<tr><td>PRODUCT_CODE</td><td>CHAR(12)</td><td>商品コード (FK)</td></tr>
<tr><td>WAREHOUSE_ID</td><td>CHAR(3)</td><td>倉庫ID (FK)</td></tr>
<tr><td>TRANSACTION_DATE</td><td>DATETIME</td><td>日時</td></tr>
<tr><td>IN_OUT</td><td>CHAR(1)</td><td>I=入庫 / O=出庫</td></tr>
<tr><td>QUANTITY</td><td>INT</td><td>数量</td></tr>
<tr><td>TRANSACTION_STATE_ID</td><td>CHAR(2)</td><td>状態 (FK)</td></tr>
</tbody>
</table>
<br>
<p>6.PURCHASE_ORDER(発注管理)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>ORDER_ID</td><td>CHAR(12)</td><td>発注ID (PK)</td></tr>
<tr><td>PRODUCT_ID</td><td>CHAR(12)</td><td>商品ID (FK)</td></tr>
<tr><td>SUPPLIER_ID</td><td>CHAR(4)</td><td>仕入れ先ID (FK)</td></tr>
<tr><td>UNIT_PRICE</td><td>DECIMAL(10,2)</td><td>単価</td></tr>
<tr><td>ORDER_QUANTITY</td><td>INT</td><td>数量</td></tr>
<tr><td>ORDER_DATE</td><td>DATETIME</td><td>発注日</td></tr>
<tr><td>ORDER_STATE</td><td>CHAR(1)</td><td>発注ステータス</td></tr>  
<tr><td>DELIVERY_DATE</td><td>DATETIME</td><td>納期</td></tr>
<tr><td>DELETE_FLAG</td><td>BOOLEAN</td><td>論理削除</td></tr>
</tbody>
</table>
<br>
<p>7.CATEGORY(カテゴリ)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>CATEGORY_ID</td><td>CHAR(6)</td><td>カテゴリID (PK)</td></tr>
<tr><td>CATEGORY_NAME</td><td>VARCHAR(20)</td><td>カテゴリ名</td></tr>
</tbody>
</table>
<br>
<p>8.SUPPLIER(仕入れ先)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>SUPPLIER_ID</td><td>CHAR(4)</td><td>仕入れ先ID (PK)</td></tr>
<tr><td>SUPPLIER_NAME</td><td>VARCHAR(60)</td><td>企業名</td></tr>
<tr><td>SUPPLIER_ADDRESS</td><td>VARCHAR(100)</td><td>住所</td></tr>
<tr><td>DELETE_FLAG</td><td>BOOLEAN</td><td>論理削除</td></tr>
</tbody>
</table>

<p>9.SUPPLIER_CONTACT (仕入れ先連絡先)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>SUPPLIER_CONTACT_ID</td><td>CHAR(4)</td><td>仕入れ先連絡先ID (PK)</td></tr>
<tr><td>SUPPLIER_ID</td><td>CHAR(4)</td><td>仕入れ先ID (FK)</td></tr>
<tr><td>CONTACT_TYPE_ID</td><td>CHAR(1)</td><td>種別 (FK)</td></tr>
<tr><td>CONTACT_DETAIL</td><td>VARCHAR(60)</td><td>内容</td></tr>
</tbody>
</table>
<br>
<p>10：CONTACT_TYPE(連絡先種別)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>CONTACT_TYPE_ID</td><td>CHAR(1)</td><td>ID (PK)</td></tr>
<tr><td>CONTACT_TYPE</td><td>CHAR(8)</td><td>種別</td></tr>
</tbody>
</table>
<br>
<p>11.WAREHOUSE_TYPE(倉庫タイプ)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>WAREHOUSE_TYPE_ID</td><td>CHAR(1)</td><td>ID (PK)</td></tr>
<tr><td>WAREHOUSE_TYPE_NAME</td><td>CHAR(10)</td><td>倉庫タイプ</td></tr>
</tbody>
</table>
<br>
<p>12.PRODUCT_STATE(商品情報ステータス)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>PRODUCT_STATE_ID</td><td>CHAR(2)</td><td>ID (PK)</td></tr>
<tr><td>PRODUCT_STATE_NAME</td><td>VARCHAR(20)</td><td>状態名</td></tr>
</tbody>
</table>
<br>
<p>13.TRANSACTION_STATE(トランザクションステータス)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>TRANSACTION_STATE_ID</td><td>CHAR(1)</td><td>ID (PK)</td></tr>
<tr><td>TRANSACTION_STATE</td><td>VARCHAR(20)</td><td>状態名</td></tr>
</tbody>
</table>
<br>
<p>14.WEIGHT_UNIT(重量単位)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>WEIGHT_UNIT_ID</td><td>CHAR(2)</td><td>ID (PK)</td></tr>
<tr><td>WEIGHT_UNIT_NAME</td><td>VARCHAR(20)</td><td>単位名</td></tr>
</tbody>
</table>
<br>
<p>15.EMPLOYEE(社員)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>EMPLOYEE_ID</td><td>CHAR(12)</td><td>ID (PK)</td></tr>
<tr><td>EMPLOYEE_NAME</td><td>VARCHAR(60)</td><td>氏名</td></tr>
</tbody>
</table>
  
16.MAKER（メーカー)
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>MAKER_ID</td><td>CHAR(20)</td><td>ID (PK)</td></tr>
<tr><td>MAKER_NAME</td><td>VARCHAR(60)</td><td>メーカー名</td></tr>
<tr><td>MAKER_ADDRESS</td><td>VARCHAR(100)</td><td>住所</td></tr>
<tr><td>MAKER_ADDRESS</td><td>VARCHAR(100)</td><td>代表電話番号</td></tr>
<tr><td>DELETE_FLAG</td><td>BOOLEAN</td><td>論理削除</td></tr>
</tbody>
</table>
<br>
<p>17.MAKER_CONTACT (仕入れ先連絡先)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>MAKER_CONTACT_ID</td><td>CHAR(4)</td><td>連絡先ID (PK)</td></tr>
<tr><td>MAKER_ID</td><td>CHAR(20)</td><td>メーカーID (FK)</td></tr>
<tr><td>CONTACT_TYPE_ID</td><td>CHAR(1)</td><td>種別 (FK)</td></tr>
<tr><td>CONTACT_DETAIL</td><td>VARCHAR(60)</td><td>内容</td></tr>
</tbody>
</table>
<br>
18.COUNTRY_CODE(国コード)<br>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>COUNTRY_ID</td><td>CHAR(2)</td><td>ID (PK)</td></tr>
<tr><td>COUNTRY</td><td>VARCHAR(30)</td><td>国名</td></tr>
</tbody>
</table>
<br>
19.TRANSACTION_REASON(入出庫理由)
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>TRANSACTION_REASON_ID</td><td>CHAR(2)</td><td>ID (PK)</td></tr>
<tr><td>TRANSACTION_REASON</td><td>VARCHAR(30)</td><td>入出庫理由</td></tr>
</tbody>
20.EMPLOYEE(従業員)
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>EMPLOYEE_ID</td><td>CHAR(12)</td><td>ID (PK)</td></tr>
<tr><td>EMPLOYEE_NAME</td><td>VARCHAR(60)</td><td>従業員氏名</td></tr>
<tr><td>DELETE_FLAG</td><td>BOOLEAN</td><td>論理削除</td></tr>
</tbody>

</table>
