==========================================
ニューラルネットワーク分子動力学法を用いたCeO\ :sub:`2`\の熱特性の解析
==========================================

材料の熱特性の詳細を調べる方法として、第一原理計算や古典分子動力学（MD）計算などの原子レベルのシミュレーションが有効ですが、
比較的大規模なモデルを用いて長時間のシミュレーションを行う必要があるため、第一原理計算では計算コストがかかってしまいます。
一方で古典分子動力学(MD)計算では原子間ポテンシャルの精度に依存するため、融点等の高温時の物性を正確に予測できません。
そこで本事例では第一原理計算よりも高速で既存の古典MD計算よりも高精度なニューラルネットワークMD（NNMD）を用いてCeO\ :sub:`2`\の熱特性の評価を行いました。

|
１． NNMDポテンシャルのための学習データ作成

図1にCeO\ :sub:`2`\の学習データ作成に用いた計算モデルを示します。また、表1にその計算条件の詳細を示します。
ポテンシャルの機械学習にはDeepMD-kit[1]を使用しました。

|

  +--------------------------------------------------------------------------+
  | .. image:: ./imgs/nnmd_ceo2_thermal_property1_1.png                      |
  |    :scale: 80 %                                                          |
  |    :align: center                                                        |
  +--------------------------------------------------------------------------+

|

  +--------------------------------------------------------------------------+
  | .. image:: ./imgs/nnmd_ceo2_thermal_property1_2.png                      |
  |    :scale: 80 %                                                          |
  |    :align: center                                                        |
  +--------------------------------------------------------------------------+

|

２． 計算結果
①比熱および熱膨張係数

作成したポテンシャル関数および分子動力学コードLAMMPSを用いて、CeO\ :sub:`2`\の比熱および熱膨張係数を計算しました。
計算条件を表2に示します。比熱および熱膨張係数はエントロピーおよび体積の温度微分を用いて評価しました。
エントロピーの温度変化および比熱の計算結果を図2に示します。また、体積の温度変化および熱膨張係数の計算結果を図3に示します。
計算結果は実測[2]とよく対応していることが分かります。

|

  +--------------------------------------------------------------------------+
  | .. image:: ./imgs/nnmd_ceo2_thermal_property1_3.png                      |
  |    :scale: 80 %                                                          |
  |    :align: center                                                        |
  +--------------------------------------------------------------------------+

|

  +--------------------------------------------------------------------------+
  | .. image:: ./imgs/nnmd_ceo2_thermal_property1_4.png                      |
  |    :scale: 80 %                                                          |
  |    :align: center                                                        |
  +--------------------------------------------------------------------------+

|

  +--------------------------------------------------------------------------+
  | .. image:: ./imgs/nnmd_ceo2_thermal_property1_5.png                      |
  |    :scale: 80 %                                                          |
  |    :align: center                                                        |
  +--------------------------------------------------------------------------+

|
②融点

図2および図3の比熱および熱膨張係数の計算では、融点を正確に評価できていないため、固液共存モデルを用いて融点の評価を行いました。
融点の計算条件および計算モデルを表3および図4に示します。

|

  +--------------------------------------------------------------------------+
  | .. image:: ./imgs/nnmd_ceo2_thermal_property1_6.png                      |
  |    :scale: 80 %                                                          |
  |    :align: center                                                        |
  +--------------------------------------------------------------------------+

|

  +--------------------------------------------------------------------------+
  | .. image:: ./imgs/nnmd_ceo2_thermal_property1_7.png                      |
  |    :scale: 80 %                                                          |
  |    :align: center                                                        |
  +--------------------------------------------------------------------------+

|

図5にエンタルピーおよび密度の温度依存性の計算結果を示します。エンタルピーおよび密度はCeO2の実測の融点の近傍2650K～2750Kで不連続となり、
融点付近で固相と液相が共存していることが確認できました。

|

  +--------------------------------------------------------------------------+
  | .. image:: ./imgs/nnmd_ceo2_thermal_property1_8.png                      |
  |    :scale: 80 %                                                          |
  |    :align: center                                                        |
  +--------------------------------------------------------------------------+

|

融点近傍の2650Kと2700KにおけるMDアニメーションを以下に示します。2650Kでは液相が結晶化しているのに対して、2700Kでは固相が溶融している様子が確認できています。

|

.. raw:: html

   <div style="text-align: center;">
   <iframe width="560" height="315" src="https://www.youtube.com/embed/evjmOiu4rWk" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
   </div>
|

3．参考文献

[1]Han Wang, Linfeng Zhang, Jiequn Han, and Weinan E.
"DeePMD-kit: A deep learning package for many-body potential energy representation and molecular dynamics."
Computer Physics Communications 228 (2018): 178-184.

|

[2] N. Nelson, D Rittman, J. White et al.,
"An Evaluation of the Thermophysical Properties of Stoichiometric CeO2 in Comparison to UO2 and PuO2”,
Journal of the American Ceramic Society, 97, 3652-3659 (2014)

|
| `上記事例に関するお問い合わせ / CONTACT US <https://form.run/@nanowork>`_



