◇パッチの目的
撃沈された船等へと追従していた船がセクター00・座標のX0・Y0に向かう事が無い様にする。


◇変更内容
SHIP.ERB
@DELETE_SHIP (転籍時と同様に)除去時にも除去対象艦を追従している艦から追従情報をクリアする様に


