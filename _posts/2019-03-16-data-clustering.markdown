---
layout: post
title:  "Clusterização de dados"
date:   2019-03-16 12:00:00 -0300
categories: Artigos
---

## Clusterização de dados

#### Introdução

Clusterização ou aprendizado não supervisionado, é uma das técnicas mais importantes em análise de dados [1]. Técnicas de clusterização buscam encontrar padrões naturais inerentes aos dados, agrupando dados não rotulados em grupos homogêneos, chamados de Cluster. Dados de um mesmo cluster são mais similares entre eles e menos similares em relação a dados de outros clusters.

As técnicas de clusterização tem sido amplamente aplicadas nas áreas de mineração de dados, segmentação de imagens, reconhecimento de padrões, pesquisa de mercado, etc. [2],[3].

Abordagens tradicionais de clusterização são divididas em dois grupos principais: algoritmos hierárquicos e algoritmos de partição. Algoritmos hierárquicos são capazes de encontrar clusters aninhados de modo aglomerativo, de maneira que os pontos de dados mais similares são fundidos recursivamente até formar uma hierarquia de clusters, e divisivo onde todos os dados começam em um mesmo cluster e então são divididos recursivamente em clusters menores. Algoritmos de partição encontram simultaneamente todas as partições de dados sem impor qualquer estrutura hierárquica [1]. Dentre os métodos mais comuns de algoritmos de partição temos: K-Means, Mean-Shift, DBScan e Expectation-Maximization usando modelos de misturas gaussianas.

Dentre todas as abordagens de clusterização, a mais difundida e utilizada, mas, não necessariamente a melhor, é o K-Means. O K-Means é um algoritmo simples e que em termos gerais funciona razoavelmente bem para muitas aplicações. Neste artigo pretendo explicar o conceito de funcionamento do K-Means, seu comportamento em algumas bases de dados e como poderíamos estimar automaticamente o número de cluster uma vez que este método exige como entrada um número definido de cluster.