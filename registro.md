# Terasteel Bookstore - Sistema de Livraria Online

## Visão Geral

O Terasteel Bookstore é uma aplicação web completa para gerenciamento de livraria online, desenvolvida com arquitetura cliente-servidor utilizando tecnologias web modernas. O sistema oferece funcionalidades de catálogo de produtos, carrinho de compras e interface administrativa para gestão de estoque.

## Arquitetura do Sistema

### Stack Tecnológico

**Frontend:**
- HTML5 com estrutura semântica
- CSS3 com Flexbox e Grid Layout
- JavaScript ES6+ (Vanilla)
- Design responsivo e acessível

**Backend:**
- Node.js (Runtime JavaScript)
- Express.js (Framework web)
- Arquitetura RESTful

**Persistência:**
- Sistema de dados em memória (desenvolvimento)
- Preparado para integração com PostgreSQL

### Padrões Arquiteturais

- **MVC (Model-View-Controller)**: Separação clara entre lógica de negócio, apresentação e controle
- **SPA (Single Page Application)**: Navegação dinâmica sem recarregamento de página
- **API REST**: Interface padronizada para comunicação cliente-servidor

## Estrutura do Projeto

```
Livraria/
├── assets/
│   └── img/
│       ├── logo.ico              # Favicon da aplicação
│       └── logo.png              # Logotipo principal
├── src/
│   ├── css/
│   │   └── styles.css            # Folhas de estilo principais
│   ├── js/
│   │   ├── script.js             # Lógica do frontend
│   │   └── server.js             # Servidor Express
│   ├── json/
│   │   ├── package.json          # Dependências do projeto
│   │   └── package-lock.json     # Lock de versões
│   └── index.html                # Interface principal
├── LICENSE                       # Licença MIT
└── registro.md                   # Documentação técnica
```

## Funcionalidades Implementadas

### 1. Catálogo de Produtos
- Exibição dinâmica de livros disponíveis
- Informações detalhadas: título, preço, descrição e estoque
- Interface responsiva com cards interativos
- Controle de disponibilidade em tempo real

### 2. Sistema de Carrinho
- Adição/remoção de itens
- Controle de quantidade com validação de estoque
- Cálculo automático de totais
- Interface lateral deslizante (sidebar)
- Persistência durante a sessão

### 3. Gestão de Estoque
- Controle automático de disponibilidade
- Validação de quantidade máxima por item
- Indicadores visuais de status do produto
- Prevenção de overselling

### 4. Interface Administrativa
- Operações CRUD para livros (em desenvolvimento)
- Formulários de cadastro e edição
- Validação de dados no frontend

## Especificações Técnicas

### Requisitos do Sistema

**Ambiente de Desenvolvimento:**
- Node.js >= 14.0.0
- npm >= 6.0.0
- Navegador moderno com suporte a ES6+

**Dependências:**
- Express.js ^5.1.0

### Configuração e Instalação

1. **Preparação do Ambiente**
   ```bash
   cd src/json
   npm install
   ```

2. **Inicialização do Servidor**
   ```bash
   cd ../js
   node server.js
   ```

3. **Acesso à Aplicação**
   - URL: `http://localhost:3000`
   - Interface: Abrir `src/index.html` em navegador

### Estrutura de Dados

**Modelo de Livro:**
```javascript
{
  id: Number,           // Identificador único
  nome: String,         // Título do livro
  preco: Number,        // Preço em formato decimal
  descricao: String,    // Descrição detalhada
  estoque: Number       // Quantidade disponível
}
```

**Modelo de Item do Carrinho:**
```javascript
{
  ...livro,            // Herda propriedades do livro
  quantity: Number     // Quantidade selecionada
}
```

## Fluxos de Funcionamento

### 1. Carregamento da Aplicação
1. Inicialização do DOM
2. Configuração de event listeners
3. Carregamento assíncrono do catálogo
4. Renderização da interface inicial

### 2. Gestão do Carrinho
1. Seleção de produto no catálogo
2. Validação de disponibilidade
3. Atualização do estado do carrinho
4. Recálculo de totais
5. Atualização da interface

### 3. Finalização de Compra
1. Validação do carrinho não vazio
2. Cálculo do total final
3. Simulação de processamento
4. Limpeza do carrinho
5. Feedback ao usuário

## Padrões de Código

### JavaScript
- Uso de async/await para operações assíncronas
- Funções puras quando possível
- Nomenclatura descritiva em camelCase
- Tratamento adequado de erros
- Separação de responsabilidades

### CSS
- Metodologia BEM para nomenclatura de classes
- Variáveis CSS para consistência visual
- Mobile-first responsive design
- Flexbox e Grid para layouts

### HTML
- Estrutura semântica
- Acessibilidade (ARIA labels)
- Meta tags apropriadas
- Otimização para SEO

## Segurança e Boas Práticas

### Frontend
- Validação de entrada no cliente
- Sanitização de dados exibidos
- Prevenção de XSS através de innerHTML controlado
- Uso de HTTPS em produção (recomendado)

### Backend
- Middleware de parsing JSON
- Estrutura preparada para autenticação
- Rotas organizadas por domínio
- Tratamento de erros centralizado

## Limitações Atuais

1. **Persistência**: Dados armazenados apenas em memória
2. **Autenticação**: Sistema de usuários não implementado
3. **Pagamentos**: Simulação básica de checkout
4. **Validação**: Validação apenas no frontend
5. **Escalabilidade**: Arquitetura monolítica

## Roadmap de Desenvolvimento

### Fase 1 - Infraestrutura
- [ ] Integração com banco de dados PostgreSQL
- [ ] Sistema de autenticação JWT
- [ ] Middleware de validação no backend
- [ ] Tratamento robusto de erros

### Fase 2 - Funcionalidades
- [ ] Sistema completo de usuários
- [ ] Histórico de pedidos
- [ ] Sistema de busca e filtros
- [ ] Upload de imagens de produtos

### Fase 3 - Otimização
- [ ] Cache de dados
- [ ] Otimização de performance
- [ ] Testes automatizados
- [ ] Monitoramento e logs

### Fase 4 - Expansão
- [ ] API para aplicações móveis
- [ ] Sistema de avaliações
- [ ] Integração com gateways de pagamento
- [ ] Notificações em tempo real

## Licenciamento

Este projeto está licenciado sob a Licença MIT. Consulte o arquivo LICENSE para detalhes completos sobre direitos de uso, modificação e distribuição.

**Copyright (c) 2025 Adriana Balon**

## Contribuição e Desenvolvimento

### Ambiente de Desenvolvimento
1. Fork do repositório
2. Criação de branch para feature
3. Implementação com testes
4. Pull request com descrição detalhada

### Padrões de Commit
- Mensagens descritivas em português
- Commits atômicos por funcionalidade
- Referência a issues quando aplicável

### Estrutura de Testes
- Testes unitários para funções puras
- Testes de integração para fluxos completos
- Testes de interface para componentes visuais

---

**Documentação técnica - Terasteel Bookstore v1.0.0**  
*Última atualização: Janeiro 2025*
