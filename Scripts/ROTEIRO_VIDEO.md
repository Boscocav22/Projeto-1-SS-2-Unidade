# Roteiro do vídeo (≈ 3 min): Convolução 1D

Notebook: `Scripts/3_Convolucion_1D_Projeto.ipynb`. Compartilhe a tela e rode as células enquanto fala.

| Tempo | Tela | O que falar |
|---|---|---|
| 0:00–0:20 | Título do notebook | "Este é meu projeto de convolução 1D, baseado no código do vídeo. Vou mostrar o exemplo básico, o filtro de média nos dados do motor e depois testar um kernel maior e um kernel gaussiano." |
| 0:20–0:55 | Seção 1 | "Importo NumPy, Matplotlib e Pandas. O sinal I tem 7 amostras e o kernel k tem 3. Na convolução, o kernel é refletido, desliza sobre o sinal e somamos os produtos. O resultado tem 7+3−1 = 9 amostras. Aqui eu fiz a mesma conta com dois laços `for`, seguindo a fórmula, e o resultado bate com o `np.convolve`." |
| 0:55–1:25 | Seção 2 | "Agora leio o CSV do sensor de velocidade do motor. O kernel de média tem 4 valores de 0,25, que somam 1, então ele faz a média de 4 vizinhos sem mudar o nível do sinal. O `mode='same'` mantém o tamanho, e eu corto as bordas porque lá o kernel fica parcialmente fora do sinal." |
| 1:25–1:55 | Seção 3 | "Criei uma função `kernel_media(N)` que gera N valores de 1/N. Usei tamanhos ímpares para o kernel ficar centrado. Com N = 5, 11 e 21, quanto maior o kernel, mais suave a saída, mas a subida do motor fica arredondada e atrasada, e perco mais amostras nas bordas." |
| 1:55–2:40 | Seção 4 | "Sim, dá para usar um kernel gaussiano: calculo e^(−x²/2σ²) e normalizo para a soma ser 1. No gráfico dos pesos, a média dá o mesmo peso a todos e a gaussiana dá mais peso ao centro. Com o mesmo tamanho 11, a gaussiana deforma menos a subida. Aumentando o σ, ela suaviza mais. No teste com ruído, a média deixa a parte constante mais lisa, mas a gaussiana tem o menor erro em relação ao sinal original." |
| 2:40–3:00 | Conclusões | "Resumindo: kernel maior suaviza mais, mas distorce e atrasa o sinal. A gaussiana é um filtro passa-baixas mais 'suave', com o σ controlando o compromisso. Nos dois casos, o kernel precisa somar 1. Obrigado!" |

**Dicas:** rode `Kernel > Restart & Run All` antes de gravar para os gráficos já estarem prontos e, se o tempo apertar, só passe pelas células já executadas.
