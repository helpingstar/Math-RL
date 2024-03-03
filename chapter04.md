$$
\begin{align*}
\nabla_\theta J(\theta) &= \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \sum_{t=0}^T \left( \gamma^t \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \left( \sum_{k=t}^T \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) \right) \right] \\

&= \sum_{t=0}^T \left\{ \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \gamma^t \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \left( \sum_{k=t}^T \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) \right] \right\}
\end{align*}
\tag{4.1}
$$

$$
\begin{align*}
\tau &= (\mathrm{x}_0, \mathrm{u}_0, \mathrm{x}_1, \mathrm{u}_1, \ldots, \mathrm{x}_T, \mathrm{u}_T) \\

&= (\mathrm{x}_0, \mathrm{u}_0, \ldots, \mathrm{x}_t, \mathrm{u}_t) \cup (\mathrm{x}_{t+1}, \mathrm{u}_{t+1}, \ldots, \mathrm{x}_T, \mathrm{u}_T) \\

&= \tau_{\mathrm{x}_0:\mathrm{u}_t} \cup \tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}
\end{align*}
\tag{4.2}
$$

$$
\begin{align*}
\nabla_\theta J(\theta) & = \sum_{t=0}^T \int_{\tau_{\mathrm{x}_0:\mathrm{u}_t}} \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} \left( \gamma^t \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \left( \sum_{k=t}^T \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) \right) \\

& \qquad p_\theta(\tau_{\mathrm{x}_0:\mathrm{u}_t}, \tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} d\tau_{\mathrm{x}_0:\mathrm{u}_t} \\

& = \sum_{t=0}^T \int_{\tau_{\mathrm{x}_0:\mathrm{u}_t}} \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} \left( \gamma^t \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \left( \sum_{k=t}^T \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) \right) \\

& \qquad p_\theta(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} \vert \tau_{\mathrm{x}_{0}:\mathrm{u}_t})p_\theta(\tau_{\mathrm{x}_0: \mathrm{u}_t}) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} d\tau_{\mathrm{x}_0:\mathrm{u}_t} \\

&= \sum_{t=0}^T \int_{\tau_{\mathrm{x}_0:\mathrm{u}_t}} \gamma^t \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \\

& \qquad \left[ \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} \left( \sum_{k=t}^T \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p_\theta(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \tau_{\mathrm{x}_0:\mathrm{u}_t}) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} \right] p_\theta(\tau_{\mathrm{x}_0:\mathrm{u}_t}) d\tau_{\mathrm{x}_0:\mathrm{u}_t}

\end{align*}
\tag{4.3}
$$

$$
\begin{align*}
\int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} & \left( \sum_{k=t}^T \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p_\theta(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \tau_{\mathrm{x}_0:\mathrm{u}_t}) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} \\

&= \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} \left( \sum_{k=t}^T \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p_\theta(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} \\

&= Q^{\pi_\theta}(\mathrm{x}_t, \mathrm{u}_t)
\end{align*}
\tag{4.4}
$$

$$
\begin{align*}
\nabla_\theta J(\theta) &= \sum_{t=0}^T \int_{\tau_{\mathrm{x}_0:\mathrm{u}_t}} \gamma^t \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) Q^{\pi_\theta}(\mathrm{x}_t, \mathrm{u}_t) p_\theta(\tau_{\mathrm{x}_0:\mathrm{u}_t}) d\tau_{\mathrm{x}_0:\mathrm{u}_t} \\

&= \sum_{t=0}^T \left( \int_{(\mathrm{x}_t, \mathrm{u}_t)} \gamma^t \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) Q^{\pi_\theta}(\mathrm{x}_t, \mathrm{u}_t) p_\theta(\mathrm{x}_t, \mathrm{u}_t) d\mathrm{x}_t d\mathrm{u}_t \right)
\end{align*}
\tag{4.5}
$$

$$
\begin{align*}
\nabla_\theta J(\theta) &= \sum_{t=0}^T \left( \int_{(\mathrm{x}_t, \mathrm{u}_t)} \gamma^t \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) Q^{\pi_\theta}(\mathrm{x}_t, \mathrm{u}_t) \pi_\theta (\mathrm{u}_t | \mathrm{x}_t) p_\theta(\mathrm{x}_t) d\mathrm{x}_t d\mathrm{u}_t \right) \\

&= \sum_{t=0}^T \left( \mathbb{E}_{\mathrm{x}_t \sim p_\theta(\mathrm{x}_t), \mathrm{u}_t \sim \pi_\theta(\mathrm{u}_t | \mathrm{x}_t)} \left[ \gamma^t \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) Q^{\pi_\theta}(\mathrm{x}_t, \mathrm{u}_t) \right] \right) \\

&= \sum_{t=0}^T \left( \mathbb{E}_{\mathrm{x}_t \sim d_\theta(\mathrm{x}_t), \mathrm{u}_t \sim \pi_\theta(\mathrm{u}_t | \mathrm{x}_t)} \left[ \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) Q^{\pi_\theta}(\mathrm{x}_t, \mathrm{u}_t) \right] \right)
\end{align*}
\tag{4.6}
$$

$$
\begin{align*}
\nabla_\theta J(\theta) &= \sum_{t=0}^T \left( \int_{(\mathrm{x}_t, \mathrm{u}_t)} \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) Q^{\pi_\theta}(\mathrm{x}_t, \mathrm{u}_t) \pi_\theta(\mathrm{u}_t \vert \mathrm{x}_t) p_\theta(\mathrm{x}_t) d\mathrm{x}_t d\mathrm{u}_t \right) \\

&= \sum_{t=0}^T \mathbb{E}_{\mathrm{x}_t \sim p_\theta(\mathrm{x}_t), \mathrm{u}_t \sim \pi_\theta(\mathrm{u}_t | \mathrm{x}_t)} \left[ \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) Q^{\pi_\theta}(\mathrm{x}_t, \mathrm{u}_t) \right]
\end{align*}
\tag{4.7}
$$

$$
\begin{align*}
\nabla_\theta J(\theta) &= \sum_{t=0}^T \left( \int_{(\mathrm{x}_t, \mathrm{u}_t)} \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) b_t \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) p_\theta(\mathrm{x}_t) d\mathrm{x}_t d\mathrm{u}_t \right) \\

&= \sum_{t=0}^T \left( \int_{(\mathrm{x}_t, \mathrm{u}_t)} \nabla_\theta \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) b_t p_\theta(\mathrm{x}_t) d\mathrm{x}_t d\mathrm{u}_t \right) \\

&= \sum_{t=0}^T \left( \int_{\mathrm{x}_t} \left[ \int_{\mathrm{u}_t} \nabla_\theta \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) b_t d\mathrm{u}_t \right] p_\theta(\mathrm{x}_t) d\mathrm{x}_t \right)
\end{align*}
\tag{4.8}
$$

$$
\begin{align*}
\int_{\mathrm{u}_t} \nabla_\theta \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) b_t d\mathrm{u}_t &= b_t \nabla_\theta \int_{\mathrm{u}_t} \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) d\mathrm{u}_t \\

& = b_t \nabla_\theta (1) = 0
\end{align*}
\tag{4.9}
$$

$$
\begin{align*}
\nabla_\theta J(\theta) &= \sum_{t=0}^T \left( \int_{(\mathrm{x}_t, \mathrm{u}_t)} \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) b_t \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) p_\theta(\mathrm{x}_t) d\mathrm{x}_t d\mathrm{u}_t \right) \\

&= 0
\end{align*}
\tag{4.10}
$$

$$
\nabla_\theta J(\theta) = \sum_{t=0}^T \left( \mathbb{E}_{\mathrm{x}_t \sim p_\theta(\mathrm{x}_t), \mathrm{u}_t \sim \pi_\theta(\mathrm{u}_t | \mathrm{x}_t)} \left[ \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \left( Q^{\pi_\theta}(\mathrm{x}_t, \mathrm{u}_t) - b_t \right) \right] \right)
\tag{4.11}
$$

$$
V^\pi(\mathrm{x}_t)=\int_{\mathrm{u}_t}Q^{\pi}(\mathrm{x}_t, \mathrm{u}_t)\pi(\mathrm{u}_t \vert \mathrm{x}_t)d \mathrm{u}_t
\tag{4.12}
$$

$$
\begin{align*}
\nabla_\theta J(\theta) &= \sum_{t=0}^T \left( \mathbb{E}_{\mathrm{x}_t \sim p_\theta(\mathrm{x}_t), \mathrm{u}_t \sim \pi_\theta(\mathrm{u}_t | \mathrm{x}_t)} \left[ \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \left\{ Q^{\pi_\theta}(\mathrm{x}_t, \mathrm{u}_t) - V^{\pi_\theta}(\mathrm{x}_t) \right\} \right] \right) \\

&= \sum_{t=0}^T \left( \mathbb{E}_{\mathrm{x}_t \sim p_\theta(\mathrm{x}_t), \mathrm{u}_t \sim \pi_\theta(\mathrm{u}_t | \mathrm{x}_t)} \left[ \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) A^{\pi_\theta}(\mathrm{x}_t, \mathrm{u}_t) \right] \right)
\end{align*}
\tag{4.13}
$$

$$
\nabla_{\theta} J(\theta) \approx \sum_{t=0}^{T} \left[ \frac{1}{M} \sum_{m=1}^{M} ( \nabla_{\theta} \log \pi_{\theta}(\mathrm{u}_t^{(m)} | \mathrm{x}_t^{(m)}) A^{\pi_{\theta}}(\mathrm{x}_t^{(m)}, \mathrm{u}_t^{(m)})) \right]
\tag{4.14}
$$

$$
\nabla_{\theta} J(\theta) \approx \sum_{t=0}^{T} \left( \nabla_{\theta} \log \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)  A^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t)\right)
\tag{4.15}
$$

$$
Q^{\pi}(\mathrm{x}_t, \mathrm{u}_t) = r(\mathrm{x}_t, \mathrm{u}_t) + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t,\mathrm{u}_t)} \left[ \gamma V^{\pi}(\mathrm{x}_{t+1}) \right]
\tag{4.16}
$$

$$
\begin{align*}
A^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t) &= Q^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t) - V^{\pi_{\theta}}(\mathrm{x}_t) \\
& \approx r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V^{\pi_{\theta}}(\mathrm{x}_{t+1}) - V^{\pi_{\theta}}(\mathrm{x}_t)
\end{align*}
\tag{4.17}
$$

$$
V^{\pi}(\mathrm{x}_t) = \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t|\mathrm{x}_t)} \left[ r(\mathrm{x}_t, \mathrm{u}_t) + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma V^{\pi}(\mathrm{x}_{t+1}) \right] \right]
\tag{4.18}
$$

$$
V_\phi(\mathrm{x}_t) \approx r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V_\phi(\mathrm{x}_{t+1})
\tag{4.19}
$$

$$
Loss_{critic}(\phi) = \frac{1}{2} \sum_i \left\| r(\mathrm{x}_i, \mathrm{u}_i) + \gamma V_{\phi}(\mathrm{x}_{i+1}) - V_{\phi}(\mathrm{x}_i) \right\|^2
\tag{4.20}
$$

$$
A_\phi (\mathrm{x}_i, \mathrm{u}_i) \approx r(\mathrm{x}_i, \mathrm{u}_i) + \gamma V_\phi(\mathrm{x}_{i+1}) - V_\phi(\mathrm{x}_i)
\tag{4.21}
$$

$$
Loss_{actor}(\theta) \approx -\sum_i \left( \log \pi_{\theta}(\mathrm{u}_i | \mathrm{x}_i) A_{\phi}(\mathrm{x}_i, \mathrm{u}_i) \right)
\tag{4.22}
$$

$$
\theta \leftarrow \theta - \alpha \nabla_\theta \sum_i - (\log\pi_\theta(\mathrm{u}_t \vert \mathrm{x}_t) A_\phi (\mathrm{x}_i, \mathrm{u}_i))
\tag{4.23}
$$

$$
\begin{align*}
\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) &= \frac{1}{\sqrt{(2\pi)^m \det P_{\theta}}} \exp \left\{ -\frac{1}{2} (\mathrm{u}_t - \mu_{\theta}(\mathrm{x}_t))^T P_{\theta}^{-1} (\mathrm{u}_t - \mu_{\theta}(\mathrm{x}_t)) \right\} \\
&= \prod_{j=1}^m \pi_{\theta}(u_{t,j} | \mathrm{x}_t)
\end{align*}
\tag{4.24}
$$

$$
\pi_{\theta}(u_{t,j} | \mathrm{x}_t) = \frac{1}{\sqrt{2\pi \sigma^2_{\theta,j}(\mathrm{x}_t)}} \exp \left\{ -\frac{(u_{t,j} - \mu_{\theta,j}(\mathrm{x}_t))^2}{2\sigma^2_{\theta,j}(\mathrm{x}_t)} \right\}
\tag{4.25}
$$

$$
\begin{align*}
\log \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) &= \sum_{j=1}^m \log \pi_{\theta}(u_{t,j} | \mathrm{x}_t) \\
&= -\sum_{j=1}^m \left[ \frac{(u_{t,j} - \mu_{\theta,j}(\mathrm{x}_t))^2}{2\sigma_{\theta,j}^2(\mathrm{x}_t)}  + \frac{1}{2} \log(2\pi\sigma_{\theta,j}^2(\mathrm{x}_t))\right]
\end{align*}
\tag{4.26}
$$
