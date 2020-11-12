==============================
第一原理計算を用いた全固体電池電解質中のLiイオンの拡散解析
==============================

本事例では全固体電池に使用される固体電解質中のLiイオンの拡散を、第一原理計算を用いて解析した事例を紹介します。第一原理計算を用いて固体中のイオン拡散を解析する場合、通常は第一原理分子動力学法(第一原理MD)を用いてイオンの運動を直接追跡する方法が用いられます[1]。しかし、第一原理MDを用いてイオンの拡散経路を完全に再現するためには、長時間のMD計算の結果を用いてイオン分布の統計的に評価しなければならないため、非常に計算コストがかかります。そこで、本事例では溶液論である3D-RISM法と第一原理計算を連成させた3D-RISM-SCF法[2,3]を用いて、簡便に固体電解質中のLiイオンの拡散分布を評価しました。

１．計算モデル
=======

ここでは固体電解質としてLi3PS4を検討しました。また、Li3PS4に対して一部酸素をドープしたLi3PS3.75O0.25も併せて解析し、元素ドープがLiイオンの拡散に与える影響を検討しました。図1に本事例で用いた計算モデルを示します。

  +--------------------------------------------------------------------------+
  | .. image:: ./imgs/qe_li3ps4_3d-rism_1.png                                |
  |    :scale: 80 %                                                          |
  |    :align: center                                                        |
  +--------------------------------------------------------------------------+

計算手順として、図1の計算モデルを用いて構造最適化を行ったのち、計算モデルからLiを削除し、Liイオンを溶媒種として3D-RISM-SCF法よりLiイオンの分布を解析しました。



２． 計算条件
=======

表1に本事例における計算条件を示します。

  +--------------------------------------------------------------------------+
  | .. image:: ./imgs/qe_li3ps4_3d-rism_2.png                                |
  |    :scale: 80 %                                                          |
  |    :align: center                                                        |
  +--------------------------------------------------------------------------+


３． 計算結果
=======

図2にLi3PS4におけるLiイオン分布の3D-RISM-SCF計算結果と第一原理MDによる文献結果[1]を示します。3D-RISM-SCF計算結果は第一原理MDの計算結果をよく再現していることが分かります。第一原理計算ではLiイオンに与える運動エネルギーとLiイオンの拡散パスの対応を解析していますが、3D-RISM-SCFでは溶媒種の温度を変えることで同様の解析が可能となっています。また、第一原理MDでは数千ステップ以上の計算を要しますが、3D-RISM-SCF法ではエネルギー1点計算の結果のため、計算コストを大幅に削減した計算となっています。

  +--------------------------------------------------------------------------+
  | .. image:: ./imgs/qe_li3ps4_3d-rism_3.png                                |
  |    :scale: 80 %                                                          |
  |    :align: center                                                        |
  +--------------------------------------------------------------------------+

また図3ににLi3PS3.75O0.25におけるLiイオン分布の3D-RISM-SCF計算結果と第一原理MDによる文献結果[1]を示します。Li3PS4の場合と同様に3D-RISM-SCF法の計算結果は第一原理MDの計算結果をよく再現しており、元素ドープがLiイオン拡散に与える影響を再現できていることが確認できました。

  +--------------------------------------------------------------------------+
  | .. image:: ./imgs/qe_li3ps4_3d-rism_4.png                                |
  |    :scale: 80 %                                                          |
  |    :align: center                                                        |
  +--------------------------------------------------------------------------+


５．参考文献
======

[1]R. Xiao, H. Li and L. Chen, “High-throughput design and optimization of fast lithium ion conductors by the combination of bond-valence method and density functional theory”, Scientfic Reports, 5, 1 (2015)
[2]A. Kovalenko and F. Hirata, “Self-consistent description of a metal–water interface by the Kohn–Sham density functional theory and the three-dimensional reference interaction site model”, J. Chem. Phys. 110, 10095 (1999)
[3]S. Nishihara and M. Otani, “Hybrid solvation models for bulk, interface, and membrane: Reference interaction site methods coupled with density functional theory”, Phys. Rev. B 96, 115429 (2017)
[4]Satomichi Nishihara's git repository(https://gitlab.com/nisihara1/q-e)


