---
date: 2023-11-15
tags:
  - Note
---
# Free energy of ideal gas
![Alt text](image/IdealGas.png)
## Introduction
The thermodynamic properties of a gas can be estimated from its molecular vibration frequency under the ideal gas approximation. This is illustrated in the context of determining the translational, rotational, and vibrational contributions to the molar entropy and the molar specific heat of a gas.

The gibbs free energy $G$ of a gas molecule is calculated by

$$
G = H-TS
$$

the enthalpy $H$, entropy $S$ at given temperature $T$ and pressure $P$ can be calculated as follows.

### Entropy

The entropy of gas can be expressed as

$$
S = k_B + k_B \ln \left(Q \right) + k_B T\left(\frac{\partial \ln Q}{\partial T}\right)_V
$$

The contributions are from translational, rotational, vibrational, and electronic components, which leaves

$$
S =  k_B \left[ \ln \left(eQ_{\text{trans}} Q_{\text{rot}} Q_{\text{vib}} Q_{\text{ele}}\right) + k_NT\left(\frac{\partial \ln Q}{\partial T}\right)_V\right]
$$

where $Q_{\text{trans}}$, $Q_{\text{rot}}$, $Q_{\text{vib}}$, $Q_{\text{ele}}$ are the translational, rotational, vibrational, and electronic partition function.

It can also be divided as

$$
S = S_{\text{trans}} + S_{\text{rot}} + S_{\text{vib}} + S_{\text{ele}}
$$

which are the translational, rotational, vibrational, and electronic contributions.

### Enthalpy
The enthalpy is derived from the partition function.

$$
E = k_B T^2 \left(\frac{\partial \ln Q}{\partial T}\right)_V 
$$

The internal can also be divided as translational, rotational, vibrational (including zero-point-energy $E_{\text{ZPE}}$), and electronic contributions.

$$
E = E_{\text{trans}} + E_{\text{rot}} + E_{\text{vib}} + E_{\text{ele}}
$$

The enthalpy $H$ of the gas is expressed by the internal energy $E$

$$
H = E + k_B T
$$

It can also be expressed as

$$
H =  \int^T_0 C_P dT = \int^T_0 C_V dT +k_B T
$$

where $C_P = \left(\frac{\partial H}{\partial T}\right)_P$ and $C_V = \left(\frac{\partial E}{\partial T}\right)_V$. $C_P$ can be expressed as

$$
C_P = C_{V, \text{trans}} + C_{V, \text{rot}} + C_{V, \text{vib}} + C_{V, \text{ele}} + (C_P - C_V)
$$

where $C_V$ is the "constant-volume" heat capacity. $C_{V, \text{trans}}$,  $C_{V, \text{rot}}$, $C_{V, \text{vib}}$, and $C_{V, \text{ele}}$ are the translational, rotational, vibrational, and electronic contributions to the heat capacity, respectively. For the ideal gas, the difference between $C_P$ and $C_V$ is a constant:

$$
C_P - C_V = k_B
$$

## Translational contributions
The translational partition function from the Sackur-Tetrode equation is

$$
Q_{\text{trans}} = \left ( \frac{2 \pi m k_B T} {h^2} \right )^{\frac{3}{2}} V
$$

where V is the volume. 

For an ideal gas molecule, based on $PV = k_BT$, the equation can be rewritten. The translational partition function is used to calculate the translational entropy (which
includes the factor of $e$ which comes from Stirling’s approximation): 

$$
\begin{split}
S_{\text{trans}} & \equiv k_B \left[ \ln \left(Q_{\text{trans}} e\right) + T\left(\frac{\partial \ln Q_{\text{trans}}}{\partial T}\right)_V\right] \\
 & = k_B \left(\frac{5}{2} + \ln \left[ \frac{k_B T}{P} \left ( \frac{2 \pi m k_B T} {h^2} \right )^{\frac{3}{2}} \right] \right)    
\end{split}
$$

Its contribution to $E$ is

$$
\begin{split}
E_{trans} & \equiv k_BT^2 \left(\frac{\partial \ln Q_{\text{trans}}}{\partial T}\right)_V \\
& = \frac {3} {2} k_B T
\end{split}
$$

## Rotational contributions
For a monatomic molecule, the partition function is

$$
Q_{\text{rot, mona}} = 1
$$

For a linear molecule, 

$$
Q_{\text{rot,linear}} = \frac {8 \pi^2 k_B T I_r} {\sigma h^2}
$$

where $I_r$ is the moment of inertia of the molecule along the direction that perpendicular to the axis of molecule, and $\sigma$ is the symmetry number, which is determined from the point group of the molecule.

For a nonlinear molecule,

$$
Q_{rot, nonlinear} =  \frac { \left( 8 \pi^2 k_B T \right)^{3/2} \sqrt {\pi I_A I_B I_C}} {\sigma h^3}
$$

where $I_A$, $I_B$, and $I_C$ correspond to the three principal moments of rotational inertia with respect to three perpendicular axes.

| Point Groups                | Symmetry Numbers |
|:---------------------------:|:----------------:|
| $C_1$, $C_i$, $C_s$         | 1                |
| $C_2$, $C_{2v}$, $C_{2h}$   | 2                |
| $C_3$, $C_{3v}$, $C_{3h}$   | 3                |
| $C_4$, $C_{4v}$, $C_{4h}$   | 4                |
| $C_6$, $C_{6v}$, $C_{6h}$   | 6                |
| $D_2$, $D_{2d}$, $D_{2h}$   | 4                |
| $D_3$, $D_{3d}$, $D_{3h}$   | 6                |
| $D_4$, $D_{4d}$, $D_{4h}$   | 8                |
| $D_6$, $D_{6d}$, $D_{6h}$   | 12               |
| $S_6$                       | 3                |
| $C_{\infty}$                | 1                |
| $D_{\infty h}$              | 2                |
| $T$, $T_d$                  | 12               |
| $O_h$                       | 24               |

Its contribution to $S$ is

$$
\begin{split}
S_{\text{rot}} & \equiv k_B \left[ \ln \left(Q_{\text{rot}} \right) + T\left(\frac{\partial \ln Q_{\text{rot}}}{\partial T}\right)_V\right] \\
& = \begin{cases} 
0 & \text{monatomic} \\
k_B \left[\ln \left(\frac {8 \pi^2 k_B T I_r} {\sigma h^2} \right) + 1\right] & \text{linear} \\
k_B \left[\ln \left(\frac { \left( 8 \pi^2 k_B T \right)^{3/2} \sqrt {\pi I_A I_B I_C}} {\sigma h^3} \right) + \frac{3}{2}\right] & \text{nonlinear}
\end{cases}
\end{split}
$$

Its contribution to $E$ is

$$
\begin{split}
E_{\text{rot}} & \equiv k_BT^2 \left(\frac{\partial \ln Q_{\text{rot}}}{\partial T}\right)_V \\
& = \begin{cases} 
0 & \text{monatomic} \\
k_B T & \text{linear} \\
\frac {3}{2} k_B T & \text{nonlinear}
\end{cases}
\end{split}
$$

## Vibrational contributions
Only the real modes ($3n_{\text{atoms}} −6$ for non-linear molecules or $n_{\text{atoms}} −5$ for linear molecules) should be considered; modes with imaginary frequencies are ignored.

If we choose the zero reference point to be the bottom of the well, the partition function is

$$
Q_{\text{vib}} = \prod_i \frac {e^{-\frac{h\nu_i}{2k_BT}}} {1-e^{-\frac{h\nu_i}{k_BT}}}
$$

On the other hand, if you choose the first vibrational energy level to be the zero of energy, the partition function is

$$
Q_{\text{vib}} = \prod_i \frac {1} {1-e^{-\frac{h\nu_i}{k_BT}}}
$$

Independent to the forms of the partition functions, its contribution to $S$ is

$$
\begin{split}
S_{\text{vib}} & \equiv k_B \left[ \ln \left(Q_{\text{vib}} \right) + T\left(\frac{\partial \ln Q_{\text{vib}}}{\partial T}\right)_V\right] \\
& = k_B  \left\{\sum_i \left[ \frac{h\nu_i}{2k_BT} + \ln\left(1-e^{-\frac{h\nu_i}{k_BT}}\right) \right] + T\left[\sum_i \frac{h\nu_i}{2k_BT^2} +\sum_i \left(\frac{h\nu_i}{k_BT^2}\frac{e^{-\frac{h\nu_i}{k_BT}} }{ 1-e^{-\frac{h\nu_i}{k_BT}}} \right) \right]\right\} \\
& = k_B \sum_i \left[ \frac{h\nu_i}{{k_BT} \left(e^{\frac{h\nu_i}{k_BT}}-1\right)} - \ln\left(1-e^{-\frac{h\nu_i}{k_BT}}\right) \right]
\end{split}
$$

If we choose the zero reference point to be the bottom of the well, the contribution to $E$ is

$$
\begin{split}
E_{\text{vib}} & \equiv k_BT^2 \left(\frac{\partial \ln Q_{\text{vib}}}{\partial T}\right)_V \\
& = k_B T^2\left[\sum_i \frac{h\nu_i}{2k_BT^2} +\sum_i \left(\frac{h\nu_i}{k_BT^2}\frac{e^{-\frac{h\nu_i}{k_BT}} }{ 1-e^{-\frac{h\nu_i}{k_BT}}} \right) \right]\\
& = \sum_i \left(\frac{h\nu_i}{2}+\frac{h \nu_i} {e^{\frac{h\nu_i}{k_BT}} - 1}\right)
\end{split}
$$

if you choose the first vibrational energy level to be the zero of energy, the contribution to $E$ is

$$
\begin{split}
E_{\text{vib}} & \equiv E_{\text{ZPE}} + k_BT^2 \left(\frac{\partial \ln Q_{\text{vib}}}{\partial T}\right)_V \\
& = E_{\text{ZPE}} + k_B T^2\sum_i \left(\frac{h\nu_i}{k_BT^2}\frac{e^{-\frac{h\nu_i}{k_BT}} }{ 1-e^{-\frac{h\nu_i}{k_BT}}} \right) \\
\end{split}
$$

Since the contribution to $E$ should be independent to the forms of the partition functions

$$
E_{\text{ZPE}} =\frac{1}{2} \sum_i h\nu_i
$$

## Reference
[1] Ochterski, Joseph W. "Thermochemistry in gaussian." Gaussian Inc 1 (2000): 1-19.