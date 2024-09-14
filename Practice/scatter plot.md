### 1. 添加散点图里面的文字标签

```R
options(repr.plot.width =4, repr.plot.height =3)
p1<-ggplot(scores_with_conditions, 
       aes(PC1, PC2, color = batch)) +
  geom_point(size = 4) +
  xlab(paste0("PC1: ",explained_variance[1],"% variance")) +
  ylab(paste0("PC2: ",explained_variance[2],"% variance")) + 
  coord_fixed(ratio = 1) +
  theme_classic()+
  ggtitle("PCA plot with batch effect")+
  ggrepel::geom_text_repel(aes(label = sample), size = 3, show.legend = FALSE, 
                          box.padding = unit(0.5, 'lines')) #添加文字标签
p1
pdf("TEsubfamily_batch_before.pdf",width = 4,height = 3)
p1
dev.off()
```
![c1f9c4beff467fd4fe3a973ded64fce](https://github.com/user-attachments/assets/98d7605e-6edb-442f-8f55-093b0cba3ae4)


