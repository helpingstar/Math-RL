$$
\begin{align*}
\nabla_{\theta} J(\theta) &= \sum_{t=0}^{T} \left[ \mathbb{E}_{\tau_{\mathrm{x}_0:\mathrm{u}} \sim p_{\theta} (\tau_{\mathrm{x}_0:\mathrm{u}})} \left[ \gamma^t \nabla_{\theta} \log \pi_{\theta} (\mathrm{u}_t | \mathrm{x}_t) A^{\pi_{\theta}} (\mathrm{x}_t, \mathrm{u}_t) \right] \right] \\
&= \sum_{t=0}^{T} \left[ \mathbb{E}_{\mathrm{x}_t \sim p_{\theta}(\mathrm{x}_t), \mathrm{u}_t \sim \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \gamma^t \nabla_{\theta} \log \pi_{\theta} (\mathrm{u}_t | \mathrm{x}_t) A^{\pi_{\theta}} (\mathrm{x}_t, \mathrm{u}_t) \right] \right]
\end{align*}
\tag{6.1}
$$

$$
\mathbb{E}_{\mathrm{x} \sim p(\mathrm{x})} \left[ f(\mathrm{x}) \right] = \mathbb{E}_{\mathrm{x} \sim q(\mathrm{x})} \left[ \frac{p(\mathrm{x})}{q(\mathrm{x})} f(\mathrm{x}) \right]
\tag{6.2}
$$

$$
\nabla_{\theta} J(\theta) = \sum_{t=0}^{T} \left( \mathbb{E}_{\tau_{\mathrm{x}_0:\mathrm{u}} \sim p_{\theta_{OLD}}(\tau_{\mathrm{x}_0:\mathrm{u}_t})} \left[ \frac{p_{\theta}(\tau_{\mathrm{x}_0:\mathrm{u}_t})}{p_{\theta_{OLD}}(\tau_{\mathrm{x}_0:\mathrm{u}_t})} \gamma^t \nabla_{\theta} \log \pi_{\theta}(\mathrm{u}_t | x_t) A^{\pi_{\theta}}(x_t, \mathrm{u}_t) \right] \right)
\tag{6.3}
$$

$$
p_{\theta}(\tau) = p(\mathrm{x}_0) \prod_{t=0}^{T} \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t)
\tag{6.4}
$$

$$
\begin{align*}
\frac{p_{\theta}(\tau_{\mathrm{x}_0:\mathrm{u}_t})}{p_{\theta_{OLD}}(\tau_{\mathrm{x}_0:\mathrm{u}_t})} &= \frac{p(\mathrm{x}_0) \prod_{k=0}^{t} \pi_{\theta}(\mathrm{u}_k | \mathrm{x}_k)p(\mathrm{x}_{k+1} | \mathrm{x}_k, \mathrm{u}_k)}{p(\mathrm{x}_0) \prod_{k=0}^{t} \pi_{\theta_{OLD}}(\mathrm{u}_k | \mathrm{x}_k)p(\mathrm{x}_{k+1} | \mathrm{x}_k, \mathrm{u}_k)} \\
&= \prod_{k=0}^{t} \frac{\pi_{\theta}(\mathrm{u}_k | \mathrm{x}_k)}{\pi_{\theta_{OLD}}(\mathrm{u}_k | \mathrm{x}_k)}
\end{align*}
\tag{6.5}
$$

$$
\nabla_{\theta} J(\theta) = \sum_{t=0}^{T} \left( \mathbb{E}_{\tau_{\mathrm{x}_0: \mathrm{u}_t}\sim p_{\theta_{OLD}}(\tau_{\mathrm{x}_0: \mathrm{u}_t})}  \left[ \left( \prod_{k=0}^{t} \frac{\pi_{\theta}(\mathrm{u}_k | \mathrm{x}_k)}{\pi_{\theta_{OLD}}(\mathrm{u}_k | \mathrm{x}_k)} \right) \gamma^t \nabla_{\theta} \log \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) A^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right)
\tag{6.6}
$$

$$
\nabla_{\theta} J(\theta) = \sum_{t=0}^{T} \left( \mathbb{E}_{\mathrm{x}_t \sim p_{\theta}(\mathrm{x}_t), \mathrm{u}_t \sim \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \gamma^t \nabla_{\theta} \log \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) A^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right)
\tag{6.7}
$$

$$
\nabla_{\theta} J(\theta) = \sum_{t=0}^{T} \left( \mathbb{E}_{\mathrm{x}_t \sim p_{\theta_{OLD}}(\mathrm{x}_t)} \left[ \frac{p_{\theta}(\mathrm{x}_t)}{p_{\theta_{OLD}}(\mathrm{x}_t)} \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta_{OLD}}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \gamma^t  \frac{\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{OLD}}(\mathrm{u}_t | \mathrm{x}_t)} \nabla_{\theta} \log \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) A^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right] \right)
\tag{6.8}
$$

$$
\nabla_{\theta} J(\theta) = \sum_{t=0}^{T} \left( \mathbb{E}_{\mathrm{x}_t \sim p_{\theta_{OLD}}(\mathrm{x}_t)} \left[ \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta_{OLD}}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \gamma^t \frac{\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{OLD}}(\mathrm{u}_t | \mathrm{x}_t)} \nabla_{\theta} \log \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) A^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right] \right)
\tag{6.9}
$$

$$
J(\theta) = \mathbb{E}_{\tau \sim p(\tau)} \left[ \sum_{t=0}^{T} \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right]
\tag{6.10}
$$

$$
\theta \leftarrow \theta + \alpha \nabla_\theta J(\theta)
\tag{6.11}
$$

$$
\begin{align*}
&J(\theta) = \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ \sum_{t=0}^{\infty} \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right] \\
&J(\theta_{{OLD}}) = \mathbb{E}_{\tau \sim p_{\theta_{{OLD}}}(\tau)} \left[ \sum_{t=0}^{\infty} \gamma^t r(\mathrm{x}_t, \mathrm{u}_t) \right]
\end{align*}
\tag{6.12}
$$

$$
\begin{align*}
J(\theta) &= \mathbb{E}_{\mathrm{x}_0 \sim p(\mathrm{x}_0)} \left[ V^{\pi_{\theta}}(\mathrm{x}_0) \right] \\
&= \int_{\mathrm{x}_0} V^{\pi_{\theta}}(\mathrm{x}_0) p(\mathrm{x}_0) d\mathrm{x}_0
\end{align*}
\tag{6.13}
$$

$$
J(\theta) - J(\theta_{OLD}) = \mathbb{E}_{\mathrm{x}_0 \sim p(\mathrm{x}_0)} \left[ V^{\pi_{\theta}}(\mathrm{x}_0) \right] - \mathbb{E}_{\mathrm{x}_0 \sim p(\mathrm{x}_0)} \left[ V^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_0) \right]
\tag{6.14}
$$

$$
\begin{align*}
\mathbb{E}_{\mathrm{x}_0 \sim p(\mathrm{x}_0)} \left[ V^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_0) \right] &= \int_{\mathrm{x}_0} V^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_0)p(\mathrm{x}_0)d\mathrm{x}_0 \\
&= \int_{\mathrm{x}_0} \left[ \int_{(\mathrm{u}_0, \mathrm{x}_1, \mathrm{u}_1, \ldots)} p_{\theta}(\mathrm{u}_0, \mathrm{x}_1, \mathrm{u}_1, \ldots)d\mathrm{u}_0d\mathrm{x}_1d\mathrm{u}_1 \cdots \right] V^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_0)p(\mathrm{x}_0)d\mathrm{x}_0  \\
&= \int V^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_0)p_{\theta}(\tau)d\tau \\
&= \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ V^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_0) \right]
\end{align*}
\tag{6.15}
$$

$$
\mathbb{E}_{\mathrm{x}_0 \sim p(\mathrm{x}_0)} \left[ V^{\pi_{\theta}}(\mathrm{x}_0) \right] = \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ V^{\pi_{\theta}}(\mathrm{x}_0) \right]
\tag{6.16}
$$

$$
J(\theta) - J(\theta_{{OLD}}) = \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ V^{\pi_{\theta}}(\mathrm{x}_0) \right] - \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ V^{\pi_{\theta_{{OLD}}}} (\mathrm{x}_0) \right]
\tag{6.17}
$$

$$
\begin{align*}
\mathbb{E}_{\tau \sim p_{\theta}(\tau)} & \left[ V^{\pi_{\theta}}(\mathrm{x}_0) \right] - \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ V^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_0) \right] \\
&= \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ V^{\pi_{\theta}}(\mathrm{x}_0) \right] - \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ \sum_{t=0}^{\infty} \gamma^t V^{\pi_{\theta_{OLD}}} (\mathrm{x}_t) - \sum_{t=1}^{\infty} \gamma^t V^{\pi_{\theta_{OLD}}} (\mathrm{x}_t) \right]  \\
&= \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ \sum_{t=0}^{\infty} \gamma^t r(\mathrm{x}_t, \mathbb{E}_t) \right] + \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ \sum_{t=0}^{\infty} \gamma^t \left( \gamma V^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_{t+1}) - V^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t) \right) \right] \\
&= \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ \sum_{t=0}^{\infty} \gamma^t \left( r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_{t+1}) - V^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t) \right) \right]
\end{align*}
\tag{6.18}
$$

$$
\begin{align*}
A^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t) &= Q^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t) - V^{\pi_{\theta}}(\mathrm{x}_t) \\
&= r(\mathrm{x}_t, \mathrm{u}_t) + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t,\mathrm{u}_t)} \left[ \gamma V^{\pi_{\theta}}(\mathrm{x}_{t+1}) \right] - V^{\pi_{\theta}}(\mathrm{x}_t) \\
&= \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{u}_t)} \left[ r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V^{\pi_{\theta}}(\mathrm{x}_{t+1}) - V^{\pi_{\theta}}(\mathrm{x}_t) \right]
\end{align*}
\tag{6.19}
$$

$$
\begin{align*}
J(\theta) - J(\theta_{{OLD}}) &= \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ \sum_{t=0}^{\infty} \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \\
&= \sum_{t=0}^{\infty} \mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right]
\end{align*}
\tag{6.20}
$$

$$
\begin{align*}
p_{\theta}(\tau) &= p_{\theta}(\mathrm{x}_0, \mathrm{u}_0, \ldots, \mathrm{u}_{t-1}, \mathrm{x}_t, \mathrm{u}_t, \mathrm{x}_{t+1}, \ldots) \\
&= p_{\theta}(\tau_{\mathrm{x}_0:\mathrm{u}_{t-1}}, \mathrm{x}_t, \mathrm{u}_t, \tau_{\mathrm{x}_{t+1}:\infty}) \\
&= p_{\theta}(\mathrm{u}_t | \mathrm{x}_t, \tau_{\mathrm{x}_0:\mathrm{u}_{t-1}}, \tau_{\mathrm{x}_{t+1}:\infty})p_{\theta}(\mathrm{x}_t, \tau_{\mathrm{x}_0:\mathrm{u}_{t-1}}, \tau_{\mathrm{x}_{t+1}:\infty})
\end{align*}
\tag{6.21}
$$

$$
p_\theta(\tau) = \pi_\theta(\mathrm{u}_t \vert \mathrm{x}_t)p_\theta (\mathrm{x}_t, \tau_{\mathrm{x}_0:\mathrm{u}_{t-1}}, \tau_{\mathrm{x}_{t+1}: \infty})
\tag{6.22}
$$

$$
\begin{align*}
\mathbb{E}_{\tau \sim p_{\theta}(\tau)} &\left[ \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \\
&= \int_\tau \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) p_{\theta}(\tau) d\tau \\
&= \int_{\mathrm{x}_t} \int_{\mathrm{u}_t} \int_{\tau_{\mathrm{x}_0:\mathrm{u}_{t-1}}} \int_{\tau_{\mathrm{x}_{t+1}:\infty}} \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) p_{\theta}(\mathrm{x}_t, \tau_{\mathrm{x}_0:\mathrm{u}_{t-1}}, \tau_{\mathrm{x}_{t+1}:\infty}) d\tau_{\mathrm{x}_0:\mathrm{u}_{t-1}} d\tau_{\mathrm{x}_{t+1}:\infty}   d\mathrm{u}_t d\mathrm{x}_t \\
&= \int_{\mathrm{x}_t} \int_{\mathrm{u}_t} \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) p_{\theta}(\mathrm{x}_t) d\mathrm{u}_t d\mathrm{x}_t
\end{align*}
\tag{6.23}
$$

$$
\begin{align*}
\mathbb{E}_{\tau \sim p_{\theta}(\tau)} \left[ \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] &= \int_{\mathrm{x}_t} \left[ \int_{\mathrm{u}_t} A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) d\mathrm{u}_t \right] \gamma^t p_{\theta}(\mathrm{x}_t) d\mathrm{x}_t \\
&= \int_{\mathrm{x}_t} \left[ \int_{\mathrm{u}_t} A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) d\mathrm{u}_t \right] d_{\theta}(\mathrm{x}_t) d\mathrm{x}_t \\
&= \mathbb{E}_{\mathrm{x}_t \sim d_{\theta}(\mathrm{x}_t)} \left[ \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)} \left[ A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right]
\end{align*}
\tag{6.24}
$$

$$
\begin{align*}
\mathbb{E}_{\mathrm{x}_t \sim p_{\theta}(\mathrm{x}_t)} &\left[ \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right] \\
&= \mathbb{E}_{\mathrm{x}_t \sim p_{\theta}(\mathrm{x}_t)} \left[ \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \frac{\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right]
\end{align*}
\tag{6.25}
$$

$$
J(\theta) - J(\theta_{{OLD}}) = \sum_{t=0}^{\infty} \mathbb{E}_{\mathrm{x}_t \sim p_{\theta}(\mathrm{x}_t)} \left[ \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \frac{\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right]
\tag{6.26}
$$

$$
J(\theta) - J(\theta_{{OLD}}) = \sum_{t=0}^{\infty} \mathbb{E}_{\mathrm{x}_t \sim p_{\theta_{{OLD}}}(\mathrm{x}_t)} \left[ \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \frac{\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right]
\tag{6.27}
$$

$$
L(\theta) = \sum_{t=0}^{\infty} \mathbb{E}_{\mathrm{x}_t \sim p_{\theta_{{OLD}}}(\mathrm{x}_t)} \left[ \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \frac{\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right]
\tag{6.28}
$$

$$
J(\theta) = J(\theta_{OLD}) + L(\theta)
\tag{6.29}
$$

$$
\begin{align*}
\nabla_{\theta} L(\theta) &= \sum_{t=0}^{\infty} \mathbb{E}_{\mathrm{x}_t \sim p_{\theta_{{OLD}}}(\mathrm{x}_t)} \left[ \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \frac{\nabla_\theta \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right] \\
&= \sum_{t=0}^{\infty} \mathbb{E}_{\mathrm{x}_t \sim p_{\theta_{{OLD}}}(\mathrm{x}_t)} \left[ \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \frac{\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \nabla_{\theta} \log \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right]
\end{align*}
\tag{6.30}
$$

$$
\nabla_{\theta} L(\theta) = \sum_{t=0}^{\infty} \mathbb{E}_{\mathrm{x}_t \sim p_{\theta}(\mathrm{x}_t)} \left[ \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \nabla_{\theta} \log \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) \gamma^t A^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right]
\tag{6.31}
$$

$$
\begin{align*}
&\theta \leftarrow \underset{\theta}{\mathrm{argmax}} \sum_{t=0}^{\infty} \mathbb{E}_{\tau_{\mathrm{x}_0 : \mathrm{u}_t} \sim p_{\theta_{OLD}}(\tau_{\mathrm{x}_0: \mathrm{u}_t})} \left[ \frac{\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \\
&\text{Constraints: } \pi_\theta(\mathrm{u_t} \vert \mathrm{x}_t) \approx \pi_{\theta_{OLD}}(\mathrm{u}_t \vert \mathrm{x}_t)
\end{align*}
\tag{6.32}
$$

$$
\begin{align*}
L(\theta) &= \sum_{t=0}^{\infty} \mathbb{E}_{\mathrm{x}_t \sim p_{\theta_{{OLD}}}(\mathrm{x}_t)} \left[ \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \frac{\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right] \\
&= \sum_{t=0}^{\infty} \mathbb{E}_{\tau_{\mathrm{x}_0 : \mathrm{u}_t} \sim p_{\theta_{OLD}}(\tau_{\mathrm{x}_0 : \mathrm{u}_t})} \left[ \mathbb{E}_{\mathrm{u}_t \sim \pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \left[ \frac{\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} \gamma^t A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \right]
\end{align*}
\tag{6.33}
$$

$$
\begin{align*}
&\theta \leftarrow \underset{\theta}{\text{argmax}} \sum_{t=0}^{\infty} \mathbb{E}_{\tau_{\mathrm{x}_0:\mathrm{u}_t} \sim p_{\theta_{{OLD}}}(\tau_{\mathrm{x}_0:\mathrm{u}_t})} \left[ \frac{\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)} A^{\pi_{\theta_{{OLD}}}}(\mathrm{x}_t, \mathrm{u}_t) \right] \\
&\text{Constraints: } D_{KL}(\pi_{\theta_{OLD}}(\mathrm{u}_t \vert \mathrm{x}_t) \vert \vert \pi_\theta (\mathrm{u}_t \vert \mathrm{x}_t)) \leq \delta
\end{align*}
\tag{6.34}
$$

$$
r_t(\theta) = \frac{\pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t)}{\pi_{\theta_{{OLD}}}(\mathrm{u}_t | \mathrm{x}_t)}, \quad r_t(\theta_{{OLD}}) = 1
\tag{6.35}
$$

$$
clip(r_t(\theta), 1-\epsilon, 1+\epsilon) = 
\begin{cases}
1+\epsilon, & \text{if } r_t(\theta) \geq 1+\epsilon \\
1-\epsilon, & \text{if } r_t(\theta) \leq 1-\epsilon \\
r_t(\theta), & \text{otherwise}
\end{cases}
\tag{6.36}
$$

$$
\theta = \arg\max_{\theta} \sum_{t=0}^{\infty} \mathbb{E}_{\tau_{\mathrm{x}_0:\mathrm{u}_t} \sim p_{\theta_{OLD}}(\tau_{\mathrm{x}_0:\mathrm{u}_t})} \left[ L_t^{{clip}} (\theta) \right] \\

L_t^{{clip}} (\theta) = \min \left\{ r_t(\theta) A^{\pi_{{OLD}}}(\mathrm{x}_t, \mathrm{u}_t), {clip}(r_t(\theta), 1-\epsilon, 1+\epsilon) A^{\pi_{{OLD}}}(\mathrm{x}_t, \mathrm{u}_t) \right\}
\tag{6.37}
$$

$$
\begin{align*}
\log \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) &= \sum_{j=1}^{m} \log \pi_{\theta}(u_{t,j} | \mathrm{x}_t) \\

&= -\sum_{j=1}^{m} \left[ \frac{(u_{t,j} - \mu_{\theta,j}(\mathrm{x}_t))^2}{2 \sigma_{\theta,j}^2(\mathrm{x}_t)} + \frac{1}{2} \log(2\pi\sigma_{\theta,j}^2(\mathrm{x}_t)) \right]
\end{align*}
\tag{6.38}
$$

$$
\begin{align*}
&\log r_t(\theta) = \log \pi_{\theta}(\mathrm{u}_t | \mathrm{x}_t) - \log \pi_{{OLD}}(\mathrm{u}_t | \mathrm{x}_t) \\
&r_t(\theta) = \exp(\log r_t(\theta))
\end{align*}
\tag{6.39}
$$

$$
A^{(1)}_{\phi}(\mathrm{x}_t, \mathrm{u}_t) = r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V_{\phi}(\mathrm{x}_{t+1}) - V_{\phi}(\mathrm{x}_t)
\tag{6.40}
$$

$$
A_{\phi}^{(\infty)}(\mathrm{x}_t, \mathrm{u}_t) = \sum_{k=t}^{\infty} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) - V_{\phi}(\mathrm{x}_t)
\tag{6.41}
$$

$$
\begin{align*}
A_{\phi}^{(n)}(\mathrm{x}_t, \mathrm{u}_t) &= r(\mathrm{x}_t, \mathrm{u}_t) + \gamma r(\mathrm{x}_{t+1}, \mathrm{u}_{t+1}) + \dots + \gamma^{n-1} r(\mathrm{x}_{t+n-1}, \mathrm{u}_{t+n-1}) \\
& \qquad + \gamma^n V_{\phi}(\mathrm{x}_{t+n}) - V_{\phi}(\mathrm{x}_t) \\

&= \sum_{k=t}^{t+n-1} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) + \gamma^n V_{\phi}(\mathrm{x}_{t+n}) - V_{\phi}(\mathrm{x}_t)
\end{align*}
\tag{6.42}
$$

$$
A_{\phi}^{{GAE}}(\mathrm{x}_t, \mathrm{u}_t) = \sum_{n=1}^{\infty} w_n A_{\phi}^{(n)}(\mathrm{x}_t, \mathrm{u}_t)
\tag{6.43}
$$

$$
\delta_t = r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V_{\phi}(\mathrm{x}_{t+1}) - V_{\phi}(\mathrm{x}_t)
\tag{6.44}
$$

$$
\begin{align*}
A_{\phi}^{(1)}(\mathrm{x}_t, \mathrm{u}_t) &= r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V_{\phi}(\mathrm{x}_{t+1}) - V_{\phi}(\mathrm{x}_t) \\
&= \delta_t\\
A_{\phi}^{(2)}(\mathrm{x}_t, \mathrm{u}_t) &= r(\mathrm{x}_t, \mathrm{u}_t) + \gamma r(\mathrm{x}_{t+1}, \mathrm{u}_{t+1}) + \gamma^2 V_{\phi}(\mathrm{x}_{t+2}) - V_{\phi}(\mathrm{x}_t) \\
&= r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V_\phi(\mathrm{x}_{t+1}) - V_\phi(\mathrm{x}_t) \\
& \qquad + \gamma(r(\mathrm{x}_{t+1}, \mathrm{u}_{t+1}) + \gamma V_\phi(\mathrm{x}_{t+2}) - V_\phi(\mathrm{x}_{t+1})) \\
&= \delta_t + \gamma \delta_{t+1} \\
\cdots \\
A_{\phi}^{(n)}(\mathrm{x}_t, \mathrm{u}_t) &= \sum_{k=t}^{t+n-1} \gamma^{k-t} \delta_k
\end{align*}
\tag{6.45}
$$

$$
\begin{align*}
A_{\phi}^{{GAE}}(\mathrm{x}_t, \mathrm{u}_t) &= \sum_{n=1}^{\infty} w_n A_{\phi}^{(n)}(\mathrm{x}_t, \mathrm{u}_t) \\
&= (1 - \lambda) \sum_{n=1}^{\infty} \lambda^{n-1} A_{\phi}^{(n)}(\mathrm{x}_t, \mathrm{u}_t) \\
&= (1 - \lambda) \sum_{n=1}^{\infty} \left( \delta_t + \lambda(\delta_t + \gamma \delta_{t+1}) + \lambda^2(\delta_t + \gamma \delta_{t+1} + \gamma^2 \delta_{t+2}) + \cdots \right) \\
&= (1 - \lambda) \left[ \delta_t (1 + \lambda + \lambda^2 + \cdots) + \gamma \delta_{t+1} (\lambda + \lambda^2 + \cdots) + \gamma^2 \delta_{t+2} (\lambda^2 + \cdots) + \dots \right]
 \\
&= (1 - \lambda) \left[ \frac{\delta_t}{1 - \lambda} + \frac{\gamma \lambda \delta_{t+1}}{1 - \lambda} + \frac{\gamma^2 \lambda^2 \delta_{t+2}}{1 - \lambda} + \cdots \right] \\
&= \sum_{k=t}^{\infty} (\gamma \lambda)^{k-t} \delta_k
\end{align*}
\tag{6.46}
$$

$$
\begin{align*}
A_{\phi}^{{GAE}}(\mathrm{x}_t, \mathrm{u}_t) &= \delta_t = r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V_{\phi}(\mathrm{x}_{t+1}) - V_{\phi}(\mathrm{x}_t) \\
&= A_{\phi}^{(1)}(\mathrm{x}_t, \mathrm{u}_t)
\end{align*}
$$

$$
\begin{align*}
A_{\phi}^{{GAE}}(\mathrm{x}_t, \mathrm{u}_t) &= \sum_{k=t}^{\infty} \gamma^{k-t} \delta_k \\
&= A_{\phi}^{(\infty)}(\mathrm{x}_t, \mathrm{u}_t)
\end{align*}
$$
