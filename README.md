# Architecture Determines Optimization: Deriving Weight Updates from Network Topology

Cameron L. Bass
*Independent Researcher*
cameronlbass@gmail.com


## Abstract

We derive neural network weight updates from first principles without assuming gradient descent or a specific loss function. Starting from the error equation $E = y - f(x)$ and linearizing with respect to the free parameters, while noting that the data $x$ and target $y$ are fixed observations, we obtain a linear constraint on the weight perturbations. The minimum-norm solution to this underdetermined system is algebraically identical to the standard weight gradient. Gradient descent is therefore a consequence of minimizing weight change subject to error correction. This derivation exposes three structural facts obscured by the standard loss-based approach. First, the minimum-norm solution uses the $L_2$ norm to determine the update direction, but the weights within a layer are structurally independent, making the $L_1$ norm the appropriate measure of update magnitude; the $L_1$ normalization also provides scale invariance with respect to input magnitude. Second, the denominator in the minimum-norm solution averages over continuous input dimensions; a layer in a neural network is a discrete space with $d_l$ independent outputs, each training step addresses one correction among $d_l$ alternatives, and $O(\ln(d_l))$ effective measurements are required, yielding a per-layer step size of $1/\ln(d_l)$. Third, while the standard gradient vanishes at convergence, the Hessian also vanishes, leaving converged weights with no restoring force against perturbation, which provides a first-principles explanation for catastrophic forgetting and clarifies the role of error-based updates in maintaining instantaneous correction.

This work is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).