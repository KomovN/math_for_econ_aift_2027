# Задача Марковица
Задачу можно поставить следующим образом

$$
 \min\limits_x\left(-\cfrac{1}{2}x^{\top}Vx\right) \quad s.t. \quad x^{\top}e=1 \quad x^{\top}r = r_p
$$

Лагранжиан для данной задачи будет иметь вид

$$
 \mathcal{L} = -\cfrac{1}{2}x^{\top}Vx + \lambda \left(x^{\top}r - r_p\right) + \mu\left(x^{\top}e - 1\right)
$$

Вычислим условия первого порядка

$$
 \cfrac{\partial\mathcal{L}}{\partial x} = -Vx + \lambda r + \mu e = 0
$$

на выходе имеем простое линейное уравнение, решение которого имеет вид

$$
 x = V^{-1}\left(\lambda r + \mu e\right)
$$

Подставим его в уравнения связи и придем к двумерной линейной системе уравнений

$$
 \begin{cases}
 \lambda r^{\top}V^{-1}r + \mu r^{\top}V^{-1}e = r_p \\
 \\
 \lambda r^{\top}V^{-1}e + \mu e^{\top}V^{-1}e = 1
 \end{cases}
$$

Let's introduce the notation (Записать матрицу)

$$
 L_p = ...
$$

The solution of the system can be written in the form 

$$
 \begin{pmatrix}\lambda \\ \mu \end{pmatrix} = L_p^{-1}\begin{pmatrix}r_p \\ 1 \end{pmatrix}
$$

Thus for optimal share x we can write 

$$
 x^* = \begin{pmatrix}V^{-1}r, \ V^{-1}e\end{pmatrix}L_p^{-1}\begin{pmatrix}r_p \\ 1\end{pmatrix}
$$

For the variance of the portfolio we have 

$$
 \sigma^2 = x^{\top}Vx = \begin{pmatrix}r_p, \ 1\end{pmatrix}L_p^{-1}\begin{pmatrix}r_p \\ 1\end{pmatrix}
$$

Введем обозначения

$$
 \begin{cases}
 A = r^{\top}V^{-1}e \\
 B = r^{\top}V^{-1}r \\
 C = e^{\top}V^{-1}e \\
 D = BC - A^2
 \end{cases}
$$

И раскроем скобки 

$$
 \sigma^2 = \cfrac{C}{D}\left(r_p - \cfrac{A}{C}\right)^2 + \cfrac{1}{C}
$$

Придем к уравнению гиперболы! Данная гипербола описывает отношение риск-доходности множества эффективных портфелей! 

Добавим безрисковый актив. Перепишем задачу в виде 

$$
 \mathcal{L} = -\cfrac{1}{2}x^{\top}Vx + \lambda\left(r^{\top}x + (1 - x^{\top}e)r_f - r_p\right)
$$

Условия первого порядка дадут 

$$
 \cfrac{\partial L}{\partial x} = -Vx + \lambda(r - r_fe) = 0
$$

Найдем $\lambda$. Из условий первого порядка

$$
 r_p - r_f = x^{\top}(r - r_fe)
$$

Придем к ответу 

$$
 \lambda = \cfrac{r_p - r_f}{\left(r - r_fe\right)^{\top}V^{-1}\left(r - r_fe\right)} = \cfrac{r_p - r_f}{B - 2Ar_f + Cr_f^2}
$$

Для оптимальной доли рискованного актива получим

$$
 x = \cfrac{r_p - r_f}{B - 2Ar_f + Cr_f^2}V^{-1}(r - r_fe)
$$

Для относительной доли (относительно других рискованных) актива получим

$$
 \tilde{x} = \cfrac{V^{-1}(r - r_fe)}{A - r_fC}
$$

Нетрудно заметить, что данное выражение свободно от параметра $r_p$. Как следствие отсюда должен получиться вывод о рыночном портфеле! Рассчитаем дисперсию только как если бы мы набирали рискованные активы с долями $\tilde{x}$

$$
 \tilde{x}^{\top}V\tilde{x} = \cfrac{\tilde{r} - r_f}{A - r_fC}
$$

где

$$
 \tilde{r} = r^{\top}\tilde{x} = \cfrac{B - r_fA}{A - r_fC}
$$

Посмотрим, лежит ли данный портфель на эффективном множестве рискованных активов.

$$
 \cfrac{C}{D}\left(\cfrac{B - r_fA}{A - r_fC} - \cfrac{A}{C}\right)^2 + \cfrac{1}{C} = \cfrac{C}{D}\cfrac{D^2}{C^2\left(A - r_fC\right)^2} + \cfrac{1}{C} = \cfrac{B - 2r_fA + r_fC^2}{\left(A - r_fC\right)^2} = \tilde{x}^{\top}V\tilde{x}
$$

Пойдем дальше и оценим доходность и вариацию портфеля с безрисковым активом 

$$
\begin{cases}
 r_p = r^{\top}x + (1 - x^{\top}e)r_f = (x^{\top}e) \tilde{r} + (1 - x^{\top}e)r_f \\
 \\
 \sigma^2 = \left(x^{\top}e\right)^2\tilde{x}V\tilde{x}
\end{cases}
$$

Далее (Если $x^{\top}e > 0$, то ?)

$$
 \sigma = \pm(x^{\top}e)\tilde{\sigma}
$$

данное соотношение приведет нас к efficient frontier

$$
 r_p = r \pm \cfrac{\tilde{r} - r_f}{\tilde{\sigma}}\sigma
$$

Вывести CAPM? Нужно брать портфель 

$$
 r = \alpha r_i + (1 - \alpha)r_M
$$

И предположить, что tangency portfolio тот же самый (рыночный), так как ты не можешь beat the market! Отразить тот факт, что инвесторы ищут портфель с максимальным Sharpe Ratio!

CAPM: теория Марковица с безрисковым активом утверждает, что для того, чтобы собрать оптимальный портфель, необходимо собрать единственный касательный портфель (tangent portfolio) из рисковых активов и войти в некоторую позицию по безрисковому активу. Предположим, что на рынке отсутствует асимметрия информации и все участники оценивают свои модели с помощью модели Марковица. Тогда логично предположить, что касательный портфель должен быть рыночным портфелем, то есть тем, который собирает каждый участник на рынке. Чтобы вывести CAPM модель, необходимо предположить следующее. Пусть вы ограничены выбором из рыночного портфеля и некоторой ценной бумаги. Логично предположить, что в данном случае касательным портфелем должен быть рыночный портфель. Возьмем комбинацию рыночного портфеля и заданного актива

$$
 x = \alpha x_i + (1 - \alpha)x_M
$$

Вычислим ожидаемые доходности и волатильность портфеля

$$
 \begin{cases}
 r = \alpha r_i + (1 - \alpha)r_M \\
 \\
 \sigma^2 = \alpha^2\sigma_i^2 + (1 - \alpha)^2\sigma_M^2 + 2\alpha(1 - \alpha)\sigma_{iM}
 \end{cases}
$$

Вычислим производные по $\alpha$ 

$$
 \begin{cases}
 \cfrac{dr}{d\alpha} = r_i - r_M \\
 \\
 \cfrac{d\sigma^2}{d\alpha} = 2\alpha\sigma_i^2 - 2(1 - \alpha)\sigma_M^2 + 2(1 - \alpha)\sigma_{iM} - 2\alpha\sigma_{iM}
 \end{cases}
$$

И вычислим значение касательной efiicient frontier в точке $\alpha = 0$

$$
 \cfrac{dr}{d\sigma} = 2\sigma_M\cfrac{dr}{d\sigma^2} = \left. 2\sigma_M\cfrac{dr}{d\alpha}\left(\cfrac{d\sigma^2}{d\alpha}\right)^{-1}\right|_{\alpha=0} = \sigma_M\cfrac{r_i - r_M}{\sigma_{iM} - \sigma_M^2} = \cfrac{r_M - r_f}{\sigma_M}
$$

Из последнего равенства получаем уравнение CAPM

$$
 \mathbb{E}r_i = r_f + \beta\left(r_M - r_f\right)
$$

где

$$
 \beta = \cfrac{\sigma_{iM}}{\sigma_M^2}
$$

