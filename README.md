# Melhorando a Indexação de um Site

## Índice

- [Introdução](#introdução)
- [Performance](#performance)
- [Acessibilidade](#acessibilidade)
- [SEO](#seo)
- [Boas Práticas](#boas-práticas)
- [Base de dados](#base-de-dados)

## Introdução

A indexação eficaz de um site é crucial para garantir que ele seja visível e encontrado por motores de busca. Este guia fornece estratégias para melhorar a indexação do seu site, abordando aspectos de performance, acessibilidade e boas práticas de SEO.

## Performance

Melhorar o tempo de carregamento e a eficiência do seu site pode ajudar a melhorar seu ranking nos motores de busca e a experiência do usuário.

### Técnicas de Performance

1. **Otimização de Imagens**
   - **Formatos Recomendados**: Use WebP e AVIF para tamanhos reduzidos e alta qualidade.
   - **Lazy Loading**: Carregue imagens somente quando necessário.
     
     ```html
     <img src="imagem.jpg" loading="lazy" alt="Descrição da imagem">
     ```

   - **Atributos `srcset` e `sizes`**: Fornecem diferentes versões de uma imagem para vários tamanhos de tela.
     
     ```html
     <img src="imagem-small.jpg" 
          srcset="imagem-small.jpg 480w, imagem-medium.jpg 800w, imagem-large.jpg 1200w"
          sizes="(max-width: 600px) 480px, (max-width: 1200px) 800px, 1200px"
          alt="Descrição da imagem">
     ```

   - **Fetch Priority**: Define a prioridade de carregamento da imagem.
     
     ```html
     <img src="imagem-importante.jpg" fetchpriority="high" alt="Descrição da imagem">
     ```

2. **Minificação de Recursos**
   - **CSS e JavaScript**: Minifique e combine arquivos para reduzir tamanho e solicitações.

3. **Utilização de Cache**
   - **Cache do Navegador**: Configure cabeçalhos de cache para recursos estáticos.

     ```apache
     # .htaccess
     <IfModule mod_expires.c>
       ExpiresActive On
       ExpiresDefault "access plus 1 year"
       ExpiresByType image/jpeg "access plus 1 year"
       ExpiresByType image/png "access plus 1 year"
       ExpiresByType image/gif "access plus 1 year"
       ExpiresByType text/css "access plus 1 month"
       ExpiresByType application/javascript "access plus 1 month"
     </IfModule>
     ```

4. **Otimização de Fontes**
   - **Fontes Web**: Utilize formatos modernos e evite carregar fontes desnecessárias.

     ```html
     <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap">
     ```

5. **Utilização de Content Delivery Network (CDN)**
   - **CDN**: Distribua seu conteúdo para melhorar a velocidade de carregamento global.

6. **Implementação de AMP (Accelerated Mobile Pages)**
   - **AMP**: Use para melhorar o desempenho em dispositivos móveis.
## Accelerated Mobile Pages (AMP)

O AMP (Accelerated Mobile Pages) é uma iniciativa do Google para melhorar o desempenho de páginas da web em dispositivos móveis, fornecendo uma versão mais rápida e eficiente das páginas. O objetivo é oferecer uma experiência de carregamento instantânea para os usuários móveis.

### Vantagens do AMP

- **Carregamento Rápido**: Páginas AMP carregam mais rapidamente do que páginas tradicionais, melhorando a experiência do usuário.
- **Melhor Experiência Móvel**: Otimiza a visualização em dispositivos móveis com design responsivo.
- **Maior Visibilidade**: Sites que implementam AMP podem obter uma melhor visibilidade e melhores rankings nos resultados de pesquisa do Google.

### Estrutura Básica de uma Página AMP

Uma página AMP deve seguir uma estrutura HTML específica e usar o framework AMP para garantir que seja carregada de forma otimizada. Aqui está um exemplo básico:

```html
<!doctype html>
<html ⚡>
<head>
  <meta charset="utf-8">
  <title>Título da Página</title>
  <meta name="description" content="Descrição da página.">
  <link rel="canonical" href="https://www.exemplo.com/pagina-original">
  <meta name="viewport" content="width=device-width,minimum-scale=1">
  <style amp-custom>
    /* Seus estilos CSS aqui */
  </style>
  <script async src="https://cdn.ampproject.org/v0.js"></script>
</head>
<body>
  <header>
    <h1>Seu Cabeçalho</h1>
  </header>
  <main>
    <article>
      <h2>Título do Artigo</h2>
      <p>Conteúdo do artigo...</p>
      <amp-img src="imagem.jpg" width="600" height="400" layout="responsive" alt="Descrição da imagem"></amp-img>
    </article>
  </main>
  <footer>
    <p>Rodapé da página</p>
  </footer>
</body>
</html>
```

## Acessibilidade

Garantir que seu site seja acessível a todos, incluindo pessoas com deficiências, melhora a experiência do usuário e pode influenciar positivamente o SEO.

### Práticas de Acessibilidade

1. **Uso de Tags Semânticas**
   - **Tags**: `<header>`, `<main>`, `<footer>`, `<section>`, `<article>`, `<nav>`, `<figure>`, `<figcaption>`, `<time>`, `<details>`, `<summary>`

2. **Texto Alternativo em Imagens**
   - **Atributo `alt`**: Fornece uma descrição textual para imagens.

     ```html
     <img src="imagem.jpg" alt="Descrição da imagem">
     ```

3. **Agrupamento de Campos Relacionados**
   - **Uso de `<fieldset>` e `<legend>`**: Agrupa elementos de formulário e fornece uma legenda.

     ```html
     <fieldset>
       <legend>Informações Pessoais</legend>
       <label for="name">Nome:</label>
       <input type="text" id="name" name="name">
       <label for="email">E-mail:</label>
       <input type="email" id="email" name="email">
     </fieldset>
     ```

4. **Uso do Teclado para Navegação**
   - **Atributo `tabindex`**: Define a ordem de navegação por teclado.

     ```html
     <button tabindex="1">Primeiro</button>
     <button tabindex="2">Segundo</button>
     <button tabindex="3">Terceiro</button>
     ```

5. **Uso de Título em Elementos Sem Texto**
   - **Atributo `aria-label`**: Fornece um texto descritivo para elementos sem texto visível.

     ```html
     <button aria-label="Fechar">X</button>
     ```

6. **Associação de Conteúdos ao Elemento Pai por ID**
   - **Atributo `aria-labelledby`**: Associa um elemento a um rótulo definido por outro elemento.

     ```html
     <h1 id="main-title">Título Principal</h1>
     <div aria-labelledby="main-title">Conteúdo relacionado ao título principal</div>
     ```

7. **Ocultação para Motores de Busca de Elementos Decorativos**
   - **Atributo `aria-hidden="true"`**: Oculta elementos decorativos dos leitores de tela.

     ```html
     <div aria-hidden="true">Elemento decorativo</div>
     ```

8. **Uso de Anúncio em Elementos Dinâmicos**
   - **Atributo `aria-live`**: Define como as atualizações dinâmicas devem ser anunciadas.

     ```html
     <div aria-live="polite">Atualizações serão anunciadas quando o leitor de tela estiver ocioso.</div>
     ```

   - **`aria-live="assertive"`**: Anuncia atualizações imediatamente.

     ```html
     <div aria-live="assertive">Atualizações serão anunciadas imediatamente.</div>
     ```

9. **Uso de ARIA em Elementos Expansíveis**
   - **Atributo `aria-expanded`**: Indica se um elemento expansível está expandido ou recolhido.

     ```html
     <button aria-expanded="false">Mostrar mais</button>
     ```

10. **Uso de Indicadores para Elementos Pai e Filho pelo ID**
    - **Atributo `aria-controls`**: Indica que um elemento controla outro.

      ```html
      <button aria-controls="details">Mostrar detalhes</button>
      <div id="details">Informações adicionais...</div>
      ```

11. **Uso de `aria-live` em Mensagens Temporárias**
    - **`aria-live`**: Pode ser usado para mensagens temporárias ou mudanças dinâmicas na interface do usuário.

      ```html
      <div aria-live="polite">Mensagem temporária exibida aqui.</div>
      ```

12. **Descrição de Elementos Interativos**
    - Forneça descrições claras para botões e controles interativos.

      ```html
      <button aria-label="Enviar formulário">Enviar</button>
      ```

## SEO

A otimização para motores de busca (SEO) é crucial para melhorar a visibilidade do site nos resultados de pesquisa.

### Estratégias de SEO

1. **Estrutura de URLs**
   - **URLs Amigáveis**: Use URLs descritivas e amigáveis para SEO.

     ```html
     <a href="/artigos/como-melhorar-seo">Leia nosso artigo sobre SEO</a>
     ```

2. **Uso de Meta Tags**
   - **Meta Description**: Descreve o conteúdo da página.

     ```html
     <meta name="description" content="Descrição do conteúdo da página">
     ```

   - **Meta Robots**: Controla a indexação de páginas específicas.

     ```html
     <meta name="robots" content="noindex, nofollow">
     ```

3. **Utilização de Schema Markup**
   - **Schema.org**: Adiciona dados estruturados para ajudar motores de busca a entender o conteúdo da página.

     ```html
     <script type="application/ld+json">
     {
       "@context": "https://schema.org",
       "@type": "Article",
       "headline": "Título do Artigo",
       "author": {
         "@type": "Person",
         "name": "Nome do Autor"
       },
       "datePublished": "2024-08-01"
     }
     </script>
     ```

## Schema.org

O Schema.org é um vocabulário de marcação que ajuda os motores de busca a entender melhor o conteúdo de uma página, fornecendo informações estruturadas sobre o que está sendo apresentado. Usar Schema.org pode melhorar a visibilidade e a indexação de seu site nos motores de busca.

### Vantagens do Schema.org

- **Melhor Compreensão do Conteúdo**: Permite que os motores de busca entendam o contexto do conteúdo da página.
- **Resultados de Pesquisa Mais Ricos**: Pode gerar rich snippets (resultados enriquecidos), como estrelas de avaliações, preços de produtos, e muito mais.
- **Aprimoramento de SEO**: Melhora a capacidade dos motores de busca em indexar e categorizar o conteúdo de forma eficaz.

### Tipos Comuns de Schema.org

- **Produto**: Informações sobre produtos e serviços.
- **Artigo**: Detalhes sobre artigos, notícias e posts de blog.
- **Evento**: Informações sobre eventos, como datas, localizações e detalhes.
- **Organização**: Dados sobre empresas e organizações.

### Exemplo de Implementação de Schema.org

Abaixo está um exemplo de como você pode adicionar marcação Schema.org a uma página HTML. Usamos o formato JSON-LD, que é recomendado pelo Google:

``` html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <title>Produto Exemplo</title>
</head>
<body>
  <h1>Produto Exemplo</h1>
  <p>Descrição detalhada do produto.</p>

  <!-- Marcação Schema.org para um Produto -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org/",
    "@type": "Product",
    "name": "Produto Exemplo",
    "image": "https://www.exemplo.com/imagem-produto.jpg",
    "description": "Descrição detalhada do produto.",
    "sku": "12345",
    "brand": {
      "@type": "Brand",
      "name": "Marca Exemplo"
    },
    "offers": {
      "@type": "Offer",
      "priceCurrency": "USD",
      "price": "29.99",
      "itemCondition": "https://schema.org/NewCondition",
      "availability": "https://schema.org/InStock",
      "url": "https://www.exemplo.com/produto"
    }
  }
  </script>
</body>
</html>
```

4. **Links Internos e Externos**
   - **Links Internos**: Melhoram a navegação e distribuem autoridade entre páginas.

     ```html
     <a href="/sobre">Sobre nós</a>
     ```

   - **Links Externos**: Aumentam a relevância e a autoridade do conteúdo.

     ```html
     <a href="https://www.exemplo.com" target="_blank" rel="noopener noreferrer">Visite nosso parceiro</a>
     ```

5. **Otimização de Conteúdo**
   - **Palavras-Chave**: Utilize palavras-chave relevantes de forma natural no conteúdo.

     ```html
     <h1>Como melhorar o SEO do seu site</h1>
     ```

   - **Cabeçalhos**: Use tags de cabeçalho (`<h1>`, `<h2>`, `<h3>`) para estruturar o conteúdo.

6. **Sitemap XML**
   - **Sitemap**: Ajuda os motores de busca a encontrar todas as páginas do site.

     ```xml
     <?xml version="1.0" encoding="UTF-8"?>
     <urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
       <url>
         <loc>https://www.exemplo.com/</loc>
         <lastmod>2024-08-01</lastmod>
         <changefreq>daily</changefreq>
         <priority>1.0</priority>
       </url>
     </urlset>
     ```

7. **Robots.txt**
   - **Robots.txt**: Controla quais páginas devem ser rastreadas pelos motores de busca.

     ```plaintext
     User-agent: *
     Disallow: /admin/
     Allow: /
     ```

## Boas Práticas

- **Design Responsivo**: Garanta que o site seja acessível em diferentes dispositivos.
- **Segurança**: Use HTTPS para proteger a privacidade dos usuários.
- **Atualização Regular**: Mantenha o conteúdo atualizado e relevante.

## Base de Dados

Uma boa estrutura de base de dados é essencial para o desempenho e a organização do seu site.

- **Defina Nome e Tipos de Dados Claros**:
Escolha nomes de colunas e tabelas que sejam claros e descritivos.
Utilize tipos de dados adequados para cada coluna (e.g., VARCHAR para texto, INT para inteiros).

``` sql
  CREATE TABLE clientes (
    cliente_id INT AUTO_INCREMENT PRIMARY KEY,  -- Identificador único do cliente
    nome VARCHAR(100) NOT NULL,  -- Nome completo do cliente
    email VARCHAR(255) UNIQUE NOT NULL,  -- Endereço de e-mail único
    data_nascimento DATE  -- Data de nascimento do cliente
  );
```
#
- **Use Chaves Primárias e Índices**:
Defina uma chave primária (PRIMARY KEY) para garantir a unicidade dos registros.
Adicione índices (INDEX) em colunas que serão frequentemente usadas em consultas para melhorar o desempenho.

``` sql
  CREATE TABLE produtos (
    produto_id INT AUTO_INCREMENT PRIMARY KEY,  -- Chave primária
    nome VARCHAR(100) NOT NULL,  -- Nome do produto
    preco DECIMAL(10, 2) NOT NULL,  -- Preço do produto
    categoria_id INT,  -- Chave estrangeira
    INDEX idx_nome (nome),  -- Índice para pesquisa rápida pelo nome
    FOREIGN KEY (categoria_id) REFERENCES categorias(categoria_id)  -- Referência à tabela de categorias
  );
```
#
- **Normalização**:
Aplique princípios de normalização para reduzir redundâncias e dependências. Comece com a 1ª Forma Normal (1NF) e considere avançar para a 2ª (2NF) e 3ª Forma Normal (3NF) se necessário.

<br>

**1° Forma de Normalização**: Cada coluna deve conter valores atômicos.
``` sql
  CREATE TABLE pedidos (
    pedido_id INT AUTO_INCREMENT PRIMARY KEY,
    cliente_id INT,
    data_pedido DATE,
    total DECIMAL(10, 2)
  );
```
<br>

**2° Forma de Normalização**: Eliminar dependências parciais. Se um pedido pode ter vários itens, crie uma tabela separada para os itens do pedido.
```sql 
  CREATE TABLE pedido_itens (
    item_id INT AUTO_INCREMENT PRIMARY KEY,
    pedido_id INT,
    produto_id INT,
    quantidade INT,
    FOREIGN KEY (pedido_id) REFERENCES pedidos(pedido_id),
    FOREIGN KEY (produto_id) REFERENCES produtos(produto_id)
  );
```

<br>

**3° Forma de Normalização**: Remova colunas que não são dependentes da chave primária.
``` sql
  CREATE TABLE clientes (
    cliente_id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    endereco_id INT,
    FOREIGN KEY (endereco_id) REFERENCES enderecos(endereco_id)
  );
```

#
- **Defina Restrições**:
Utilize restrições como NOT NULL, UNIQUE e FOREIGN KEY para garantir a integridade dos dados.

```sql 
  CREATE TABLE funcionarios (
    funcionario_id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100) NOT NULL,
    salario DECIMAL(10, 2) CHECK (salario > 0),  -- Restrição de checagem para salários positivos
    email VARCHAR(255) UNIQUE NOT NULL,  -- E-mail único
    departamento_id INT,
    FOREIGN KEY (departamento_id) REFERENCES departamentos(departamento_id)  -- Chave estrangeira
  );
```

#
- **Escolha Apropriada de Tamanho e Precisão**:
Defina tamanhos e precisões adequados para colunas numéricas e de texto. Por exemplo, evite usar VARCHAR(255) se 50 caracteres forem suficientes.

```sql
  CREATE TABLE vendas (
    venda_id INT AUTO_INCREMENT PRIMARY KEY,
    produto_nome VARCHAR(50) NOT NULL,  -- Nome do produto com tamanho adequado
    quantidade INT UNSIGNED NOT NULL,  -- Quantidade não negativa
    preco_unitario DECIMAL(8, 2) NOT NULL  -- Precisão apropriada para valores monetários
  );
```

#
- **Considere o Uso de Default Values**:
Defina valores padrão para colunas quando apropriado para evitar problemas com dados ausentes.

``` sql
  CREATE TABLE tarefas (
    tarefa_id INT AUTO_INCREMENT PRIMARY KEY,
    descricao VARCHAR(255) NOT NULL,
    status ENUM('pendente', 'em andamento', 'concluída') DEFAULT 'pendente',  -- Valor padrão
    data_criacao TIMESTAMP DEFAULT CURRENT_TIMESTAMP  -- Valor padrão para a data de criação
  );
```

#
- **Comentários**:
Adicione comentários (COMMENT) para descrever a finalidade das colunas e tabelas, ajudando na manutenção futura.

```sql
  CREATE TABLE contatos (
    contato_id INT AUTO_INCREMENT PRIMARY KEY COMMENT 'Identificador único do contato',
    nome VARCHAR(100) NOT NULL COMMENT 'Nome completo do contato',
    telefone VARCHAR(15) COMMENT 'Número de telefone do contato',
    email VARCHAR(255) UNIQUE COMMENT 'Endereço de e-mail único'
  );
```
#
- **Documentação e Scripts**:
Mantenha um script de criação bem documentado e versionado para facilitar o gerenciamento e as atualizações.

``` sql
  -- Script para criação da tabela de produtos
  CREATE TABLE produtos (
      produto_id INT AUTO_INCREMENT PRIMARY KEY,  -- Identificador único do produto
      nome VARCHAR(100) NOT NULL,  -- Nome do produto
      preco DECIMAL(10, 2) NOT NULL,  -- Preço do produto
      categoria_id INT,  -- Referência à tabela de categorias
      INDEX idx_nome (nome),  -- Índice para otimização de consultas pelo nome
      FOREIGN KEY (categoria_id) REFERENCES categorias(categoria_id)  -- Chave estrangeira para a tabela de categorias
  );
```

#

### Otimizando consultas na base de dados:

- **Use Índices Eficientemente**: 
  - **Crie Índices**: Índices ajudam a acelerar as buscas. Crie índices em colunas que são frequentemente usadas em cláusulas WHERE, JOIN, ORDER BY e GROUP BY.
  - **Evite Índices Desnecessários**: Muitos índices podem degradar o desempenho de inserções e atualizações.

``` sql
  CREATE INDEX idx_nome ON clientes(nome);
```

#

- **Otimização de Consultas**:
  - **Utilize EXPLAIN**: Use a palavra-chave EXPLAIN para analisar como o MySQL executa uma consulta e identificar possíveis gargalos.

``` sql
  EXPLAIN SELECT * FROM pedidos WHERE cliente_id = 1;
```
  - **Evite SELECT *...**: Selecione apenas as colunas necessárias para reduzir o volume de dados processados.

``` sql
  SELECT nome, preco FROM produtos WHERE categoria_id = 2;
```

  - **Use LIMIT**: Limite o número de registros retornados para consultas grandes.

``` sql
  SELECT nome FROM produtos ORDER BY preco DESC LIMIT 10;
```
#

- **Otimize o Uso de JOIN**:
  - **Utilize Joins de Forma Eficiente**: Garanta que as colunas usadas para joins estejam indexadas.

``` sql
  SELECT p.nome, c.nome
  FROM produtos p
  JOIN categorias c ON p.categoria_id = c.categoria_id;
```
