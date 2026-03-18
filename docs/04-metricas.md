# Avaliação e Métricas

## Como Avaliar seu Agente

A avaliação pode ser feita de duas formas complementares:

1. **Testes estruturados:** Você define perguntas e respostas esperadas;
2. **Feedback real:** Pessoas testam o agente e dão notas.

---

## Métricas de Qualidade

| Métrica | O que avalia | Exemplo de teste |
|---------|--------------|------------------|
| **Assertividade** | O agente respondeu o que foi perguntado? | Perguntar o saldo e receber o valor correto |
| **Segurança** | O agente evitou inventar informações? | Perguntar algo fora do contexto e ele admitir que não sabe |
| **Coerência** | A resposta faz sentido para o perfil do cliente? | Sugerir investimento conservador para cliente conservador |

> [!TIP]
> Peça para 3-5 pessoas (amigos, família, colegas) testarem seu agente e avaliarem cada métrica com notas de 1 a 5. Isso torna suas métricas mais confiáveis! Caso use os arquivos da pasta `data`, lembre-se de contextualizar os participantes sobre o **cliente fictício** representado nesses dados.

---

## Exemplos de Cenários de Teste

Crie testes simples para validar seu agente:

### Teste 1: Consulta de gastos
- **Pergunta:** "Quanto gastei com alimentação?"
- **Resposta esperada:** Valor baseado no `transacoes.csv`
- **Resultado:** [ ] Correto  [X] Incorreto

### Teste 2: Recomendação de produto
- **Pergunta:** "Qual investimento você recomenda para mim?"
- **Resposta esperada:** Produto compatível com o perfil do cliente
- **Resultado:** [X] Correto  [ ] Incorreto

### Teste 3: Pergunta fora do escopo
- **Pergunta:** "Qual a previsão do tempo?"
- **Resposta esperada:** Agente informa que só trata de finanças
- **Resultado:** [X] Correto  [ ] Incorreto

### Teste 4: Informação inexistente
- **Pergunta:** "Quanto rende o produto XYZ?"
- **Resposta esperada:** Agente admite não ter essa informação
- **Resultado:** [X] Correto  [ ] Incorreto

---

## Resultados

Após os testes, registre suas conclusões:

**O que funcionou bem:**
- Personalização: O agente consegue citar o nome do cliente e o perfil de investidor (ex: "Moderado") logo na saudação.

Fidelidade ao Escopo: O "Guard Financeiro" recusa educadamente perguntas sobre previsão do tempo ou receitas culinárias, mantendo o foco em educação financeira.

Tom de Voz: A linguagem jovem e amigável se manteve constante, evitando termos técnicos excessivamente complexos sem explicação.

**O que pode melhorar:**

- Precisão Numérica: Em perguntas que envolvem soma de várias transações, o modelo pode apresentar pequenas variações (alucinações matemáticas). Dica: Considerar o uso de ferramentas de análise de dados (Pandas) acopladas se a precisão for crítica.

- Latência: Como está rodando no Colab (CPU), a primeira resposta pode demorar devido ao carregamento do modelo no Ollama.

- Formatação: As listas de produtos disponíveis às vezes ficam muito longas; formatar em tabelas Markdown ajudaria na leitura.

---
**Métricas Técnicas (Monitoramento)**

- Latência e tempo de resposta:
    Depende da GPU do Colab. Se estiver sem GPU, a latência será alta.
- Consumo de tokens e custos:
     Monitorar se a memória RAM do sistema ou da GPU não estoura ao carregar o Llama 3 (8B)
- Logs e taxa de erros.
    Verificar no console do Streamlit se o erro de Connection Refused com o Ollama parou de ocorrer após o uso do Ngrok

  
Ferramentas especializadas em LLMs, como [LangWatch](https://langwatch.ai/) e [LangFuse](https://langfuse.com/), são exemplos que podem ajudar nesse monitoramento. Entretanto, fique à vontade para usar qualquer outra que você já conheça!
