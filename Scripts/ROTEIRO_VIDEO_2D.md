# Roteiro do vídeo (≈ 3 min): Convolução 2D

Notebook: `Scripts/4_Convolucion_2D_Projeto.ipynb`. Compartilhe a tela e rode as células enquanto fala.

| Tempo | Tela | O que falar |
|---|---|---|
| 0:00–0:15 | Título do notebook | "Este é meu projeto de convolução 2D, baseado no código do vídeo. Vou mostrar o exemplo básico, os filtros de imagem e testar kernels maiores." |
| 0:15–0:50 | Seção 1 | "Uma imagem é uma matriz de números. A convolução 2D é igual à 1D, mas o kernel é uma matriz que desliza nas duas direções: ele é refletido, desliza, multiplica e soma. Aqui a matriz tem metade clara e metade escura, e o kernel compara a linha de cima com a de baixo. Onde a região é uniforme dá zero, e na fronteira dá −2: o kernel detecta a borda. A primeira linha vale 2 por efeito de borda, porque fora da matriz o SciPy completa com zeros. Fiz a mesma conta com laços `for` e deu igual ao SciPy." |
| 0:50–1:15 | Seção 2 | "A imagem colorida tem 3 canais, R, G e B. A função `filtra` faz a convolução em cada canal, junta de novo e corta os valores para ficarem entre 0 e 255. O `boundary='symm'` espelha a imagem nas bordas em vez de completar com zeros." |
| 1:15–1:35 | Seções 3 e 5 | "O kernel de realce tem 5 no centro e −1 nos vizinhos; a soma é 1 e ele deixa a imagem mais nítida. O de bordas tem 8 e −1; a soma é 0, então as regiões uniformes ficam pretas e só os contornos aparecem. Com o Sobel separei as bordas verticais e horizontais." |
| 1:35–2:05 | Seção 4 | "Agora o kernel maior. O kernel de média é uma matriz N×N com valores 1/N², soma 1. Com 3×3 quase não muda; com 7, 15 e 25 a imagem fica cada vez mais borrada, porque cada pixel vira a média de uma região maior. Os detalhes menores que o kernel desaparecem." |
| 2:05–2:45 | Seção 6 | "O kernel gaussiano tem formato de sino: mais peso no centro, menos nas pontas. Uso σ = N/6 para o sino ocupar o kernel inteiro. Aumentando o tamanho, a imagem também borra mais. No zoom, com o mesmo tamanho 15, a média borra mais e a gaussiana borra de forma mais suave e natural." |
| 2:45–3:00 | Conclusões | "Resumindo: o kernel define o efeito. Soma 1 mantém o brilho, soma 0 mostra só as bordas. Kernel maior borra mais e deixa a conta mais lenta, e a gaussiana suaviza de forma mais natural que a média. Obrigado!" |

**Dicas:** rode `Kernel > Restart & Run All` antes de gravar. A seção 7 (webcam) é opcional; só funciona no seu computador, com o OpenCV instalado e `USAR_CAMERA = True`.
