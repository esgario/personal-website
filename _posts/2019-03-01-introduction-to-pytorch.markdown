---
layout: post
title:  "Introdução ao PyTorch!"
date:   2019-03-10 12:00:00 -0300
categories: Tutoriais
---

## Introdução ao PyTorch

#### O que é o PyTorch?

PyTorch é basicamente uma biblioteca desenvolvida em python baseada no Torch que foi originalmente desenvolvido em Lua cuja finalidade é facilitar o desenvolvimento de aplicações de aprendizado de máquina. Uma vez que os algoritmos de aprendizado de máquina têm se tornado mais complexos, perder tempo com a programação ao invés de se preocupar com a arquitetura do modelo a ser desenvolvido não é algo desejável. Por isso, bibliotecas como PyTorch e Tensorflow foram desenvolvidas para ajudar a nós a programarmos sistema baseados em aprendizado de máquina de forma mais eficiente.

#### Por que usar o PyTorch?

O PyTorch foi desenvolvido pelo Facebook e é utilizado por grandes empresas como o Uber. A principal diferença entre o PyTorch e o Tensorflow é que o primeiro pode ser entendido como um framework do tipo 'Definir-pela-execução' e o segundo 'Definir-e-executar', ou seja, os grafos em PyTorch vão sendo definidos durante a execução do código dando uma sensação mais natural de se codificar, diferente do Tensorflow que primeiro define-se o grafo pra só depois executá-lo.

### Instalação

Sem mais blá blá blá, vamos então instalar o PyTorch para podermos programar.

Os passos para instalação podem ser visualizados [aqui](https://pytorch.org/get-started). No entanto, eu vou descrever de forma simplificada os passos que eu realizei para instalar no meu computador. Os passos descritos aqui são para Linux mas a instalação em outros SO's é bastante simples também.

A instalação consiste em 3 passos:

#### 1. Instalar o Python

Muito provavelmente já deve vir na sua instalação do linux, caso contrário, instale. A recomendação pelo site do pytorch é usar o python 3. Para isso, execute os comandos abaixo:

```
$ sudo apt-get update
$ sudo apt-get install python3.6
```

#### 2. Instalar o gerenciador de pacote.

Você Pode utilizado tanto Anaconda quanto o Pip, particularmente, recomendo utilizar o Anaconda. Para instala-lo basta:

```
$ cd /tmp
$ curl -O https://repo.anaconda.com/archive/Anaconda3-5.2.0-Linux-x86_64.sh
$ sh Anaconda3-5.2.0-Linux-x86_64.sh
```

Durante o processo de instalação você deverá:
- Aceitar os termos.
- Definir o local de instalação.

#### 3. Instalar o PyTorch

Os comandos abaixo levam em consideração que tenha instalado o Anaconda como gerenciador de pacotes. Caso você possua acesso a uma GPU e ao CUDA, a instalação pode ser realizada pelo seguinte comando:

```
$ conda install pytorch torchvision cudatoolkit=9.0 -c pytorch
```

Para utilizar apenas a CPU pode utilizado o comando abaixo:

```
$ conda install pytorch-cpu torchvision-cpu -c pytorch
```

### Primeiros passos no PyTorch

O conceito básico do PyTorch gira em torno dos Tensores. Um tensor pode ser entendido como uma generalização de matrizes, logo, tensores são por naturezas matrizes de N dimensões. Criar tensores com PyTorch é tão simples quanto em Numpy.

Primeiro vamos importar nossa biblioteca:

```python
import torch
```

Podemos criar um tensores da seguinte forma:

```python
# vetor
v_data = [1., 2., 3., 4., 5.]
v = torch.tensor(v_data)
print(v)

# matriz
m_data = [[1., 1.5, 2.], [3., 3.5, 4]]
m = torch.tensor(m_data)
print(m)
```
```
Output:
>> tensor([1., 2., 3., 4., 5.])
>> tensor([[1., 1.5, 2.],
           [3., 3.5, 4.]])
```

Operações com tensores são realizadas de forma simples e intuitiva, por exemplo:

```python
torch.manual_seed(1)

x = torch.rand(2, 2)
print(x)

y = torch.ones(2, 2)
print(y)

# Soma de dois tensores
print(x + y)

# Subtração de dois tensores
print(x - y)

# Somatório dos valores de um tensor
print(x.sum())

# Maior valor de um tensor
print(x.max())
```
```
Output:
>> tensor([[0.7576, 0.2793],
           [0.4031, 0.7347]])
>> tensor([[1., 1.],
           [1., 1.]])
>> tensor([[1.7576, 1.2793],
           [1.4031, 1.7347]])
>> tensor([[-0.2424, -0.7207],
           [-0.5969, -0.2653]])
>> tensor(2.1747)
>> tensor(0.7576)
```