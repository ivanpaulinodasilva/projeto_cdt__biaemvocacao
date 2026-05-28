# 🍔 Hamburgueria Rosana - Cardápio Digital & Painel Administrativo

Um aplicativo web moderno e completo para gerenciar o cardápio, pedidos e o controle interno da Hamburgueria Rosana, desenvolvido de forma leve usando Flask (Python) e JavaScript puro (Vanilla JS).

## 📋 Características

- ✅ **Página Inicial:** Apresentação da identidade visual da hamburgueria e benefícios ao cliente.
- ✅ **Cardápio Dinâmico:** Listagem em grelha responsiva com 9 produtos alimentados via API.
- ✅ **Carrinho de Compras Flutuante:** Adição dinâmica, cálculo automático e modal interativo.
- ✅ **Sistema de Pedidos:** Geração automática de ID único alfanumérico com registro de timestamp.
- ✅ **Painel Admin Interno:** Página secreta (`/admin`) com tabela estruturada para gerenciamento dos pedidos.
- ✅ **Exportador de Dados:** Botão integrado para descarregar o histórico de pedidos num ficheiro estruturado em JSON.
- ✅ **Design Responsivo:** Totalmente otimizado para ecrãs de telemóveis, tablets e computadores.
- ✅ **API RESTful:** Rotas rápidas para comunicação assíncrona entre o cliente e o servidor.

## 📁 Estrutura do Projeto

```text
hamburgueria-rosana/
├── app.py                  # Servidor Backend Flask (Rotas e API em memória)
├── requirements.txt        # Dependências do Python (Flask e Gunicorn)
├── README.md               # Documentação do projeto
├── templates/              # Páginas de visualização (HTML)
│   ├── index.html          # Página inicial institucional
│   ├── menu.html           # Página de pedidos do cliente (Cardápio)
│   ├── admin.html          # Painel de controlo da administração 🆕
│   ├── 404.html            # Tratamento customizado de página não encontrada
│   └── 500.html            # Tratamento customizado de erro interno
└── static/                 # Arquivos de estilização e lógica do navegador
    ├── style.css           # CSS Global unificado (Cores da identidade e tabelas)
    └── script.js           # Engine JS (Carrinho, Checkout, Admin e Exportar)

```

## 🔌 API Endpoints

### 🌐 Páginas (HTML)

* **GET `/**` - Página inicial.
* **GET `/menu**` - Cardápio digital do cliente.
* **GET `/admin**` - Painel do administrador para monitorar os pedidos de hoje.

### ⚙️ Dados (JSON)

* **GET `/api/menu**` - Retorna todos os hambúrgueres, preços e imagens.
* **GET `/api/orders**` - Retorna o histórico de pedidos feitos na sessão.
* **POST `/api/checkout**` - Envia o carrinho para o servidor e cria o pedido com ID alfanumérico.
* **GET `/api/health**` - Diagnóstico simples de conectividade do servidor.

---

## 🚀 Como Usar Localmente

### 1. Clonar o repositório

```bash
git clone [https://github.com/seu-usuario/hamburgueria-rosana.git](https://github.com/seu-usuario/hamburgueria-rosana.git)
cd hamburgueria-rosana

```

### 2. Criar e Ativar Ambiente Virtual (Opcional, mas recomendado)

**Windows:**

```bash
python -m venv venv
venv\Scripts\activate

```

**macOS/Linux:**

```bash
python3 -m venv venv
source venv/bin/activate

```

### 3. Instalar dependências

```bash
pip install -r requirements.txt

```

### 4. Executar o servidor Flask

```bash
python app.py

```

> ⚠️ **Atenção:** Certifica-te de aceder utilizando a porta nativa do Flask **`:5000`** e evite o Live Server do VS Code (porta `:5500`) para não quebrar as requisições do Python.

* 🍔 **Cardápio do cliente:** `http://localhost:5000`
* ⚙️ **Painel Administrativo:** `http://localhost:5000/admin` (Também acessível pelo link no rodapé).

---

## 🎨 Identidade Visual e Design

* **Paleta de Cores:** Laranja Vibrante (`#ff6b35`), Castanho Escuro (`#5c3d2e`), Bege Claro (`#f5f1e8`) e Branco Puro (`#ffffff`).
* **Tabela Administrativa:** Cantos arredondados, realce de linhas (*hover*), colunas identificadoras destacadas e crachás de status (*badges*) coloridos.

---

## 🚀 Como Fazer o Deploy no Render

Por utilizar armazenamento estruturado em listas de memória do Python (`orders = []`), este projeto é **altamente recomendado para ser hospedado no Render**, uma vez que serviços Serverless (como a Vercel) resetam a memória da aplicação instantaneamente após cada clique.

### 1. Preparar o repositório

Garante que o arquivo `requirements.txt` está atualizado com o servidor de produção:

```text
Flask==3.0.2
gunicorn==21.2.0

```

Faz o envio (*push*) de todos os arquivos atualizados para o teu repositório no GitHub.

### 2. Configurar o Web Service no Render

1. Cria ou faz login na tua conta em [render.com](https://render.com).
2. No painel de controle, clica em **New** > **Web Service**.
3. Conecta com a tua conta do GitHub e escolhe o repositório do projeto.
4. Preenche as configurações da seguinte maneira:
* **Name:** `hamburgueria-rosana`
* **Environment:** `Python`
* **Build Command:** `pip install -r requirements.txt`
* **Start Command:** `gunicorn app:app`


5. Clica em **Deploy Web Service** no fim da página.

Pronto! O Render irá criar uma URL pública gratuita (ex: `https://hamburgueria-rosana.onrender.com`) onde o site estará 100% funcional.

---

## 📝 Licença

Este projeto está sob a licença MIT. Veja o arquivo LICENSE para mais detalhes.

**Feito com ❤️ para os amantes de hambúrgueres da Hamburgueria Rosana** 🍔

