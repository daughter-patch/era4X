era4X用建艦&装備更新時色々表示パッチver3

◇パッチの目的
色々と欲しかった表示を追加する為のパッチでした。
表示回りは本体へと取り込まれたので、修正用の差分のみです。


◇具体的な変更内容
艦載機の場合に必要な表示が欠けていたので追加。
艦載機の搭載数(攻撃回数に更に掛けられる事になる)をDPS表示に反映される様に。
(CHANGE_EQUIP.ERBおよびEQUIP_STATUS_DESCRIPTION.ERB)

◇備考


◇履歴
2022/11/16版
建艦時の必要資材の表示機能のみで初公開

2022/11/19版
資材確認のミス(たぶんプレイヤー以外が呼んだ時でも一部の資材確認の表示が出る)を修正
他勢力の建艦時にも艦船の性能・説明が表示されたミスを修正
必要資材確認と表示をUSE_RESOURCE_CHECK.ERBの「@USE_RESOURCE_CHECK」として関数化
@BUILD_SHIP・@BUILD_ORIGIN_SHIPの資材関係の処理をUSE_RESOURCE_CHECKで置き換え
EQUIP_UPDATE.ERBにおける各種装備更新が装備種ごとに別ERB・別関数で実行されていたのををCHANGE_EQUIP.ERBの@CHANGE_EQIPに統合
	CHANGE_EQUIP.ERBは装備更新関数を統合するのが目的であるものの、他勢力AI(AI_COUNTRY_(数値).ERB)の処理は旧来の処理のまま
装備更新時に装備の値段・武器の属性の表示を追加

2022/11/25版
装備更新時の性能表示を@SPEC_DISPLAYとして分離
新旧装備の性能比較を追加(@SPEC_DISPLAY)
艦船購入の性能表示を@SHIP_STATUS_DISPLAYとして分離
艦船購入の性能表示に積載量とオプションスロットの項目を追加(@SHIP_STATUS_DISPLAY)
武器の性能にDPTの表示を追加
必要な資材・価格の隣に利用できる資材・所持金を表示する様に変更
自分の港で装備更新する時には必要価格・所持金を灰色に(無料で出来るので)
装備のデータ表示をEQUIP_STATUS_DESCRIPTION.ERBの@EQUIP_STATUS_DESCRIPTIONとして分離
バグ修正：装甲以外の装備更新時にプレイヤー以外の勢力は問答無用で金が取られていたのを「その勢力から見て他勢力の港で更新した場合のみ」(プレイヤーと同じ条件)へ修正(装備種名.ERB)

2022/11/25版(2.1)
文字色を戻す命令を欠けさせてしまっていた艦船データを修正

2022/11/25版(2.2)
@USE_RESOURCE_CHECKの文章非表示化をSKIPDISPに変更
MAIN_WEAPON_204_凝縮式速射波動砲の対空攻撃力の表示(削除漏れ)を削除
テンプレートで購入する際に@CHANGE_EQIPが購入確認をしない様に修正
(ここまで2022/12/17時点で取り込み済み)

2022/12/18版
本体に取り込まれた部分は同梱しない様に
表示するべきデータが艦載機の場合の表示の処理を追加(CHANGE_EQUIP.ERB・EQUIP_STATUS_DESCRIPTION.ERB)