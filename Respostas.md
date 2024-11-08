# 10 - Função `concat()` em JavaScript

**Português**:  
A função `concat()` em JavaScript é usada para concatenar (unir) duas ou mais strings e retornar uma nova string. Ela não altera as strings originais.

**Inglês**:  
The `concat()` function in JavaScript is used to concatenate (join) two or more strings and return a new string. It does not modify the original strings.

---

# 1 - Algoritmo para Trocar os Valores de Duas Variáveis

Escreva um algoritmo que armazene o valor 19 em uma variável `A` e o valor 23 em uma variável `B`. Depois, troque os valores entre as duas variáveis **sem declarar uma terceira variável** e exiba os valores armazenados nas variáveis após a troca.

```
public class TrocaValores {
    public static void main(String[] args) {
        // Atribuindo os valores às variáveis
        int A = 19;
        int B = 23;

        // Mostrando os valores antes da troca
        System.out.println("Antes da troca:");
        System.out.println("A = " + A);
        System.out.println("B = " + B);

        // Realizando a troca dos valores entre A e B usando apenas atribuições
        A = A + B;  // A agora contém a soma de A e B
        B = A - B;  // Agora B recebe o valor de A (original), pois A + B - B = A
        A = A - B;  // Agora A recebe o valor original de B, pois A + B - A = B

        // Mostrando os valores após a troca
        System.out.println("\nDepois da troca:");
        System.out.println("A = " + A);
        System.out.println("B = " + B);
    }
}
```

# 2 - Programa FizzBuzz

## Crie um programa em Java para exibir uma lista de 1 a 100, com as seguintes exceções:

###    Os números divisíveis por três devem aparecer como 'Fizz' em vez do número;
###    Os números divisíveis por cinco devem aparecer como 'Buzz' em vez do número;
###    Os números divisíveis por três e cinco devem aparecer como 'FizzBuzz' em vez do número.

```
public class FizzBuzz {
    public static void main(String[] args) {
        // Loop de 1 a 100
        for (int i = 1; i <= 100; i++) {
            // Verifica se o número é divisível por 3 e por 5
            if (i % 3 == 0 && i % 5 == 0) {
                System.out.println("FizzBuzz");
            }
            // Verifica se o número é divisível apenas por 3
            else if (i % 3 == 0) {
                System.out.println("Fizz");
            }
            // Verifica se o número é divisível apenas por 5
            else if (i % 5 == 0) {
                System.out.println("Buzz");
            }
            // Caso o número não seja divisível nem por 3 nem por 5, imprime o número
            else {
                System.out.println(i);
            }
        }
    }
}
```
# 3 - Imprimir os Primeiros Números da Série Fibonacci até Exceder 100

### Imprima os primeiros números da série Fibonacci até que excedam 100. A série Fibonacci é da seguinte forma: 0, 1, 1, 2, 3, 5, 8, 13, 21, etc...

```
public class Fibonacci {
    public static void main(String[] args) {
        // Primeiros dois números da série Fibonacci
        int a = 0;
        int b = 1;
        
        // Enquanto o próximo número não exceder 100
        System.out.println(a); // Imprime 0
        while (b <= 100) {
            System.out.println(b); // Imprime o número atual de Fibonacci
            int next = a + b; // O próximo número é a soma dos dois anteriores
            a = b; // Atualiza 'a' para 'b'
            b = next; // Atualiza 'b' para o próximo número da sequência
        }
    }
}

```

# 4 - Contar o Número de Propriedades em um Objeto (JavaScript)

```

// Conta o número de propriedades do objeto
const numeroDePropriedades = Object.keys(obj).length;

// Exibe o número de propriedades
console.log("Número de propriedades no objeto:", numeroDePropriedades);

// Exemplo de propriedades do objeto
const propriedades = ["id_erp", "id_ecom", "id_produto", "quantidade", "valor", "status"];

```

# 5 - Soma de Itens Pares e Produto de Itens Ímpares

### Escreva um código que retorne a soma dos itens pares e o produto dos itens ímpares usando o array abaixo:

```
// Array fornecido
const array = [1, 2, 3, 4, 5, 6, 7, 8, 9];

// Variáveis para armazenar a soma dos números pares e o produto dos números ímpares
let somaPares = 0;
let produtoImpares = 1; // Inicializamos com 1 para multiplicar corretamente

// Loop para percorrer o array
for (let i = 0; i < array.length; i++) {
  // Verifica se o número é par
  if (array[i] % 2 === 0) {
    somaPares += array[i]; // Soma o número aos pares
  } else {
    produtoImpares *= array[i]; // Multiplica o número aos ímpares
  }
}

// Exibe os resultados
console.log("Soma dos números pares:", somaPares);
console.log("Produto dos números ímpares:", produtoImpares);
```


# DATABASE

- 1 FALSE
- 2 DISTINCT
- 3 SELECT COUNT(*) FROM table_name;

 -  4 - Relacionamento entre Tabelas (Modelo Relacional)

 ```

+--------------------+            +------------------------+
|    Products        |            |   ProductPhotos        |
+--------------------+            +------------------------+
| product_id (PK)    |<---+       | photo_id (PK)          |
| product_name       |     |       | product_id (FK)        |
| description        |     +------>| photo_url              |
| price              |             | photo_description      |
| stock_quantity     |             +------------------------+
| category_id (FK)   |             
+--------------------+         

 ```

 Esse modelo garante que cada produto possa ter várias fotos associadas, enquanto cada foto está vinculada a um único produto. Ele permite armazenar informações de produtos e suas fotos de forma eficiente.

- 5 - Consulta SQL com LEFT JOIN

```
SELECT 
    p.product_id,
    p.product_name,
    p.description,
    p.price,
    p.stock_quantity,
    p.category_id,
    ph.photo_id,
    ph.photo_url,
    ph.photo_description
FROM 
    Products p
LEFT JOIN 
    ProductPhotos ph ON p.product_id = ph.product_id;
```

Explicação:

    FROM Products p: Começamos selecionando da tabela Products (apelidada de p).
    LEFT JOIN ProductPhotos ph ON p.product_id = ph.product_id: Realizamos um LEFT JOIN entre as tabelas Products e ProductPhotos. A condição de junção é p.product_id = ph.product_id, ou seja, associamos os produtos às suas fotos.
    SELECT Fields: Selecionamos os campos relevantes de ambas as tabelas:
        Da tabela Products: product_id, product_name, description, price, stock_quantity, category_id.
        Da tabela ProductPhotos: photo_id, photo_url, photo_description.

Resultado: A consulta retorna todos os produtos junto com suas respectivas fotos. Se um produto não tiver fotos associadas, os campos relacionados às fotos terão valores NULL.

- 6 - Tipos de Bancos de Dados Não Relacionais

Document-Oriented Databases: Armazenam dados em formatos de documentos, como JSON ou BSON. Cada documento pode ter uma estrutura diferente, o que torna o banco de dados flexível e sem esquema fixo.

    Exemplo: MongoDB, CouchDB

Key-Value Stores: Armazenam dados como pares chave-valor, onde cada chave é única, e o valor pode ser qualquer tipo de dado.

    Exemplo: Redis, Riak

Column-Family Stores: Organizam dados em colunas ao invés de linhas. São otimizados para leituras e gravações rápidas em grandes conjuntos de dados, geralmente usados em cargas analíticas.

    Exemplo: Cassandra, HBase


# WEB

## 1 - Web Services

**English**:

A Web Service is a software application designed to allow different systems or applications to communicate over a network using standard protocols (such as HTTP, SOAP, or REST). It allows different platforms, written in different programming languages, to interact with each other by exchanging data in a standardized way, usually in XML or JSON format.

**Practical example**:  
A good example of a Web Service is the Google Maps API. If you’re building a website or an app and want to show a map with specific locations, you can use the Google Maps Web Service to request map data. The website sends an HTTP request to the Google Maps Web Service, which then sends back the map data in JSON format, and the website displays the map to the user.

**Português**:

Um Web Service é uma aplicação de software projetada para permitir que sistemas ou aplicações diferentes se comuniquem por meio de uma rede, utilizando protocolos padrão (como HTTP, SOAP ou REST). Ele permite que plataformas diferentes, escritas em linguagens de programação diferentes, interajam entre si, trocando dados de maneira padronizada, geralmente em formato XML ou JSON.

**Exemplo prático**:  
Um bom exemplo de Web Service é a API do Google Maps. Se você está criando um site ou aplicativo e quer mostrar um mapa com locais específicos, pode usar o Web Service do Google Maps para solicitar os dados do mapa. O site envia uma solicitação HTTP para o Web Service do Google Maps, que retorna os dados do mapa em formato JSON, e o site exibe o mapa para o usuário.

---

## 2 - Web API

**English**:

A Web API (Application Programming Interface) is a set of rules and protocols that allows different software applications to communicate with each other over the internet. Unlike traditional APIs that might require local communication between systems, Web APIs are specifically designed to be accessed via HTTP, allowing developers to interact with web servers, retrieve data, or perform actions on a remote server.

**Practical example**:  
A typical example of a Web API is the Twitter API. If you're building an app that needs to fetch user tweets, post new tweets, or follow other users, you can use Twitter's Web API. By sending HTTP requests to the Twitter API endpoints, you can retrieve data or perform actions like posting tweets. For instance, to get recent tweets from a user, your app would send a GET request to the Twitter API's endpoint, and the server would return the tweets in JSON format.

**Português**:

Uma Web API (Interface de Programação de Aplicações) é um conjunto de regras e protocolos que permite que diferentes aplicativos de software se comuniquem entre si pela internet. Ao contrário das APIs tradicionais, que podem exigir comunicação local entre sistemas, as Web APIs são projetadas para serem acessadas via HTTP, permitindo que os desenvolvedores interajam com servidores web, recuperem dados ou executem ações em um servidor remoto.

**Exemplo prático**:  
Um exemplo típico de Web API é a API do Twitter. Se você estiver criando um aplicativo que precisa buscar tweets de um usuário, publicar novos tweets ou seguir outros usuários, pode usar a Web API do Twitter. Enviando solicitações HTTP para os pontos finais da API do Twitter, você pode recuperar dados ou realizar ações, como publicar tweets. Por exemplo, para obter os tweets mais recentes de um usuário, seu aplicativo enviaria uma solicitação GET para o ponto final da API do Twitter, e o servidor retornaria os tweets em formato JSON.

---

## 3 - Imagem no Git

**Explicações em Português**:

- **A**: O cliente navega pelo catálogo de produtos.
- **B**: O cliente seleciona um produto para visualizar.
- **C**: O cliente adiciona o produto ao carrinho de compras.
- **D**: O cliente revisa o conteúdo do carrinho, podendo ajustar quantidades ou remover itens.
- **E**: O cliente prossegue para a etapa de checkout.
- **F**: O cliente insere ou confirma as informações de envio (endereço e contato).
- **G**: O cliente escolhe o método de pagamento (cartão de crédito, PayPal, etc.).
- **H**: O cliente revisa o resumo do pedido, incluindo valores, impostos e custos de envio.
- **I**: O cliente confirma o pedido.
- **J**: A autorização do pagamento é processada.
- **K**: O sistema verifica se o pagamento foi aprovado.
    - Se **Sim**, o pedido é confirmado.
    - Se **Não**, ocorre uma falha no pagamento e o cliente é informado.
- **L**: O pedido é confirmado e uma notificação é enviada ao cliente.
- **N**: O pedido é preparado e enviado do centro de distribuição.
- **O**: O pedido é entregue ao cliente.
- **P**: O cliente confirma o recebimento da entrega.
- **Q**: Caso necessário, o cliente pode solicitar suporte pós-entrega, como devoluções ou troca de produtos.

**Explanations in English**:

- **A**: The customer browses the product catalog.
- **B**: The customer selects a product to view more details.
- **C**: The customer adds the product to the shopping cart.
- **D**: The customer reviews the cart, adjusting quantities or removing items.
- **E**: The customer proceeds to the checkout stage.
- **F**: The customer enters or confirms shipping information (address and contact details).
- **G**: The customer selects the payment method (credit card, PayPal, etc.).
- **H**: The customer reviews the order summary, including prices, taxes, and shipping costs.
- **I**: The customer confirms the order.
- **J**: The payment authorization is processed.
- **K**: The system checks if the payment was successful.
    - If **Yes**, the order is confirmed.
    - If **No**, there is a payment failure, and the customer is notified.
- **L**: The order is confirmed, and a notification is sent to the customer.
- **N**: The order is prepared and shipped from the fulfillment center.
- **O**: The order is delivered to the customer.
- **P**: The customer confirms receipt of the delivery.
- **Q**: If needed, the customer can request post-delivery support, such as returns or product exchanges.
