$$
p(\mathrm{x}_{t+1} \vert \mathrm{x}_t, \mathrm{u}_t)
\tag{2.1}
$$

$$
\pi(\mathrm{u}_t \vert \mathrm{x}) = p(\mathrm{u}_t \vert \mathrm{x}_t)
\tag{2.2}
$$

$$
\tau = (\mathrm{x}_0, \mathrm{u}_0, \mathrm{x}_1, \mathrm{u}_1, \mathrm{x}_2, \mathrm{u}_2, \ldots, \mathrm{x}_T, \mathrm{u}_T)
\tag{2.3}
$$

$$
\mathrm{x}_{t+1} = \mathrm{f}(\mathrm{x}_t, \mathrm{u}_t)
\tag{2.4}
$$

$$
\mathrm{u}_t = \pi(\mathrm{x}_t)
\tag{2.5}
$$

$$
\begin{align*}
G_t &= r(\mathrm{x}_t, \mathrm{u}_t) + \gamma r(\mathrm{x}_{t+1}, \mathrm{u}_{t+1}) + \gamma^2 r(\mathrm{x}_{t+2}, \mathrm{u}_{t+2}) + \ldots + \gamma^{T-t} r(\mathrm{x}_T, \mathrm{u}_T) \\
&= \sum_{k=t}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k)
\end{align*}
\tag{2.6}
$$

$$
\begin{align*}
\vert G_t \vert &= \left|\sum_{k=t}^{\infty} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k)\right| \leq \sum_{k=t}^{\infty} \gamma^{k-t} |r(\mathrm{x}_k, \mathrm{u}_k)| \\
& \leq r_{\max} \sum_{k=0}^{\infty} \gamma^k \\
& = \frac{r_{\max}}{1 - \gamma}
\end{align*}
\tag{2.7}
$$

$$
\begin{align*}
V^\pi(\mathrm{x}_t) &= \mathbb{E}_{\tau_{\mathrm{u}_t : \mathrm{u}_T} \sim \pi(\tau_{\mathrm{u}_t : \mathrm{u}_T}|\mathrm{x}_t)} \left[ \sum_{k=t}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \vert \mathrm{x}_t \right] \\
&= \int_{\tau_{\mathrm{u}_t : \mathrm{u}_T}} \left( \sum_{k=t}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p(\tau_{\mathrm{u}_t : \mathrm{u}_T}|\mathrm{x}_t) d\tau_{\mathrm{u}_t : \mathrm{u}_T}
\end{align*}
\tag{2.8}
$$

$$
\begin{align*}
Q^\pi(\mathrm{x}_t, \mathrm{u}_t) &= \mathbb{E}_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} \sim p(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}|\mathrm{x}_t, \mathrm{u}_t)} \left[ \sum_{k=t}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) | \mathrm{x}_t, \mathrm{u}_t \right]
\\ &= \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} \left( \sum_{k=t}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}|\mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}
\end{align*}
\tag{2.9}
$$

$$
\begin{align*}
\tau_{\mathrm{u}_t:\mathrm{u}_T} & = (\mathrm{u}_t, \mathrm{x}_{t+1}, \mathrm{u}_{t+1}, \ldots, \mathrm{u}_T) \\
& = (\mathrm{u}_t) \cup (\mathrm{x}_{t+1}, \mathrm{u}_{t+1}, \ldots, \mathrm{u}_T) \\
& = (\mathrm{u}_t) \cup \tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}
\end{align*}
\tag{2.10}
$$

$$
\begin{align*}
p(\tau_{\mathrm{u}_t:\mathrm{u}_T}|\mathrm{x}_t) &= p(\mathrm{u}_t, \tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}|\mathrm{x}_t) \\
&= p(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}|\mathrm{x}_t, \mathrm{u}_t) \pi(\mathrm{u}_t|\mathrm{x}_t)
\end{align*}
\tag{2.11}
$$

$$
\begin{align*}
V^\pi(\mathrm{x}_t) &= \int_{\tau_{\mathrm{u}_t:\mathrm{u}_T}} \left( \sum_{k=t}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p(\tau_{\mathrm{u}_t:\mathrm{u}_T} | \mathrm{x}_t) d\tau_{\mathrm{u}_t:\mathrm{u}_T} \\
&= \int_{\mathrm{u}_t} \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} \left( \sum_{k=t}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p(\mathrm{u}_t, \tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \mathrm{x}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} d\mathrm{u}_t \\
&= \int_{\mathrm{u}_t} \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} \left( \sum_{k=t}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t) \pi(\mathrm{u}_t | \mathrm{x}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} d\mathrm{u}_t \\
&= \int_{\mathrm{u}_t} \left[ \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} \left( \sum_{k=t}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} \right] \pi(\mathrm{u}_t | \mathrm{x}_t) d\mathrm{u}_t
\end{align*}
\tag{2.12}
$$

$$
\begin{align*}
V^\pi(\mathrm{x}_t) &= \int_{\mathrm{u}_t} Q^\pi(\mathrm{x}_t, \mathrm{u}_t) \pi(\mathrm{u}_t | \mathrm{x}_t) d\mathrm{u}_t \\
&= \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t|\mathrm{x}_t)} [Q^\pi(\mathrm{x}_t, \mathrm{u}_t)]
\end{align*}
\tag{2.13}
$$

$$
\begin{align*}
Q^\pi(\mathrm{x}_t, \mathrm{u}_t) & = \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} \left( \sum_{k=t}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} \\
& = \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} (r_t + \gamma r_{t+1} + \ldots + \gamma^{n-1} r_{t+n-1} + \sum_{k=t+n}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k)) p(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}
\end{align*}
\tag{2.14}
$$

$$
\begin{align*}
Q^\pi(\mathrm{x}_t, \mathrm{u}_t) &= Q_1 + Q_2 \\
& = \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} (r_t + \gamma r_{t+1} + \ldots + \gamma^{n-1} r_{t+n-1}) p(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} \\
& \qquad + \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} \left( \sum_{k=t+n}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}
\end{align*}
\tag{2.15}
$$

$$
\begin{align*}
\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} &= (\mathrm{x}_{t+1}, \mathrm{u}_{t+1}, \mathrm{x}_{t+2}, \ldots, \mathrm{u}_T) \\
&= (\mathrm{x}_{t+1}, \mathrm{u}_{t+1}, \ldots, \mathrm{x}_{t+n}) \cup (\mathrm{u}_{t+n}, \mathrm{x}_{t+n+1}, \ldots, \mathrm{u}_T) \\
&= \tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} \cup \tau_{\mathrm{u}_{t+n}:\mathrm{u}_T}
\end{align*}
\tag{2.16}
$$

$$
\begin{align*}
p(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t) & = p(\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}, \tau_{\mathrm{u}_{t+n}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t) \\
& = p(\tau_{\mathrm{u}_{t+n}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t, \tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}) p(\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} | \mathrm{x}_t, \mathrm{u}_t)
\end{align*}
\tag{2.17}
$$

$$
\begin{align*}
Q_1 &= \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} (r_t + \gamma r_{t+1} + \ldots + \gamma^{n-1} r_{t+n-1}) p(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}\\
&= \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}} \int_{\tau_{\mathrm{u}_{t+n}:\mathrm{u}_T}} (r_t + \gamma r_{t+1} + \ldots + \gamma^{n-1} r_{t+n-1}) p(\tau_{\mathrm{u}_{t+n}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t, \tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}) d\tau_{\mathrm{u}_{t+n}:\mathrm{u}_T} \\
& \qquad p(\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} \vert \mathrm{x}_t, \mathrm{u}_t)d\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} \\
&= \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}} \left[ \int_{\tau_{\mathrm{u}_{t+n}:\mathrm{u}_T}}p(\tau_{\mathrm{u}_{t+n}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t, \tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}) d\tau_{\mathrm{u}_{t+n}:\mathrm{u}_T} \right] \\
& \qquad (r_t + \gamma r_{t+1} + \ldots + \gamma^{n-1} r_{t+n-1}) p(\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} \\
& =\int_{\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}} (r_t + \gamma r_{t+1} + \ldots + \gamma^{n-1} r_{t+n-1}) p(\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}
\end{align*}
\tag{2.18}
$$

$$
\begin{align*}
Q_2 & = \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T}} \left( \sum_{k=t+n}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p(\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{u}_T} \\
&= \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}} \gamma^n \left[ \int_{\tau_{\mathrm{u}_{t+n}:\mathrm{u}_T}} \left( \sum_{k=t+n}^{T} \gamma^{k-t-n} r(\mathrm{x}_k, \mathrm{u}_k) \right) p(\tau_{\mathrm{u}_{t+n}:\mathrm{u}_T} | \mathrm{x}_t, \mathrm{u}_t, \tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}) d\tau_{\mathrm{u}_{t+n}:\mathrm{u}_T} \right] \\
& \qquad p(\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} \\
&= \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}} \gamma^n \left[ \int_{\tau_{\mathrm{u}_{t+n}:\mathrm{u}_T}} \left( \sum_{k=t+n}^{T} \gamma^{k-t-n} r(\mathrm{x}_k, \mathrm{u}_k) \right) p(\tau_{\mathrm{u}_{t+n}:\mathrm{u}_{T}} | \mathrm{x}_{t+n}) d\tau_{\mathrm{u}_{t+n}:\mathrm{u}_{T}} \right]  \\
& \qquad p(\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}
\end{align*}
\tag{2.19}
$$

$$
V^{\pi}(\mathrm{x}_t) = \int_{\tau_{\mathrm{u}_t: \mathrm{u}_T}} \left( \sum_{k=t}^{T} \gamma^{k-t} r(\mathrm{x}_k, \mathrm{u}_k) \right) p(\tau_{\mathrm{u}_t : \mathrm{u}_T} \vert \mathrm{x}_t) d \tau_{\mathrm{u}_t : \mathrm{u}_T}
\tag{2.20}
$$

$$
Q_2 = \int_{\tau_{\mathrm{x}_{t+1} : \mathrm{x}_{t+n}}} \gamma^n V^\pi (\mathrm{x}_{t+n})p(\tau_{\mathrm{x}_{t+1} : \mathrm{x}_{t+n}} \vert \mathrm{x}_t, \mathrm{u}_t) d \tau_{\mathrm{x}_{t+1} : \mathrm{x}_{t+n}}
\tag{2.21}
$$

$$
\begin{align*}
Q^\pi(\mathrm{x}_t, \mathrm{u}_t) &= \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}} \left[ (r_t + \gamma r_{t+1} + \ldots + \gamma^{n-1} r_{t+n-1}) + \gamma^n V^\pi(\mathrm{x}_{t+n}) \right] \\
& \qquad p(\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} | \mathrm{x}_t, \mathrm{u}_t) d\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} \\
& = \mathbb{E}_{\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} \sim p(\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}|\mathrm{x}_t, \mathrm{u}_t)} \left[ r_t + \gamma r_{t+1} + \ldots + \gamma^{n-1} r_{t+n-1} + \gamma^n V^\pi(\mathrm{x}_{t+n}) \right]
\end{align*}
\tag{2.22}
$$

$$
\begin{align*}
V^{\pi}(\mathrm{x}_t) &= \int_{\mathrm{u}_t} \pi(\mathrm{u}_t | \mathrm{x}_t) \left[ \int_{\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}}} \left[ r_t + \ldots + \gamma^n V^{\pi}(\mathrm{x}_{t+n}) \right] p(\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} | \mathrm{x}_t, \mathrm{u}) d\tau_{\mathrm{x}_{t+1}:\mathrm{x}_{t+n}} \right] d\mathrm{u}_t \\
&= \int_{\tau_{\mathrm{u}_t:\mathrm{x}_{t+n}}} \left[ r_t + \gamma r_{t+1} + \ldots + \gamma^{n-1} r_{t+n-1} + \gamma^n V^{\pi}(\mathrm{x}_{t+n}) \right] p(\tau_{\mathrm{u}_t:\mathrm{x}_{t+n}} | \mathrm{x}_t) d\tau_{\mathrm{u}_t:\mathrm{x}_{t+n}} \\
&= \mathbb{E}_{\tau_{\mathrm{u}_t:\mathrm{x}_{t+n}} \sim p(\tau_{\mathrm{u}_t:\mathrm{x}_{t+n}} \vert \mathrm{x}_t)} \left[ r_t + \gamma r_{t+1} + \ldots + \gamma^{n-1} r_{t+n-1} + \gamma^n V^{\pi}(\mathrm{x}_{t+n}) \right]
\end{align*}
\tag{2.23}
$$

$$
\begin{align*}
V^{\pi}(\mathrm{x}_t) &= \int_{\mathrm{u}_t} \pi(\mathrm{u}_t | \mathrm{x}_t) \left[ \int_{\mathrm{x}_{t+1}} \left[ r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V^{\pi}(\mathrm{x}_{t+1}) \right] p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t) d\mathrm{x}_{t+1} \right] d\mathrm{u}_t \\
&= \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t)} \left[ r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V^{\pi}(\mathrm{x}_{t+1}) \right] \right]
\end{align*}
\tag{2.24}
$$

$$
V^{\pi}(\mathrm{x}_t) = \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t \vert \mathrm{x}_t)} \left[ r(\mathrm{x}_t, \mathrm{u}_t) + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1} \vert \mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma V^{\pi}(\mathrm{x}_{t+1}) \right] \right]
\tag{2.25}
$$

$$
\begin{align*}
Q^{\pi}(\mathrm{x}_t, \mathrm{u}_t) &= \int_{\mathrm{x}_{t+1}} \left[ r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V^{\pi}(\mathrm{x}_{t+1}) \right] p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t) d\mathrm{x}_{t+1} \\
&= \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{u}_t)} \left[ r(\mathrm{x}_t, \mathrm{u}_t) + \gamma V^{\pi}(\mathrm{x}_{t+1}) \right] \\
&= r(\mathrm{x}_t, \mathrm{u}_t) + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma V^{\pi}(\mathrm{x}_{t+1}) \right]
\end{align*}
\tag{2.26}
$$

$$
\begin{align*}
Q^{\pi}(\mathrm{x}_t, \mathrm{u}_t) &= \int_{\mathrm{x}_{t+1}} \left[ r(\mathrm{x}_t, \mathrm{u}_t) + \gamma \int_{\mathrm{u}_{t+1}} Q^{\pi}(\mathrm{x}_{t+1}, \mathrm{u}_{t+1}) \pi(\mathrm{u}_{t+1} | \mathrm{x}_{t+1}) d\mathrm{u}_{t+1} \right] p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t) d\mathrm{x}_{t+1} \\
&= \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{u}_t)} \left[ \mathbb{E}_{\mathrm{u}_{t+1} \sim \pi(\mathrm{u}_{t+1} | \mathrm{x}_{t+1})} \left[ r(\mathrm{x}_t, \mathrm{u}_t) + \gamma Q^{\pi}(\mathrm{x}_{t+1}, \mathrm{u}_{t+1})  \right] \right] \\
&= r(\mathrm{x}_t, \mathrm{u}_t) + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{u}_t)} \left[ \mathbb{E}_{\mathrm{u}_{t+1} \sim \pi(\mathrm{u}_{t+1} | \mathrm{x}_{t+1})} \left[ \gamma Q^{\pi}(\mathrm{x}_{t+1}, \mathrm{u}_{t+1}) \right] \right]
\end{align*}
\tag{2.27}
$$

$$
V^{*}(\mathrm{x}_t) = \max_{\pi}V^\pi(\mathrm{x}_t)
Q^{*}(\mathrm{x}_t, \mathrm{u}_t) = \max_{\pi}Q^{\pi}(\mathrm{x}_t, \mathrm{u}_t)
\tag{2.28}
$$

$$
\begin{align*}
V^*(\mathrm{x}_t) &= \max_{\pi} \mathbb{E}_{\mathrm{u}_t \sim \pi(\mathrm{u}_t | \mathrm{x}_t)} \left[ r(\mathrm{x}_t, \mathrm{u}_t) + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma V^{\pi}(\mathrm{x}_{t+1}) \right] \right] \\
&= \max_{\mathrm{u}_t, \mathrm{u}_{t+1}, \ldots, \mathrm{u}_T} \left\{ r(\mathrm{x}_t, \mathrm{u}_t) + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma V^{\pi}(\mathrm{x}_{t+1}) \right] \right\} \\
&= \max_{\mathrm{u}_t} \left\{ r(\mathrm{x}_t, \mathrm{u}_t) + \max_{\mathrm{u}_{t+1}, \ldots, \mathrm{u}_T} \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma V^{\pi}(\mathrm{x}_{t+1}) \right] \right\} \\
&= \max_{\mathrm{u}_t} \left\{ r(\mathrm{x}_t, \mathrm{u}_t) + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma V^*(\mathrm{x}_{t+1}) \right] \right\}
\end{align*}
\tag{2.29}
$$

$$
\begin{align*}
Q^*(\mathrm{x}_t, \mathrm{u}_t) &= r(\mathrm{x}_t, \mathrm{u}_t) + \max \left\{ \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma V^{\pi}(\mathrm{x}_{t+1}) \right] \right\} \\
&= r(\mathrm{x}_t, \mathrm{u}_t) + \max_{\mathrm{u}_{t+1}, \cdots, \mathrm{u}_T} \left\{ \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma V^{\pi}(\mathrm{x}_{t+1}) \right] \right\} \\
&= r(\mathrm{x}_t, \mathrm{u}_t) + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma V^*(\mathrm{x}_{t+1}) \right]
\end{align*}
\tag{2.30}
$$

$$
V^{*}(\mathrm{x}_t) = \max_{\mathrm{u}_t} Q^{*}(\mathrm{x}_t, \mathrm{u}_t)
\tag{2.31}
$$

$$
Q^*(\mathrm{x}_t, \mathrm{u}_t) = r(\mathrm{x}_t, \mathrm{u}_t) + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1} | \mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma \max_{\mathrm{u}_{t+1}} Q^*(\mathrm{x}_{t+1}, \mathrm{u}_{t+1}) \right]
\tag{2.32}
$$

$$
\pi^*(\mathrm{x}_t) = \underset{\mathrm{u}_t}{\mathrm{argmax}} \left[ r_t + \mathbb{E}_{\mathrm{x}_{t+1} \sim p(\mathrm{x}_{t+1}|\mathrm{x}_t, \mathrm{u}_t)} \left[ \gamma V^*(\mathrm{x}_{t+1}) \right] \right]
\tag{2.33}
$$

$$
\pi^{*}(\mathrm{x}_t) = \text{argmax}_{\mathrm{u}_t}Q^{*}(\mathrm{x}_t, \mathrm{u}_t)
\tag{2.34}
$$
