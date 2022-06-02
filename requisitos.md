# Quais os benefícios de utilizar o Redis (PROBLEMA).
A escolha do Redis para ser banco de dados de aplicações variadas, de sites a softwares, pode ser a mais adequada devido a alguns benefícios principais que ele oferece. São vantagens relacionadas às suas características, focadas principalmente em proporcionar dinâmica e rapidez no uso. A seguir, entenda melhor esses fatores e como eles são atrativos.

O Redis pode ser usado com soluções de streaming como Apache Kafka e Amazon Kinesis, atuando como datastore na memória para consumir, processar e analisar dados em tempo real com latência inferior a um milissegundo. O Redis é uma escolha ideal para casos de uso de análises em tempo real, como análises de mídia social, direcionamento de anúncios, personalização e IoT.

# Python + Redis 
``Aviso do Python``
redis-py 4.2.x será a última geração de redis-py para suportar python 3.6, pois foi End of Life'd . O suporte assíncrono foi introduzido no redis-py 4.2.x graças ao aioredis , que exige essa alteração. Continuaremos a manter o suporte 3.6 pelo maior tempo possível - mas o plano é que o redis-py versão 5+ remova oficialmente o 3.6.

``Instalação``
redis-py requer um servidor Redis em execução. Consulte o início rápido do Redis para obter instruções de instalação.

redis-py pode ser instalado usando pip semelhante a outros pacotes Python. Não use sudo com pip. Geralmente é bom trabalhar em um virtualenv ou venv para evitar conflitos com outros gerenciadores de pacotes e projetos Python. Para uma introdução rápida, veja Ambientes Virtuais do Python em Cinco Minutos .

Para instalar o redis-py, basta:

```$ pip install redis```

ou da fonte:

```$ python setup.py install```

# O Que e o redis ?
 Redis é um armazenamento de dados de código aberto, em rede, na memória e valor-chave com durabilidade opcional. Está escrito em ANSI C. O desenvolvimento do Redis é patrocinado pelo Redis Labs hoje; antes disso, foi patrocinado pela Pivotal e VMware. De acordo com o ranking mensal da DB-Engines.com, o Redis é a loja de valor-chave mais popular. O nome Redis significa REmote DIctionary Server.

## Como o Redis pode ser usado pelas empresas?

As características do Redis o colocam como um banco de dados que pode ser muito útil em algumas situações específicas, o que reforça sua versatilidade. São atividades comuns a empresas dos mais diversos tipos e que têm necessidades muitas vezes relacionadas a seus respectivos segmentos. Entenda melhor a seguir como essa solução pode ser utilizada.

Para ser capaz de funcionar com armazenamento em alta velocidade, o Redis trabalha, basicamente, com dois tipos de processamento: armazenamento de valores chaves e banco de dados na memória.

O primeiro funciona com a criação de chaves para cada entrada de informações no banco de dados. Posteriormente, essas chaves permitem acessar os dados. Entre suas características principais, estão a escalabilidade, já que esse esquema de chaves torna a estrutura do banco de dados mais simplificada.

Já o armazenamento na memória torna a atividade mais rápida, uma vez que esse processamento leva muito menos tempo do que em outras estruturas tradicionais, como as que armazenam em discos rígidos. O desempenho mais dinâmico pode ser observado tanto em bancos de dados estruturados quanto desestruturados.

### RESUMO
Redis é um armazenamento de estrutura de dados em memória, usado como um banco de dados em memória distribuído de chave-valor, cache e agente de mensagens, com durabilidade opcional.
Em sua utilidade, o Redis pode suportar diferentes estruturas de dados, entre eles:

    strings;
    hashes;
    listas;
    conjuntos;
    conjuntos ordenados com consultas de alcance;
    bitmaps;
    hiperlogs;
    índices geoespaciais;
    streams.

o Redis não deixa a desejar. Sua compatibilidade se estende, principalmente, a:

    Java;
    Python;
    PHP;
    C;
    C++;
    C#;
    JavaScript;
    Node.js;
    Ruby;
    R;
    Go.

# Referência da API
A documentação oficial do comando Redis faz um ótimo trabalho ao explicar cada comando em detalhes. redis-py tenta aderir à sintaxe de comando oficial. Há poucas exceções:

SELECIONAR : Não implementado. Consulte a explicação na seção Segurança da linha abaixo.
DEL : del é uma palavra-chave reservada na sintaxe do Python. Portanto, redis-py usa delete .
MULTI/EXEC : Estes são implementados como parte da classe Pipeline. O pipeline é encapsulado com as instruções MULTI e EXEC por padrão quando é executado, o que pode ser desabilitado especificando transaction=False. Veja mais sobre Pipelines abaixo.
SUBSCRIBE/LISTEN : semelhante aos pipelines, o PubSub é implementado como uma classe separada, pois coloca a conexão subjacente em um estado em que não pode executar comandos que não sejam pubsub. Chamar o método pubsub do cliente Redis retornará uma instância PubSub em que você pode se inscrever em canais e ouvir mensagens. Você só pode chamar PUBLISH do cliente Redis 
SCAN/SSCAN/HSCAN/ZSCAN : Os comandos *SCAN são implementados como existem na documentação do Redis. Além disso, cada comando tem um método iterador equivalente. Estes são puramente por conveniência, para que o usuário não precise acompanhar o cursor durante a iteração. Use os métodos scan_iter/sscan_iter/hscan_iter/zscan_iter para esse comportamento.

# Referencias
https://pt.wikipedia.org/wiki/Redis

https://redis.io/docs/getting-started/installation/install-redis-on-linux/

https://hub.docker.com/_/redis

https://rockcontent.com/br/blog/redis/

https://aws.amazon.com/pt/redis/

https://readthedocs.org/projects/redis/

https://redis.io/commands/
