# [cigale](https://cigale.lam.fr)

## Installation
具体过程[在这里](https://cigale.lam.fr/documentation/)

## CIGALE 运行过程
第一步：产生pcigale.ini文件，并在其中写入所用数据文件及model
```shell
pcigale init
```
修改文件中：
```text
data_file = 209.txt
sed_modules = sfhdelayed, bc03, dustatt_modified_starburst, dale2014, redshifting
analysis_method = pdf_analysis
cores = 1
```

第二步：产生model参数，并修改其参数
	
```shell
pcigale genconf
```

修改文件中：
```text
tau_main = 250, 500, 1000, 2000, 4000, 6000, 8000
age = 250, 500, 1000, 2000, 4000, 8000, 10000, 12000
E_BV_lines = 0.1, 0.15, 0.2, 0.25, 0.3, 0.35, 0.4, 0.45, 0.5, 0.55, 0.6
alpha = 1.0, 1.5, 2.0, 2.5
```

演示中修改的参数，实际根据自己要求改参数。
*注：最麻烦的过程，一组数据不可能满足所有的源。所以有时候需要修改参数使得这个源能被很好的拟合。*

第三步：跑程序，并输出最佳的拟合
	
```shell
pcigale run
```

第四步：输出最佳拟合的SED

```shell
pcigale-plots sed
```

![最佳拟合的SED。](https://github.com/njuastro/programming-day/raw/master/attachments/867_best_model.png)

*注意：要输出最佳拟合的SED，必须在跑程序之前修改 'pcigale.ini 文件中 `save_best_sed = True`*

## CIGALE数据的准备

```text
# id redshift b_goods b_goods_err i_goods i_goods_err …
209  0.416    0.00763 2.0e-05     0.0272  3.4e-05     … 
210  0.55     0.00763 2.0e-05     0.0272  3.4e-05     … 
211  0.483    0.00763 2.0e-05     0.0272  3.4e-05     … 
```

注意事项：
- id, z, filter 都要和数据一一对应。
- Id名字中不要出现减号“-”。（不要问为什么）
- Filter对应的流量单位“mJy”。
- 需要在CIGALE库中找到该filter的名字。（如果没有要自己添加）

**繁琐的过程，一定要细心。**