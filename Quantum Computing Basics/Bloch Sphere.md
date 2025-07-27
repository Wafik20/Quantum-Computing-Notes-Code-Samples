Any quantum state $|\psi\rangle$ can be written as a 
$$
|\psi\rangle = \cos\left(\frac{\theta}{2}\right)|0\rangle + e^{i\phi}\sin\left(\frac{\theta}{2}\right)|1\rangle

$$
This form corresponds to a point on the unit sphere, where: 
$\theta \in [0, \pi]$ (the angle from the z-axis), and 
$\phi \in [0, 2\pi)$ (the angle around the equator).

## Example

Let 
$$
|\psi \rangle = \frac{\sqrt{3}}{2} |0\rangle + \frac{1}{2} |1\rangle
$$  
We have:
$$
\theta = 60^\circ, \quad \phi = 0
$$
![[Pasted image 20250727013627.png]]
# Measuring in different basis

The standard computational basis states are:
$$
|0\rangle = \begin{pmatrix} 1 \\ 0 \end{pmatrix}, \quad |1\rangle = \begin{pmatrix} 0 \\ 1 \end{pmatrix}
$$
These form an orthonormal basis for the 2-dimensional complex vector space that a qubit lives in.

The Bloch sphere is a geometric representation of qubit states modulo global phase. While a qubit's state vector is a 2-dimensional complex vector, the physical states correspond to points on the surface of a 3-dimensional real unit sphere.

Measuring a qubit in a particular basis corresponds to projecting the state onto the eigenstates of the observable associated with that basis.

- The $Z$-basis measurement corresponds to the computational basis $\{|0\rangle, |1\rangle\}$.
- The $X$-basis measurement corresponds to the $\{|+\rangle, |-\rangle\}$ basis, where
$$
|+\rangle = \frac{|0\rangle + |1\rangle}{\sqrt{2}}, \quad |-\rangle = \frac{|0\rangle - |1\rangle}{\sqrt{2}}.
$$

Switching the measurement basis does not change the qubit's position on the Bloch sphere; it only changes the perspective or the "coordinate system" from which the state is observed. The qubit state itself remains fixed on the sphere.

However, **measurement** causes the qubit to collapse to one of the basis states of the measurement basis, which does change its position on the Bloch sphere to the corresponding pole.

For example, if we measure in the $Z$-basis and obtain $|0\rangle$, the qubit collapses to the north pole of the Bloch sphere; if we measure and obtain $|1\rangle$, it collapses to the south pole.

Repeated measurements in alternating bases (such as $Z$ then $X$ then $Z$ again) demonstrate the non-commuting nature of quantum measurements, leading to probabilistic outcomes that reflect the underlying geometry of the Bloch sphere.
