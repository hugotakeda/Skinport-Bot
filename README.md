
# Skinport Bot🎯

Este é um bot de Discord robusto desenvolvido em Python para monitorar o marketplace da **Skinport**. O objetivo principal é notificar usuários sobre oportunidades de "sniping" de skins de CS2, utilizando filtros personalizados de preço e *float*.

## ✨ Funcionalidades

* **Monitoramento Automático**: O bot verifica a API da Skinport a cada 6 minutos em busca de novos itens.
* **Filtros Avançados**: Permite definir limites de preço máximo (em BRL) e valor de *float* (desgaste) para cada skin.
* **Comandos Slash (/)**: Integração total com comandos modernos do Discord para facilitar o gerenciamento da lista de desejos.
* **Bypass de Proteção**: Utiliza a biblioteca `cloudscraper` para emular um navegador real e evitar bloqueios de Cloudflare.
* **Banco de Dados Local**: Armazenamento persistente usando SQLite para que sua lista de monitoramento não seja perdida ao reiniciar o bot.

## 🛠️ Tecnologias Utilizadas

* **Linguagem**: [Python](https://www.python.org/)
* 
**Biblioteca do Bot**: `discord.py` 


* **Web Scraping/API**: `cloudscraper`, `brotli`
* **Banco de Dados**: `sqlite3`

## 🚀 Como Configurar

### 1. Pré-requisitos

Certifique-se de ter o Python instalado e as dependências necessárias:

```bash
pip install -r requirements.txt

```

### 2. Configuração das Credenciais

No arquivo `main.py`, preencha as seguintes variáveis:

* `TOKEN`: O token do seu bot no Discord Developer Portal.
* `ID_CANAL`: O ID do canal onde as ofertas serão postadas.
* `CLIENT_ID` e `API_SECRET`: Suas chaves de API da Skinport.
* `COOKIE_REAL`: O valor do cookie `cf_clearance` obtido no seu navegador para validação do scraper.

### 3. Execução

Inicie o bot executando:

```bash
python main.py

```

## 🎮 Comandos Disponíveis

| Comando | Descrição |
| --- | --- |
| `/adicionar` | Adiciona uma nova skin para monitorar (Nome, Preço Máx, Float Máx). |
| `/lista` | Exibe todos os itens que estão sendo monitorados no momento. |
| `/remover` | Remove um item da lista de monitoramento com base na posição. |

## ⚠️ Avisos Importantes

* **Segurança de API**: Nunca compartilhe seu `API_SECRET` ou seu `COOKIE` publicamente.
* **Limites da API**: O bot está configurado com um intervalo de 6 minutos para evitar *rate limiting* excessivo.
* **Configuração de User-Agent**: O bot emula um sistema macOS (Darwin) para garantir maior compatibilidade com os filtros da Skinport.
