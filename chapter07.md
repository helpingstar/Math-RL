$$
\begin{align*}
J(\theta) &= \int_{\mathrm{x}_0} V^{\pi_{\theta}}(\mathrm{x}_0)p(\mathrm{x}_0)d\mathrm{x}_0 \\
&= \mathbb{E}_{\mathrm{x}_0 \sim p(\mathrm{x}_0)} \left[ V^{\pi_{\theta}}(\mathrm{x}_0) \right]
\end{align*}
\tag{7.1}
$$

$$
V^{\pi_{\theta}}(\mathrm{x}_t) = Q^{\pi_{\theta}}(\mathrm{x}_t, \mathrm{u}_t) = Q^{\pi_{\theta}}(\mathrm{x}_t, \pi_{\theta}(\mathrm{x}_t))
\tag{7.2}
$$

$$
\begin{align*}
Q^{\pi}(\mathrm{x}_t, \mathrm{u}_t) &= \int_{\mathrm{x}_{t+1}} \left[ r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V^{\pi}(\mathrm{x}_{t+1}) \right] p(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{u}_t)d\mathrm{x}_{t+1} \\

&= r(\mathrm{x}_t, \mathrm{u}_t) + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma V^{\pi}(\mathrm{x}_{t+1}) \right]
\end{align*}
\tag{7.3}
$$

$$
\begin{align*}
\nabla_{\theta} V^{\pi_{\theta}}(\mathrm{x}_0) &= \nabla_{\theta} Q^{\pi_{\theta}}(\mathrm{x}_0, \pi_{\theta}(\mathrm{x}_0)) \\

&= \nabla_{\theta} \left[ r(\mathrm{x}_0, \mathrm{u}_0) + \int_{\mathrm{x}_1} \gamma V^{\pi_{\theta}}(\mathrm{x}_1)p(\mathrm{x}_1|\mathrm{x}_0, \mathrm{u}_0)d\mathrm{x}_1 \right] \\

&= \nabla_{\theta} \pi_{\theta}(\mathrm{x}_0) \nabla_{\mathrm{u}_0} r(\mathrm{x}_0, \mathrm{u}_0) + \nabla_{\theta} \left[ \int_{\mathrm{x}_1} \gamma V^{\pi_{\theta}}(\mathrm{x}_1)p(\mathrm{x}_1|\mathrm{x}_0, \mathrm{u}_0)d\mathrm{x}_1 \right] \\

&= \nabla_{\theta} \pi_{\theta}(\mathrm{x}_0) \nabla_{\mathrm{u}_0} r(\mathrm{x}_0, \mathrm{u}_0) + \int_{\mathrm{x}_1} \gamma V^{\pi_{\theta}}(\mathrm{x}_1) \nabla_\theta \pi_\theta(\mathrm{x}_0) \nabla_{\mathrm{u}_0} p(\mathrm{x}_1|\mathrm{x}_0, \mathrm{u}_0)d\mathrm{x}_1 \\

& \qquad + \int_{\mathrm{x}_1} \gamma \nabla_{\theta} V^{\pi_{\theta}}(\mathrm{x}_1)p(\mathrm{x}_1|\mathrm{x}_0, \mathrm{u}_0)d\mathrm{x}_1
\end{align*}
\tag{7.4}
$$

$$
\begin{align*}
\nabla_{\theta} V^{\pi_{\theta}}(\mathrm{x}_0) &= \nabla_{\theta} \pi_{\theta}(\mathrm{x}_0) \nabla_{\mathrm{u}_0} \left[ r(\mathrm{x}_0, \mathrm{u}_0) + \int_{\mathrm{x}_1} \gamma V^{\pi_{\theta}}(\mathrm{x}_1)p(\mathrm{x}_1|\mathrm{x}_0, \mathrm{u}_0)d\mathrm{x}_1 \right]\\

&\qquad + \int_{\mathrm{x}_1} \gamma \nabla_{\theta} V^{\pi_{\theta}}(\mathrm{x}_1)p(\mathrm{x}_1|\mathrm{x}_0, \mathrm{u}_0)d\mathrm{x}_1 \\

&= \nabla_{\theta} \pi_{\theta}(\mathrm{x}_0) \nabla_{\mathrm{u}_0} Q^{\pi_{\theta}}(\mathrm{x}_0, \mathrm{u}_0) + \int_{\mathrm{x}_1} \gamma \nabla_{\theta} V^{\pi_{\theta}}(\mathrm{x}_1)p(\mathrm{x}_1|\mathrm{x}_0, \mathrm{u}_0)d\mathrm{x}_1

\end{align*}
\tag{7.5}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

$$

\tag{7.}
$$

