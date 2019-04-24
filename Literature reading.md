# **Literature reading **_hot phonons

------

## Transient superconductivity from electronic squeezing of optically pumped phonons

文章提出一种新的mechanism解释光学支声子激发导致电子性质改变。他使用tight-binding模型计算电子与光学支声子的耦合，考虑光学支声子为$T_{1u}$模式(Mitrano实验中的$K_3C_{60}$中的主要光学激发模，与电子以二次方关系耦合)。哈密顿量可以写成
$$
H = -\sum_{ij\sigma} J_{ij}c^\dagger_{i\sigma}c_{j\sigma}+U\sum_i \hat{n_{i\uparrow}}\hat{n_{i\downarrow}}+\sum_i (\frac{K}{2}\hat{x_i}^2+\frac{1}{2M}\hat{p_i}^2)+gK\sum_i\hat{n_i}\hat{x_i}^2
$$
$c^\dagger_{i\sigma}$这里表示在site i上产生一个自旋为$\sigma$的电子，$J_{ij}$代表电子从格点i hopping 到格点j上的量。U是电子相互作用。$\hat{n_i}$是电子占据数。$\hat{x_i}$和$\hat{p_i}$是描述位移和动量的量子力学算符。$K$是经典谐振子的回复力，$M$是质量，$g$是描述电子电子-谐振子耦合强度的无量纲数。

------

### Origins of low- and high-pressure discontinuities of $T_c$ in niobium

该文章介绍了QE中```electron-phonon = interpolated```对应的方法，一直挂在arichve上未正式发表。

Nb在金属里面算是超导转变温度比较高的$T_c = 9.25K$, 它在5GPa到50-60GPa上超导转变温度有一个不连续。这篇文章分别计算了低压下和高压下的异常。

这里主要是对QE如何计算电声耦合做一个总结。

首先，我们来看哈密顿量
$$
H_{el-ph}=\sum_{kq \nu}g_{k+q,k}^{q\nu,mn}c_{k+q}^{\dagger m}c_k^n(b_{-q\nu}^\dagger+b_{q\nu})
$$
Eliashberg谱函数可以描述体系的电声耦合
$$
\alpha_2F(\omega)=\frac{1}{N(\varepsilon_F)}\sum_{mn}\sum_{q\nu}\delta(\omega-\omega_{q\nu}) \sum_k|g_{k+q,k}^{q\nu,mn}|^2\delta(\varepsilon_{k+q,m}-\varepsilon_F)\delta (\varepsilon_{k,n}-\varepsilon_F))
$$
电声耦合常数由Eliashberg谱函数除以对应频率积分得到
$$
\lambda = 2 \int \frac {\alpha^2F(\omega)}{\omega}d\omega = \sum_{q\nu}\lambda_{q\nu}
$$
当然也可以在第一个求和中先不对声子模式求和，我们可以先计算单个声子模式对于体系电声耦合的贡献。
$$
\lambda_{q\nu} = \frac {2}{N(\varepsilon_F)\omega_{q\nu}}\sum_{mn}\sum_{k}|g_{k+q,k}^{q\nu,mn}|^2\delta(\varepsilon_{k+q,m}-\varepsilon_F)\delta (\varepsilon_{k,n}-\varepsilon_F))
$$
同时还能计算声子线宽
$$
\gamma_{q\nu} = 2\pi \omega_{q\nu}\sum_{mn}\sum_{k}|g_{k+q,k}^{q\nu,mn}|^2\delta(\varepsilon_{k+q,m}-\varepsilon_F)\delta (\varepsilon_{k,n}-\varepsilon_F))
$$
当然这里都是基于简谐近似和绝热近似下的表达式，而且是微扰论下的表达式，这意味着其实这里引入的声子实质上是没有相互作用的，包括计算中也没有包含真正的电子-声子相互作用（它没有包含真正的动力学信息，而只是给出基态上的体系的电声耦合性质）。在非绝热或者非谐下的表达式可以从量子多体理论出发得到。

首先计算DFPT下的电声耦合矩阵元
$$
g_{k+q,k}^{q\nu,mn} = (\frac{\hbar}{2\omega_{q\nu}})^{1/2}<\psi_{k+q,m}|\Delta_{KS}^{q\nu}|\psi_{k,n}>
$$
其中自冾势为
$$
\Delta_{KS}^{q\nu}=\sum_R\sum_s \frac{\part V_{KS}}{\part \vec{u_{sR}}}\vec{u_{s}^{q\nu}}\frac{e^{iqR}}{\sqrt{N}}
$$
$\vec{u_{s}^{q\nu}}​$是声子模$\vec{\nu_{s}^{q\nu}}​$的displacement pattern
$$
\vec{u_{s}^{q\nu}} = \frac {\vec{v_{s}^{q\nu}}}{\sqrt{M}}
$$
声子模是由动力学矩阵元对角化得到
$$
\sum_{s'\beta}\frac{\Phi_{ss'}^{\alpha \beta}(q)}{\sqrt{M_sM_{s'}}}\vec{v_{s'\beta}^{q\nu}} = \omega^2_{q\nu}v_{s\alpha}^{q\nu}
$$

由于电声耦合常数$\lambda$和谱函数$\alpha^2F(\omega)$都是由费米面上的双$\delta$积分得到，所以精确计算需要非常密集的k点和q点取样。在QE里面有两种方法计算(broadening technique or the tetrahedron method)

在Broadening方法里面，每个态都有一个有限的能量宽度。对于任意需要做双$\delta$积分的函数$f$，积分值都可以由下面这个积分得到。
$$
I=\int dk \int dq  f(k,q) \delta(\varepsilon_k-\varepsilon_F)\delta(\varepsilon_{k+q} - \varepsilon_F)\\
\simeq \frac {\Omega^2_{BZ}}{N_k N_q} \sum_k \sum_q f(k,q) \frac {1}{\sqrt{2\pi} \sigma} e^{-\frac{(\varepsilon_{k} - \varepsilon_F)^2}{\sigma^2}}\times \frac{1}{\sqrt{2\pi}\sigma}e^{-\frac{(\varepsilon_{k+q} - \varepsilon_F)^2}{\sigma^2}}
$$
$\sigma$就是展宽。对于有限的k点和q点抽样，积分会随着$\sigma$的减小而收敛到一个常数。这里的方法其实就是在dos计算中的高斯展宽，完全一样的。

考虑到电声耦合矩阵元是k点和q电上的连续光滑函数，我们可以采用插值的办法来加快收敛。对于确定的k-q点网格，我们可以计算出相对应的电声耦合矩阵元$g_{k+q,k}^{qs\alpha,mn}$，其中$s,\alpha$指的是对应的第s个原子在$\alpha$方向上的振动。对于每一个q矢量，我们要做一个k空间矩阵元的线性插值。

------

### Interplay of Phonon and Exciton-Mediated Superconductivity in Hybrid Semiconductor-Superconductor Structures

通常情况下大家认为有两种方式可以提升超导转变温度

1. 增大mediators的特征频率（比如说大于金属中的德拜频率$\omega_D$）
2. 增大耦合强度

但是增大耦合强度会导致晶格失稳。

电声耦合导致的超导本质上是一种电子通过声子配对的行为，这个玻色子在过去一直是声子，我们知道激子极化激元也是一种玻色子，那能不能通过激子极化激元来配对形成cooper对呢？作者沿用之前的电声耦合的理论建立了声子与激子激元并存的情形。
$$
H=H^0_e+H^0_p+H_{e-e}+H_{e-p}+H_{p-p}+H_{e-ph}
$$
$H^0_e$是电子动能项，$H^0_p$是激子动能项。

激子通过场算符来描述
$$
\phi(R)=\frac{i}{\sqrt{A}}\sum_P e^{iP \cdot R} b_P
$$

$$
\phi^{\dagger}(R)=\frac{i}{\sqrt{A}}\sum_P e^{-iP \cdot R} b_P^\dagger
$$

然后对激子激元的Bogoliubov变换，上面的哈密顿量变成电子和bogolons（激子激元凝聚的元激发）的耦合$H_{e-bog}$
$$
H_{e-bog} = \gamma_1 \int \psi^\dagger_\alpha(x)\psi_\alpha(x)\phi_1(x)dx
$$

$$
H_{e-ph} = \gamma_2 \int \psi^\dagger_\alpha(x)\psi_\alpha(x)\phi_2(x)dx
$$

$\gamma$是耦合常数。有了耦合哈密顿量以后，就可以照葫芦画瓢使用平均场理论求解超导gap，Gorkv equation
$$
\left[\begin{matrix}
\Delta_1 \\
\Delta_2
\end{matrix}\right ]=
\left[\begin{matrix}
(\lambda_1+\lambda_2)I_1 & \lambda_2I_2\\
\lambda_2 I_1 & \lambda_2I_2 \\
\end{matrix}\right ]
\left[\begin{matrix}
\Delta_1 \\
\Delta_2
\end{matrix}\right ]
$$
这里
$$
I_1 = \int_{0}^{\hbar\omega_B} \frac{d\xi}{(\xi^2+\Delta^2_1)^{\frac{1}{2}}}tanh[\frac{(\xi^2+\Delta_1^2)^\frac{1}{2}}{2k_BT}]
$$

$$
I_2 = \int_{\hbar\omega_B}^{\hbar\omega_D} \frac{d\xi}{(\xi^2+\Delta^2_2)^{\frac{1}{2}}}tanh[\frac{(\xi^2+\Delta_2^2)^\frac{1}{2}}{2k_BT}]
$$

上述矩阵的本征值为
$$
I_1 = \Psi (\frac{1}{2}+\frac{\omega_B}{2\pi T_c})-\Psi(\frac{1}{2}) \approx \ln(\frac{2e^\gamma\omega_B}{\pi k_B T_c})
$$

$$
I_2 = \Psi (\frac{1}{2}+\frac{\omega_D}{2\pi T_c})-\Psi(\frac{1}{2}-\frac{\omega_B}{2\pi T_c}) \approx \ln(\frac{\omega_D}{\omega_B })
$$

取$\lambda_2=0.3 ,\mu^*=0.14$为例，大概相当于铝的电声耦合强度，得到的随着激子的耦合强度增加得到的超导转变温度（$\hbar\omega_D = 428K,T_{c0} \approx 1K$）

![选区_342](/home/cris/图片/截图/选区_342.png)

图中6条线分别对应不同bogolons 截止频率(42.8K, 107K, 214K, 385.2K, 423.72K)， 实线对应不同激子频率下的转变温度，虚线对应的是把计算$I_1,I_2$时用到的积分用$\Gamma$函数做近似得到的数值。明显地，即使对于电声耦合相当弱的超导体，也可以通过诱发激子激元的方式获得相当高的超导转变温度。作者没有做强耦合下的计算，但是认为强耦合下应该得到类似的结果，只是随着耦合强度的增加，转变温度$T_c$相对于弱耦合下的计算会被压制一些。作者还提出一种可能的实现的结构Al薄膜与GaN异质结（负责形成bogolons）的层状结构。

这篇工作实际上来源于一篇10年的工作[Exciton-Polariton Mediated Superconductivity](https://journals.aps.org/prl/pdf/10.1103/PhysRevLett.104.106402) ，所以他最后比较了一下，虽然对不上，但是大致趋势是相同的。 





