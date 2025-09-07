Consumption choice

![L](https://latex.codecogs.com/svg.latex?\mathcal{L}=\left(\alpha_1x_1^{\tfrac{\epsilon-1}{\epsilon}}+\alpha_2x_2^{\tfrac{\epsilon-1}{\epsilon}}\right)^{\tfrac{\epsilon}{\epsilon-1}}+\lambda(w-px))

First order conditions 

![FOC](https://latex.codecogs.com/svg.latex?\begin{cases}\tfrac{\partial\mathcal{L}}{\partial%20x_1}=\alpha_1x_1^{-1/\epsilon}\left(\alpha_1x_1^{\tfrac{\epsilon-1}{\epsilon}}+\alpha_2x_2^{\tfrac{\epsilon-1}{\epsilon}}\right)^{\tfrac{1}{\epsilon-1}}-\lambda%20p_1=0\\\\\tfrac{\partial\mathcal{L}}{\partial%20x_2}=\alpha_2x_2^{-1/\epsilon}\left(\alpha_1x_1^{\tfrac{\epsilon-1}{\epsilon}}+\alpha_2x_2^{\tfrac{\epsilon-1}{\epsilon}}\right)^{\tfrac{1}{\epsilon-1}}-\lambda%20p_2=0\end{cases})

Коротко можно записать следующим образом

$$
 \cfrac{\partial\mathcal{L}}{\partial x} = \alpha x^{-1/\epsilon}\left(\alpha_1x_1^{\cfrac{\epsilon-1}{\epsilon}} + \alpha_2x_2^{\cfrac{\epsilon-1}{\epsilon}}\right)^{\cfrac{1}{\epsilon - 1}} - \lambda p = 0
$$

Беребросим член с $\lambda$ (мы предполагаем, что он больше нуля) в правую часть и возьмем отношению двух равенст. На выходе получим

![Ratio](https://latex.codecogs.com/svg.latex?\tfrac{\alpha_1x_1^{-1/\epsilon}}{\alpha_2x_2^{-1/\epsilon}}=\tfrac{p_1}{p_2})

Что позволяет нам вычислить относительную эластичность спроса на два товара

![Elasticity](https://latex.codecogs.com/svg.latex?\ln\!\left(\tfrac{x_1}{x_2}\right)=-\epsilon\left(\ln\!\left(\tfrac{\alpha_2}{\alpha_1}\right)+\ln\!\left(\tfrac{p_1}{p_2}\right)\right))

Вернемся к задача и найдем решение для $x$. Для этого выразим $x_2$ через $x_1$ и подставим выражение в бюджетное ограничение

$$
 \begin{cases}
 x_2 = x_1\left(\cfrac{\alpha_1p_2}{\alpha_2p_1}\right)^{-\epsilon}\\
 \\
 p_1x_1 + p_2x_2 = p_1x_1 + x_1p_2^{1-\epsilon}\alpha_2^{\epsilon}p_1^{\epsilon}\alpha_1^{-\epsilon} = w
 \end{cases} 
$$

После недолгих вычислений придем к конечному результату

$$
 \begin{cases}
 x_1^* = \left(\cfrac{p_1}{\alpha_1}\right)^{-\epsilon}\cfrac{w}{p_1^{1-\epsilon}\alpha_1^{\epsilon} + p_2^{1-\epsilon}\alpha_2^{\epsilon}}\\
 \\
 x_2^* = \left(\cfrac{p_2}{\alpha_2}\right)^{-\epsilon}\cfrac{w}{p_1^{1-\epsilon}\alpha_1^{\epsilon} + p_2^{1-\epsilon}\alpha_2^{\epsilon}}
 \end{cases}
$$

Для функции полезности в экстремуме получим

$$math
 U(p, w) = \left(\alpha_1x_1^{\cfrac{\epsilon-1}{\epsilon}} + \alpha_2x_2^{\cfrac{\epsilon-1}{\epsilon}}\right)^{\cfrac{\epsilon}{\epsilon - 1}} = w \left(p_1^{1-\epsilon}\alpha_1^{\epsilon} + p_2^{1-\epsilon}\alpha_2^{\epsilon}\right)^{\frac{1}{\epsilon - 1}}
$$

Обобщим нашу задачу на более общий случай с произвольным количеством товаров

$$
 \begin{cases}
  \xi_i = \alpha_ix_i^{-1/\epsilon}\\
  \\
  \cfrac{(p, \xi)}{\|p\|^2}p = \xi
 \end{cases}
$$

вектор $\xi$ должен быть собственным вектора оператора

$$
 T_{ij} = \cfrac{p_ip_j}{\|p\|^2}
$$
с собственным значением 1. Нетрудно понять, что $\xi = Cp$. Следовательно

$$
 x_i = \tilde{C}\left(\cfrac{p_i}{\alpha_i}\right)^{-\epsilon}
$$
Константу $\tilde{C}$ несложно найти из бюджетного ограничения

$$
 \tilde{C} = \cfrac{w}{\sum\limits_{i=1}^n\alpha_i^{\epsilon}p_i^{1-\epsilon}}
$$

Результат

$$
 x_i = \left(\cfrac{p_i}{\alpha_i}\right)^{-\epsilon}\cfrac{w}{\sum\limits_{i=1}^n\alpha_i^{\epsilon}p_i^{1-\epsilon}}
$$

Подстановка в функцию полезности дает

$$
 U(p, w) = w\left(\sum\limits_{i=1}^N\alpha_i^{\epsilon}p_i^{1-\epsilon}\right)^{\frac{1}{\epsilon - 1}}
$$

В случае равенства цен и $\alpha_i = 1$ придем к выражению

$$
 U(p, w) = \cfrac{w}{p}N^{\frac{1}{\epsilon - 1}}
$$

Мы видим, что благосостояние потребителей монотонно растет с ростом количества товаров в случае $\epsilon < 1$. Это означает, что чем больше товаров заменителей представлено на рынке, тем лучше для потребителя, что дает право рынкам с большим разнообразием товаров поднимать цены. 