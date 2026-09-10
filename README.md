La Casa Fest

Site institucional desenvolvido como projeto final do curso de Web Design Front End do SENAI Frederico Jacob.

O projeto apresenta a La Casa Fest, um espaço voltado para eventos e locações, com foco em uma experiência visual moderna, navegação simples e apresentação dos serviços, estrutura e possibilidades do espaço.

✨ Sobre o projeto

O site foi desenvolvido para funcionar como uma vitrine digital da La Casa Fest. A proposta combina um visual elegante com recursos interativos para apresentar o espaço e facilitar o contato de pessoas interessadas em realizar eventos.

Entre os principais recursos estão:

Página inicial com apresentação da La Casa Fest;

Seção de locações e informações sobre o espaço;

Página de programação;

Galeria com imagens e vídeos;

Carrossel de conteúdo com movimento contínuo;

Animações de entrada durante a rolagem da página;

Formulário para solicitação de orçamento;

Validação de dados no formulário;

Máscara para telefone;

Consulta de datas já reservadas através de API;

Integração do formulário com uma API de orçamentos;

Geração de link para contato via WhatsApp após o envio;

Tratamento de erros e respostas da API.

🛠️ Tecnologias utilizadas

Front-end

HTML5 — estrutura e organização das páginas;

CSS3 — estilização, layout, tipografia, animações e efeitos visuais;

JavaScript — interações, validações, carrossel, animações e integração com API.

Integração

O formulário de orçamento utiliza JavaScript com Fetch API para se comunicar com um back-end externo.

A aplicação realiza:

GET  /api/orcamentos/datas-bloqueadas
POST /api/orcamentos

A consulta GET permite verificar datas que já possuem reservas.

O POST envia os dados preenchidos pelo usuário para a API.

📁 Estrutura do projeto

SiteLaCasaFest/
│
├── index.html
├── programacao.html
├── locacoes.html
├── formulario.html
├── style.css
│
├── script/
│   ├── carrossel.js
│   ├── formulario.js
│   ├── orcamento-api.js
│   ├── programacao.js
│   └── reveal.js
│
├── imagens/
│   ├── logoLaCasa.png
│   ├── ... imagens do projeto
│   └── ... vídeos
│
└── midia/
    └── ... vídeos utilizados no site

🎞️ Carrossel infinito

O arquivo script/carrossel.js controla o carrossel de conteúdos da página.

Ele foi desenvolvido para manter o movimento contínuo dos cards, criando um efeito de rolagem infinita.

O script também trabalha com:

Clonagem automática dos cards;

Cálculo do tamanho do ciclo;

Movimento usando requestAnimationFrame;

Arraste com mouse ou ponteiro;

Pausa durante interação;

Prevenção de clique acidental após arrastar;

Reprodução otimizada dos vídeos visíveis;

Lazy loading de conteúdo de mídia.

A velocidade principal do carrossel pode ser ajustada diretamente no JavaScript:

const VELOCIDADE = 40;
const SENTIDO = -1;

✨ Animações de entrada

O arquivo script/reveal.js utiliza IntersectionObserver para identificar quando elementos entram na área visível da página.

Quando isso acontece, a classe:

.is-visible

é adicionada ao elemento.

O sistema suporta diferentes classes de animação:

.reveal
.reveal-left
.reveal-right
.reveal-scale

Isso permite criar efeitos de entrada sem precisar controlar manualmente a animação durante o scroll.

📝 Formulário de orçamento

O formulário coleta informações necessárias para uma solicitação de orçamento, como:

Nome;

Telefone;

Tipo de evento;

Data do evento;

Quantidade de convidados;

Mensagem adicional.

Antes do envio, o JavaScript realiza validações básicas, incluindo:

Campos obrigatórios;

Quantidade mínima de convidados;

Data não pode estar no passado;

Verificação de datas já reservadas;

Validação do telefone.

Durante o envio, o botão é desabilitado e apresenta o estado de carregamento.

Em caso de sucesso, o formulário é ocultado e uma tela de confirmação é exibida, podendo disponibilizar um link para contato via WhatsApp.

🔌 Comunicação com a API

A integração é feita utilizando fetch().

Exemplo simplificado:

const res = await fetch(API_BASE, {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify(payload)
});

O código também trata diferentes respostas do servidor, incluindo:

400 — dados inválidos;

409 — data já reservada;

429 — excesso de solicitações;

Outros erros de comunicação ou servidor.

Atualmente, a integração pública utiliza a API configurada em:

const API_BASE = "https://backend-olfs.onrender.com/api/orcamentos";

🎨 Design

O projeto utiliza uma identidade visual voltada para eventos e entretenimento, combinando:

Tipografia de destaque;

Contrastes fortes;

Elementos dourados;

Fundo escuro;

Imagens e vídeos para destacar o espaço;

Microinterações e animações.

O CSS central do projeto está no arquivo:

style.css

🚀 Como executar

Por ser um projeto front-end, os arquivos podem ser executados localmente utilizando um servidor web.

Uma opção simples é utilizar a extensão Live Server no VS Code.

Clone o repositório;

Abra a pasta no VS Code;

Inicie um servidor local;

Abra index.html.

O formulário de orçamento depende da API configurada em script/formulario.js. Caso a API não esteja disponível, as funções que dependem do back-end não funcionarão corretamente.

📌 Observações

O projeto contém uma integração front-end com uma API externa para gerenciamento das solicitações de orçamento e consulta de datas reservadas.

A estrutura foi organizada separando:

Estrutura (HTML);

Estilos (CSS);

Comportamentos e integrações (JavaScript);

Imagens e vídeos (imagens/ e midia/).

👨‍💻 Autores

Ítalo Moreno

Projeto desenvolvido como trabalho final do curso de Web Design Front End — SENAI Frederico Jacob.

⭐ Se este projeto foi útil ou interessante para você, considere deixar uma estrela no repositório.
