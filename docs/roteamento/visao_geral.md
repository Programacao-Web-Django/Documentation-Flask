# Variáveis de URL no Flask

As variáveis de URL são uma característica poderosa do Flask que permite criar rotas dinâmicas e personalizadas. Elas permitem que você capture valores diretamente das URLs e os use em suas funções de rota, tornando as URLs mais flexíveis e interativas.

## Definindo Variáveis de URL

No Flask, você pode definir variáveis de URL diretamente nas rotas usando a sintaxe de marcador de posição. Variáveis de URL são especificadas dentro de colchetes angulares (`< >`) na definição da rota. Esses valores são então passados para a função de rota como parâmetros.

## Tipos de Variáveis

O Flask permite especificar tipos para variáveis de URL, como `int` e `float`, para garantir que os valores correspondam ao tipo esperado. Isso ajuda a validar as variáveis e a evitar erros ao processar as solicitações.

## Utilizando Variáveis de URL

Uma vez que uma variável de URL é definida, seu valor pode ser acessado diretamente dentro da função de rota. Isso permite personalizar a resposta com base no valor da variável, facilitando a criação de páginas dinâmicas e interativas.

## Exemplo de Uso

As variáveis de URL são frequentemente usadas para criar rotas que dependem de valores fornecidos pelos usuários, como IDs de recursos, nomes de usuário e outros parâmetros. Isso permite construir URLs que são únicas e adaptáveis com base nos dados fornecidos.

## Conclusão

As variáveis de URL são uma ferramenta essencial no Flask para criar rotas dinâmicas e interativas. Elas permitem capturar e utilizar valores diretamente das URLs, tornando a criação de aplicações web mais flexível e poderosa.
