### 1.经典boxplot

```R 
library(ggpubr)
options(repr.plot.width =8, repr.plot.height =3)
p<-ggplot(data = selectedMean2,aes(x = subfamily2, y = log2(count+1),fill=group))+ #绘图所用的数据集及x，y轴
geom_boxplot()+ #绘制盒式图
#scale_fill_brewer(palette="Accent")+
scale_fill_brewer(palette="Set3")+  #色板
labs(title="",x="",y="log2(mean(TPM)+1)")+ #横纵坐标
# stat_compare_means(
#                    aes(label = ..p.signif..), 
#                        symnum.args = list(cutpoints = c(0, 0.01, 0.05, 1), 
#                                           symbols = c("***",  "*", "notsig")),
#                        label.x = 1.5)+ #添加置信度
# geom_dotplot(binaxis = 'y', stackdir = 'up', dotsize = 0.5)+
geom_jitter(shape=16,aes(colour = group),position = position_jitterdodge(0.2))+ #加抖动点，position = position_jitterdodge(0.2)保证点分开，aes(colour = group)按照group对点进行着色
theme_classic() 
p
pdf("sg2_sg10_sg12_sg16_sg17_loci_TPM_0.pdf",width = 8,height = 3) #保存为pdf
print(p)
dev.off()
```
![1dabaecf06fc0bb588833a20e79da0b](https://github.com/user-attachments/assets/d4296c15-49ec-449d-a285-e3326df98cd4)

