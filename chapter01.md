## Chatper01

$$P \{ A \} \geq 0 \tag{1.1}$$

$$P \{ S \} = 0 \tag{1.2}$$

$$P\{A \cup B\}=P \{ A \}+P \{ B \} \tag{1.3}$$

$$P\{ \varnothing \} \tag{1.4}$$

$$P\{A\} = 1 - P\{ \overline{A} \} \tag{1.5}$$

$$F_X(x) = P\{X \leq x \} \tag{1.6}$$

$$\int_{-\infty}^x p_X(x)dx = P\{X \leq x \} = F_X(x) \tag{1.7}$$

$$\begin{align*}
p_X(x) &= \frac{dF_X(x)}{dx} \\
&= \lim_{\Delta x \to 0} \frac{F_X(x + \Delta x) - F_X(x)}{\Delta x} \\
&= \lim_{\Delta x \to 0} \frac{P\{x < X \leq x + \Delta x\}}{\Delta x}
\end{align*}\tag{1.8}$$

$$\begin{align*}
P\{a < X \leq b\} &= F_X(X \leq b) - F_X(X \leq a) \\
&= \int_{a}^{b} p_X(x)dx
\end{align*} \tag{1.9}$$

$$w_X(x_i) = P\{X=x_i\}, \quad i=1, ..., n \tag{1.10}$$

$$p_X(x) = \sum_{i=1}^{n} w_X(x_i) \delta(x - x_i) \tag{1.11}$$

---

### 용어 설명: p.7

$$\delta(x - a) =
\begin{cases}
\infty, & x = a \\
0, & x \neq a
\end{cases}$$

$$\int_{-\infty}^{\infty} \delta(x-a)dx=1$$

$$
\begin{align*}
1 = \int_{-\infty}^{\infty} p_X(x) dx & = \int_{-\infty}^{\infty} \sum_{i=1}^{n} w_X(x_i) \delta(x - x_i) dx \\
&= \sum_{i=1}^{n} w_X(x_i) \int_{-\infty}^{\infty} \delta(x - x_i) dx \\
&= \sum_{i=1}^{n} w_X(x_i)
\end{align*}
$$

---

$$\begin{align*}
F_{XY}(x, y) = P\{(X \leq x) \cap (Y \leq y)\} &= P\{(X \leq x) \text{ and } (Y \leq y)\} \\ &= P\{X \leq x, Y \leq y\}
\end{align*}\tag{1.12}$$

$$\begin{align*}
& 0 \leq F_{XY}(x, y) \leq 1 \\
& F_{XY}(\infty, \infty) = 1 \\
& F_{XY}(-\infty, y) = F_{XY}(x, -\infty) = 0 \\
& F_{XY}(x, \infty) = F_X(x) \\
& F_{XY}(\infty, y) = F_Y(y)
\end{align*}\tag{1.13}$$

$$F_{XY}(x, y) = \int_{-\infty}^{y} \int_{-\infty}^{x} p_{XY}(u, v) du dv = \int_{-\infty}^{x} \int_{-\infty}^{y} p_{XY}(u, v) dv du
 \tag{1.14}$$

$$\begin{align*}
p_{XY}(x, y) & = \frac{\partial^2 F_{XY}(x, y)}{\partial x \partial y} \\
& = \lim_{\Delta x, \Delta y \to 0} \frac{P\{x < X \leq x + \Delta x, y < Y \leq y + \Delta y\}}{\Delta x \Delta y}
\end{align*}\tag{1.15}$$

1. $$p_{XY}(x,y) \geq 0$$
2. $$\int_{-\infty}^{\infty} \int_{-\infty}^{\infty} p_{XY}(x, y) dx dy = 1$$

$$p_X(x) = \int_{-\infty}^{\infty} p_{XY}(x, y) dy \tag{1.16}$$

$$p_Y(y) = \int_{-\infty}^{\infty} p_{XY}(x, y) dx \tag{1.17}$$

---

### 노트: p.10

$$F_X(x)=P\{X \leq x\} = P\{X \leq x, Y \leq \infty\}$$

$$\begin{align*}
\int_{-\infty}^{x} p_X(u) du &= \int_{-\infty}^{x} \int_{-\infty}^{\infty} p_{XY}(u, v) dv du \\ &= \int_{-\infty}^{x} \left( \int_{-\infty}^{\infty} p_{XY}(u, v) dv \right) du
\end{align*}$$

$$p_X(x) = \int_{-\infty}^{\infty}p_{XY}(x,y)dy$$

---

$$P\{A|B\} = \frac{P\{A, B\}}{P\{B\}} \tag{1.18}$$

---

### 노트: p.12

$$P\{A|B\} = \frac{P\{A, B\}}{P\{B\}} = \frac{1/3}{1/2}= \frac{2}{3}$$

---

$$P\{A|S\} = \frac{P\{A, S\}}{P\{S\}} = \frac{P\{A\}}{1} = P\{A\} \tag{1.19}$$

$$\begin{align*}
P\{A|B, C\} &= \frac{P\{A, B, C\}}{P\{B, C\}} \\
&= \frac{P\{A, B|C\} P\{C\}}{P\{B|C\} P\{C\}} \\
&= \frac{P\{A, B|C\}}{P\{B|C\}}
\end{align*}\tag{1.20}$$

$$P\{X \leq x | Y = y\} = \int_{-\infty}^{x} p_{X|Y}(u|y) du \tag{1.21}$$

$$\begin{align*}
\newcommand\ddfrac[2]{\frac{\displaystyle #1}{\displaystyle #2}}
\int_{-\infty}^{x} p_{X|Y}(u|y) du = \ddfrac{\int_{-\infty}^{x}  \int_{y}^{y+dy} p_{XY}(u, v) dv du}{\int_{y}^{y+dy} p_Y(v) dv} \\
\newcommand\ddfrac[2]{\frac{\displaystyle #1}{\displaystyle #2}}
= \ddfrac{\int_{-\infty}^{x} \left[ p_{XY}(u, y) dy \right] du}{p_Y(y) dy} \end{align*}\tag{1.22}$$

$$p_{X|Y}(x|y) = \frac{p_{XY}(x, y)}{p_Y(y)}, \quad p_Y(y) \neq 0 \tag{1.23}$$

$$p_{X|Y,Z}(x|y, z) = \frac{p_{XY|Z}(x, y|z)}{p_{Y|Z}(y|z)}, \quad p_{Y|Z}(y|z) \neq 0 \tag{1.24}$$

$$\begin{align*}
& p_{XY}(x, y) = p_{X|Y}(x|y) p_Y(y) \\
& p_{XY|Z}(x, y|z) = p_{X|Y,Z}(x|y, z) p_{Y|Z}(y|z)
\end{align*} \tag{1.25}$$

$$P\{a < X \leq b | Y = y\} = \int_{a}^{b} p_{X|Y}(x|y) dx \tag{1.26}$$

$$P\{A, B\} = P\{A\}P\{B\} \tag{1.27}$$

$$P\{X \leq x, Y \leq y\} = P\{X \leq x\} P\{Y \leq y\} \tag{1.28}$$

$$\begin{align*}
F_{XY}(x, y) = F_X(x) F_Y(y) \\
p_{XY}(x, y) = p_X(x) p_Y(y)
\end{align*}\tag{1.29}$$

$$\begin{align*}
p_{X|Y}(x|y)=p_x(x) \\
p_{Y|X}(y|x)=p_y(y)
\end{align*} \tag{1.30}$$

---

### 노트: p.15

$$
p_{XY}(x, y) = \begin{cases} 
8xy, & 0 < x \leq 1, 0 \leq y \leq x \\
0, & \text{otherwise} 
\end{cases}
$$

$$
p_X(x) = \int_{-\infty}^{\infty} p_{XY}(x, y) dy = \int_{0}^{x} 8xy dy = 4x^3, \quad 0 < x \leq 1
$$

$$
p_Y(y) = \int_{-\infty}^{\infty} p_{XY}(x, y) dx = \int_{y}^{1} 8xy dx = 4y (1 - y^2), \quad 0 \leq y \leq 1
$$

$$
p_{Y|X}(y|x) = \frac{p_{XY}(x, y)}{p_X(x)} = 
\begin{cases} 
\frac{2y}{x^2}, & 0 \leq y \leq x, 0 < x \leq 1 \\
0, & \text{otherwise}
\end{cases}
$$

$$
Z = X + Y
$$

$$
P\{Z \leq z | X = x\} = P\{X + Y \leq z | X = x\}
$$

$$
P\{x + Y \leq z | X = x\} = P\{Y \leq z - x | X = x\}
$$

$$
P\{Y \leq z-x | X = x\} = P\{Y \leq z-x\}
$$

$$
P\{Z \leq z | X = x\} = P\{Y \leq z-x\}
$$

$$
p_{Z|X}(z|x) = p_Y(z - x)
$$

---


$$F_Y(y)= P\{Y \leq y\} = P\{g(X) \leq y\} = P\{X \in I_x\} \tag{1.31}$$

$$p_X(x)=\begin{cases}
1/2, & -1\leq x \leq 1 \\
0, & \text{otherwise}
\end{cases} \tag{1.32}$$

$$Y = X^2 \tag{1.33}$$

$$\begin{align*}
F_Y(y) & = P\{Y = X^2 \leq y\} \\
& = P\{-\sqrt{y} < X \leq \sqrt{y}\} =
\begin{cases}
0, & y \leq 0 \\
\sqrt{y}, & 0 < y \leq 1 \\
1, & y > 1
\end{cases}
\end{align*}\tag{1.34}$$

$$p_Y(y) = \frac{dF_Y(y)}{dy} = 
\begin{cases} 
1/(2\sqrt{y}), & 0 < y \leq 1 \\
0, & \text{otherwise}
\end{cases} \tag{1.35}$$

$$P\{A\} = \sum_{i=1}^{n} P\{A, B_i\} = \sum_{i=1}^{n} P\{A|B_i\}P\{B_i\} \tag{1.36}$$

$$p_X(x) = \int_{-\infty}^{\infty} p_{XY}(x, y) dy = \int_{-\infty}^{\infty} p_{X|Y}(x|y)p_Y(y) dy \tag{1.37}$$

$$P\{B_i|A\} = \frac{P\{A, B_i\}}{P\{A\}} = \frac{P\{A|B_i\}P\{B_i\}}{P\{A\}}\tag{1.38}$$

$$P\{B_i|A\} = \frac{P\{A|B_i\}P\{B_i\}}{\sum_{j=1}^{n} P\{A|B_j\}P\{B_j\}}\tag{1.39}$$

$$\begin{align*}
p_{Y|X}(y|x) & = \frac{p_{X|Y}(x|y)p_Y(y)}{p_X(x)} \\
& \newcommand\ddfrac[2]{\frac{\displaystyle #1}{\displaystyle #2}} =\ddfrac{p_{X|Y}(x|y)p_Y(y)}{\int_{-\infty}^{\infty} p_{X|Y}(x|y)p_Y(y) dy}
\end{align*}\tag{1.40}$$

$$x \sim p_X(x) \tag{1.41}$$

$$\begin{align*}
w_X(x^{(i)}) &= P\{X=x^{(i)}\} \\
&= \frac{1}{N}, \quad i=1, \ldots, N
\end{align*}\tag{1.42}$$

$$p_X(x) \approx \sum_{i=1}^N w_X(x^{(i)}) \delta(x - x^{(i)}) = \frac{1}{N} \sum_{i=1}^N \delta(x - x^{(i)}) \tag{1.43}$$

$$\begin{align*}
p_X(x)dx &= \int_{x}^{x+dx} p_X(x) dx \approx \int_{x}^{x+dx} \frac{1}{N} \sum_{i=1}^N \delta(x - x^{(i)}) dx \\
&= \frac{1}{N} \sum_{i=1}^N \int_{x}^{x+dx} \delta(x - x^{(i)}) dx \\
&= \frac{\text{the number of samples in the interval } (x, x+dx]}{N}
\end{align*}\tag{1.44}$$

$$
p_X(x)=\begin{cases}
1/2, & -1 \leq x \leq 1 \\
0, & \text{otherwise}
\end{cases}
$$

---

### 노트: p.23

$$
p_X(x) = 
\begin{cases} 
1/2, & -1 \leq x \leq 1 \\
0, & \text{otherwise}
\end{cases}
$$

$$
p_Y(y) =
\begin{cases}
1/(2\sqrt{y}), & 0 < y \leq 1 \\
0, & \text{otherwise}
\end{cases}
$$

$$
y^{(i)} = (x^{(i)})^2, \quad i=1, \ldots, N
$$

---

$$\mathbb{E}[X] = \int_{-\infty}^{\infty} xp_X(x)dx \tag{1.45}$$

$$\mathbb{E}[g(X)] = \int_{-\infty}^{\infty} g(x)p_X(x)dx \tag{1.46}$$

$$\begin{align*}
\mathbb{E}[g(X)] &= \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} g(x)p_{XY}(x, y)dxdy \\
&= \int_{-\infty}^{\infty} g(x)p_X(x)dx
\end{align*}\tag{1.47}$$

$$\mathbb{E}[g(X, Y)] = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} g(x, y)p_{XY}(x, y)dxdy \tag{1.48}$$

$$\mathbb{E}[a g_1(X) + b g_2(X)] = a \mathbb{E}[g_1(X)] + b \mathbb{E}[g_2(X)]$$

---

### 노트: p.26

$$\begin{align*}
\mathbb{E}[X] = \int_{-\infty}^{\infty} x p_X(x) dx &= \int_{-\infty}^{\infty} x \sum_{i=1}^{n} w_X(x_i) \delta(x - x_i) dx \\
&= \sum_{i=1}^{n} w_X(x_i) \int_{-\infty}^{\infty} x \delta(x - x_i) dx \\
&= \sum_{i=1}^{n} x_i w_X(x_i)  
\end{align*}
$$

---

$$
\begin{align*}
Var(X) & = \mathbb{E}[(X - \mathbb{E}[X])^2] \\
& = \int_{-\infty}^{\infty} (x - \mathbb{E}[X])^2 p_X(x) dx \\
& = \mathbb{E}[ X^2 - 2X\mathbb{E}[X] + (\mathbb{E[X]})^2]\\
& = \mathbb{E}[X^2] - (\mathbb{E}[X])^2
\end{align*}\tag{1.49}
$$

$$
\begin{align*}
Cov(X, Y) & = \mathbb{E}[(X - \mathbb{E}[X])(Y - \mathbb{E}[Y])] \\
& = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} (x - \mathbb{E}[X])(y - \mathbb{E}[Y]) p_{XY}(x, y) dx dy \\
& = \mathbb{E}[XY - X\mathbb{E}[Y] - Y\mathbb{E}[X] + \mathbb{E}[X]\mathbb{E}[Y]]  \\
& = \mathbb{E}[XY] - \mathbb{E}[X]\mathbb{E}[Y]
\end{align*}\tag{1.50}
$$

$$
\begin{align*}
Cor(X, Y) &= \mathbb{E}[XY] \\
&= \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} xy p_{XY}(x, y) dx dy
\end{align*}\tag{1.51}
$$

$$
Cor(X, Y) = \mathbb{E}[XY] = \mathbb{E}[X]\mathbb{E}[Y]\tag{1.52}
$$

$$
\rho_{XY} = \frac{Cov(X, Y)}{\sqrt{Var(X) Var(Y)}}
\tag{1.53}
$$

---

### 노트: p.27

$$
\begin{align*}
\mathbb{E}[XY] &= \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} xy p_{XY}(x, y) dy dx \\
&= \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} xy p_X(x) p_Y(y) dy dx\\
&= \int_{-\infty}^{\infty} x p_X(x) \left(\int_{-\infty}^{\infty} y p_Y(y) dy\right) dx \\
&= \mathbb{E}[Y] \int_{-\infty}^{\infty} x p_X(x) dx = \mathbb{E}[X]\mathbb{E}[Y] \\
\end{align*}
$$

$$
p_{XY}(x,y) \begin{cases}
8xy, & 0 < x \leq 1, 0 \leq y \leq x \\
0, & \text{otherwise}
\end{cases}
$$

$$
\begin{align*}
\mathbb{E}[X] &= \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} x p_{XY}(x, y) dy dx \\
&= \int_{0}^{1} \int_{0}^{x} x(8xy) dy dx \\
&= \int_{0}^{1} 4x^4 dx = \frac{4}{5}
\end{align*}
$$

$$
\begin{align*}
\mathbb{E}[Y] &= \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} y p_{XY}(x, y) dy dx \\
&= \int_{0}^{1} \int_{0}^{x} y(8xy) dy dx \\
&= \int_{0}^{1} \frac{8}{3} x^4 dx = \frac{8}{15}
\end{align*}
$$

$$
\begin{align*}
\mathbb{E}[X^2] &= \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} x^2 p_{XY}(x, y) dy dx \\
&= \int_{0}^{1} \int_{0}^{x} x^2 (8xy) dy dx \\
&= \int_{0}^{1} 4x^5 dx = \frac{2}{3}
\end{align*}
$$

$$
\begin{align*}
Var(X) &= \mathbb{E}[X^2] - (\mathbb{E}[X])^2 \\
&= \frac{2}{3} - \left(\frac{4}{5}\right)^2 = \frac{2}{75}
\end{align*}
$$

$$
\begin{align*}
\mathbb{E}[XY] &= \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} xy p_{XY}(x, y) dy dx \\
&= \int_{0}^{1} \int_{0}^{x} xy (8xy) dy dx \\
&= \int_{0}^{1} \frac{8}{3} x^5 dx = \frac{4}{9}
\end{align*}
$$

$$
\begin{align*}
Cov(X, Y) &= \mathbb{E}[XY] - \mathbb{E}[X]\mathbb{E}[Y] \\
&= \frac{4}{9} - \frac{4}{5} \left(\frac{8}{15}\right) = \frac{4}{225}
\end{align*}
$$

---

$$
\mathbb{E}[X|Y=y] = \int_{-\infty}^{\infty} x p_{X|Y}(x|y) dx  \tag{1.54}
$$

$$
\mathbb{E}[X|Y] = \int_{-\infty}^{\infty} x p_{X|Y}(x|Y) dx \tag{1.55}
$$

$$
\mathbb{E}[g(X)|Y=y] = \int_{-\infty}^{\infty} g(x) p_{X|Y}(x|y) dx \tag{1.56}
$$

$$
\mathbb{E}[g(X)|Y)=\int_{-\infty}^{\infty} g(x)p_{X|Y}(x|Y)dx \tag{1.57}
$$

$$
\begin{align*}
Var(X|Y=y) &= \mathbb{E}[(X - \mathbb{E}[X|Y=y])^2 | Y=y] \\
&= \mathbb{E}[X^2|Y=y] - (\mathbb{E}[X|Y=y])^2
\end{align*}\tag{1.58}
$$

$$
\begin{align*}
Var(X|Y) &= \mathbb{E}[(X - \mathbb{E}[XY])^2 | Y] \\
&= \mathbb{E}[X^2|Y] - (\mathbb{E}[X|Y])^2
\end{align*}\tag{1.59}
$$

$$
\begin{align*}
\mathbb{E}[Var(X|Y)] &= \mathbb{E}[\mathbb{E}[X^2|Y] - (\mathbb{E}[X|Y])^2] \\
&= \mathbb{E}[X^2] - \mathbb{E}[(\mathbb{E}[X|Y])^2]
\end{align*}\tag{1.60}
$$

$$
\begin{align*}
Var(\mathbb{E}[X|Y]) &= \mathbb{E}_Y[(\mathbb{E}[X|Y] - \mathbb{E}[\mathbb{E}[X|Y]])^2] \\
&= \mathbb{E}[(\mathbb{E}[X|Y])^2] - (\mathbb{E}[X])^2
\end{align*}\tag{1.61}
$$

$$
Var(X) = \mathbb{E}[Var(X|Y)] + Var(\mathbb{E}[X|Y]) \tag{1.62}
$$

---

### 노트: p.31

$$
p_{XY}(x,y) = \begin{cases}
8xy, & 0 < x \leq 1, 0 \leq y \leq x \\
0, & \text{otherwise}
\end{cases}
$$

$$
p_{Y|X}(y|x) = \frac{p_{XY}(x,y)}{p_X(x)}=\begin{cases}
\frac{2y}{x^2}, & 0 \leq y \leq x, 0 < x \leq 1 \\
0, & \text{otherwise}
\end{cases}
$$

$$
\begin{align*}
\mathbb{E}[Y|X=x] &= \int_{-\infty}^{\infty} y p_{Y|X}(y|x)dy \\
&= \int_0^x y \frac{2y}{x^2}dy \\
&= \frac{2}{3}x, \quad 0 < x \leq 1
\end{align*}
$$

---

$$
F_{X_1,\ldots,X_n}(x_1, x_2, \ldots, x_n) = P\{X_1 \leq x_1, X_2 \leq x_2, \ldots, X_n \leq x_n\} \tag{1.63}
$$

$$
F_\mathrm{X}(\mathrm{x}) = F_{X_1,\ldots,X_n}(x_1, x_2, \ldots, x_n) \tag{1.64}
$$

$$
\mathrm{X} = \begin{bmatrix} X_1 \\ X_2 \\ \vdots \\ X_n \end{bmatrix}, \mathrm{x} = \begin{bmatrix} x_1 \\ x_2 \\ \vdots \\ x_n \end{bmatrix}
$$

$$
F_\mathrm{X}(\mathrm{x}) = \int_{-\infty}^{x_1} \int_{-\infty}^{x_2} \ldots \int_{-\infty}^{x_n} p_{X_1,\ldots,X_n}(u_1, u_2, \ldots, u_n)  du_n \ldots du_2  du_1
\tag{1.65}
$$

$$
p_{X_1,\ldots,X_n}(x_1, x_2, \ldots, x_n) = p_\mathrm{X}(\mathrm{x})\tag{1.66}
$$

$$
\int_{-\infty}^{x_1} \int_{-\infty}^{x_2} \ldots \int_{-\infty}^{x_n} \ldots du_1 du_2 \ldots du_n = \int_{-\infty}^{\mathrm{x}} \ldots \mathrm{du}\tag{1.67}
$$

$$
F_\mathrm{X}(\mathrm{x}) = \int_{-\infty}^{\mathrm{x}} p_\mathrm{X}(\mathrm{u}) \mathrm{du}
\tag{1.68}
$$

$$
\begin{align*}
& p_{X_1}(x_1), p_{X_2}(x_2), p_{X_3}(x_3) \\
& p_{X_1, X_2}(x_1, x_2), p_{X_1, X_3}(x_1, x_3), p_{X_2, X_3}(x_2, x_3)
\end{align*}
$$

$$
\begin{align*}
& p_{X_1}(x_1) = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} p_\mathrm{X}(\mathrm{x})  dx_2  dx_3 \\
& p_{X_1, X_2}(x_1, x_2) = \int_{-\infty}^{\infty} p_\mathrm{X}(\mathrm{x})  dx_3
\end{align*}
$$

$$
\begin{align*}
P(X \leq \mathrm{x} | Y = \mathrm{y}) = \int_{-\infty}^{\mathrm{x}} p_{\mathrm{X|Y}}(\mathrm{u|y})\mathrm{du}
\end{align*}
\tag{1.69}
$$

$$
\begin{align*}
\{\mathrm{X} \leq \mathrm{x}\} &= \{X_1 \leq x_1, X_2 \leq x_2, \ldots, X_n \leq x_n\} \\
\{\mathrm{Y} = \mathrm{y}\} &= \{Y_1 = y_1, Y_2 = y_2, \ldots, Y_m = y_m\} \\
p_{\mathrm{X|Y}}(\mathrm{u|y}) &= p_{X_1,\ldots,X_n|Y_1,\ldots,Y_m}(u_1, u_2, \ldots, u_n | y_1, y_2, \ldots, y_m)
\end{align*}
\tag{1.70}
$$

$$
p_{\mathrm{X|Y}}(\mathrm{x|y}) = \frac{p_{\mathrm{XY}}(\mathrm{x, y})}{p_\mathrm{Y}(\mathrm{y})} = \frac{p_{X_1,\ldots,X_n,Y_1,\ldots,Y_m}(x_1, \ldots, x_n, y_1, \ldots, y_m)}{p_{Y_1,\ldots,Y_m}(y_1, \ldots, y_m)}
\tag{1.71}
$$

$$
\begin{align*}
p_\mathrm{X}(\mathrm{x}) & = p_{X_1,...,X_n}(x_1, x_2, ..., x_n) \\
& = p_{X_1}(x_1)p_{X_2}(x_2) \cdots p_{X_n}(x_n) \\
& = \prod_{i=1}^{n} p_{X_i}(x_i)
\end{align*}
\tag{1.72}
$$

$$
p_{X_1, X_2|X_3}(x_1, x_2 | x_3) = p_{X_1|X_3}(x_1 | x_3) p_{X_2|X_3}(x_2 | x_3) \tag{1.73}
$$

$$
\begin{align*}
\mathbb{E}[\mathrm{X}] = \begin{bmatrix}
\mathbb{E}[X_1] \\
\vdots \\
\mathbb{E}[X_n]
\end{bmatrix} &= \int_{-\infty}^{\infty} \mathrm{x} p_\mathrm{X}(\mathrm{x}) \mathrm{dx} \\
& = \int_{-\infty}^{\infty} \begin{bmatrix}
x_1 \\
\vdots \\
x_n
\end{bmatrix} p_\mathrm{X}(\mathrm{x}) \mathrm{dx}\tag{1.74}
\end{align*}
$$

$$
\mathbb{E}[X_i] = \int_{-\infty}^{\infty} x_i p_{X_i}(x_i)  dx_i = \int_{-\infty}^{\infty} x_i p_{\mathrm{X}}(\mathrm{x}) \mathrm{dx} \tag{1.75}
$$

$$
\mathbb{E}[g(\mathrm{X})] = \int_{-\infty}^{\infty} g(\mathrm{x}) p_\mathrm{X}(\mathrm{x}) \mathrm{dx}
\tag{1.76}
$$

$$
\begin{align*}
Cov(\mathrm{X}) &= \mathbb{E}[(\mathrm{X} - \mathbb{E}[\mathrm{X}])(\mathrm{X} - \mathbb{E}[\mathrm{X}])^T] \\
&= \int_{-\infty}^{\infty} (\mathrm{x} - \mathbb{E}[\mathrm{X}])(\mathrm{x} - \mathbb{E}[\mathrm{X}])^T p_{\mathrm{X}}(\mathrm{x}) \mathrm{dx} \\
&= \begin{bmatrix}
\sigma_{11} & \sigma_{12} & \cdots & \sigma_{1n} \\
\sigma_{21} & \sigma_{22} & \cdots & \sigma_{2n} \\
\vdots & \vdots & \ddots & \vdots \\
\sigma_{n1} & \sigma_{n2} & \cdots & \sigma_{nn} \\
\end{bmatrix}
\end{align*}\tag{1.77}
$$

$$
\begin{align*}
& \mathbb{E}[\mathrm{X}\mathrm{Y}^T] = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} \mathrm{x} \mathrm{y}^T p_{\mathrm{XY}}(\mathrm{x}, \mathrm{y})  \mathrm{dx}\mathrm{dy} \\
& \mathbb{E}[(\mathrm{X} - \mathbb{E}[\mathrm{X}])(\mathrm{Y} - \mathbb{E}[\mathrm{Y}])^T] = \int_{-\infty}^{\infty} \int_{-\infty}^{\infty} (\mathrm{x} - \mathbb{E}[\mathrm{X}])(\mathrm{y} - \mathbb{E}[\mathrm{Y}])^T p_{\mathrm{XY}}(\mathrm{x}, \mathrm{y})  \mathrm{dx}\mathrm{dy}
\end{align*}
\tag{1.78}
$$

$$
p_{\mathrm{XY}}(\mathrm{x}, \mathrm{y}) = p_{\mathrm{X}}(\mathrm{x})p_{\mathrm{Y}}(\mathrm{y})
\tag{1.79}
$$

$$
\mathbb{E}[\mathrm{X}|\mathrm{Y}=\mathrm{y}] = \int_{-\infty}^{\infty} \mathrm{x} p_{\mathrm{XY}}(\mathrm{x}|\mathrm{y}) \mathrm{dx}
\tag{1.80}
$$

$$
\mathbb{E}[\mathrm{X|Y}] = \int_{-\infty}^{\infty} \mathrm{x} p_{\mathrm{XY}}(\mathrm{x}|\mathrm{Y}) \mathrm{dx}
\tag{1.81}
$$

$$
Cov(\mathrm{X|Y=y}) = \mathbb{E}[(\mathrm{X} - \mathbb{E}[\mathrm{X|Y=y}])(\mathrm{X} - \mathbb{E}[\mathrm{X|Y=y}])^T|\mathrm{Y=y}]
\tag{1.82}
$$

$$
Cov(\mathrm{X|Y}) = \mathbb{E}[(\mathrm{X} - \mathbb{E}[\mathrm{X|Y}])(\mathrm{X} - \mathbb{E}[\mathrm{X|Y}])^T|\mathrm{Y}]
\tag{1.83}
$$

$$
p_{\mathrm{X}}(\mathrm{x}) \approx \sum_{i=1}^{N} w_{X}(\mathrm{x}^{(i)}) \delta(\mathrm{x} - \mathrm{x}^{(i)}) = \frac{1}{N} \sum_{i=1}^{N} \delta(\mathrm{x} - \mathrm{x}^{(i)})
\tag{1.84}
$$

$$
\begin{align*}
\mathbb{E}[\mathrm{X}] &= \int_{-\infty}^{\infty} \mathrm{x} p_{\mathrm{X}}(\mathrm{x}) \mathrm{d}\mathrm{x} \\
&\approx \int_{-\infty}^{\infty} \mathrm{x} \frac{1}{N} \sum_{i=1}^{N} \delta(\mathrm{x}-\mathrm{x}^{(i)}) \mathrm{d}\mathrm{x} \\
&= \frac{1}{N} \sum_{i=1}^{N} \int_{-\infty}^{\infty} \mathrm{x} \delta(\mathrm{x}-\mathrm{x}^{(i)}) \mathrm{d}\mathrm{x} \\
&= \frac{1}{N} \sum_{i=1}^{N} \mathrm{x}^{(i)}
\end{align*}
\tag{1.85}
$$

$$
\begin{align*}
\mathbb{E}[g(\mathrm{X})] &= \int_{-\infty}^{\infty} g(\mathrm{x}) p_{\mathrm{X}}(\mathrm{x}) \mathrm{dx} \\
&\approx \frac{1}{N} \sum_{i=1}^{N} \int_{-\infty}^{\infty} g(\mathrm{x}) \delta(\mathrm{x}-\mathrm{x}^{(i)}) \mathrm{dx} \\
&= \frac{1}{N} \sum_{i=1}^{N} g(\mathrm{x}^{(i)})
\end{align*}
\tag{1.86}
$$

---

### 노트: p.38

$$
\int_{-\infty}^{\infty} f(x) \delta (x-a)dx = \int_{a - \epsilon}^{a + \epsilon} f(x) \delta (x-a)dx
$$

$$
\begin{align*}
\int_{a - \epsilon}^{a + \epsilon} f(x) \delta (x-a)dx &= f(a) \int_{a - \epsilon}^{a + \epsilon} \delta (x-a)dx \\
&=f(a)
\end{align*}
$$

$$
\int_{-\infty}^{\infty} f(x) \delta (x-a)dx = f(a)
$$

---


$$
p_{X}(x) = N(x | \mu, \sigma^2) \equiv \frac{1}{\sqrt{2\pi\sigma^2}} \exp\left\{ -\frac{(x - \mu)^2}{2\sigma^2} \right\}
\tag{1.87}
$$

$$
\begin{align*}
p_{\mathrm{X}}(\mathrm{x}) &= N(\mathrm{x} | \mu_{\mathrm{X}}, P_{\mathrm{XX}}) \\ 
&= \frac{1}{\sqrt{(2\pi)^n \det P_{\mathrm{XX}}}} \exp\left\{ -\frac{1}{2} (\mathrm{x} - \mu_{\mathrm{X}})^T P_{\mathrm{XX}}^{-1} (\mathrm{x} - \mu_{\mathrm{X}}) \right\}
\end{align*}
\tag{1.88}
$$

$$
\int_{-\infty}^{\infty} N(\mathrm{x}|\mu_{\mathrm{X}}, P_{\mathrm{XX}}) \mathrm{dx} = 1 \\
\int_{-\infty}^{\infty} \mathrm{x} N(\mathrm{x}|\mu_{\mathrm{X}}, P_{\mathrm{XX}}) \mathrm{dx} = \mu_{\mathrm{X}} \\
\int_{-\infty}^{\infty} (\mathrm{X} - \mu_{\mathrm{X}})(\mathrm{X} - \mu_{\mathrm{X}})^T N(\mathrm{x}|\mu_{\mathrm{X}}, P_{\mathrm{XX}}) \mathrm{dx} = P_{\mathrm{XX}}
\tag{1.89}
$$

$$
p_{\mathrm{XY}}(\mathrm{x}, \mathrm{y}) = p_{\mathrm{Z}}(\mathrm{z}) = N(\mathrm{z} | \mu_{\mathrm{Z}}, P_{\mathrm{ZZ}})
\tag{1.90}
$$

$$
\mu_{\mathrm{Z}} = \begin{bmatrix}
\mu_{\mathrm{X}} \\
\mu_{\mathrm{Y}}
\end{bmatrix}, \quad P_{\mathrm{ZZ}} = \begin{bmatrix}
P_{\mathrm{XX}} & P_{\mathrm{XY}} \\
P_{\mathrm{YX}} & P_{\mathrm{YY}}
\end{bmatrix}
\tag{1.91}
$$

$$
P_{\mathrm{XX}} = \mathbb{E}[(\mathrm{X} - \mu_{\mathrm{X}})(\mathrm{X} - \mu_{\mathrm{X}})^T], \quad P_{\mathrm{YY}} = \mathbb{E}[(\mathrm{Y} - \mu_{\mathrm{Y}})(\mathrm{Y} - \mu_{\mathrm{Y}})^T] \\
P_{\mathrm{XY}} = \mathbb{E}[(\mathrm{X} - \mu_{\mathrm{X}})(\mathrm{Y} - \mu_{\mathrm{Y}})^T] = P_{\mathrm{YX}}^T
$$

$$
\mathrm{Z} = A\mathrm{X} \sim N(A\mu_{\mathrm{X}}, AP_{\mathrm{XX}}A^T)
\tag{1.92}
$$

$$
\mathrm{X} \sim N(\mu_{\mathrm{X}}, P_{\mathrm{XX}}), \mathrm{Y} \sim N(\mu_{\mathrm{Y}}, P_{\mathrm{YY}})
\tag{1.93}
$$

$$
p_{\mathrm{Y|X}}(\mathrm{y}|\mathrm{x}) = \frac{1}{\sqrt{(2\pi)^n \det P_{\mathrm{Y|X}}}} \exp\left( -\frac{1}{2} \{(\mathrm{y} - \mu_{\mathrm{Y|X}})^T P_{\mathrm{Y|X}}^{-1} (\mathrm{y} - \mu_{\mathrm{Y|X}}) \}\right)
\tag{1.94}
$$

$$
\begin{align*}
&P_{\mathrm{Y|X}} = P_{\mathrm{YY}} - P_{\mathrm{YX}} P_{\mathrm{XX}}^{-1} P_{\mathrm{XY}} \\
&\mu_{\mathrm{Y|X}} = \mu_{\mathrm{Y}} + P_{\mathrm{YX}} P_{\mathrm{XX}}^{-1} (\mathrm{x} - \mu_{\mathrm{X}})
\end{align*}
$$

$$
X_t \equiv X_t(e)
\tag{1.95}
$$

$$
\mathrm{X}_t \equiv \mathrm{X}_t(e) = [X_{t,1}(e) \ X_{t,2}(e) \ \ldots \ X_{t,n}(e)]^T
\tag{1.96}
$$

$$
\mathrm{X}(t) \equiv \mathrm{X}(t, e) = [X_1(t, e) \ X_2(t, e) \ \ldots \ X_n(t, e)]^T
\tag{1.97}
$$

$$
{\text{μ}}_{\mathrm{X}_t} = \mathbb{E}[\mathrm{X}_t] = \int_{-\infty}^{\infty} \mathrm{x}_t p_{\mathrm{X}_t}(\mathrm{x}_t) d\mathrm{x}_t
\tag{1.98}
$$

$$
\begin{align*}
R_{\mathrm{X}_k \mathrm{X}_l} &= \mathbb{E}[\mathrm{X}_k \mathrm{X}_l^T] \\
&= \int_{-\infty}^{\infty} \mathrm{x}_k \mathrm{x}_l^T p_{\mathrm{X}_k \mathrm{X}_l}(\mathrm{x}_k, \mathrm{x}_l) d\mathrm{x}_k d\mathrm{x}_l \\
&= \begin{bmatrix}
\mathbb{E}[X_{k,1} X_{l,1}] & \cdots & \mathbb{E}[X_{k,1} X_{l,n}] \\
\vdots & \ddots & \vdots \\
\mathbb{E}[X_{k,n} X_{l,1}] & \cdots & \mathbb{E}[X_{k,n} X_{l,n}]
\end{bmatrix}
\end{align*}
\tag{1.99}
$$

$$
P_{\mathrm{X}_k \mathrm{X}_l} = \mathbb{E}[(\mathrm{X}_k - \mathbb{E}[\mathrm{X}_k])(\mathrm{X}_l - \mathbb{E}[\mathrm{X}_l])^T]
\tag{1.100}
$$

$$
R_{\mathrm{W}_t \mathrm{W}_{t+m}} = \mathbb{E}[\mathrm{W}_t \mathrm{W}_{t+m}^{T}]=S_t \delta_m
\tag{1.101}
$$

$$
\delta_m = \begin{cases}
1, & m=0 \\
0, & m \neq 0
\end{cases}
\tag{1.102}
$$

$$
p_{\mathrm{X}_t}(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{x}_{t-1}, \ldots, \mathrm{x}_0) = p_{\mathrm{X}_t}(\mathrm{x}_{t+1}|\mathrm{x}_t)
\tag{1.103}
$$

$$
p_{\mathrm{X}}(\mathrm{x}(t)|\mathrm{x}(s), s \leq t_1) = p_{\mathrm{X}}(\mathrm{x}(t)|\mathrm{x}(t_1)), \quad \forall t \geq t_1
\tag{1.104}
$$

$$
\mathrm{X}_{t+1} = F_t \mathrm{X}_t + G_t \mathrm{W}_t
\tag{1.105}
$$

$$
\begin{align*}
& \mathbb{E}[\mathrm{X}_0] = \overline{\mathrm{x}_0} \\
& \mathbb{E}[(\mathrm{X}_0 - \overline{\mathrm{x}_0})(\mathrm{X}_0 - \overline{\mathrm{x}_0})^T] = P_0
\end{align*}
\tag{1.106}
$$

$$
\begin{align*}
&\mathbb{E}[\mathrm{W}_t] = 0 \\
&\mathbb{E}[\mathrm{W}_t \mathrm{W}_{t+m}^T] = Q_t \delta_m
\end{align*}
\tag{1.107}
$$

$$
\begin{align*}
\mathbb{E}[\mathrm{X}_{t+1}] & = \mathbb{E}[F_t\mathrm{X}_t + G_t\mathrm{W}_t] \\
& = F_t \mathbb{E}[\mathrm{X}_t] + G_t \mathbb{E}[\mathrm{W}_t] \\
& = F_t \mathbb{E}[\mathrm{X}_t]
\end{align*}
\tag{1.108}
$$

$$
\begin{align*}
(\mathrm{X}_{t+1} &- \mathbb{E}[\mathrm{X}_{t+1}])(\mathrm{X}_{t+1} - \mathbb{E}[\mathrm{X}_{t+1}])^T \\
& = (F_t\mathrm{X}_t + G_t \mathrm{W}_t - F_t\mathbb{E}[\mathrm{X}_t])(F_t\mathrm{X}_t + G_t \mathrm{W}_t - F_t\mathbb{E}[\mathrm{X}_t])^T \\
& = F_t(\mathrm{X}_t - \mathbb{E}[\mathrm{X}_t])(\mathrm{X}_t - \mathbb{E}[\mathrm{X}_t])^T F_t + G_t \mathrm{W}_t \mathrm{W}_t^TG_t^T \\
& \qquad+ G_t \mathrm{W}_t (\mathrm{X}_t - \mathbb{E}[\mathrm{X}_t])^T F_t + F_t(\mathrm{X}_t - \mathbb{E}[\mathrm{X}_t]) \mathrm{W}_t^T
\end{align*}
\tag{1.109}
$$

$$
\begin{align*}
P_{t+1} &= \mathbb{E}[(\mathrm{X}_{t+1} - \mathbb{E}[\mathrm{X}_{t+1}])(\mathrm{X}_{t+1} - \mathbb{E}[\mathrm{X}_{t+1}])^T] \\
&= F_t\mathbb{E}[(\mathrm{X}_t - \mathbb{E}[\mathrm{X}_t])(\mathrm{X}_t - \mathbb{E}[\mathrm{X}_t])^T]F_t^T + G_t\mathbb{E}[\mathrm{W}_t \mathrm{W}_t^T]G_t^T \\
& \qquad + G_t\mathbb{E}[\mathrm{W}_t(\mathrm{X}_t - \mathbb{E}[\mathrm{X}_t])^T]F_t + F_t\mathbb{E}[(\mathrm{X}_t - \mathbb{E}[\mathrm{X}_t])\mathrm{W}_t^T]G_t^T \\
& = F_t P_t F_t^T + G_t Q_t G_t^T + G_t M_t^T F_t + F_t M_t G_t^T
\end{align*}
\tag{1.110}
$$

$$
M_t = \mathbb{E}[(\mathrm{X}_t - \mathbb{E}[\mathrm{X}_t])\mathrm{W}_t^T] = 0
\tag{1.111}
$$

---

### 노트: p.52

$$
\begin{align*}
& X_{t+1} = X_t + W, X_0 = 0, P_0 = 0 \\
& \mathbb{E}[W_t^2]=q
\end{align*}
$$

---

$$
\begin{align*}
\mathbb{E}_{\mathrm{x} \sim p(\mathrm{x})}[f(\mathrm{x})] &= \int_\mathrm{x} p(\mathrm{x})f(\mathrm{x})d\mathrm{x} \\
& = \int_\mathrm{x} \frac{q(\mathrm{x})}{q(\mathrm{x})} p(\mathrm{x})f(\mathrm{x})d\mathrm{x} \\
& = \int_\mathrm{x} q(\mathrm{x}) \frac{p(\mathrm{x})}{q(\mathrm{x})} f(\mathrm{x})d\mathrm{x} \\
& = \mathbb{E}_{\mathrm{x} \sim q(\mathrm{x})}\left[ \frac{p(\mathrm{x})}{q(\mathrm{x})} f(\mathrm{x}) \right]
\end{align*}
\tag{1.112}
$$

$$
Var_{p(\mathrm{x})}[f(\mathrm{x})] = \mathbb{E}_{\mathrm{x} \sim p(\mathrm{x})}[(f(\mathrm{x}))^2] - (\mathbb{E}_{\mathrm{x} \sim p(\mathrm{x})}[f(\mathrm{x})])^2
\tag{1.113}
$$

$$
\begin{align*}
\text{Var}_{q(\mathrm{x})}\left[\frac{p(\mathrm{x})}{q(\mathrm{x})}f(\mathrm{x})\right] &= \mathbb{E}_{\mathrm{x} \sim q(\mathrm{x})}\left[\left(\frac{p(\mathrm{x})}{q(\mathrm{x})}f(\mathrm{x})\right)^2\right] - \left(\mathbb{E}_{\mathrm{x} \sim q(\mathrm{x})}\left[\frac{p(\mathrm{x})}{q(\mathrm{x})}f(\mathrm{x})\right]\right)^2 \\
&= \int \left(\frac{p(\mathrm{x})}{q(\mathrm{x})}f(\mathrm{x})\right)^2 q(\mathrm{x})d\mathrm{x} - \left(\mathbb{E}_{\mathrm{x} \sim p(\mathrm{x})}[f(\mathrm{x})]\right)^2 \\
&= \int \left(f(\mathrm{x})\right)^2 \frac{p(\mathrm{x})}{q(\mathrm{x})} p(\mathrm{x}) d\mathrm{x} - \left(\mathbb{E}_{\mathrm{x} \sim p(\mathrm{x})}[f(\mathrm{x})]\right)^2 \\
&= \mathbb{E}_{\mathrm{x} \sim p(\mathrm{x})}\left[\left(\frac{p(\mathrm{x})}{q(\mathrm{x})}f(\mathrm{x})\right)^2\right] - \left(\mathbb{E}_{\mathrm{x} \sim p(\mathrm{x})}[f(\mathrm{x})]\right)^2
\end{align*}
\tag{1.114}
$$

$$
h(x) = -\log p(\mathrm{x})
\tag{1.115}
$$

$$
\mathcal{H}(p) = \mathbb{E}_{\mathrm{x} \sim p(\mathrm{x})}[- \log p (\mathrm{x})] = -\int_\mathrm{x} p(\mathrm{x}) \log p(\mathrm{x}) d\mathrm{x}
\tag{1.116}
$$

$$
p(x) = \frac{1}{(2\pi\sigma^2)^{1/2}} \exp\left(-\frac{(x - \mu)^2}{2\sigma^2}\right)
\tag{1.117}
$$

$$
\mathcal{H}(p) = \frac{1}{2}(1 + \log (2 \pi \sigma^2))
\tag{1.118}
$$

$$
\begin{align*}
\mathcal{H}(p, q) &= \mathbb{E}_{\mathrm{x} \sim p(\mathrm{x})}[- \log q (\mathrm{x})] \\
&= - \int_\mathrm{x} p(\mathrm{x}) \log q(\mathrm{x}) d\mathrm{x}
\end{align*}
\tag{1.119}
$$

$$
\begin{align*}
D_{KL}(p(\mathrm{x}) \| q(\mathrm{x})) &= -\int_\mathrm{x} p(\mathrm{x})\log q(\mathrm{x}) d\mathrm{x} - \left(-\int_\mathrm{x} p(\mathrm{x})\log p(\mathrm{x}) d\mathrm{x}\right) \\
&= \int_\mathrm{x} p(\mathrm{x}) \log \frac{p(\mathrm{x})}{q(\mathrm{x})} d\mathrm{x}
\end{align*}
\tag{1.120}
$$

$$
D_{KL}(p(\mathrm{x}) \| q(\mathrm{x})) \neq D_{KL}(q(\mathrm{x}) \| p(\mathrm{x}))
\tag{1.121}
$$

$$
\mathbb{E}[f(g(\mathrm{x}))] \leq f(\mathbb{E}[g(\mathrm{x})])
\tag{1.122}
$$

$$
\begin{align*}
D_{KL}(p(\mathrm{x}) || q(\mathrm{x})) &= \int_{\mathrm{x}} p(\mathrm{x}) \log \frac{p(\mathrm{x})}{q(\mathrm{x})} d\mathrm{x} = -\int_{\mathrm{x}} p(\mathrm{x}) \log \frac{q(\mathrm{x})}{p(\mathrm{x})} d\mathrm{x} \\
&\geq -\log \mathbb{E} \left[ \frac{q(\mathrm{x})}{p(\mathrm{x})} \right] = -\log \int_{\mathrm{x}} p(\mathrm{x}) \frac{q(\mathrm{x})}{p(\mathrm{x})} d\mathrm{x} \\
&= -\log \int_{\mathrm{x}} q(\mathrm{x}) d\mathrm{x} = -\log 1 = 0
\end{align*}
\tag{1.123}
$$

$$
D_{KL}(p(\mathrm{x}) || q(\mathrm{x})) = \frac{1}{2} \left( tr(P_q^{-1} P_p) + (\mu_q - \mu_p)^T P_q^{-1} (\mu_q - \mu_p) - n + \log \frac{\det P_q}{\det P_p} \right)
\tag{1.124}
$$

$$
\begin{align*}
\underset{q}{\text{argmin}} D_{KL}(p||q) &= \underset{q}{\text{argmin}} \left\{ -\int_{\mathrm{x}} p(\mathrm{x})\log q(\mathrm{x}) d\mathrm{x} + \int_{\mathrm{x}} p(\mathrm{x})\log p(\mathrm{x}) d\mathrm{x} \right\} \\
&= \underset{q}{\text{argmin}} \left\{ -\int_{\mathrm{x}} p(\mathrm{x})\log q(\mathrm{x}) d\mathrm{x} \right\} \\
&= \underset{q}{\text{argmin}} \mathcal{H}(p, q)
\end{align*}
\tag{1.125}
$$

$$
\hat{\mathrm{x}} = g(\mathrm{z})
\tag{1.126}
$$

$$
p(\mathrm{x} \vert \mathrm{z}) = \frac{p(\mathrm{z}|\mathrm{x})p(\mathrm{x})}{p(\mathrm{z})}
\tag{1.127}
$$

$$
\begin{align*}
\hat{\mathrm{x}}^{MAP} &= \text{argmax} \ p(\mathrm{x}|\mathrm{z}) \\
&=\text{argmax}[p(\mathrm{z}|\mathrm{x})p(\mathrm{x})]
\end{align*}
\tag{1.128}
$$

$$
\hat{\mathrm{x}}^{ML} = \text{argmax} \ p(\mathrm{z}(\mathrm{x}))
\tag{1.129}
$$

$$
\hat{\mathrm{x}}^{ML} = \text{argmax} \ p(\mathrm{z} \vert \mathrm{x})
\tag{1.130}
$$

---

### 노트: p.62

$$
z = x + v
$$

$$
v \sim N(0, \sigma_v^2)
$$

$$
p(z \vert x) = N(z \vert x, \sigma_v^2) = \frac{1}{\sqrt{2 \pi \sigma_v^2}} \exp \left( - \frac{(z-x)^2}{2\sigma_v^2} \right)
$$

$$
\hat{x}^{ML} = \text{argmax} \ p(z \vert x) = z
$$

$$
p(x) = N(x \vert \overline{x}, \sigma_x^2)
$$

$$
\begin{align*}
p(x|z) &= \frac{p(z|x)p(x)}{p(z)} \\
&= \frac{p(z|x)p(x)}{\int p(z|x) p(x) dx} \\
&= \frac{1}{c_0} \exp \left( -\frac{(z - x)^2}{2\sigma_v^2} - \frac{(x - \bar{x})^2}{2\sigma_x^2} \right)
\end{align*}
$$

$$
p(x \vert z) = \frac{1}{c_1} \exp \left( -\frac{(x - \hat{x}(z))^2}{2 \sigma_1^2} \right)
$$

$$
\hat{x}(z) = \overline{x} + \frac{\sigma_x^2}{\sigma_x^2 + \sigma_v^2} (z - \overline{x}), \quad \sigma_1^2 = \frac{\sigma_x^2 \sigma_v^2}{\sigma_x^2 + \sigma_v^2}, \quad c_1 = \frac{1}{\sqrt{2\pi\sigma_1^2}}
$$

$$
\begin{align*}
\hat{x}^{MAP} &= \text{argmax} \ p(x|z) = \hat{x}(z) \\
&= \overline{x} + \frac{\sigma_x^2}{\sigma_x^2 + \sigma_v^2}(z - \overline{x})
\end{align*}
$$

---

$$
\frac{df(\mathrm{x})}{d\mathrm{x}} = \nabla_\mathrm{x} f(\mathrm{x}) = \left[ \begin{array}{c}
\frac{\partial f}{\partial x_1} \\
\frac{\partial f}{\partial x_2} \\
\vdots \\
\frac{\partial f}{\partial x_n}
\end{array} \right] \in R^n
\tag{1.131}
$$

$$
f(\mathrm{x}) = \mathrm{w}^T\mathrm{x} = w_1 x_1 + w_2 x_2 + \cdots + w_n x_n
\tag{1.132}
$$

$$
\nabla_\mathrm{x} f(\mathrm{x}) = \left[ \begin{array}{c}
\frac{\partial f}{\partial x_1} \\
\frac{\partial f}{\partial x_2} \\
\vdots \\
\frac{\partial f}{\partial x_n}
\end{array} \right]
= \left[ \begin{array}{c}
w_1 \\
w_2 \\
\cdots \\
w_n
\end{array} \right] = \mathrm{w}
\tag{1.133}
$$

$$
\begin{align*}
f(\mathrm{x}) &= a_{11}x_1^2 + a_{12}x_1x_2 + \cdots + a_{1n}x_1x_n \\
& \quad + a_{21}x_2x_1 + a_{22}x_2^2 + \cdots + a_{2n}x_2x_n \\
& \quad + \cdots \\
& \quad + a_{n1}x_nx_1 + a_{n2}x_nx_2 + \cdots + a_{nn}x_n^2
\end{align*}
\tag{1.134}
$$

$$
\begin{align*}
\nabla_\mathrm{x} f(\mathrm{x}) &= \nabla_\mathrm{x} \mathrm{x}^T \mathrm{A} \mathrm{x} \tag{1.135} \\
& = \left[ \begin{array}{c}
2a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n + a_{21}x_2 + \cdots + a_{1n}x_n \\
a_{12}x_1 + a_{21}x_1 +  2a_{22}x_2 + \cdots + a_{2n}x_n + a_{32}x_2 + \cdots + a_{n2}x_n \\
\vdots \\
a_{1n}x_1 + a_{2n}x_2 + \cdots + a_{n1}x_1 + a_{n2}x_2 + \cdots + 2a_{nn}x_n \\
\end{array} \right] \\
&= (\mathrm{A} + \mathrm{A}^T)\mathrm{x}
\end{align*}
$$

$$
\frac{dg(\mathrm{x})}{d\mathrm{x}} = \nabla_\mathrm{x} g(\mathrm{x}) = \left[ \begin{array}{ccc}
\frac{\partial g_1}{\partial x_1} & \frac{\partial g_2}{\partial x_1} & \cdots & \frac{\partial g_m}{\partial x_1} \\
\frac{\partial g_1}{\partial x_2} & \frac{\partial g_2}{\partial x_2} & \cdots & \frac{\partial g_m}{\partial x_2} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial g_1}{\partial x_n} & \frac{\partial g_2}{\partial x_n} & \cdots & \frac{\partial g_m}{\partial x_n}
\end{array} \right] \in R^{n \times m}
\tag{1.136}
$$

$$
\begin{align*}
\nabla_\mathrm{x} g(\mathrm{x}) = \nabla_\mathrm{x} \mathrm{A}\mathrm{x} & = \nabla_x \left[ \begin{array}{c}
a_{11}x_1 + a_{12}x_2 + \cdots + a_{1n}x_n \\
a_{21}x_1 + a_{22}x_2 + \cdots + a_{2n}x_n \\
\vdots \\
a_{n1}x_1 + a_{n2}x_2 + \cdots + a_{nn}x_n
\end{array} \right] \\
&= \left[ \begin{array}{ccc}
a_{11} & a_{21} & \cdots & a_{n1} \\
a_{12} & a_{22} & \cdots & a_{n2} \\
\vdots & \vdots & \ddots & \vdots \\
a_{1n} & a_{2n} & \cdots & a_{nn}
\end{array} \right] = \mathrm{A}^T
\end{align*}
\tag{1.137}
$$

$$
\begin{align*}
\frac{d \nabla_\mathrm{x} f(\mathrm{x})}{d\mathrm{x}} = \nabla_x (\nabla_\mathrm{x} f(\mathrm{x})) = \nabla_\mathrm{x}^2 f(\mathrm{x}) = \left[ \begin{array}{ccc}
\frac{\partial^2 f}{\partial x_1^2} & \frac{\partial^2 f}{\partial x_1 \partial x_2} & \cdots & \frac{\partial^2 f}{\partial x_1 \partial x_n} \\
\frac{\partial^2 f}{\partial x_2 \partial x_1} & \frac{\partial^2 f}{\partial x_2^2} & \cdots & \frac{\partial^2 f}{\partial x_2 \partial x_n} \\
\vdots & \vdots & \ddots & \vdots \\
\frac{\partial^2 f}{\partial x_n \partial x_1} & \frac{\partial^2 f}{\partial x_n \partial x_2} & \cdots & \frac{\partial^2 f}{\partial x_n^2}
\end{array} \right]
\end{align*}
\tag{1.138}
$$

$$
\begin{align*}
\frac{df(\mathrm{Y})}{d\mathrm{Y}} = \nabla_{\mathrm{Y}} f(\mathrm{Y}) = \left[ \begin{array}{ccc}
\frac{\partial f}{\partial y_{11}} & \frac{\partial f}{\partial y_{12}} & \cdots & \frac{\partial f}{\partial y_{1n}} \\
\frac{\partial f}{\partial y_{21}} & \frac{\partial f}{\partial y_{22}} & \cdots & \frac{\partial f}{\partial y_{2n}} \\
\vdots & \vdots & \ddots &
\vdots \\
\frac{\partial f}{\partial y_{m1}} & \frac{\partial f}{\partial y_{m2}} & \cdots & \frac{\partial f}{\partial y_{mn}}
\end{array} \right] \in \mathbb{R}^{m \times n}
\end{align*}
\tag{1.139}
$$

$$
\begin{align*}
\nabla_{\mathrm{X}} f(\mathrm{X}) &= \nabla_{\mathrm{X}} tr(\mathrm{W}\mathrm{X}) \\
&= \nabla_{\mathrm{X}} (w_{11}x_{11} + w_{12}x_{21} + \cdots + w_{1n}x_{n1} \\
& \qquad + w_{21}x_{12} + w_{22}x_{22} + \cdots + w_{2n}x_{n2} \\
& \qquad + \cdots \\
& \qquad + w_{n1}x_{1n} + w_{n2}x_{2n} + \cdots + w_{nn}x_{nn}) \\
&= \left[ \begin{array}{cccc}
w_{11} & w_{21} & \cdots & w_{n1} \\
w_{12} & w_{22} & \cdots & w_{n2} \\
\vdots & \vdots & \ddots & \vdots \\
w_{1n} & w_{2n} & \cdots & w_{nn}
\end{array} \right] = \mathrm{W}^T
\end{align*}
\tag{1.140}
$$

$$
\nabla_\mathrm{x}f(\mathrm{X}) = \nabla_\mathrm{x} \det (\mathrm{X}) = adj^T(\mathrm{X})
\tag{1.141}
$$

$$
\begin{align*}
\nabla_\mathrm{x}f(\mathrm{X}) = \nabla_\mathrm{x} \log(\det(\mathrm{X})) & = \frac{\nabla_{\mathrm{x}} \det(\mathrm{X})}{\det (\mathrm{X})} \\
& = \frac{adj^T (\mathrm{X})}{\det (\mathrm{X})} = \mathrm{X}^{-T}
\end{align*}
\tag{1.142}
$$

---

### 용어 설명 : p.68

$$
\mathrm{X}^{-1} = \frac{\left[ \begin{array}{cc}
x_{22} & -x_{12} \\
-x_{21} & x_{11}
\end{array} \right]}{(x_{11}x_{22} - x_{12}x_{21})} = \frac{adj(\mathrm{X})}{\det(\mathrm{X})}
$$

$$
\nabla_{\mathrm{X}} \det(\mathrm{X}) = \left[ \begin{array}{cc}
x_{22} & -x_{21} \\
-x_{12} & x_{11}
\end{array} \right] = adj^T(\mathrm{X})
$$

---

$$
\mathrm{A} = \mathrm{L}\mathrm{L}^T = \mathrm{U}^T\mathrm{U}
\tag{1.143}
$$

$$
\mathrm{A}^{-1} = \mathrm{L}^{-T}\mathrm{L}^{-1} = \mathrm{U}^{-1}\mathrm{U}^{-T}
\tag{1.144}
$$

$$
\det \mathrm{A} = (\det\mathrm{L})^2 = (\det\mathrm{U})^2
\tag{1.145}
$$

---

### 용어 설명 : p.69

$$
\mathrm{x}^T\mathrm{Ax} > 0, \quad \forall\mathrm{x} \neq 0
$$

$$
\mathrm{x}^T\mathrm{Ax} \geq 0, \quad \forall\mathrm{x}
$$

---

$$
\theta^{*} = \underset{\theta}{\text{argmin}} \ L(\theta), \theta \in R^n
\tag{1.146}
$$

$$
L(\theta + \eta\mathrm{d}) \approx L(\theta) + \nabla_\theta^T L(\theta) \eta \mathrm{d}
\tag{1.147}
$$

$$
\nabla_{\theta} L(\theta) = \left[ \begin{array}{c}
\frac{\partial L(\theta)}{\partial \theta_1} \\
\frac{\partial L(\theta)}{\partial \theta_2} \\
\vdots \\
\frac{\partial L(\theta)}{\partial \theta_n}
\end{array} \right]
\tag{1.148}
$$

$$
\begin{align*}
L(\theta) - L(\theta + \eta \mathrm{d}) & \approx - \nabla_\theta^T L(\theta)\eta \mathrm{d} \\
&= -\cos(\phi) \vert \nabla_\theta L(\theta) \vert \eta
\end{align*}
\tag{1.149}
$$

$$
\mathrm{d} = -\frac{\nabla_\theta L(\theta)}{\vert \nabla_\theta L(\theta) \vert}
\tag{1.150}
$$

$$
\begin{align*}
\theta + \eta \mathrm{d} & = \theta - \eta \frac{\nabla_\theta L(\theta)}{\vert \nabla_\theta L(\theta) \vert} \\
& = \theta - \alpha \nabla_\theta L(\theta),\quad \alpha > 0
\end{align*}
\tag{1.151}
$$

