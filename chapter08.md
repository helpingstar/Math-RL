$$
J = \mathbb{E}_{\tau \sim p(\tau)} \left[ \sum_{t=0}^{T} \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right]
\tag{8.1}
$$

$$
J = \mathbb{E}_{\tau \sim p(\tau)} \left[ \sum_{t=0}^{T} \gamma^t \left( r(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) \right) \right]
\tag{8.2}
$$

$$
\begin{align*}
J &= \int_{\tau} \left[ \sum_{t=0}^{T} \gamma^t \left( r(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) \right) \right] p(\tau) \mathrm{d}\tau \\

&= \sum_{t=0}^{T} \int_{(\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma^t \left( r(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) \right) \right] p(\mathrm{x}_t, \mathrm{u}_t) d\mathrm{x}_t d\mathrm{u}_t \\

&= \sum_{t=0}^{T} \mathbb{E}_{(\mathrm{x}_t, \mathrm{u}_t) \sim p(\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma^t \left( r(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) \right) \right]
\end{align*}
\tag{8.3}
$$

$$
\begin{align*}
J &= \sum_{t=0}^{T} \mathbb{E}_{(\mathrm{x}_t, \mathrm{u}_t) \sim p(\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right] - \sum_{t=0}^{T} \alpha \gamma^t \int_{(\mathrm{x}_t, \mathrm{u}_t)} \log \pi(\mathrm{u}_t | \mathrm{x}_t) p(\mathrm{x}_t, \mathrm{u}_t) d\mathrm{x}_t d\mathrm{u}_t \\

&= \sum_{t=0}^{T} \mathbb{E}_{(\mathrm{x}_t, \mathrm{u}_t) \sim p(\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right] - \sum_{t=0}^{T} \alpha \gamma^t \int_{(\mathrm{x}_t, \mathrm{u}_t)} \log \pi(\mathrm{u}_t | \mathrm{x}_t) \pi(\mathrm{u}_t | \mathrm{x}_t) p(\mathrm{x}_t) d\mathrm{x}_t d\mathrm{u}_t \\

&= \sum_{t=0}^{T} \mathbb{E}_{(\mathrm{x}_t, \mathrm{u}_t) \sim p(\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right] + \sum_{t=0}^{T} \gamma^t \mathbb{E}_{\mathrm{x}_t \sim p(\mathrm{x}_t)} \left[ \alpha \mathcal{H}(\pi(\mathrm{u}_t | \mathrm{x}_t)) \right]
\end{align*}
\tag{8.4}
$$

$$
\mathcal{H}(\pi(\mathrm{u}_t | \mathrm{x}_t)) = -\int_{\mathrm{u}_t} \log \pi(\mathrm{u}_t | \mathrm{x}_t) \pi(\mathrm{u}_t | \mathrm{x}_t) d\mathrm{u}_t
\tag{8.5}
$$

$$
\begin{align*}
J &= \sum_{t=0}^{T} \mathbb{E}_{(\mathrm{x}_t, \mathrm{u}_t) \sim p(\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right] + \sum_{t=0}^{T} \gamma^t \mathbb{E}_{\mathrm{x}_t \sim p(\mathrm{x}_t)} \left[ \alpha \mathcal{H}(\pi(\mathrm{u}_t | \mathrm{x}_t)) \right] \\

&= \sum_{t=0}^{T} \gamma^t \mathbb{E}_{(\mathrm{x}_t, \mathrm{u}_t) \sim p(\mathrm{x}_t, \mathrm{u}_t)} \left[ r(\mathrm{x}_t, \mathrm{u}_t) + \alpha \mathcal{H}(\pi(\cdot | \mathrm{x}_t)) \right]

\end{align*}
\tag{8.6}
$$

$$
V^{\pi}(\mathrm{x}_t) = \mathbb{E}_{\tau_{u_t: u_T} \sim p(\tau_{u_t : u_T} | \mathrm{x}_t)} \left[ \sum_{k=t}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right]
\tag{8.7}
$$

$$
V^{\pi}_{soft}(\mathrm{x}_t) = \mathbb{E}_{\tau_{u_t: u_T} \sim p(\tau_{u_t : u_T} | \mathrm{x}_t)} \left[ \sum_{k=t}^{T} \gamma^{k-t} \left( r(\mathrm{x}_k, \mathrm{u}_k) - \alpha \log \pi(\mathrm{u}_k | \mathrm{x}_k) \right) \right]
\tag{8.8}
$$

$$
J = \mathbb{E}_{\mathrm{x}_0 \sim p(\mathrm{x}_0)} \left[ V^{\pi}_{soft} (\mathrm{x}_0) \right]
\tag{8.9}
$$

$$
\begin{align*}
V^{\pi}_{soft}(\mathrm{x}_t) &= \mathbb{E}_{\tau_{u_t:u_T} \sim p(\tau_{u_t:u_T} | \mathrm{x}_t)} \left[ -\alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) + \sum_{k=t}^{T} \gamma^{k-t} \left( r_k - \gamma \alpha \log \pi(\mathrm{u}_{k+1} | \mathrm{x}_{k+1}) \right) \right] \\

&= \int_{\tau_{u_t:u_T}} -\alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) p(\tau_{u_t:u_T} | \mathrm{x}_t) d\tau_{u_t:u_T} \\

&\qquad +\int_{\tau_{u_t:u_T}} \sum_{k=t}^{T} \gamma^{k-t} \left[ r_k - \gamma \alpha \log \pi(\mathrm{u}_{k+1} | \mathrm{x}_{k+1}) \right] p(\tau_{u_t:u_T} | \mathrm{x}_t) d\tau_{u_t:u_T} \\

&=\int_{\mathrm{u}_t} \int_{\tau_{x_{t+1}:u_T}} -\alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) p(\tau_{x_{t+1}:u_T} | \mathrm{x}_t, \mathrm{u}_t) \pi(\mathrm{u}_t | \mathrm{x}_t) d\tau_{x_{t+1}:u_T} d\mathrm{u}_t \\

& \qquad + \int_{\mathrm{u}_t} Q_{soft}^{\pi} (\mathrm{x}_t, \mathrm{u}_t)d \mathrm{u}_t\\

&= \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t \vert \mathrm{x}_t)} [ -\alpha \log \pi(\mathrm{u}_t \vert \mathrm{x}_t) + Q_{soft}^{\pi}(\mathrm{u}_t, \mathrm{x}_t) ]
\end{align*}
\tag{8.10}
$$

$$
\begin{align*}
Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) &= \int_{\tau_{x_{t+1}:u_T}} \sum_{k=t}^{T} \gamma^{k-t} \left[ r_k - \gamma \alpha \log \pi(\mathrm{u}_{k+1} | \mathrm{x}_{k+1}) \right] p(\tau_{x_{t+1}:u_T} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{x_{t+1}:u_T} \\

&=\mathbb{E}_{\tau_{x_{t+1}:u_T} \sim p(\tau_{x_{t+1}:u_T} | \mathrm{x}_t, \mathrm{u}_t)} \left[ \sum_{k=t}^{T} \gamma^{k-t} \left( r_k - \gamma \alpha \log \pi(\mathrm{u}_{k+1} | \mathrm{x}_{k+1}) \right) \right]
\end{align*}
\tag{8.11}
$$

$$
J = \mathbb{E}_{x_0 \sim p(x_0), \mathrm{u}_0 \sim \pi(u_0 | x_0)} \left[ Q^{\pi}_{soft}(\mathrm{x}_0, \mathrm{u}_0) \right]
\tag{8.12}
$$

$$
\begin{align*}
& V^{\pi}_{soft}(\mathrm{x}_t) = \mathbb{E}_{\tau_{u_t:u_T} \sim p(\tau_{u_t:u_T} | \mathrm{x}_t)} \left[ \sum_{k=t}^{T} \gamma^{k-t} \left( r(\mathrm{x}_k, \mathrm{u}_k) - \alpha \log \pi(\mathrm{u}_k | \mathrm{x}_k) \right) \right] \\
& Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) = \mathbb{E}_{\tau_{x_{t+1}:u_T} \sim p(\tau_{x_{t+1}:u_T} | \mathrm{x}_t, \mathrm{u}_t)} \left[ \sum_{k=t}^{T} \gamma^{k-t} \left( r(\mathrm{x}_k, \mathrm{u}_k) - \gamma \alpha \log \pi(\mathrm{u}_{k+1} | \mathrm{x}_{k+1}) \right) \right]


\end{align*}
\tag{8.13}
$$

$$
V^{\pi}_{soft}(\mathrm{x}_t) = \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) \right]
\tag{8.14}
$$

$$
\begin{align*}
Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) &= \int_{\tau_{x_{t+1} : u_T}} \left( \sum_{k=t}^{T} \gamma^{k-t} \left( r_k - \gamma \alpha \log \pi(\mathrm{u}_{k+1} | \mathrm{x}_{k+1}) \right) p(\tau_{x_{t+1} : u_T} | \mathrm{x}_t, \mathrm{u}_t) \right) d\tau_{x_{t+1} : u_T} \\

&= \int_{\tau_{x_{t+1} : u_T}} \left( r_t + \sum_{k=t+1}^{T} \gamma^{k-t} \left( r_k - \alpha \log \pi(\mathrm{u}_k | \mathrm{x}_k) \right) \right) p(\tau_{x_{t+1} : u_T} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{x_{t+1} : u_T} \\

&= r_t + \int_{\tau_{x_{t+1} : u_T}} \left( \sum_{k=t+1}^{T} \gamma^{k-t} \left( r_k - \alpha \log \pi(\mathrm{u}_k | \mathrm{x}_k) \right) \right) p(\tau_{x_{t+1} : u_T} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{x_{t+1} : u_T}
\end{align*}
\tag{8.15}
$$

$$
\begin{align*}
p(\tau_{x_{t+1} : u_T} | \mathrm{x}_t, \mathrm{u}_t) &= p(\mathrm{x}_{t+1}, \tau_{u_{t+1} : u_T} | \mathrm{x}_t, \mathrm{u}_t) \\

&= p(\tau_{u_{t+1} : u_T} | \mathrm{x}_{t+1}, \mathrm{x}_t, \mathrm{u}_t) p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t) \\

&= p(\tau_{u_{t+1} : u_T} | \mathrm{x}_{t+1}) p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t)
\end{align*}
\tag{8.16}
$$

$$
\begin{align*}
\int_{\tau_{x_{t+1}:u_T}} &\left( \sum_{k=t+1}^{T} \gamma^{k-t} (r_k - \alpha \log \pi(\mathrm{u}_k | \mathrm{x}_k)) \right) p(\tau_{x_{t+1}:u_T} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{x_{t+1}:u_T} \\

&= \int_{\tau_{x_{t+1}:u_T}} \left( \sum_{k=t+1}^{T} \gamma^{k-t} (r_k - \alpha \log \pi(\mathrm{u}_k | \mathrm{x}_k)) \right) p(\tau_{u_{t+1}:u_T} | \mathrm{x}_{t+1}) p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{x_{t+1}:u_T} \\

&= \int_{\mathrm{x}_{t+1}} \gamma  \left[ \int_{\tau_{u_{t+1}:u_T}} \left( \sum_{k=t+1}^{T} \gamma^{k-t-1} \left( r_k - \alpha \log \pi(\mathrm{u}_k | \mathrm{x}_k) \right) \right) p(\tau_{u_{t+1}:u_T} | \mathrm{x}_{t+1}) d\tau_{u_{t+1}:u_T} \right] p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t)  d\mathrm{x}_{t+1}
\end{align*}
\tag{8.17}
$$

$$
\begin{align*}
Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) &= r_t + \gamma \int_{\mathrm{x}_{t+1}} V^{\pi}_{soft}(\mathrm{x}_{t+1}) p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t) d\mathrm{x}_{t+1} \\

&= r_t + \gamma \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t)}[V^{\pi}_{soft}(\mathrm{x}_{t+1})]
\end{align*}
\tag{8.18}
$$

$$
V^{\pi}_{soft}(\mathrm{x}_t) = \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) \right]
\tag{8.19}
$$

$$
V^{\pi}_{soft}(\mathrm{x}_t) = \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ r_t + \gamma \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t)} \left[ V^{\pi}_{soft}(\mathrm{x}_{t+1}) \right] - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) \right]
\tag{8.20}
$$

$$
\begin{align*}
Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) = & r_t + \gamma \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t), \mathrm{u}_{t+1} \sim \pi(\mathrm{u}_{t+1} | \mathrm{x}_{t+1})} \\
& \left[ Q^{\pi}_{soft}(\mathrm{x}_{t+1}, \mathrm{u}_{t+1}) - \alpha \log \pi(\mathrm{u}_{t+1} | \mathrm{x}_{t+1}) \right]
\end{align*}
\tag{8.21}
$$

$$
\begin{align*}
J_t &= V^{\pi}_{soft}(\mathrm{x}_t) = \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) \right] \\

&= \int_{\mathrm{u}_t} \left[ Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) \right] \pi(\mathrm{u}_t | \mathrm{x}_t) d\mathrm{u}_t
\end{align*}
\tag{8.22}
$$

$$
\frac{\partial J_t}{\partial \pi(\mathrm{u}_t | \mathrm{x}_t)} = 0 = \int_{\mathrm{u}_t} \left[ Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) - \alpha \right] d\mathrm{u}_t
\tag{8.23}
$$

$$
\pi(\mathrm{u}_t | \mathrm{x}_t) = \exp\left(\frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) - 1\right) \propto \exp\left(\frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t)\right)
\tag{8.24}
$$

$$
\begin{align*}
\pi(\mathrm{u}_t | \mathrm{x}_t) &= \frac{\exp\left(\frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t)\right)}{\int_{\mathrm{u}'} \exp\left(\frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}')\right) d\mathrm{u}'} \\

&= \underset{\mathrm{u}_t}{\text{softmax}} \left( \frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) \right)
\end{align*}
\tag{8.25}
$$

$$
\pi(\mathrm{x}_t)=\underset{\mathrm{u}_t}{\text{argmax}}Q^{\pi}(\mathrm{x}_t, \mathrm{u}_t)
\tag{8.26}
$$

$$
\begin{align*}
V^{\pi}_{soft}(\mathrm{x}_t) &= \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) \right] \\

&= \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) - \left( Q_{soft}^{\pi}(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \int_{\mathrm{u}'_{t}} \exp\left( \frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}') \right) d\mathrm{u}' \right) \right] \\

&= \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ \alpha \log \int_{\mathrm{u}_t} \exp\left(\frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}')\right) d\mathrm{u}' \right] \\

&= \alpha \log \int_{\mathrm{u}'} \exp\left(\frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}')\right) d\mathrm{u}'

\end{align*}
\tag{8.27}
$$

$$
\begin{align*}
J_t &= \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) \right] \\

&= -\mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ \alpha \left( \log \pi(\mathrm{u}_t | \mathrm{x}_t) - \frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) \right) \right] \\

&= -\alpha \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ \log \pi(\mathrm{u}_t | \mathrm{x}_t) - \log \exp \left( \frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) \right) \right] \\

&= -\alpha \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ \log \pi(\mathrm{u}_t | \mathrm{x}_t) - \log \exp \left( \frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) \right) + \log Z(\mathrm{x}_t) - \log Z(\mathrm{x}_t) \right] \\

&= -\alpha \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ \log \frac{\pi(\mathrm{u}_t \vert \mathrm{x}_t)}{\frac{\exp\left(\frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t)\right)}{Z(\mathrm{x}_t)}} -\log Z (\mathrm{x}_t) \right] \\

&= -\alpha D_{KL} \left( \pi(\mathrm{u}_t | \mathrm{x}_t) \Bigg\| \frac{\exp\left(\frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t)\right)}{Z(\mathrm{x}_t)} \right) + \alpha \log Z(\mathrm{x}_t)
\end{align*}
\tag{8.28}
$$

$$
Z(\mathrm{x}_t)=\int_{\mathrm{u}'} \exp\left(\frac{1}{\alpha}Q_{soft}^{\pi}(\mathrm{x}_t, \mathrm{u}')\right)d \mathrm{u}'
\tag{8.29}
$$

$$
\begin{align*}
\pi(\mathrm{u}_t | \mathrm{x}_t) &= \text{argmax} \; \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) - \alpha \log \pi(\mathrm{u}_t | \mathrm{x}_t) \right] \\

&= \underset{\pi}{\text{argmin}} \; D_{KL} \left( \pi(\mathrm{u}_t | \mathrm{x}_t) \middle\| \frac{\exp\left( \frac{1}{\alpha} Q^{\pi}_{soft}(\mathrm{x}_t, \mathrm{u}_t) \right)}{Z(\mathrm{x}_t)} \right)
\end{align*}
\tag{8.30}
$$
