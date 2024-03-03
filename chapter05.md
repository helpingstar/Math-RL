$$
\nabla_{\theta}J(\theta) = \sum_{t=0}^{T} \left( \mathbb{E}_{\mathrm{x}_t \sim p_0(\mathrm{x}_t), \mathrm{u}_t \sim \pi_{\theta}(\mathrm{u}_t|\mathrm{x}_t)} \left[ \nabla_{\theta} \log \pi_{\theta}(\mathrm{u}_t|\mathrm{x}_t) A^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right)
\tag{5.1}
$$

$$
\nabla_{\theta}J(\theta) \approx \sum_{t=0}^{T} \left[ \frac{1}{M} \sum_{m=1}^{M} ( \nabla_{\theta} \log \pi_{\theta}(\mathrm{u}_t^{(m)}|\mathrm{x}_t^{(m)}) A^{\pi_{\theta}}(\mathrm{x}_t^{(m)}, \mathrm{u}_t^{(m)}) ) \right]
\tag{5.2}
$$

$$
\nabla_{\theta}J(\theta) \approx \sum_{t=0}^{T} \left( \nabla_{\theta} \log \pi_{\theta}(\mathrm{u}_t|\mathrm{x}_t) A^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t) \right)
\tag{5.3}
$$

$$
\begin{align*}
\nabla_{\theta}J(\theta) & \approx \sum_{t=0}^{T} \left[\frac{1}{M} \sum_{m=1}^{M} \left( \nabla_{\theta}\log \pi_{\theta}(\mathrm{u}_t^{(m)}|\mathrm{x}_t^{(m)}) A^{\pi_{\theta}}(\mathrm{x}_t^{(m)}, \mathrm{u}_t^{(m)}) \right) \right] \\
& = \frac{1}{M} \sum_{m=1}^{M} \sum_{t=0}^{T} \left( \nabla_{\theta}\log \pi_{\theta}(\mathrm{u}_t^{(m)}|\mathrm{x}_t^{(m)}) A^{\pi_{\theta}}(\mathrm{x}_t^{(m)}, \mathrm{u}_t^{(m)}) \right) \\
& \approx \frac{1}{M} \sum_{m=1}^{M} \sum_{i=t}^{t+N-1} \left( \nabla_{\theta}\log \pi_{\theta}(\mathrm{u}_i^{(m)}|\mathrm{x}_i^{(m)}) A^{\pi_{\theta}}(\mathrm{x}_i^{(m)}, \mathrm{u}_i^{(m)}) \right)
\end{align*}
\tag{5.4}
$$

$$
V_{\phi}(\mathrm{x}_t) \approx r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V_{\phi}(\mathrm{x}_{t+1})
\tag{5.5}
$$

$$
A_{\phi}(\mathrm{x}_t, \mathrm{u}_t) \approx r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V_{\phi}(\mathrm{x}_{t+1}) - V_{\phi}(\mathrm{x}_t)
\tag{5.6}
$$

$$
A_{\phi}(\mathrm{x}_t, \mathrm{u}_t) \approx \sum_{k=t}^{\infty} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) - V_{\phi}(\mathrm{x}_t)
\tag{5.7}
$$

$$
\begin{align*}
&V_{\phi}(\mathrm{x}_t) \approx r(\mathrm{x}_t, \mathrm{u}_t) + \gamma r(\mathrm{x}_{t+1}, \mathrm{u}_{t+1}) + \ldots + \gamma^{n-1} r(\mathrm{x}_{t+n-1}, \mathrm{u}_{t+n-1}) + \gamma^n V_{\phi}(\mathrm{x}_{t+n}) \\

&A_{\phi}(\mathrm{x}_t, \mathrm{u}_t) \approx r(\mathrm{x}_t, \mathrm{u}_t) + \gamma r(\mathrm{x}_{t+1}, \mathrm{u}_{t+1}) + \ldots + \gamma^{n-1} r(\mathrm{x}_{t+n-1}, \mathrm{u}_{t+n-1}) \\

& \qquad \qquad \qquad + \gamma^n V_{\phi}(\mathrm{x}_{t+n}) - V_{\phi}(\mathrm{x}_t) \\

&\qquad \qquad =\sum_{k=t}^{t+n-1} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) + \gamma^n V_{\phi}(\mathrm{x}_{t+n}) - V_{\phi}(\mathrm{x}_t)
\end{align*}
\tag{5.8}
$$
