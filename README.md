[![Open in MATLAB Online](https://www.mathworks.com/images/responsive/global/open-in-matlab-online.svg)](https://matlab.mathworks.com/open/github/v1?repo=tigremiau/MMP2)

# Practica 2: Caos en sistemas biologicos


\documentclass{article}
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\usepackage{amsfonts}

%TCIDATA{OutputFilter=LATEX.DLL}
%TCIDATA{Version=5.50.0.2953}
%TCIDATA{<META NAME="SaveForMode" CONTENT="1">}
%TCIDATA{BibliographyScheme=Manual}
%TCIDATA{Created=Monday, October 26, 2026 15:59:34}
%TCIDATA{LastRevised=Monday, November 09, 2026 08:03:17}
%TCIDATA{<META NAME="GraphicsSave" CONTENT="32">}
%TCIDATA{<META NAME="DocumentShell" CONTENT="Standard LaTeX\Blank - Standard LaTeX Article">}
%TCIDATA{CSTFile=40 LaTeX article.cst}

\newtheorem{theorem}{Theorem}
\newtheorem{acknowledgement}[theorem]{Acknowledgement}
\newtheorem{algorithm}[theorem]{Algorithm}
\newtheorem{axiom}[theorem]{Axiom}
\newtheorem{case}[theorem]{Case}
\newtheorem{claim}[theorem]{Claim}
\newtheorem{conclusion}[theorem]{Conclusion}
\newtheorem{condition}[theorem]{Condition}
\newtheorem{conjecture}[theorem]{Conjecture}
\newtheorem{corollary}[theorem]{Corollary}
\newtheorem{criterion}[theorem]{Criterion}
\newtheorem{definition}[theorem]{Definition}
\newtheorem{example}[theorem]{Example}
\newtheorem{exercise}[theorem]{Exercise}
\newtheorem{lemma}[theorem]{Lemma}
\newtheorem{notation}[theorem]{Notation}
\newtheorem{problem}[theorem]{Problem}
\newtheorem{proposition}[theorem]{Proposition}
\newtheorem{remark}[theorem]{Remark}
\newtheorem{solution}[theorem]{Solution}
\newtheorem{summary}[theorem]{Summary}
\newenvironment{proof}[1][Proof]{\noindent\textbf{#1.} }{\ \rule{0.5em}{0.5em}}
\input{tcilatex}
\begin{document}


Palabras clave: Sistema no lineal; Caos; Estabilidad; Simulaciones num\'{e}%
ricas; Sistema biol\'{o}gico.

\bigskip

Correo: 16041206@itdurango.edu.mx

Carrera: Maestr\'{\i}a en Ingenier\'{\i}a

Asignatura: Biolog\'{\i}a de Sistemas

Profesor: Dr. Paul Antonio Valles Trujillo (paul.valle@tectijuana.edu.mx)

\bigskip

\section{Modelo matem\'{a}tico}

El modelo matem\'{a}tico que describe la din\'{a}mica entre tres poblaciones
celulares est\'{a} descrito por las siguientes tres EDOs no lineales de
primer orden:

\begin{eqnarray*}
\dot{x} &=&r_{1}x(1-b_{1}x)-a_{12}xy-a_{13}xz \\
\dot{y} &=&r_{2}y(1-b_{2}y)-a_{21}xy \\
\dot{z} &=&(r_{3-a_{31}}xz)-d_{3}z+\rho
\end{eqnarray*}

donde todos los par\'{a}metros son positivos, las condiciones iniciales no
negativas y el par\'{a}metro de control $\rho \geq 0$.

\bigskip

\section{Positividad del sistema}

Con base en el trabajo de De Leenheer y Aeyels, se realiza el siguiente c%
\'{a}lculo para establecer la positividad del sistema:\newline

\begin{eqnarray*}
\left. \dot{x}\right\vert _{x=0}
&=&r_{1}(0)(1-b_{1}(0))-a_{12}(0)y-a_{13}(0)z=0, \\
\left. \dot{y}\right\vert _{y=0} &=&r_{2}(0)(1-b_{2}(0))-a_{21}x(0)=0, \\
\left. \dot{z}\right\vert _{z=0} &=&(r_{3}-a_{31})x(0)-d_{3}(0)+\rho =\rho
\geq 0
\end{eqnarray*}

entonces, siguiendo el criterio general para la positividad en las
soluciones de un sistema din\'{a}mico no lineal, se establece el siguiente
resultado:

\textbf{Resultado: Positividad e invarianza en el octante no negativo. }Sea $%
\psi =(x(t),y(t),z(t))^{T}$ una soluci\'{o}n/trayectoria del sistema con
condiciones iniciales no negativas, es decir, $\psi (t_{0})\in 
%TCIMACRO{\U{211d} }%
%BeginExpansion
\mathbb{R}
%EndExpansion
_{+,0}^{3}$, por lo tanto el octante no negativo definido por:

\[
%TCIMACRO{\U{211d} }%
%BeginExpansion
\mathbb{R}
%EndExpansion
_{+,0}^{3}=\{\psi \in 
%TCIMACRO{\U{211d} }%
%BeginExpansion
\mathbb{R}
%EndExpansion
_{+,0}^{3}:x,y,z\geq 0\}, 
\]

es positivamente invariante y $\psi (t,x,y,z)\in 
%TCIMACRO{\U{211d} }%
%BeginExpansion
\mathbb{R}
%EndExpansion
_{+,0}^{3}$ para $t\geq 0$.

\bigskip

\section{Puntos de equilibrio libre de c\'{e}lulas patol\'{o}gicas}

Con el objetivo de determinar condiciones para la eliminaci\'{o}n de c\'{e}%
lulas patol\'{o}gicas, se calculan los equiulibrios donde $x=0$, es decir,
se debe resolver el siguiente sistema de ecuaciones:

\begin{eqnarray*}
r_{1}x(1-b_{1}x)-a_{12}xy-a_{13}xz &=&0, \\
r_{2}y(1-b_{2}y)-a_{21}xy &=&0, \\
(r_{3-a_{31}}xz)-d_{3}z+\rho &=&0,
\end{eqnarray*}

entonces, si $x=0$, se reescribe de la siguiente forma:

\begin{eqnarray*}
x &=&0 \\
y(1-b_{2}y) &=&0 \\
-d_{3}z+\rho &=&0
\end{eqnarray*}

por lo tanto, se resuelve despejando cada variable de estado:

\begin{eqnarray*}
x^{\ast } &=&0, \\
y(1-b_{2}y) &=&0, \\
z^{\ast } &=&\frac{\rho }{d_{3},}
\end{eqnarray*}

resolviendo para $y$ se obtiene lo siguiente:

\begin{eqnarray*}
y_{0}^{\ast } &=&0, \\
y_{1}^{\ast } &=&\frac{1}{b_{2}}
\end{eqnarray*}

y los equilibrios donde $x=0$, est\'{a}n dados por:

\begin{eqnarray*}
(x_{0}^{\ast },y_{0}^{\ast },z_{0}^{\ast }) &=&(0,0,\frac{\rho }{d_{3}}), \\
(x_{1}^{\ast },y_{1}^{\ast },z_{1}^{\ast }) &=&(0,\frac{1}{b_{2}},\frac{\rho 
}{d_{3}}).
\end{eqnarray*}

\bigskip

\section{Estabilidad asint\'{o}tica local}

Ahora, con el prop\'{o}sito de establecer condiciones para asegurar la
estabilidad asint\'{o}tica local del punto de equilibrio libre de c\'{e}%
lulas patol\'{o}gicas $(x_{1}^{\ast },y_{1}^{\ast },z_{1}^{\ast })$, se
calcula la matriz Jacobiana del sistema como se muestra a continuaci\'{o}n:

\[
J=\left[ 
\begin{array}{ccc}
\frac{\partial \dot{x}}{\partial x} & \frac{\partial \dot{x}}{dy} & \frac{%
\partial \dot{x}}{\partial z} \\ 
\frac{\partial \dot{y}}{dx} & \frac{\partial \dot{y}}{dy} & \frac{\partial 
\dot{y}}{\partial z} \\ 
\frac{\partial \dot{z}}{\partial x} & \frac{\partial \dot{z}}{\partial y} & 
\frac{\partial \dot{z}}{\partial z}%
\end{array}%
\right] =\left[ 
\begin{array}{ccc}
r_{1}-2b_{1}r_{1}x-a_{12}x-a_{13}z & -a_{12}x & -a_{13}x \\ 
-a_{21}y & r_{2}-2b_{2}r_{2}y-a_{21}x & 0 \\ 
r_{3}z-a_{31}z & 0 & r_{3}x-a_{31}x-d_{3}%
\end{array}%
\right] 
\]

\[
(r_{1}x-r_{1}b_{1}x^{2}-a_{12}xy-a_{13}xz,r_{2}y-r_{2}b_{2}y^{2}-a_{21}xy,r_{3}xz-a_{31}xz-d_{3}z+\rho ) 
\]

Para evaluar la estabilidad del equilibrio de inter\'{e}s, se eval\'{u}a $J$
en $(x_{1}^{\ast },y_{1}^{\ast },z_{1}^{\ast })$ y se calculan los valores
propios de la matriz resultante, es decir,

\[
\left. J\right\vert _{(x_{1}^{\ast },y_{1}^{\ast },z_{1}^{\ast })}=\left[ 
\begin{array}{ccc}
r_{1}-2b_{1}r_{1}x-a_{12}x-a_{13}z & -a_{12}x & -a_{13}x \\ 
-a_{21}y & r_{2}-2b_{2}r_{2}y-a_{21}x & 0 \\ 
r_{3}z-a_{31}z & 0 & r_{3}x-a_{31}x-d_{3}%
\end{array}%
\right] _{x=0,y=1/b_{2}z=\rho /d_{3}} 
\]

\[
\left. J\right\vert _{(x_{1}^{\ast },y_{1}^{\ast },z_{1}^{\ast })}=\left[ 
\begin{array}{ccc}
r_{1}-\frac{a_{12}}{b_{2}}-\frac{a_{13}\rho }{d_{3}} & 0 & 0 \\ 
-\frac{a_{21}}{b_{2}} & -r_{2} & 0 \\ 
\frac{\rho }{d_{3}}(r_{3}-a_{31}) & 0 & -d_{3}%
\end{array}%
\right] 
\]

Para determinar los valores propios de la matriz, se calculan las ra\'{\i}%
ces del Jacobiano:

\[
\det (A-\lambda I)=0, 
\]

\begin{eqnarray*}
\det \left( 
\begin{array}{ccc}
r_{1}-\frac{a_{12}}{b_{2}}-\frac{a_{13}\rho }{d_{3}} & 0 & 0 \\ 
-\frac{a_{21}}{b_{2}} & -r_{2} & 0 \\ 
\frac{\rho }{d_{3}}(r_{3}-a_{31}) & 0 & -d_{3}%
\end{array}%
-\lambda 
\begin{array}{ccc}
1 & 0 & 0 \\ 
0 & 1 & 0 \\ 
0 & 0 & 1%
\end{array}%
\right) &=&0, \\
\det \left( 
\begin{array}{ccc}
r_{1}-\frac{a_{12}}{b_{2}}-\frac{a_{13}\rho }{d_{3}} & 0 & 0 \\ 
-\frac{a_{21}}{b_{2}} & -r_{2} & 0 \\ 
\frac{\rho }{d_{3}}(r_{3}-a_{31}) & 0 & -d_{3}%
\end{array}%
-%
\begin{array}{ccc}
\lambda & 0 & 0 \\ 
0 & \lambda & 0 \\ 
0 & 0 & \lambda%
\end{array}%
\right) &=&0, \\
\det \left( 
\begin{array}{ccc}
r_{1}-\frac{a_{12}}{b_{2}}-\frac{a_{13}\rho }{d_{3}}-\lambda & 0 & 0 \\ 
-\frac{a_{21}}{b_{2}} & -r_{2}-\lambda & 0 \\ 
\frac{\rho }{d_{3}}(r_{3}-a_{31}) & 0 & -d_{3}-\lambda%
\end{array}%
\right) &=&0,
\end{eqnarray*}

\bigskip 
\begin{eqnarray*}
-\frac{1}{b_{2}d_{3}}(\lambda +d_{3})(\lambda +r_{2})(d_{3}a_{12}+\lambda
b_{2}d_{3}+\rho b_{2}a_{13}-b_{2}d_{3}r_{1}) &=&0 \\
(\lambda +d_{3})(\lambda +r_{2})(d_{3}a_{12}+\lambda b_{2}d_{3}+\rho
b_{2}a_{13}-b_{2}d_{3}r_{1}) &=&0
\end{eqnarray*}

\[
-\lambda ^{3}+\left( -\frac{1}{b_{2}d_{3}}\left(
d_{3}a_{12}+b_{2}d_{3}(d_{3}+r_{2})+\rho b_{2}a_{13}-b_{2}d_{3}r_{1}\right)
\right) \allowbreak \lambda ^{2}+\left( -\frac{1}{b_{2}d_{3}}\left(
(d_{3}+r_{2})(d_{3}a_{12}+\rho b_{2}a_{13}-b_{2}d_{3}r_{1})\right) \right)
\allowbreak 
\]

Cuando la matriz $A$ es triangular (inferior o superior), entonces los
valores propios son los elementos de la diagonal:

\begin{eqnarray*}
\lambda _{1} &=&r_{1}-\frac{a_{12}}{b_{2}}-\frac{a_{13}\rho }{d_{3}}, \\
\lambda _{2} &=&-r_{2} \\
\lambda _{3} &=&-d_{3}
\end{eqnarray*}

se observa que $a_{2,3}<0$ y se determina la siguiente condici[on sobre el
par\'{a}metro de control $\rho $ para asegurar que $\lambda _{1}<0$:

\begin{eqnarray*}
r_{1}-\frac{a_{12}}{b_{2}}-\frac{a_{13}\rho }{d_{3}} &<&0, \\
\rho &>&\frac{d_{3}}{a_{13}}(r_{1}-\frac{a_{12}}{b_{2}}),
\end{eqnarray*}

por lo tanto, se establece el siguiente resultado con respecto a la
estabilidad asint\'{o}tica local de $(x_{1}^{\ast },y_{1}^{\ast
},z_{1}^{\ast })$.

\bigskip

\textbf{Resultado: Condici[on de eliminaci[on local de c\'{e}lulas patol\'{o}%
gicas. }\textit{Si la condici\'{o}n }%
\[
\rho >\frac{d_{3}}{a_{13}}\left( r_{1}-\frac{a_{12}}{b_{2}}\right) , 
\]%
\textit{se cumple, entonces, el equilibrio libre de c\'{e}lulas patol\'{o}%
gicas }$(x_{1}^{\ast },y_{1}^{\ast },z_{1}^{\ast })$\textit{\ es local aint%
\'{o}ticamente estable y se puede asegurar la eliminaci\'{o}n de una poblaci%
\'{o}n inicial de c\'{e}lulas patol\'{o}gicas cercana a dicho equilibrio.}

Del resultado anterior, se obtiene el siguiente resultado complementario:

\bigskip

\textbf{Resultado: Persistencia. }\textit{Si la siguiente condici\'{o}n se
cumple:}

\[
\rho <\frac{d_{3}}{a_{13}}(r_{1}-\frac{a_{12}}{b_{2}}) 
\]

\textit{entonces, se observar\'{a} una persistencia de la poblaci\'{o}n de c%
\'{e}lulas patol\'{o}gicas en las soluciones y trayectorias del sistema.}

\bigskip

\textbf{Tarea: }

Realizar el an\'{a}lisis de estabilidad asint\'{o}tica local\ de $%
(x_{0}^{\ast },y_{0}^{\ast },z_{0}^{\ast })=(0,0,\frac{\rho }{d_{3}})$.

\bigskip

\section{An\'{a}lisis de estabilidad asint\'{o}tica local de $(x_{0}^{\ast
},y_{0}^{\ast },z_{0}^{\ast })$}

Con el prop\'{o}sito de establecer las condiciones de estabilidad asint\'{o}%
tica local del punto de equilibrio libre de c\'{e}lulas tanto patol\'{o}%
gicas como sanas, definido por $(x_{0}^{\ast },y_{0}^{\ast },z_{0}^{\ast
})=(0,0,\frac{\rho }{d_{3}})$, se eval\'{u}a la matriz Jacobiana general del
sistema en dicho punto:

\[
\left. J\right\vert _{(x_{0}^{\ast },y_{0}^{\ast },z_{0}^{\ast })}=\left[ 
\begin{array}{ccc}
r_{1}-2b_{1}r_{1}x-a_{12}y-a_{13}z & -a_{12}x & -a_{13}x \\ 
-a_{21}y & r_{2}-2b_{2}r_{2}y-a_{21}x & 0 \\ 
(r_{3}-a_{31})z & 0 & (r_{3}-a_{31})x-d_{3}%
\end{array}%
\right] _{x=0,y=0,z=\rho /d_{3}} 
\]

\[
\left. J\right\vert _{(x_{0}^{\ast },y_{0}^{\ast },z_{0}^{\ast })}=\left[ 
\begin{array}{ccc}
r_{1}-\frac{a_{13}\rho }{d_{3}} & 0 & 0 \\ 
0 & r_{2} & 0 \\ 
\frac{\rho }{d_{3}}(r_{3}-a_{31}) & 0 & -d_{3}%
\end{array}%
\right] 
\]

Para determinar los valores propios de la matriz, se calculan las ra\'{\i}%
ces del Jacobiano:

\[
\det (A-\lambda I)=0, 
\]

\begin{eqnarray*}
\det \left( 
\begin{array}{ccc}
r_{1}-\frac{a_{13}\rho }{d_{3}} & 0 & 0 \\ 
0 & r_{2} & 0 \\ 
\frac{\rho }{d_{3}}(r_{3}-a_{31}) & 0 & -d_{3}%
\end{array}%
-\lambda 
\begin{array}{ccc}
1 & 0 & 0 \\ 
0 & 1 & 0 \\ 
0 & 0 & 1%
\end{array}%
\right)  &=&0, \\
\det \left( 
\begin{array}{ccc}
r_{1}-\frac{a_{13}\rho }{d_{3}} & 0 & 0 \\ 
0 & r_{2} & 0 \\ 
\frac{\rho }{d_{3}}(r_{3}-a_{31}) & 0 & -d_{3}%
\end{array}%
-%
\begin{array}{ccc}
\lambda  & 0 & 0 \\ 
0 & \lambda  & 0 \\ 
0 & 0 & \lambda 
\end{array}%
\right)  &=&0, \\
\det \left( 
\begin{array}{ccc}
r_{1}-\frac{a_{13}\rho }{d_{3}}-\lambda  & 0 & 0 \\ 
0 & r_{2}-\lambda  & 0 \\ 
\frac{\rho }{d_{3}}(r_{3}-a_{31}) & 0 & -d_{3}-\lambda 
\end{array}%
\right)  &=&0,
\end{eqnarray*}%
: 

Cuando la matriz $A$ es triangular (inferior o superior), entonces los
valores propios son los elementos de la diagonal:

\begin{eqnarray*}
\lambda _{1} &=&r_{1}-\frac{a_{13}\rho }{d_{3}}, \\
\lambda _{2} &=&r_{2}, \\
\lambda _{3} &=&-d_{3}
\end{eqnarray*}

Para asegurar la estabilidad asint\'{o}tica local, todos los valores propios
deben tener parte real estrictamente negativa. 

Analizando cada uno de ellos bajo la premisa de que todos los par\'{a}metros
del sistema son positivos ($r_{2},d_{3}>0$):

$\lambda _{3}=-d_{3}<0$, lo cual favorece la estabilidad.

$\lambda _{2}=r_{2}>0$, dado que la tasa de crecimiento intr\'{\i}nseca de
la poblaci\'{o}n sana es una constante positiva.

\textbf{Resultado: Inestabilidad del equilibrio libre de c\'{e}lulas.}
Debido a que el valor propio $\lambda _{2}=r_{2}$ es \textbf{estrictamente
positivo} de forma independiente a los par\'{a}metros de control, el punto
de equilibrio $(0,0,\frac{\rho }{d_{3}})$ es \textbf{localmente inestable}
para cualquier configuraci\'{o}n del sistema. Espec\'{\i}ficamente, se
clasifica como un \textit{punto de silla}.

Biol\'{o}gicamente, esto indica que el estado de extinci\'{o}n celular total
no puede mantenerse de forma natural; cualquier peque\~{n}a introducci\'{o}n
o presencia residual de c\'{e}lulas sanas ($y$) crecer\'{a} exponencialmente
debido a su tasa intr\'{\i}nseca $r_{2}$.

\end{document}
