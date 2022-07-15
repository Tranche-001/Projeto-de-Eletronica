# Projeto-de-Eletronica-USP
## Participantes:
| **Nome Completo**              | **N°USP**|
|--------------------------------|----------|
| [Guilherme Motta Tranche](https://github.com/Tranche-001)               | 13671549 |
| [Allan Garcia Cavalcante e Silva](https://github.com/rinderomna)         | 13731222 | 
| [Raphael David Phillippe Levéque](https://github.com/raphaelleveque)| 12542522 |


## Objetivo:
Desenvolver uma fonte de tensão retificadora que transforma uma corrente alternada de tensão 127RMS em uma corrente contínua.
A fonte deve ser capaz de variar sua tensão entre 3 e 12 volts.

## Falstad:
![Diagrama da fonte no software Falstad](imagens/falstad.jpg "Diagrama da fonte no software Falstad")

## Equações:
\documentclass{article}
\usepackage[utf8]{inputenc}
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{physics}
\usepackage{amssymb}

\title{Fonte de Tensão Variável entre 3 e 12v}
\author{Allan Garcia da Silva 
\and 
Guilherme da Motta Tranche
\and
Téo Sobrino Alves
}
\date{July 2022}

\begin{document}

\maketitle

\section{Cálculos da Fonte:}
\subsection{Trasnformador:}
\large A tensão de entrada em nosso projeto foi de \(18\) v RMS =\( 18 \cdot \sqrt{2} \approx 25,5\)v no pico, assim a razão do transformador é de:

\[n = \tfrac{18\cdot \sqrt{2}}{180} \approx 0,14\]

\subsection{Resistor do LED:}
Para o  LED, temos que: \(I_{ideal} = 5\text{mA}\), \(V_{ideal} = 2 \text{v}\) assim:

\[I_{ideal} = \tfrac{V_{max} - V_{ideal}}{R} \implies R = \tfrac{V_{max} - V_{ideal}}{I_{ideal}} = \tfrac{ 25,5 - 2}{5\cdot 10^{-3}} = 4,7K \Omega\]
\paragraph{}

No prpjeto final, pelo valor comercial, foi usado um resistor de \(4.6 K\Omega\).
\paragraph{ }

\subsection{Resistor em Série com o Potenciômetro:}
Escolha do valor do resistor em série com o potenciômetro:

\text{Mínimo desejado:} 3\text{v} + 1 \text{v} \text{(por conta do capacitor)} = 4 \text{v}

Máximo desejado: 13 v.

Resistência mínima do capacitor: \(R_{pot_{min}} = 25 \Omega\).

Resistência máxima do capacitor: \(R_{pot_{max}} = 5K\,\Omega\) 

\paragraph{ }
\[\dfrac{V_{min}}{R+R_{pot_{min}}} = \dfrac{V_{max}}{R+R_{pot_{max}}} \approx 2K\,\Omega\]

\subsection{Valor do Capacitor:}
Escolha do Capacitor:

Tensão de Ripple aceitável: 2v.

\centering{\(f\) é a frequência da tensão, 120 Hz (60 . 2), pois foi retificada na ponte de diodo. A corrente máxima é de cerca de \(130 mA\)}.

\[C = \tfrac{I_{max}}{f\cdot V_{ripple}} \approx 560 \mu F \]

\centering{Essa capacitância é a mínima para ser aceitável, um valor maior que esse irá diminuir a \(V_{ripple}\), por conveniência e disponibilidade usamos um capacitor de \(2200 \mu F\)}.Um resistor de 120 $\Omega$ foi colocado no emissor do transistor, para simular um dispositivo sendo carregado (e não haver curto-circuito).

\end{document}

## Imagem esquemático da PCB no Eagle


