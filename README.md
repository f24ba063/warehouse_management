
No.	テーブル名	カラム名	型	制約	説明
<table>1 PRODUCT_MASTER
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td> PRODUCT_ID </td><td> BIGINT </td><td> PK	 </td><td> 商品コード </td></tr>
  <tr><td> PRODUCT_NAME </td><td> VARCHAR(255) </td><td> NOT NULL	 </td><td> 商品名 </td></tr>
  <tr><td> UNIT_OF_MEASURE </td><td> VARCHAR(10) </td><td> NOT NULL	 </td><td> 計測単位 (例: PCS, 箱, ケース) [拡張性向上] </td></tr>
  <tr><td> SAFETY_STOCK </td><td> INT </td><td> NOT NULL </td><td> 安全在庫数 </td></tr>
  <tr><td> MIN_ORDER_QTY </td><td> INT </td><td> NOT NULL </td><td> 最低発注数量 </td></tr>
  <tr><td> IS_LOT_MANAGED </td><td> BOOLEAN </td><td> NOT NULL </td><td> ロット管理対象フラグ </td></tr>
  <tr><td> IS_ACTIVE </td><td> BOOLEAN </td><td> NOT NULL </td><td> 有効フラグ </td></tr>
 </tbody>
</table>

<table>
<thead>2	WAREHOUSE_MASTER
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td> WAREHOUSE_ID </td><td> CHAR(5) </td><td> PK </td><td> 倉庫ID </td></tr>
  <tr><td> WAREHOUSE_NAME </td><td> VARCHAR(50) </td><td> NOT NULL </td><td> 倉庫名 </td></tr>
 </tbody>
</table>

<table>
<thead>5	LOCATION_MASTER
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td> WAREHOUSE_ID </td><td> CHAR(5) </td><td> PK, FK </td><td> 倉庫ID </td></tr>
  <tr><td> ZONE_ID </td><td> CHAR(3) </td><td> PK, FK </td><td> ゾーンID </td></tr>
  <tr><td> RACK_ID </td><td> CHAR(3) </td><td> PK, FK </td><td> ラックID </td></tr>
  <tr><td> SHELF_ID </td><td> CHAR(5) </td><td> PK, FK </td><td> シェルフID </td></tr>
  <tr><td> LOCATION_CODE </td><td> CHAR(16) </td><td> UNIQUE </td><td> 参照用コード (在庫実体参照キー) </td></tr>
  <tr><td> MAX_CAPACITY </td><td> INT </td><td>  </td><td> 最大収容数量 </td></tr>
 </tbody>
</table>

			
					
					
					
					
					

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>



<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>

6	PURCHASE_HEAD	ORDER_ID	CHAR(12)	PK	発注ID
		SUPPLIER_ID	CHAR(4)	FK (P.M.)	仕入れ先ID
		ORDER_DATE	DATE	NOT NULL	発注日 [追加]
		TOTAL_AMOUNT	DECIMAL(14, 2)		合計金額 (JPY)

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>

<table>
<thead>
 <tr><th>カラム名</th><th>型</th><th>制約</th><th>説明</tr>
</thead>
 <tbody>
  <tr><td>  </td><td>  </td><td>  </td><td>  </td></tr>
 </tbody>
</table>


15	PARTNER_MASTER	PARTNER_ID	CHAR(4)	PK	取引先ID (仕入先、得意先共通)
		PARTNER_TYPE	CHAR(1)	NOT NULL	種別 (S:仕入先, C:得意先, B:両方)
		PARTNER_NAME	VARCHAR(100)	NOT NULL	取引先名

7	PURCHASE_DETAIL	ORDER_ID	CHAR(12)	PK, FK	発注ID
		LINE_NO	INT	PK	行番号
		PRODUCT_ID	BIGINT	FK	商品ID
		UNIT_PRICE	DECIMAL(10, 2)	NOT NULL	発注単価 (JPY)
		ORDER_QUANTITY	INT	NOT NULL	数量
16	SALES_HEAD	SALES_ID	CHAR(12)	PK	出荷伝票ID
		CUSTOMER_ID	CHAR(4)	FK (P.M.)	得意先ID
		SHIPPING_DATE	DATE	NOT NULL	出荷予定日
17	SALES_DETAIL	SALES_ID	CHAR(12)	PK, FK	出荷伝票ID
		LINE_NO	INT	PK	行番号
		PRODUCT_ID	BIGINT	FK	商品ID
		UNIT_PRICE	DECIMAL(10, 2)	NOT NULL	販売単価 (JPY)
		ORDER_QUANTITY	INT	NOT NULL	注文数量
No.	テーブル名	カラム名	型	制約	説明
8	INVENTORY_STOCK	STOCK_ID	BIGINT	PK	在庫実体ID (代理主キー)
		PRODUCT_ID	BIGINT	FK	商品ID
		LOCATION_CODE	CHAR(16)	FK	ロケーションコード
		LOT_NO	CHAR(20)	FK	ロット番号
		(複合制約)		UNIQUE(PRODUCT_ID, LOCATION_CODE, LOT_NO)	在庫の唯一性の定義
		STOCK	INT	NOT NULL	現在の在庫数 (真実)
9	SLIP_HEAD	SLIP_ID	CHAR(12)	PK	伝票番号
		SLIP_STATE_ID	CHAR(1)	NOT NULL, FK	伝票の状態
10	SLIP_DETAIL	SLIP_ID	CHAR(12)	PK, FK	伝票番号
		LINE_NO	INT	PK	行番号
		PRODUCT_ID	BIGINT	FK	商品ID
		QUANTITY	INT	NOT NULL	処理数量
11	STOCK_MOVEMENT	MOVEMENT_ID	BIGINT	PK	移動履歴ID (代理主キー)
		SLIP_ID	CHAR(12)	FK	元伝票ID
		LINE_NO	INT	FK	元伝票行番号
		MOVE_SEQ	INT		移動時の連番
		(複合制約)		UNIQUE(SLIP_ID, LINE_NO, MOVE_SEQ)	履歴ログの一意性定義
		PRODUCT_ID	BIGINT	FK	商品ID (分析・監査対応)
		LOT_NO	CHAR(20)	NOT NULL, FK	移動ロット
		LOCATION_FROM	CHAR(16)	FK	移動元 [NULL許容]
		LOCATION_TO	CHAR(16)	FK	移動先 [NULL許容]
		STOCK_CHANGE	INT	NOT NULL	増減量 (IN=+ / OUT=-)
18	ALLOCATION_HEAD	ALLOCATE_HEAD_ID	CHAR(12)	PK	引当ヘッダID
		SALES_ID	CHAR(12)	FK	元の出荷伝票ID
		STATUS	CHAR(1)	NOT NULL	引当ステータス
12	ALLOCATION_STOCK	SLIP_ID	CHAR(12)	PK, FK	引当元伝票ID
		LINE_NO	INT	PK, FK	引当元行番号
		ALLOCATION_ID	BIGINT	PK	引当識別子
		LOT_NO	CHAR(20)	FK	引当対象ロット
		ALLOCATED_QUANTITY	INT	NOT NULL	引当済み数量
No.	テーブル名	カラム名	型	制約	説明


14	LOT_MASTER	PRODUCT_ID	BIGINT	PK, FK	ロットの対象商品
		LOT_NO	CHAR(20)	PK	ロット番号
		CREATION_DATE	DATETIME	NOT NULL	ロット生成日時 (入庫時)
		SUPPLIER_ID	CHAR(4)	FK (P.M.)	仕入先ID
		EXPIRATION_DATE	DATE		ロット有効期限
		QC_STATUS_ID	CHAR(1)	NOT NULL	品質管理ステータス
13	LOT_COST	PRODUCT_ID	BIGINT	PK, FK	ロットの対象商品
		LOT_NO	CHAR(20)	PK, FK	ロット番号
		CONVERTED_COST_JPY	DECIMAL(14, 2)	NOT NULL	日本円換算後の原価 (JPY)

サイズと重量も必須でありこれも国によって単位が違うから調整素材を導入した。<br>
