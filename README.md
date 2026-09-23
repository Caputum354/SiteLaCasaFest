# La Casa Fest

Site institucional desenvolvido como projeto final do curso de Web Design Front End do SENAI Frederico Jacob, com foco na apresentação de um espaço para eventos, locações e experiências culturais em Ferraz de Vasconcelos, SP.

O projeto foi pensado como uma vitrine digital profissional para a La Casa Fest, combinando identidade visual premium, navegação intuitiva, elementos interativos e comunicação direta com clientes por meio de formulários e WhatsApp.

## Visão geral

A La Casa Fest é um espaço voltado para experiências de lazer, celebrações e eventos. O site foi criado para transmitir essa proposta de forma moderna e envolvente, permitindo que visitantes:

- conheçam a casa e o ambiente;
- vejam a programação e os momentos realizados no espaço;
- entendam as possibilidades de locação para festas e eventos;
- solicitem orçamento diretamente pela web;
- entrem em contato rapidamente pelo WhatsApp.

## Objetivo do projeto

O principal objetivo foi desenvolver um site comercial e visualmente impactante, com foco em:

- branding e apresentação do espaço;
- experiência de navegação em múltiplas páginas;
- storytelling do ambiente e da atmosfera da casa;
- geração de leads por meio de formulário de orçamento;
- uso de recursos visuais e interativos para reforçar a proposta da marca.

## Funcionalidades principais

### 1. Página inicial
A home apresenta a identidade da marca com:

- vídeo de destaque em hero section;
- navegação principal para programação, locações e orçamento;
- blocos de apresentação do espaço e dos tipos de experiência;
- galeria estilo feed com vídeos e carrossel;
- links para redes sociais e contato.

### 2. Página de programação
A página de programação comunica o clima da casa e mostra o tipo de experiência oferecida, com destaque para:

- eventos e encontros musicais;
- resenhas e momentos especiais;
- identidade e ambiente da marca;
- navegação para outras páginas do site.

### 3. Página de locações
Essa área explica como o espaço funciona para eventos privados e sociais, com foco em:

- organização do processo de locação;
- apresentação dos momentos de festa (dia e noite);
- comunicação clara de como reservar e contratar o espaço;
- integração com a página de orçamento.

### 4. Formulário de orçamento
O formulário foi pensado para captar oportunidades de negócio diretamente do site. Ele coleta:

- nome do cliente;
- telefone/WhatsApp;
- tipo de evento;
- quantidade de convidados;
- data do evento;
- mensagem complementar.

Além disso, o front-end valida:

- campos obrigatórios;
- quantidade mínima de convidados;
- data não pode estar no passado;
- telefone em formato válido;
- bloqueio de datas já reservadas;
- mensagens e respostas de erro amigáveis.

### 5. Integração de dados e marcação de datas
O projeto inclui integração com API externa para:

- consultar datas bloqueadas;
- enviar orçamento para backend;
- impedir reservas duplicadas;
- devolver resposta ao cliente com feedback visual.

### 6. Carrossel e interações visuais
O site utiliza JavaScript para criar experiência dinâmica, com:

- carrossel infinito de conteúdo;
- reprodução automática de vídeos visíveis;
- lazy loading para otimizar performance;
- arraste com mouse e interação manual;
- animações ao rolar a página;
- reveals com IntersectionObserver.

## Tecnologias utilizadas

### Front-end
- HTML5 — estrutura das páginas e semântica do conteúdo;
- CSS3 — layout, responsividade, tipografia, paleta visual, microinterações e animações;
- JavaScript — interações, validações, carrossel, efeitos e integrações.

### Integrações
- Fetch API — comunicação com backend para envio e consulta de dados;
- API externa para orçamentos e datas bloqueadas.

## Estrutura do projeto

```text
SiteLaCasaFest/
├── index.html
├── programacao.html
├── locacoes.html
├── formulario.html
├── style.css
├── script/
│   ├── carrossel.js
│   ├── formulario.js
│   ├── orcamento-api.js
│   ├── programacao.js
│   └── reveal.js
├── imagens/
│   ├── logo e ícones da marca
│   ├── imagens do espaço
│   └── conteúdos visuais do projeto
├── midia/
│   └── vídeos e animações utilizados na interface
├── README.md
└── ...
```

## Arquivos principais

### `index.html`
Página inicial do site, com hero, navegação, galeria e apresentação visual da marca.

### `programacao.html`
Página dedicada à programação e ao clima do espaço.

### `locacoes.html`
Apresenta as possibilidades de locação do ambiente e os momentos de uso.

### `formulario.html`
Formulário de orçamento com interface de coleta de dados e resposta visual.

### `style.css`
Arquivo central de estilos do site, com a identidade visual, responsividade e componentes do layout.

### `script/carrossel.js`
Controla o carrossel de conteúdo e as interações de mídia, incluindo comportamento infinito.

### `script/reveal.js`
Aplica animações de entrada conforme os elementos entram na área visível da página.

### `script/formulario.js`
Gerencia validações do formulário, máscara de telefone, bloqueio de datas e envio de dados.

### `script/orcamento-api.js`
Arquivo de integração com a API do orçamento, incluindo consulta de datas reservadas e envio do pedido.

### `script/programacao.js`
Script relacionado à página de programação e interações da área de agenda.

## Fluxo de funcionamento do formulário

1. O usuário acessa a página de orçamento.
2. Preenche nome, telefone, tipo de evento, convidados, data e mensagem.
3. O front-end valida as informações localmente.
4. O sistema consulta as datas bloqueadas na API.
5. Caso a data esteja disponível, o formulário é enviado.
6. O backend responde com sucesso ou erro.
7. Em caso de sucesso, o usuário recebe confirmação visual e um link para WhatsApp.

## API utilizada

O projeto utiliza uma integração com backend para orçamentos e datas bloqueadas. Em termos funcionais, o front-end realiza:

- GET para consultar datas já reservadas;
- POST para enviar uma solicitação de orçamento.

Exemplo da lógica de comunicação:

```javascript
const res = await fetch(API_BASE, {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify(payload)
});
```

A aplicação também trata cenários como:

- 400 — dados inválidos;
- 409 — data já reservada;
- 429 — excesso de requisições;
- falhas gerais de conexão ou servidor.

## Como executar localmente

Como é um projeto front-end, o site pode ser executado em qualquer servidor local simples.

### Opção recomendada: VS Code + Live Server

1. Clone o repositório.
2. Abra a pasta no VS Code.
3. Inicie o projeto com Live Server ou outro servidor local.
4. Acesse a página inicial em `index.html`.

### Observação importante

O formulário de orçamento depende da disponibilidade da API externa configurada no projeto. Se a API estiver indisponível, as funções de consulta de datas e envio de solicitações podem falhar.

## Design e identidade visual

O projeto possui uma identidade visual marcante, com:

- fundo escuro para valorizar elementos luminosos;
- tipografia forte e impactante;
- contraste entre elementos dourados, claros e escuros;
- uso de vídeo, imagens e mídia para reforçar a atmosfera do evento;
- layout pensado para transmitir luxo, energia e experiências memoráveis.

## Diferenciais do projeto

- interface comercial e profissional;
- experiência visual moderna e envolvente;
- arquitetura organizada em HTML, CSS e JavaScript;
- foco em conversão para reservas e contato;
- presença digital forte para marca e espaço de eventos.

## Status

Projeto finalizado como entrega acadêmica, com foco em apresentação visual, usabilidade e comunicação comercial do espaço La Casa Fest.

## Créditos

Projeto desenvolvido por:

- Ítalo Moreno
- Kaio Oliveira
- Juan Carlos
- Gabriel Soares
- Jeferson Junior
- Isaac Peres

Trabalho final do curso de Web Design Front End — SENAI Frederico Jacob.

## Observação final

Este repositório representa mais do que um site estático: é um projeto de branding digital, apresentação de espaço e conversão de leads para um negócio de eventos. O conjunto de páginas, recursos visuais e integrações foi pensado para entregar uma experiência profissional e funcional para clientes e visitantes.
