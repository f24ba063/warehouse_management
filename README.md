<p>1．PRODUCT_MASTER(商品情報マスター)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td> PRODUCT_ID        </td><td> BIGINT        </td><td> 商品コード (PK)(自動採番)  </td></tr>
<tr><td> PRODUCT_NAME      </td><td> VARCHAR(30)   </td><td> 商品名                    </td></tr>
<tr><td> MAKER_ID          </td><td> CHAR(20)      </td><td> メーカーID (FK)           </td></tr>
<tr><td> CATEGORY_ID       </td><td> CHAR(6)       </td><td> カテゴリID (FK)           </td></tr>
<tr><td> JAN_CODE          </td><td> VARCHAR(13)   </td><td> JANコード                 </td></tr>
<tr><td> PRICE             </td><td> DECIMAL(14,2) </td><td> 価格                      </td></tr>
<tr><td> COST_PRICE        </td><td> DECIMAL(14,2) </td><td> 原価                      </td></tr>
<tr><td> PRODUCT_STATE_ID  </td><td> CHAR(2)       </td><td> 商品状態(FK)              </td></tr>
<tr><td> WIDTH             </td><td> number(10,2)  </td><td> 幅                       </td></tr>
<tr><td> HEIGHT            </td><td> number(10,2)  </td><td> 高さ                     </td></tr>
<tr><td> DEPTH             </td><td> number(10,2)  </td><td> 奥行き                   </td></tr>
<tr><td> SCALE_ID        </td><td> CHAR(2)       </td><td> 寸法単位(FK)             </td></tr>
<tr><td> CREATED_AT        </td><td> DATETIME      </td><td> 登録日時                 </td></tr>
<tr><td> UPDATED_AT        </td><td> DATETIME      </td><td> 更新日時                 </td></tr>
<tr><td> WEIGHT_VALUE      </td><td> DECIMAL(8,4)  </td><td> 重量値                   </td></tr>
<tr><td> WEIGHT_UNIT_ID    </td><td> CHAR(2)       </td><td> 重量単位 (FK)            </td></tr>
<tr><td> DELETE_FLAG       </td><td> BOOLEAN       </td><td> 論理削除                 </td></tr>
</tbody>
</table>
<br>

<p>2．WAREHOUSE_MASTER(倉庫情報マスター)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>WAREHOUSE_ID</td><td>CHAR(5)</td><td>倉庫ID (PK)</td></tr>
<tr><td>WAREHOUSE_NAME</td><td>VARCHAR(60)</td><td>倉庫名</td></tr>
<tr><td>LATITUDE</td><td>DECIMAL(10,7)</td><td>緯度</td></tr>
<tr><td>LONGITUDE</td><td>DECIMAL(10,7)</td><td>経度</td></tr>
<tr><td>POSTAL_CODE</td><td>VARCHAR(12)</td><td>郵便番号</td></tr>
<tr><td>COUNTRY_CODE</td><td>CHAR(2)</td><td>国コード(ISO3166-1準拠) (FK)</td></tr>
<tr><td>REGION_CODE</td><td>VARCHAR(10)</td><td>県・地域（ISO3166-2準拠)(FK)</td></tr>
<tr><td>CITY</td><td>VARCHAR(30)</td><td>市町村</td></tr>
<tr><td>ADDRESS_LINE</td><td>VARCHAR(100)</td><td>町名・番地</td></tr>
<tr><td>WAREHOUSE_TYPE_ID</td><td>CHAR(1)</td><td>倉庫タイプ (FK)</td></tr>
<tr><td>DELETE_FLAG</td><td>BOOLEAN</td><td>論理削除</td></tr>
</tbody>
</table>
<br>

<p>3．INVENTORY(商品在庫管理)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>PRODUCT_ID</td><td>BIGINT</td><td>商品コード (PK)(FK)</td></tr>
<tr><td>STOCK</td><td>INT</td><td>在庫数</td></tr>
<tr><td>LOCATION_ID</td><td>CHAR(20)</td><td>商品所在地を一意に識別するコード(FK)(PK)</td></tr>
<tr><td>SAFE_STOCK</td><td>INT</td><td>安全在庫数</td></tr>
<tr><td>LOT_NO</td><td>CHAR(20)</td><td>ロット番号(PK)</td></tr>
<tr><td>EXPIRATION_DATE</td><td>DATETIME</td><td>使用期限・賞味期限</td></tr>
</tbody>
  <br>
</table>

<p>4．LOCATION_MASTER(商品所在地マスター)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
  <tr><td>　LOCATION_ID　</td><td>　CHAR(20)　</td><td>　区画を一意に識別するID(PK)　</td></tr>
  <tr><td>　WAREHOUSE_ID　</td><td>　CHAR(5)　</td><td>　所属する倉庫(FK)　</td></tr>
  <tr><td>　ZONE_ID　</td><td>　CHAR(3)　</td><td>　冷蔵、大型機械などのゾーンのID(FK)　</td></tr>
  <tr><td>　RACK_ID　</td><td>　CHAR(3)　</td><td>　どの棚(ラック)か(FK)　</td></tr>
  <tr><td>　SHELF_ID　</td><td>　CHAR(5)　</td><td>　どの段(シェルフ)にするか(FK)　</td></tr>
  <tr><td> DELETE_FLAG       </td><td> BOOLEAN       </td><td> 論理削除     </td></tr>
</tbody>
</table>
<br>

<p>5．T_ZONE(区画マスター)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td> ZONE_ID　  </td><td> CHAR(3)   　</td><td> 冷蔵、大型機械などのゾーン(PK) </td></tr>
<tr><td> ZONE_NAME　</td><td> VARCHAR(30) </td><td> ゾーンの実体名                </td></tr>
  <tr><td> DELETE_FLAG       </td><td> BOOLEAN       </td><td> 論理削除     </td></tr>
</tbody>
</table>
<br>

<p>6．T_RACK(ラック番号マスター)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>　RACK_ID　</td><td>　CHAR(3)　</td><td>　ラックID(PK)　</td></tr>
<td>　RACK_NO　</td><td>　INT　</td><td>　ラックの実体番号　</td></tr>
  <tr><td> DELETE_FLAG       </td><td> BOOLEAN       </td><td> 論理削除     </td></tr>
</tbody>
</table>
<br>

<p>6．SHELF_MASTER(シェルフ番号マスター)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
  <tr><td> SHELF_ID　  </td><td> CHAR(5) </td><td> 棚ID(PK)        </td></tr>
  <tr><td> SHELF_NO　  </td><td> INT     </td><td> シェルフ実体番号 </td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
<br>



<p>7．TRANSACTION_HISTORY(入出庫履歴) </p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>TRANSACTION_ID</td><td>INT</td><td>入出庫ID (PK)(自動採番)</td></tr>
<tr><td>SLIP_ID</td><td> char(12)</td><td伝票票コード (FK)</td></tr>
<tr><td>PRODUCT_ID</td><td>BIGINT</td><td>商品コード (FK)</td></tr>
<tr><td>WAREHOUSE_ID</td><td>CHAR(5)</td><td>倉庫ID (FK)</td></tr>
<tr><td>TRANSACTION_DATE</td><td>DATETIME</td><td>移動日時</td></tr>
<tr><td>TRANSACTION_REASON_ID</td><td>CHAR(2)</td><td>入出庫理由 (FK)</td></tr>
<tr><td>TRANSACTION_STATE_ID</td><td>CHAR(1)</td><td>状態 (FK)</td></tr>
</tbody>
</table>
<br>

<p>8.PURCHASE_ORDER(発注管理)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>ORDER_ID</td><td>CHAR(12)</td><td>発注ID (PK)</td></tr>
<tr><td>PRODUCT_ID</td><td>BIGINT</td><td>商品ID (FK)</td></tr>
<tr><td>SUPPLIER_ID</td><td>CHAR(4)</td><td>仕入れ先ID (FK)</td></tr>
<tr><td>UNIT_PRICE</td><td>DECIMAL(10,2)</td><td>単価</td></tr>
<tr><td>ORDER_QUANTITY</td><td>INT</td><td>数量</td></tr>
<tr><td>ORDER_DATE</td><td>DATETIME</td><td>発注日</td></tr>
<tr><td>ORDER_STATE</td><td>CHAR(1)</td><td>発注ステータス(FK)</td></tr>  
<tr><td>DELIVERY_DATE</td><td>DATETIME</td><td>納期</td></tr>
<tr><td>DELETE_FLAG</td><td>BOOLEAN</td><td>論理削除</td></tr>
</tbody>
</table>
<br>

<p>9.CATEGORY(商品カテゴリ)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>CATEGORY_ID</td><td>CHAR(6)</td><td>カテゴリID (PK)</td></tr>
<tr><td>CATEGORY_NAME</td><td>VARCHAR(20)</td><td>カテゴリ名</td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
<br>

<p>10.SUPPLIER(仕入れ先)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>SUPPLIER_ID</td><td>CHAR(4)</td><td>仕入れ先ID (PK)</td></tr>
<tr><td>SUPPLIER_NAME</td><td>VARCHAR(60)</td><td>企業名</td></tr>
<tr><td>COUNTRY_CODE</td><td>CHAR(2)</td><td>国コード(ISO3166-1準拠) (FK)</td></tr>
<tr><td>REGION_CODE</td><td>VARCHAR(10)</td><td>県・地域（ISO3166-2準拠)(FK)</td></tr>
<tr><td>CITY</td><td>VARCHAR(30)</td><td>市町村</td></tr>
<tr><td>ADDRESS_LINE</td><td>VARCHAR(100)</td><td>町名・番地</td></tr>
  <tr><td>DELETE_FLAG</td><td>BOOLEAN</td><td>論理削除</td></tr>
</tbody>
</table>
<br>

<p>11.CONTACT (連絡先マスター)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>SUPPLIER_CONTACT_ID</td><td>CHAR(4)</td><td>仕入れ先連絡先ID (PK)</td></tr>
<tr><td>SUPPLIER_ID</td><td>CHAR(4)</td><td>仕入れ先ID (FK)</td></tr>
<tr><td>CONTACT_TYPE_ID</td><td>CHAR(1)</td><td>種別 (FK)</td></tr>
<tr><td>CONTACT_DETAIL</td><td>VARCHAR(60)</td><td>内容</td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
<br>

<p>12：CONTACT_TYPE(連絡先種別)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>CONTACT_TYPE_ID</td><td>CHAR(1)</td><td>ID (PK)</td></tr>
<tr><td>CONTACT_TYPE</td><td>CHAR(8)</td><td>種別</td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
<br>

<p>13.WAREHOUSE_TYPE(倉庫タイプ)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>WAREHOUSE_TYPE_ID</td><td>CHAR(1)</td><td>ID (PK)</td></tr>
<tr><td>WAREHOUSE_TYPE_NAME</td><td>CHAR(10)</td><td>倉庫タイプ</td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
<br>

<p>14.PRODUCT_STATE(商品情報ステータス)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>PRODUCT_STATE_ID</td><td>CHAR(2)</td><td>ID (PK)</td></tr>
<tr><td>PRODUCT_STATE_NAME</td><td>VARCHAR(20)</td><td>状態名</td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
<br>

<p>15.TRANSACTION_STATE(トランザクションステータス)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>TRANSACTION_STATE_ID</td><td>CHAR(1)</td><td>ID (PK)</td></tr>
<tr><td>TRANSACTION_STATE</td><td>VARCHAR(20)</td><td>状態名</td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
<br>

<p>16.WEIGHT_UNIT(重量単位)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>WEIGHT_UNIT_ID</td><td>CHAR(2)</td><td>ID (PK)</td></tr>
<tr><td>WEIGHT_UNIT_NAME</td><td>VARCHAR(20)</td><td>単位名</td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
<br>

<p>17.EMPLOYEE(社員)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>EMPLOYEE_ID</td><td>CHAR(12)</td><td>ID (PK)</td></tr>
<tr><td>EMPLOYEE_NAME</td><td>VARCHAR(60)</td><td>氏名</td></tr>
<tr><td>DEPARTMENT_ID</td><td>INT</td><td>所属部署ID(FK)</td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
  
18.MAKER（メーカー)
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>MAKER_ID</td><td>CHAR(20)</td><td>ID (PK)</td></tr>
<tr><td>MAKER_NAME</td><td>VARCHAR(60)</td><td>メーカー名</td></tr>
<tr><td>COUNTRY_CODE</td><td>CHAR(2)</td><td>国コード(ISO3166-1準拠) (FK)</td></tr>
<tr><td>REGION_CODE</td><td>VARCHAR(10)</td><td>県・地域（ISO3166-2準拠)(FK)</td></tr>
<tr><td>CITY</td><td>VARCHAR(30)</td><td>市町村</td></tr>
<tr><td>ADDRESS_LINE</td><td>VARCHAR(100)</td><td>町名・番地</td></tr>
<tr><td>DELETE_FLAG</td><td>BOOLEAN</td><td>論理削除</td></tr>
</tbody>
</table>
<br>

</table>
19.COUNTRY_CODE(国コードマスター)<br>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>COUNTRY_CODE</td><td>CHAR(2)</td><td>ID (PK)</td></tr>
<tr><td>COUNTRY_NAME_JA</td><td>VARCHAR(30)</td><td>日本語国名</td></tr>
<tr><td>COUNTRY_NAME_EN</td><td>VARCHAR(30)</td><td>英語国名</td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
<br>

20.TRANSACTION_REASON(入出庫素性マスター)
<table>
  <thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>TRANSACTION_REASON_ID</td><td>CHAR(2)</td><td>ID (PK)</td></tr>
<tr><td>TRANSACTION_REASON</td><td>VARCHAR(30)</td><td>入出庫理由</td></tr>
<tr><td>IN_OUT</td><td>CHAR(1)</td><td>I=入庫 / O=出庫</td></tr>
</tbody>
</table>

21.REGION_MASTER(地域マスター)
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>REGION_CODE</td><td>VARCHAR(7)</td><td>リージョン番号 (PK)</td></tr>
<tr><td>COUNTRY_CODE</td><td>CHAR(2)</td><td>所属国コード(PK)(FK)</td></tr>
<tr><td>REGION_NAME_LOCAL</td><td>VARCHAR(100)</td><td>現地語地域名</td></tr> 
</tbody>
</table>

22.SCALE_MASTER(寸法単位マスター)
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>SCALE_ID</td><td>CHAR(2)</td><td>寸法単位ID (PK)</td></tr>
<tr><td>SCALE_UNIT</td><td>CHAR(12)</td><td>寸法単位</td></tr>
</tbody>
</table>

23.ORDER_STATE_MASTER(発注ステータスマスター)
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>ORDER_STATE_ID</td><td>CHAR(1)</td><td>発注ステータスID (PK)</td></tr>
<tr><td>ORDER_STATE</td><td>CHAR(12)</td><td>発注ステータス</td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
<br>

<p>24.DEPARTMENT_MASTER(所属部署マスター)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td>DEPARTMENT_ID</td><td>INT</td><td>所属部署ID (PK)</td></tr>
<tr><td>DEPARTMENT</td><td>CHAR(12)</td><td>所属部署名>td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
<br />

<p>25.SLIP_ID(入出庫伝票テーブル)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td> SLIP_ID </td><td> CHAR(12) </td><td> 伝票番号(PK) </td></tr>
<tr><td> TYPE </td><td> CHAR(1) </td><td> 'I'＝入庫　'O'=出庫 </td></tr>
<tr><td> EMPLOYEE_ID </td><td> CHAR(12) </td><td> 担当者ID(FK) </td></tr>
<tr><td> WAREHOUSE_ID </td><td> CHAR(5) </td><td> 倉庫ID(FK) </td></tr>
<tr><td> DESTINATION_ID </td><td> CHAR(6) </td><td> 出庫先(入庫はNULL)(FK) </td></tr>
<tr><td> STATUS </td><td> CHAR(1) </td><td>  'D'=下書き 'C'=確定(FK)  </td></tr>
<tr><td> CREATED_AT </td><td> DATETIME </td><td> 作成日時 </td></tr>
<tr><td> UPDATED_AT </td><td> DATETIME </td><td> 更新日時 </td></tr>
</tbody>
</table>
<br />

<p>26.SLIP_DETAIL(伝票商品詳細)</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td> SLIP_ID </td><td> CHAR(12) </td><td> ID(PK)(FK) </td></tr>
<tr><td> LINE_NO </td><td> INT </td><td> 行番号(PK) </td></tr>
<tr><td> PRODUCT_ID </td><td> BIGINT </td><td> 商品コード(FK) </td></tr>
<tr><td> QUANTITY </td><td> INT </td><td> 数量 </td></tr>
<tr><td> SHELF </td><td> VARCHAR </td><td> 棚番号 </td></tr>
<tr><td> REMARK </td><td> VARCHAR(50) </td><td> 備考 </td></tr>
</tbody>
</table>

<p>27.ALLOCATION（引き当てテーブル）</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
<tr><td> ALLOCATION_ID    </td><td> BIGINT    </td><td> 引き当てID（自動採番）(PK)</td></tr>
<tr><td> SLIP_ID          </td><td> CHAR(12)  </td><td> (FK)                    </td></tr>
<tr><td> PRODUCT_ID       </td><td> BIGINT    </td><td> (FK)                    </td></tr>
<tr><td> LOCATION_ID      </td><td> CHAR(20)  </td><td> (FK)                    </td></tr>
<tr><td> LOT_NO           </td><td> CHAR(20)  </td><td> (FK)                    </td></tr>
<tr><td> COUNT            </td><td> INT       </td><td>                         </td></tr>
<tr><td> PRIORITY         </td><td> CHAR(1)   </td><td> (FK)                    </td></tr>
<tr><td> ALLOCATION_STATE </td><td> CHAR(1)   </td><td> (FK)                    </td></tr>
</tbody>
</table>
<br />

<p>28.PRIORITY（優先度マスター）</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
  <tr><td> PRIORITY_ID   </td><td> CHAR(1) </td><td> (pk) </td></tr>
  <tr><td> PRIORITY_NAME </td><td> CHAR(8) </td><td>      </td></tr>
  <tr><td> DELETE_FLAG </td><td> BOOLEAN </td><td> 論理削除        </td></tr>
</tbody>
</table>
<br />
<tr><td>    </td><td></td><td>    </td></tr>

<p>29.ALLOCATION_STATE（引き当てステータスマスター）</p>
<table>
<thead><tr><th>カラム名</th><th>型</th><th>制約</th></tr></thead>
<tbody>
  <tr><td> ALLOCATION_STATE_ID   </td><td> CHAR(1)  </td><td>  (PK)  </td></tr>
  <tr><td> ALLOCATION_STATE_NAME </td><td> CHAR(10) </td><td>    </td></tr>
</tbody>
</table>
<br />

<tr><td>    </td><td></td><td>    </td></tr>

想定：建築資材を主眼に置いた。数十メートルスケールの資材を考えている。<br>
重量については数値と単位を切り離すことで、一定の柔軟性を獲得する。<br>
グラムとポンド、メートルとヤードの互換性を暫定的に獲得。<br>
当初は物品の入出を管理することだけが目的で作成していったが、管理上必要なことを考えていくと<br>
責任の所在を明確にするために作業履歴にかかわる担当社員のテーブルを作成し<br>
倉庫同士の連携を想定するために座標を獲得し外国進出に際しては<br>
どこの通貨建てで調達するかも考え通貨の概念も導入し、トラック積載に関しては<br>
サイズと重量も必須でありこれも国によって単位が違うから調整素材を導入した。<br>
