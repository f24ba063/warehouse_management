<table>
1．商品情報マスター(PRODUCT_MASTER) <br>
PRODUCT_CODE(CHAR(12)) (商品コード)<br>
PRODUCT_NAME (VARCHAR(30)) (商品名)<br>
MAKER_ID (CHAR(20)) —外部キー (メーカーID)<br>
CATEGORY_ID (CHAR(6))—外部キー (カテゴリID)<br>
PRICE (DECIMAL(14,2)) (価格)<br>
COST_PRICE (DECIMAL(14,2)) (原価)<br>
PRODUCT_STATE_ID (CHAR(2)) —外部キー (商品情報ステータス)<br>
CREATED_AT (DATETIME) (登録日時)<br>
UPDATED_AT (DATETIME) (更新日時)<br>
WEIGHT_VALUE (DECIMAL(8,4)) (重量値)<br>
WEIGHT_UNIT_ID(CHAR(2)) —外部キー (重量単位)<br>
DELETE_FLG(BOOLEAN)<br>
<br>
2．WAREHOUSE_MASTER倉庫情報マスター <br>
WAREHOUSE_ID (CHAR(3)) (倉庫ID)<br>
WAREHOUSE_NAME (VARCHAR(60) (倉庫名)<br>
POSTAL_CODE (VARCHAR(12)) (倉庫所在地・郵便番号)<br>
COUNTRY_CODE (CHAR(2)) —外部キー(倉庫所在地・国)<br>
PREFECTURE_CODE(VARCHAR(20)) (倉庫所在地・県)<br>
CITY (VARCHAR(30)) (倉庫所在地・市町村)<br>
ADDRESS_LINE(VARCHAR(100)(倉庫所在地・町名・番地・建物名)<br>
WAREHOUSE_TYPE_ID(CHAR(2)) —外部キー (倉庫タイプ)<br>
DELETE_FLG(BOOLEAN)<br>
<br>
3．WAREHOUSE_CONTACT倉庫連絡先 <br>
CONTACT_ID (CHAR(3)) (連絡先ID)<br>
WAREHOUSE_ID (CHAR(3)) —外部キー (倉庫ID)<br>
CONTACT_TYPE_ID (CHAR(2)) —外部キー (連絡先種別)<br>
CONTACT_DETAIL(VARCHAR(60)) —バリデーション（電話番号なら数字10～13桁、メールなら@、.がつく） <br>
<br>
4．INVENTORY(商品在庫管理)<br>
PRODUCT_CODE(CHAR(12)) —外部キー (商品コード)<br>
WAREHOUSE_ID (CHAR(3)) —外部キー (倉庫ID)<br>
STOCK (INT) (在庫数) <br>
SECTION_NO (INT) (配置区画番)<br>
SHELF_NO (INT) (配置棚番)<br>
COLUMN_NO (INT) (列番)<br>
SAFE_STOCK (INT) (安全在庫数)<br>
LOT_NO (CHAR(20)) (ロット番号)<br>
<br>
5．TRANSACTION_HISTORY(入出庫履歴)<br>
TRANSACTION_ID (CHAR(12)) (入出庫ID)<br>
EMPLOYEE_ID (CHAR(12)) (担当者ID) —外部キー<br>
TRANSACTION_REASON_ID(CHAR(2)) —外部キー(入出庫理由)<br>
PRODUCT_CODE (CHAR(12)) —外部キー (1.商品コード)<br>
WAREHOUSE_ID (CHAR(3)) —外部キー (11.倉庫ID)<br>
TRANSACTION_DATE(DATETIME) (日付)<br>
IN_OUT(CHAR(1))I =入庫、O=出庫<br>
QUANTITY (INT) (個数)<br>
TRANSACTION_STATE_ID (CHAR(2)) (トランザクションステータス) —外部キー<br>
<br>
6：PURCHASE_ORDER(仕入れ先・発注管理 )<br>
ORDER_ID (CHAR(12))自動採番 (発注ID)<br>
PRODUCT_ID (CHAR(12)) —外部キー (商品ID)<br>
SUPPLIER_ID (CHAR(4)) —外部キー (仕入れ先ID)<br>
UNIT_PRICE (DECIMAL(10,2)) (発注単価)<br>
ORDER_QUANTITY (INT) (発注単位)<br>
ORDER_DATE (DATETIME) (発注日)<br>
DELIVERY_DATE (DATETIME) (納期)<br>
DELETE_FLG(BOOLEAN)<br>
<br>
7：CATEGORY(カテゴリ)<br>
CATEGORY_ID (CHAR(6)) (カテゴリID)<br>
CATEGORY_NAME (VARCHAR(20)) (カテゴリ名)<br>
<br>
8：SUPPLIER(仕入れ先 )<br>
SUPPLIER_ID (CHAR(4)) (仕入れ先ID)<br>
SUPPLIER_NAME(VARCHAR(60)) (仕入れ先企業名)<br>
SUPPLIER_ADDRESS (VARCHAR(100)) (仕入れ先住所)<br>
DELETE_FLG(BOOLEAN) (仕入れ先ソフトデリートフラグ)<br>
<br>
9：SUPPLIER_CONTACT (仕入れ先連絡先 )<br>
SUPPLIER_CONTACT_ID (CHAR(4))--自動採番 (仕入れ先連絡先ID)<br>
SUPPLIER_ID (char(4))—外部キー (仕入れ先ID)→8<br>
CONTACT_TYPE_ID (CHAR(1)) —外部キー (連絡先種別)→10<br>
CONTACT_DETAIL(VARCHAR(60))(連絡先)<br>
<br>
10：CONTACT_TYPE(連絡先種別)<br>
CONTACT_TYPE_ID (CHAR(1)) (連絡先種別ID)<br>
CONTACT_TYPE (CHAR(8)) (連絡先種別)<br>
<br>
11：WAREHOUSE_TYPE(倉庫タイプ)<br>
WAREHOUSE_TYPE_ID (CHAR(1)) (倉庫タイプID)<br>
WAREHOUSE_TYPE_NAME (CHAR(10)) (倉庫タイプ)<br>
<br>
12：PRODUCT_STATE(商品情報ステータス )<br>
PRODUCT_INFORMATION_ID（CHAR(2)）(商品情報ID)<br>
PRODUCT_STATE_NAME (VARCHAR(20)) (商品情報ステータス)<br>
<br>
13：TRANSACTION_STATE(トランザクションステータス )<br>
TRANSACTION_STATE_ID (CHAR(1)) (トランザクションステータスID)<br>
TRANSACTION_STATE（VARCHAR(20)） (トランザクションステータス)<br>
<br>
14：WEIGHT_UNIT(重量単位)<br>
WEIGHT_UNIT_ID (CHAR(2))(重量単位ID)<br>
WEIGHT_UNIT_NAME (VARCHAR(20)) (重量単位名)<br>
<br>
15：EMPLOYEE(社員)<br>
EMPLOYEE_ID(CHAR(12))<br>
EMPLOYEE_NAME(VARCHAR(60))<br>
<br>
16：MAKER（メーカー）<br>
MAKER_ID(CHAR(20))（メーカーID）<br>
MAKER_NAME(VARCHAR(60))<br>
MAKER_ADDRESS(VARCHAR(100))<br>
DELETE_FLG(BOOLEAN)<br>
<br>
17：MAKER_CONTACT (仕入れ先連絡先 )<br>
MAKER_CONTACT_ID (CHAR(4))--自動採番 (メーカー連絡先ID)<br>
MAKER_ID (char(4))—外部キー (メーカーID)<br>
CONTACT_TYPE_ID (CHAR(1)) —外部キー (連絡先種別)→10<br>
CONTACT_DETAIL(VARCHAR(60))(連絡先)<br>
<br>
18：COUNTRY(国コード)<br>
COUNTRY_ID(CHAR(2))<br>
</table>
COUNTRY（VARCHAR(30)）<br>
