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
