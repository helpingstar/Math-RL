$$
\begin{align*}
\theta^* = \underset{\theta}{\mathrm{argmax}} \, J(\theta) \\

J(\theta) = \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right]
\end{align*}
\tag{3.1}
$$

$$
\begin{align*}
p_\theta(\tau) &= p_\theta(\mathrm{x}_0, \mathrm{u}_0, \mathrm{x}_1, \mathrm{u}_1, \ldots, \mathrm{x}_T, \mathrm{u}_T) \\
&= p(\mathrm{x}_0)p_\theta(\mathrm{u}_0, \mathrm{x}_1, \ldots, \mathrm{x}_T, \mathrm{u}_T \mid \mathrm{x}_0)
\end{align*}
\tag{3.2}
$$

$$
\begin{align*}
&= p(\mathrm{x}_0)p_\theta(\mathrm{u}_0|\mathrm{x}_0)p_\theta(\mathrm{x}_1, \mathrm{u}_1, \ldots, \mathrm{x}_T, \mathrm{u}_T|\mathrm{x}_0, \mathrm{u}_0) \\

&= p(\mathrm{x}_0)p_\theta(\mathrm{u}_0|\mathrm{x}_0)p(\mathrm{x}_1|\mathrm{x}_0, \mathrm{u}_0) p_\theta(\mathrm{u}_1, \mathrm{x}_2, \ldots, \mathrm{x}_T, \mathrm{u}_T|\mathrm{x}_0, \mathrm{u}_0, \mathrm{x}_1) \\

&= p(\mathrm{x}_0)p_\theta(\mathrm{u}_0|\mathrm{x}_0)p(\mathrm{x}_1|\mathrm{x}_0, \mathrm{u}_0)p_\theta(\mathrm{u}_1|\mathrm{x}_0, \mathrm{u}_0, \mathrm{x}_1)p_\theta(\mathrm{x}_2, \ldots, \mathrm{x}_T, \mathrm{u}_T|\mathrm{x}_0, \mathrm{u}_0, \mathrm{x}_1, \mathrm{u}_1) \\

&= p(\mathrm{x}_0)p_\theta(\mathrm{u}_0|\mathrm{x}_0)p(\mathrm{x}_1|\mathrm{x}_0, \mathrm{u}_0)p_\theta(\mathrm{u}_1|\mathrm{x}_0, \mathrm{u}_0, \mathrm{x}_1)p(\mathrm{x}_2|\mathrm{x}_0, \mathrm{u}_0, \mathrm{x}_1, \mathrm{u}_1) \\ 

& \qquad p_\theta(\mathrm{u}_2, \ldots, \mathrm{x}_T, \mathrm{u}_T|\mathrm{x}_0, \mathrm{u}_0, \mathrm{x}_1, \mathrm{u}_1, \mathrm{x}_2)

\end{align*}
\tag{3.3}
$$

$$
\begin{align*}
& p_\theta(\mathrm{u}_1 | \mathrm{x}_0, \mathrm{u}_0, \mathrm{x}_1) = \pi_\theta(\mathrm{u}_1 | \mathrm{x}_1) \\

& p(\mathrm{x}_2 | \mathrm{x}_0, \mathrm{u}_0, \mathrm{x}_1, \mathrm{u}_1) = p(\mathrm{x}_2 | \mathrm{x}_1, \mathrm{u}_1)
\end{align*}
\tag{3.4}
$$

$$
p_\theta(\tau) = p(\mathrm{x}_0) \prod_{t=0}^T \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t)
\tag{3.5}
$$

$$
\begin{align*}
J(\theta) &= \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right] \\

&= \int_{\tau} p_\theta(\tau) \left( \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right) d\tau
\end{align*}
\tag{3.6}
$$

$$
\begin{align*}
\tau &= (\mathrm{x}_0, \mathrm{u}_0, \mathrm{x}_1, \mathrm{u}_1, \ldots, \mathrm{x}_T, \mathrm{u}_T) \\

&= (\mathrm{x}_0) \cup (\mathrm{u}_0, \mathrm{x}_1, \mathrm{u}_1, \ldots, \mathrm{x}_T, \mathrm{u}_T) \\

&= (\mathrm{x}_0) \cup \tau_{\mathrm{u}_0 : \mathrm{u}_T}
\end{align*}
\tag{3.7}
$$

$$
\begin{align*}
p_\theta(\tau) &= p_\theta(\mathrm{x}_0, \tau_{\mathrm{u}_0 : \mathrm{u}_T}) \\

&= p(\mathrm{x}_0) p_\theta(\tau_{\mathrm{u}_0 : \mathrm{u}_T} | \mathrm{x}_0)
\end{align*}
\tag{3.8}
$$

$$
\begin{align*}
J(\theta) &= \int_{\mathrm{x}_0} \int_{\tau_{\mathrm{u}_0 : \mathrm{u}_T}} p_\theta(\mathrm{x}_0, \tau_{\mathrm{u}_0 : \mathrm{u}_T}) \left( \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right) d\tau_{\mathrm{u}_0 : \mathrm{u}_T} d\mathrm{x}_0 \\

&= \int_{\mathrm{x}_0} \int_{\tau_{\mathrm{u}_0 : \mathrm{u}_T}} p(\mathrm{x}_0) p_\theta(\tau_{\mathrm{u}_0 : \mathrm{u}_T} | \mathrm{x}_0) \left( \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right) d\tau_{\mathrm{u}_0 : \mathrm{u}_T} d\mathrm{x}_0 \\

&= \int_{\mathrm{x}_0} \left[ \int_{\tau_{\mathrm{u}_0 : \mathrm{u}_T}} p_\theta(\tau_{\mathrm{u}_0 : \mathrm{u}_T} | \mathrm{x}_0) \left( \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right) d\tau_{\mathrm{u}_0 : \mathrm{u}_T} \right] p(\mathrm{x}_0) d\mathrm{x}_0
\end{align*}
\tag{3.9}
$$

$$
\begin{align*}
J(\theta) &= \int_{\mathrm{x}_0} V^{\pi_\theta}(\mathrm{x}_0) p(\mathrm{x}_0) d\mathrm{x}_0 \\
&= \mathbb{E}_{\mathrm{x}_0 \sim p(\mathrm{x}_0)} \left[ V^{\pi_\theta}(\mathrm{x}_0) \right]
\end{align*}
\tag{3.10}
$$

$$
\begin{align*}
\frac{\partial J(\theta)}{\partial \theta} &= \nabla_\theta J(\theta) = \nabla_\theta \int_\tau p_\theta(\tau)  \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) d\tau \\
&= \int_\tau \nabla_\theta p_\theta(\tau) \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) d\tau
\end{align*}
\tag{3.11}
$$

$$
\begin{align*}
&= \int_\tau \frac{p_\theta(\tau)}{p_\theta(\tau)} \nabla_\theta p_\theta(\tau)  \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t)  d\tau \\

&= \int_\tau p_\theta(\tau) \nabla_\theta \log p_\theta(\tau)  \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t)  d\tau
\end{align*}
\tag{3.12}
$$

$$
\begin{align*}
\nabla_\theta \log p_\theta(\tau) &= \nabla_\theta \log \left( p(\mathrm{x}_0) \prod_{t=0}^T \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t) \right) \\

&= \nabla_\theta \left( \log p(\mathrm{x}_0) + \sum_{t=0}^T \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) + \log p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t) \right)
\end{align*}
\tag{3.13}
$$

$$
\nabla_\theta \log p_\theta(\tau) = \sum_{t=0}^T \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t)
\tag{3.14}
$$

$$
\begin{align*}
\nabla_\theta J(\theta) = \int_\tau p_\theta(\tau) \left( \sum_{t=0}^T \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \right) \left( \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right) d\tau \\

= \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \left( \sum_{t=0}^T \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \right) \left( \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right) \right]
\end{align*}
\tag{3.15}
$$

$$
J(\theta) = \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \sum_{t=0}^{T}\gamma^t r(\mathrm{x}_t, \mathrm{u}_u) \right]
\tag{3.16}
$$

$$
\begin{align*}
\nabla_\theta J(\theta) &= \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \left( \sum_{t=0}^T \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \right) \left( \sum_{t=0}^T \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right) \right] \\

&= \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \sum_{t=0}^T \left( \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t)  \left( \sum_{k=0}^T \gamma^k r(\mathrm{x}_k, \mathrm{u}_k) \right) \right) \right]
\end{align*}
\tag{3.17}
$$

$$
\begin{align*}
\nabla_\theta J(\theta) = \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \sum_{t=0}^T \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \left( \sum_{k=t}^T \gamma^k r(\mathrm{x}_k, \mathrm{u}_k) \right) \right]
\end{align*}
\tag{3.18}
$$

$$
\begin{align*}
\nabla_\theta J(\theta) &= \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \sum_{t=0}^T \left( \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \left( \sum_{k=t}^T \gamma^t \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) \right) \right] \\
&= \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \sum_{t=0}^T \left( \gamma^t \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \left( \sum_{k=t}^T \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) \right) \right]
\end{align*}
\tag{3.19}
$$

$$
\nabla_\theta J(\theta) = \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \sum_{t=0}^T \left( \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \left( \sum_{k=t}^T r(\mathrm{x}_k, \mathrm{u}_k) \right) \right) \right]
\tag{3.20}
$$

$$
\nabla_\theta J(\theta) = \mathbb{E}_{\tau \sim p_\theta(\tau)} \left[ \sum_{t=0}^T \left( \nabla_\theta \log \pi_\theta(\mathrm{u}_t | \mathrm{x}_t) \left( \sum_{k=t}^T \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) \right) \right]
\tag{3.21}
$$

$$
\theta \leftarrow \theta + \alpha \nabla_\theta J(\theta)
\tag{3.22}
$$

$$
\mathbb{E}_{\tau \sim p_\theta(\tau)}[\cdot] \approx \frac{1}{M} \sum_{m=1}^M [\cdot]
\tag{3.23}
$$

$$
\nabla_\theta J(\theta) \approx \frac{1}{M} \sum_{m=1}^M \left[ \sum_{t=0}^T \left\{ \nabla_\theta \log \pi_\theta(\mathrm{u}_t^{(m)} | \mathrm{x}_t^{(m)}) \left( \sum_{k=t}^T \gamma^{k-t} r(\mathrm{x}_k^{(m)}, \mathrm{u}_k^{(m)}) \right) \right\} \right]
\tag{3.24}
$$

$$
\begin{align*}
\nabla_\theta J(\theta) & \approx \frac{1}{M} \sum_{m=1}^M \left[ \sum_{t=0}^T \left( \nabla_\theta \log \pi_\theta(\mathrm{u}_t^{(m)} | \mathrm{x}_t^{(m)}) G_t^{(m)} \right) \right] \\

&= \nabla_\theta \frac{1}{M} \sum_{m=1}^M \left[ \sum_{t=0}^T (\log \pi_\theta(\mathrm{u}_t^{(m)} | \mathrm{x}_t^{(m)}) G_t^{(m)}) \right]
\end{align*}
\tag{3.25}
$$

$$
loss = -\sum_{t=0}^T (\log \pi_\theta(\mathrm{u}_t^{(m)} | \mathrm{x}_t^{(m)}) G_t^{(m)})
\tag{3.26}
$$

$$
\begin{align*}
\theta \leftarrow & \theta + \alpha \nabla_\theta J(\theta) \\

& \approx \theta - \alpha \nabla_\theta \sum_{t=0}^T (\log \pi_\theta(\mathrm{u}_t^{(m)} | \mathrm{x}_t^{(m)}) G_t^{(m)})
\end{align*}
\tag{3.27}
$$
