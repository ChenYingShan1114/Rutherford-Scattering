# Rutherford Scattering
In Rutherford scattering, and alpha particle is deflected as it passes near the gold nuclei of a heavy atom. It used this experiment to prove that the plum pudding model is wrong. In this file, I use numerical method to simulate the Coulomb force between alpha particle and gold ion, and compare the simulation result with theoritical solution.


## Folders

I use three method to simulate Rutherford Scattering. The folder Euler, RK4 and RKa corresponding to Euler-Cromer method, fourth-order Runge-Kutta method and Adaptive Runge-Kutta method.

## Input parameter

I simulate an 5-MeV alpha particle  $\left(\mathrm{^4_2He}\right)$ striking a gold nucleus $\left(\mathrm{Au^{+79}}\right)$ from left hand side. The initial position is $(-10^{12},b)$ where $b$ is an impact parameter. In each folder, I put the simulation result of alpha particle's position under different $b$. For example, the file **output_-100.txt** means $b=-100$ $\mathrm{fm}$.

## Normalization constant

In this system, the magnitude of those physical quantities are very different. Therefore, I do the normalization to all parameters to reduce the truncation error. The following is the normalization conversion formula.
$$
\widetilde{x}=\frac{x}{10^{-15}}, \widetilde{t}=\frac{ct}{10^{-15}} , \widetilde{v}=\frac{v}{c} , \widetilde{q}=\frac{q}{q_e} ,\\ \widetilde{m}=\frac{m}{m_e} ,\widetilde{4\pi \epsilon_0}=\frac{4\pi \epsilon_0}{4\pi \epsilon_0} = 1, \widetilde{E}=\frac{E}{m_e c^2}, \widetilde{F}=\frac{(10^{-15})^2 \times 4\pi \epsilon_0 F}{q_e^2} \\
$$
## Governing equations

The Rutherford scattering use Coulomb force to simulate the motion of alpha particle. Therefore, the equation of motion of alpha particle is
$$
\vec{F}=\frac{q_{\alpha}q_{Au}}{4\pi \epsilon_0} \frac{\vec{r}}{|r^3|}=m_{\alpha}\frac{d\vec{v}}{dt}.
$$
After substituting the normalization conversion formula, we mainly solve the following four equations in the code
$$
\frac{d \widetilde{v}_x}{d\widetilde{t}}= \frac{q_e^2}{10^{-15}\times4\pi\epsilon_0m_ec^2} \widetilde{q}_{\alpha} \widetilde{q}_{Au} \frac{1}{\widetilde{m}_{\alpha}}\frac{\widetilde{x}}{(\widetilde{x}^2+\widetilde{y}^2)^{1.5}} \\
\frac{d \widetilde{v}_y}{d\widetilde{t}}= \frac{q_e^2}{10^{-15}\times4\pi\epsilon_0m_ec^2} \widetilde{q}_{\alpha} \widetilde{q}_{Au} \frac{1}{\widetilde{m}_{\alpha}}\frac{\widetilde{y}}{(\widetilde{x}^2+\widetilde{y}^2)^{1.5}} \\
\frac{d \widetilde{x}}{d\widetilde{t}}= \widetilde{v}_x \\
\frac{d \widetilde{y}}{d\widetilde{t}}= \widetilde{v}_y
$$
## Theoritical solution

You can delete the current file by clicking the **Remove** button in the file explorer. The file will be moved into the **Trash** folder and automatically deleted after 7 days of inactivity.
