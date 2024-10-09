# DesafioPBL

## Comparação de detcção de faces: OpenCV Cascade Classifier vs. Dlib HOG

Este projeto realiza uma comparação entre dois métodos populares de detecção de faces: o Cascade Classifier da biblioteca OpenCV e o Histogram of Oriented Gradients (HOG) do Dlib. O objetivo é avaliar o desempenho de cada abordagem em termos de precisão e tempo de execução, utilizando uma imagem e um vídeo como entrada.

## Abordagem Utilizada

Neste projeto, as duas bibliotecas de detecção de faces — OpenCV e Dlib — foram testadas em um conjunto de dados de imagem e vídeo. A implementação foi realizada no ambiente Google Colab.

A comparação foi feita com base em:

1. Tempo de execução para imagens e vídeos.
2. Número de faces detectadas corretamente.
3. Número de falsos positivos (detecções incorretas).

- Resultados
> ## OpenCV Cascade Classifier
> - Imagem
>   1. Tempo: ~3 segundos
>   2. Faces detectadas: 10 de 16
>   3. Falsos positivos: 1
> - Vídeo
>   1. Tempo: ~67 segundos (para um vídeo de 5 segundos)
>   2. Faces detectadas: 19 de 24
>   3. Falsos positivos: 4


> ## Dlib HOG
> - Imagem
>   1. Tempo: ~5 segundos
>   2. Faces detectadas: 12 de 16
>   3. Falsos positivos: 0
> - Vídeo
>   1. Tempo: ~134 segundos (para um vídeo de 5 segundos)
>   2. Faces detectadas: 20 de 24
>   3. Falsos positivos: 1


## Como Executar o Código no Google Colab

Faça upload do notebook do projeto ou clone este repositório diretamente para o Google Colab.

Configure um caminho do drive com imagens a serem detectadas.
Essas imagens serão usadas como padrão mais a frente no código.

Execute a segunda célula do código para carregar as imagens.
Essa célula vai pedir um upload, caso nenhuma imagem seja carregada, vai procurar na pasta do drive definida na primeira célula.

Depois de carregadas as imagens, basta executar uma das células de detecção.

## Funcionamento da Detecção de Faces

### OpenCV Cascade Classifier

O CascadeClassifier do OpenCV utiliza um modelo em cascata treinado para detectar objetos, como faces. Esse modelo passa por várias etapas (ou janelas) que filtram a imagem para encontrar regiões onde provavelmente há uma face. No entanto, ele pode gerar falsos positivos, pois se baseia em padrões fixos, e o desempenho pode variar conforme a qualidade da imagem ou vídeo.

- Vantagens:
    1. Mais rápido na detecção em imagens.
    2. Fácil de usar com modelos pré-treinados.
- Desvantagens:
    1. Menor precisão, com mais falsos positivos.
    2. Desempenho relativamente inferior em vídeos.


### Dlib HOG (Histogram of Oriented Gradients)

O método HOG no Dlib utiliza um algoritmo que identifica contornos de objetos, analisando a orientação de gradientes na imagem. Ele é mais robusto a variações de iluminação e posição, resultando em menos falsos positivos. Entretanto, o HOG pode ser mais lento do que o Cascade Classifier, especialmente quando usado em vídeos.

- Vantagens:
    1. Alta precisão, com menos falsos positivos.
    2. Desempenho consistente tanto em imagens quanto em vídeos.
- Desvantagens:
    1. Mais lento na execução, especialmente em vídeos.
    2. Requer mais recursos computacionais.
