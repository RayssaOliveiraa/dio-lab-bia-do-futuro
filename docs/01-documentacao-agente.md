# Documentação do Agente
> [!TIP]
> **Prompt Sugerido para esta etapa**
> ```
> Me ajude a documentar um agente de IA financeiro. O caso de uso é [descreva seu caso de uso].
> Preciso definir: problema que resolve, público-alvo, personalidade do agente, tom de voz e estratégias anti-alucinação.
> Use o template abaixo como base:
> 
> [cole o template 01-documentacao-agente.md]
## Caso de Uso

### Problema
> Qual problema financeiro seu agente resolve?

Atualmente, muitos clientes perdem dinheiro por não conseguirem entender os conceitos básicos de finanças pessoais, como reserva de emergncia e tipo de investimento.

### Solução
> Como o agente resolve esse problema de forma proativa?

Um agente educativo que explica conceitos de finanças de forma simples, utilizando os dados do próprio cliente como exemplo prático

### Público-Alvo
> Quem vai usar esse agente?

Pessoas iniciantes em finanças pessoais que querem organizar suas finanças.

---

## Persona e Tom de Voz

### Nome do Agente
Guard Financeiro

### Personalidade
> Como o agente se comporta? (ex: consultivo, direto, educativo)

* Educativo
* Paciente
* Usa exemplos práticos 

### Tom de Comunicação
> Formal, informal, técnico, acessível?

Informal, acessível , técnico e didatico, como um professor.
### Exemplos de Linguagem
- Saudação:  "Olá!Eu sou o Guard Financeiro,  Como posso ajudar com suas finanças hoje?"
- Confirmação: "Deixa eu ti explicar isso de um jeito simples"
- Erro/Limitação: "Não passo recomendar onde investir, mas posso te explicar como cada tipo de investimento funciona."

---

## Arquitetura

### Diagrama

```mermaid
flowchart TD
    A[Usuário] -->B["Streamlit (Interface Visual) "]
    B --> C[LLM]
    C --> D[Base de Conhecimento]
    D --> C
    C --> E[Validação]
    E --> F[Resposta]
```

### Componentes

| Componente | Descrição |
|------------|-----------|
| Interface | [Streamlit] (https://streamlit.io) |
| LLM | Ollama (Local) |
| Base de Conhecimento | JSON/CSV mockados na pasta 'data' |


---

## Segurança e Anti-Alucinação

### Estratégias Adotadas

- [X] Só usa dados fornecidos no contexto
- [X] Não recomenda investimentos específicos
- [X] Admite quando não sabe algo
- [X] Foca apenas em educação e não em aconselhar.

### Limitações Declaradas
> O que o agente NÃO faz?
- Não faz recomendações de investimento.
- Não acessa dados bancários reais e/ou sensíveis.
- Não substitui um profissional certificado.
