# daily-paper-reading

Short and daily paper reading

2022-03

<table style="width:100%">
  <tr>
    <th>Name</th>
    <th>Number</th>
    <th>Total</th>
  </tr>
  <tr>
    <td>Liang Ding</td>
    <td>0</td>
    <td rowspan=19>24</td>
  </tr>
  <tr>
    <td>Keqin Peng</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Zheng Zhang</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Changtong Zan</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Qingyu Lu</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Qihuang Zhong</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Hexuan Deng</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Jun Rao</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Meizhi Zhong</td>
    <td>7</td>
  </tr>
  <tr>
    <td>*Fei Wang</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Chia-Ming Hsu</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Tengfei Yu</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Ziheng Cheng</td>
    <td>17</td>
  </tr>
  <tr>
    <td>*Fuqiang Yu</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Bing Wang</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Baopu Qiu</td>
    <td>17</td>
  </tr>
  <tr>
    <td>Runze Fan</td>
    <td>0</td>
  </tr>
  <tr>
    <td>Boan Liu</td>
    <td>0</td>
  </tr>
  <tr>
    <td>*Shuai He</td>
    <td>0</td>
  </tr>
</table>




("*" means on-site members)

---



### ADePT

**Title**ADePT: Auto-encoder based Differentially Private Text Transformation》（EACL 2021 short paper）<br>

**Author**Satyapriya Krishna;Rahul Gupta;Christophe Dupuy(Amazon Alexa)<br>

*注：这个模型的隐私强度分析存在错误（由When differential privacy meets NLP这篇文章提出）<br>*

**动机** 	在进行包含敏感信息的数据集的Differentially Private Text Transformation任务中中添加了噪声的这种转换算法的精度较差。因此作者通过使用自动编码器来提供一种保持精度的Differentially Private Text Transformation算法。<br>

**模型**     一个文本重写的auto-encoder:<br>

<a href="https://sm.ms/image/Tb2OztdRQJhMy61" target="_blank"><img src="https://s2.loli.net/2022/03/20/Tb2OztdRQJhMy61.png" alt="image-20220320201643519.png" style="zoom:33%;" ></a><br>

<br>

**主要思想**  1. 对encoder产生的中间向量进行裁剪加噪（这样加噪的好处是1.可以很容易地分析其隐私保护强度（指定Laplace参数--->推出差分隐私参数） 2. 中间向量长得更像比最终的输出更像会使得精度的损失少一些）3. Enc和Dec使用的都是简单的单向LSTM模型 4. 最后的使用有MIA（member Inference Attack分析，一种对训练集数据泄露程度量化分析）<br>

**实验**    <br>

 *数据集：ATIS SNIPS* <br>

*噪声选取：Gaussian and Laplacian noises<br>*

*噪声参数选取*使用离散值 (1, 6, 9, 15, 28, 100)和(0.25, 0.5, 0.6, 0.75, 0.85, 1)<br>

*baseline：*[1910.08917.pdf (arxiv.org)](https://arxiv.org/pdf/1910.08917.pdf)<br>

*result*<br>

<a href="https://sm.ms/image/72ahFR4CXpJqsoM" target="_blank"><img src="https://s2.loli.net/2022/03/20/72ahFR4CXpJqsoM.png" alt="image-20220320203425629.png" style="zoom:33%;" ></a>

<a href="https://sm.ms/image/3MPWqLnlBuQ2Sgs" target="_blank"><img src="https://s2.loli.net/2022/03/20/3MPWqLnlBuQ2Sgs.png" alt="image-20220320203503246.png" style="zoom:33%;" ></a>

<br>

by *Meizhi Zhong*

<br>