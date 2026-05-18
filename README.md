Motor de Busca Semântica com Sentence-Transformers ,

Este projeto implementa um motor de busca semântica em Python capaz de receber consultas (queries) em texto livre e retornar os artigos mais relevantes de um corpus de notícias econômicas de 2023. O sistema utiliza representações numéricas de texto (embeddings) para calcular a proximidade conceitual entre a busca do usuário e o conteúdo dos artigos.

Decisões de Projeto,

Modelo Utilizado: paraphrase-multilingual-MiniLM-L12-v2.

É um modelo de NLP altamente eficiente, leve e treinado para tarefas multilíngues . Ele é ideal para ambientes de desenvolvimento locais porque gera vetores densos de 384 dimensões, equilibrando performance semântica com baixo consumo de memória e processamento rápido na CPU.,

Estratégia de Entrada: Concatenação (Título + Conteúdo).

Em vez de vetorizar apenas o título ou apenas o corpo do texto, o script combina ambos no formato: \"Título: \[Título\]. Conteúdo: \[Texto\]\". Isso garante que o modelo capture tanto o resumo de alto impacto (título) quanto os detalhes contextuais (corpo), gerando embeddings mais precisos para a busca.,

Métrica de Proximidade: Similaridade de Cosseno (util.cos_sim).

Para determinar a relevância, utilizei a Similaridade de Cosseno operando diretamente sobre tensores do PyTorch. Esta métrica mede o ângulo entre os vetores no espaço multidimensional, ignorando a diferença no tamanho dos textos e focando estritamente na equivalência do significado.

Como Rodar o Projeto,

Utilizei os passos abaixo no terminal do VS Code Studio utilizando o sistema operacional Linux:

Clonar ou Acessar a Pasta do Projeto,

Abra o terminal na pasta do projeto e inicie o VS Code:

bash cd caminho/para/projeto.

code .

Conclusão da Avaliação.

​O sistema demonstrou robustez e imunidade a variações de vocabulário, provando ser uma fundação sólida para sistemas de recomendação de notícias, assistentes virtuais financeiros ou ferramentas inteligentes de clipping de imprensa.
