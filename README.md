# Simulação de N-Corpos com Paralelismo em CPU e GPU

Este repositório contém a implementação paralela do problema dos N-corpos, conforme descrito no artigo **"Arquiteturas Paralelas e a Simulação dos N-Corpos: Uma Análise"**. O objetivo do projeto é simular as interações gravitacionais entre corpos celestes, utilizando técnicas de paralelização em CPU (OpenMP) e GPU (CUDA), com foco em alto desempenho.

## Autores
- **Lucas Menduiña Ramos Evangelista** - [menduina19@ufrrj.br](mailto:menduina19@ufrrj.br)
- **Gabriel Marinho de Souza** - [gmarinho@ufrrj.br](mailto:gmarinho@ufrrj.br)
- **Juliana Nascente** - [juliananascente@gmail.com](mailto:juliananascente@gmail.com)
- **Marcelo Zamith** - [mzamith@ufrrj.br](mailto:mzamith@ufrrj.br)

## Descrição do Projeto

O problema dos N-corpos consiste em prever o movimento de corpos sob a influência de forças gravitacionais mútuas. A implementação aqui proposta utiliza duas abordagens de paralelismo:
- **CPU**: Utilizando OpenMP para aproveitar múltiplos núcleos em processadores.
- **GPU**: Utilizando CUDA da Nvidia para acelerar a computação massivamente paralela.

### Algoritmos Implementados
1. **Versão Sequencial**: Baseada em um algoritmo clássico de força bruta, onde o cálculo das forças gravitacionais tem complexidade O(n²).
2. **Versão Multithread (OpenMP)**: Executa os cálculos em múltiplas threads na CPU.
3. **Versão CUDA**: Paraleliza os cálculos na GPU, utilizando milhares de núcleos CUDA.

## Requisitos

### CPU
- Sistema operacional Linux (Debian/Ubuntu recomendados)
- Compilador com suporte a OpenMP
- Processador com suporte a múltiplos núcleos

### GPU
- Nvidia GPU com suporte a CUDA (Arquiteturas Kepler ou superiores)
- Driver Nvidia CUDA Toolkit instalado

## Como Executar

### Versão CPU (OpenMP)
1. Compile o código usando `gcc` com suporte a OpenMP:
    ```bash
    gcc -fopenmp -o nbody_cpu nbody_cpu.c
    ```
2. Execute o programa:
    ```bash
    ./nbody_cpu
    ```

### Versão GPU (CUDA)
1. Compile o código usando o `nvcc` do CUDA Toolkit:
    ```bash
    nvcc -o nbody_gpu nbody_gpu.cu
    ```
2. Execute o programa:
    ```bash
    ./nbody_gpu
    ```

## Resultados

Os testes realizados mostram uma melhoria significativa no desempenho da versão paralela em relação à versão sequencial. A implementação em CUDA apresentou um *speedup* de até 40x para grandes volumes de dados. Para sistemas menores, a versão em OpenMP pode ser mais eficiente devido à sobrecarga inicial de transferência de dados entre CPU e GPU.

Gráficos e tabelas com comparações de desempenho estão disponíveis no artigo.

## Referências
- Clua, E. W. G., & Zamith, M. P. (2015). *Programming in CUDA for Kepler and Maxwell architecture*. Revista de Informática Teórica e Aplicada, 22(2), 233–257.
- Díaz, D. H. S. (2013). *Um novo simulador de N-corpos para cosmologia computacional utilizando GPUs*. Master's thesis, Instituto Nacional de Pesquisas Espaciais.
- Stallings, W. (2003). *Computer organization and architecture: designing for performance*. Pearson Education India.

