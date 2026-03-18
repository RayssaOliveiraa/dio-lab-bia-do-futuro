---


# 🎓 Guard Financeiro: Seu Educador Financeiro com IA

O **Guard Financeiro** é um agente inteligente especializado em educação financeira. Ele utiliza modelos de linguagem de código aberto (LLMs) para analisar dados reais de perfil de investimento,
transações e histórico de atendimento, oferecendo ensinamentos didáticos e personalizados.
```markdown
---

## 🚀 Passo a Passo de Execução

### 1. Setup do Ollama
Para rodar a inteligência artificial localmente, siga estes comandos no seu terminal:

```bash
# 1. Instalar o Ollama (acesse ollama.com)

# 2. Baixar o modelo leve configurado
ollama pull gpt-oss

# 3. Testar se o modelo está respondendo
ollama run gpt-oss "Olá!"
```

### 2. Código Completo
Todo o código-fonte lógico, interface e integração está concentrado no arquivo `app.py`. A aplicação utiliza **Streamlit** para a interface, **Pandas** para manipulação de dados e **Requests** para comunicação com a API do Ollama.

### 3. Como Rodar Localmente
```bash
# 1. Instalar as dependências necessárias
pip install streamlit pandas requests

# 2. Garantir que o servidor Ollama está rodando em segundo plano
ollama serve

# 3. Rodar o app
streamlit run app.py
```

---

## 💻 Execução via Google Colab (Recomendado)

Devido a **limitações de hardware** (modelos de linguagem exigem alta capacidade de memória VRAM e processamento), este projeto foi adaptado para rodar na infraestrutura de nuvem da Google, garantindo performance e acessibilidade gratuita a GPUs.

### 🔗 Link do Projeto no Colab
[Acesse o Notebook do Guard Financeiro aqui](https://colab.research.google.com/drive/13jBd4OLbpMmgrAFASTzxwJSmIBkcQyqZ?usp=sharing)

### ⚠️ Importante: Persistência de Dados no Colab
O ambiente do Google Colab é **efêmero (temporário)**.
Isso significa que toda vez que a sessão é encerrada ou a página é reiniciada, os arquivos salvos no disco local são apagados, com isso é necessario criar as pastas e adicionar os arquivos.

**Por que criar as pastas `data` e `src`?**

O código busca informações específicas nesses diretórios. Sem eles, o agente não terá contexto.

1. **Crie as pastas:** Certifique-se de criar `data` e `src` no menu lateral.
   
3. **Upload:** Adicione os arquivos JSON e CSV na pasta `data` para que o agente funcione com seus dados reais.
   <img width="482" height="601" alt="image" src="https://github.com/user-attachments/assets/409d6296-9d5c-4362-bd4d-acedc5edb0e0" />
4. **Codigo app.py: ** é criado o arquivo automaticamente quando usado na celula 3.
   <img width="395" height="593" alt="image" src="https://github.com/user-attachments/assets/d006f550-03fc-4afe-a70f-d01dc21d59e8" />
   <img width="1547" height="299" alt="image" src="https://github.com/user-attachments/assets/25ac45b2-2ec8-4b3a-a19f-0e3654f28c0e" />

    



### 🛠️ O que é e como funciona o Ngrok?
O Colab protege suas portas internas por segurança. Para que você consiga acessar a interface do Streamlit no seu navegador, usamos o **Ngrok**.
* Ele cria um **túnel reverso seguro**, gerando um link público que "aponta" para o servidor rodando dentro do Colab.
  
* **O que fazer:** Insira seu `Authtoken` gratuito (obtido em ngrok.com) na célula correspondente e clique no link gerado.

---

## 📂 Estrutura de Arquivos (`./data/`)
O agente baseia seus ensinamentos nos seguintes arquivos:
* `perfil_investidor.json`: Dados demográficos e objetivos do cliente.
* `transacoes.csv`: Histórico de movimentações financeiras.
* `historico_atendimento.csv`: Registro de interações anteriores.
* `produtos_financeiros.json`: Catálogo de produtos para fins educativos.

---
## Evidencia da execução:

<img width="1066" height="839" alt="image" src="https://github.com/user-attachments/assets/746b494d-d3a4-41da-ac09-28cd974127c9" />
