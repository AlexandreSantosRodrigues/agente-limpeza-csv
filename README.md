# 🧹 Chega de Perder Horas Limpando Planilha. Deixa a IA Fazer Isso por Você.

> **Você carrega o arquivo. O agente limpa. O Power BI agradece.**

---

## 😤 Você conhece essa dor?

Todo projeto de dados começa da mesma forma:

1. Você recebe um `.csv` de um cliente, colega ou sistema.
2. Abre no Power BI.
3. Entra no **"Transformar Dados"**.
4. Começa a batalha:
   - Datas em 5 formatos diferentes na mesma coluna.
   - Coluna de preço com `R$`, ponto e vírgula misturados — e o Power BI não reconhece como número.
   - Coluna de peso com `"80kg"` em vez de `80`.
   - Separador de coluna errado — tudo numa célula só.
   - Células vazias escondidas no meio dos dados.

**Você resolve tudo isso na mão. Toda vez. Para cada arquivo novo.**

E o pior: no próximo projeto, você faz tudo de novo do zero.

---

## ✅ A Solução: Um Agente de IA que faz esse trabalho sujo por você

Este projeto é um **Agente Inteligente de Limpeza de Dados** que roda 100% no navegador, sem instalar nada, totalmente gratuito.

Ele combina **Python** para a limpeza pesada com **Google Gemini (IA)** para entender o que cada coluna significa — mesmo sem você explicar nada.

### O que ele resolve automaticamente:

| Problema | O que o Agente faz |
|---|---|
| Separador desconhecido (`,` `;` `TAB`) | Detecta e separa as colunas sozinho |
| Datas em formatos misturados | Padroniza tudo para `AAAA-MM-DD` |
| Preços com `R$`, `$`, pontos e vírgulas errados | Limpa os símbolos e converte para número puro |
| Números com unidades (`80kg`, `1,85m`) | Extrai apenas o valor numérico |
| Colunas que já estão certas | **Não toca.** A IA sabe quando não mexer |
| Células vazias | Mantém o vazio sem inventar dados |
| Arquivo no padrão americano indo para Power BI Brasil | Converte automaticamente na hora de salvar |

---

## 🚀 Como usar (sem instalar absolutamente nada)

**Requisito: Só uma conta Google.**

### Passo 1 — Abra o Agente no Colab
[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/AlexandreSantosRodrigues/agente-limpeza-csv/blob/main/agente_limpeza_csv.ipynb)

### Passo 2 — Gere sua chave gratuita da API
1. Acesse [aistudio.google.com](https://aistudio.google.com/)
2. Clique no ícone de chave 🔑 no menu lateral esquerdo
3. Clique em **"Create API Key"**
4. Copie o código gerado

### Passo 3 — Salve a chave no cofre do Colab
1. No Colab, clique no ícone 🔑 no menu lateral esquerdo
2. Clique em **"+ Adicionar novo secret"**
3. Nome: `GEMINI_API_KEY` | Valor: sua chave copiada
4. Ative o toggle ao lado

### Passo 4 — Aperte Play e faça o upload
Clique em ▶️ Play, selecione seu `.csv` e aguarde.

### Passo 5 — Baixe e use no Power BI
O arquivo `LIMPO_seuarquivo.csv` será baixado automaticamente, formatado no padrão brasileiro, pronto para o Power BI.

**Tempo médio: menos de 10 segundos.**

---

## 🧠 Como funciona por dentro?

```
[1] DETECTAR ──► Lê o arquivo e descobre o separador de colunas automaticamente

[2] ENTENDER ──► Envia apenas as 3 primeiras linhas para o Gemini (IA) e pergunta:
                  "O que é cada coluna? Data? Dinheiro? Número? Texto?"

[3] LIMPAR   ──► Aplica as transformações corretas em cada coluna
                  e salva no padrão Power BI Brasil (sep=';', decimal=',')
```

> 🔒 **Privacidade:** Apenas o cabeçalho e 3 linhas de amostra vão para a IA.
> O restante dos seus dados é processado localmente dentro do Colab, sem sair da sua sessão.

---

## 🔎 Verificações antes de usar o CSV gerado

Depois da limpeza, confira uma amostra do resultado antes de utilizá-lo em relatórios ou decisões:

- Compare a quantidade de linhas e colunas do arquivo original com a do CSV exportado e investigue diferenças inesperadas.
- Confira manualmente algumas datas, valores monetários, unidades convertidas e células vazias, especialmente em colunas com formatos mistos.
- Na importação para o Power BI, verifique se o delimitador de colunas é `;` (ponto e vírgula) e se os números usam vírgula como separador decimal.
- Guarde o CSV original para auditoria. Como exemplos de linhas são enviados à API de IA, não processe dados pessoais ou confidenciais sem autorização adequada.

---

## 📁 Datasets testados

| Dataset | Desafio principal | Resultado |
|---|---|---|
| 💎 Diamonds (Kaggle) | Colunas decimais no padrão americano | ✅ Convertido para padrão BR |
| 🚢 Titanic (Kaggle) | 177 células vazias na coluna `Age` | ✅ Vazios preservados |
| 📦 Logística (CSV customizado) | Mix de tipos e preços | ✅ Limpo e classificado |

---

## 🛠️ Tecnologias

- **[Google Colab](https://colab.research.google.com/)** — Ambiente de execução gratuito na nuvem
- **[Python](https://www.python.org/) + [Pandas](https://pandas.pydata.org/)** — Motor de limpeza dos dados
- **[Google Gemini API](https://aistudio.google.com/)** — IA para classificar as colunas semanticamente

---

## 👤 Autor

Feito por **Alexandre dos Santos**  
📎 [LinkedIn](https://www.linkedin.com/in/alexandresantosdata/) 

---

> *"A parte mais chata da análise de dados é limpar os dados. Agora ela é automática."*
