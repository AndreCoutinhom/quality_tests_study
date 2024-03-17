> *Anotações da Formação em Engenharia de Software da Alura.*

<h1 align="center">
  Testes e qualidade

###

![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/c9f0818d-b4e5-4dfd-8fae-c65d2c9b29ee)

</h1>

---

Um software não é considerado como "pronto" apenas com a finalização da escrita do código de suas funcionalidades. É preciso garantir que ele está funcionando conforme o esperado pelos clientes e pessoas que vão o utilizar. Por isso é essencial a realização de diversos tipos de testes que vão garantir a qualidade dele.

Com isso nasce a necessidade de uma disciplina na engenharia de software que é responsável pela garantia da qualidade do software.

Neste passo você vai estudar sobre a disciplina de testes de software, também conhecida como Quality Assurance, conhecendo sobre o processo e as ferramentas utilizadas para garantir a qualidade de um software, que permitem a identificação de bugs e melhorias necessárias.

## [Testes Automatizados – Hipsters #51](https://cursos.alura.com.br/extra/hipsterstech/testes-automatizados-hipsters-51-a535) 🎧

---
## O que é Test-Driven Development (TDD)? 🎥

![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/c223db36-6575-4e15-948a-1d19b73059a4)

Usando testes para guiar o desenvolvimento, é possível refatorar códigos através de vários testes pequenos pré-planejados.

O único requisito para se usar o TDD é utilizar testes automatizados.

### Exemplos de script de teste em PHP

``` php

test(description: 'Pessoa deve informar seu ano de nascimento', function () {
// Arrange
$pessoa = new Pessoa(
  nome: 'Vincius',
  new DateTimeImmutable(datetime: '1997-10-15')
);

// Act
$anoNascimento = $pessoa->anoNascimento();

// Assert
expect($anoNascimento)->toBe(expected: 1997)
})

```

O teste acima usa a divisão de passos Arrange - Act - Assert (AAA), na qual o cenário de teste é preparado, depois executado e finalmente visualizado.

Diretamente, o primeiro teste escrito irá falhar. No TDD todo o código escrito deve ser trabalhado para responder corretamente ao teste. Por isso o script de teste rege todas as funcionalidades.

Considera-se o sistema funcional quando o mesmo script de teste falho se torna bem-sucedido após as alterações em todos os códigos que não fazem parte do script de teste.

A cada nova refatoração, os testes precisam ser aplicados novamente, até que a aplicação esteja coesa com os resultados esperados.

A principal vantagem de utilizar a prática do TDD é que o código finalizado já esteve sendo testado. Por esse motivo muitas empresas relatam que a aplicação do TDD resultou em aplicações com menos bugs.

---
## O que é Behavior-Driven Development (BDD)? 🎥

A ideia é que equipes técnicas e não técnicas consigam colaborar nas implementações do projeto.

![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/52b657af-f923-4fc1-901e-761cc3a2b111)

A imagem acima ilustra que BDD e TDD podem ser correlacionados. Utilizando múltiplas perspectivas do projeto, os testes que geram o ciclo do TDD podem ser melhor planejados, refatorados, analisados e avaliados.

O principal do BDD é a comunicação.

![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/7d5e5daa-b120-498e-8bcb-17963d1b2f06)

Uma ferramenta muito utilizada no BDD é a lingugagem Gherkin. Ela define descrições e intitulações de features e cenários.

![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/d1dc1df8-8b1f-4ab1-98e2-d87a83177af2)

---
## Entenda a Pirâmide de Teste 🎥

![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/0e5b2dc4-cf69-4b5c-9607-547f0c3da9b4)

Na pirâmide de testes, os componentes na base da pirâmide são aqueles que são os mais rápidos de se realizarem, os menos custosos e os que devem estar em maior número.

### Testes de Unidade

Compõem testes feitos pelos próprios desenvolvedores da menor unidade do sistema como classes, objetos, funções, variáveis, etc.

### Testes de Integração

São testes que verificam a qualidade da comunicação entre uma funcionalidade e outra. Geralmente aplicada na interação entre classes, APIs e/ou microsserviços.

### Testes de ponta a ponta

São testes que avaliam o sistema real. No geral são testes de interface e front-end que verificam os requisitos funcionais da aplicação.

---
## API: Testes de contrato 🎥

Um contrato é um pacto entre duas ou mais partes. Contratos em aplicações podem ser APIs ou microsserviços por exemplo.

![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/d08dc075-f38d-4837-9a16-5750bb408f2a)

Esse tipo de teste tenta reduzir o ruído entre consumidor e fornecedor.

![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/8d7b3c42-9632-453a-85ae-20f71d48d071)

O código abaixo é um bom exemplo de contrato

![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/2873406f-2e8e-4676-86ca-ff405b5ad885)

Na imagem a requisição pode testar se os respectivos IDs estão ativos.

Dependendo da API, novas versões podem afetar a boa comunicação de contratos.

[Postman](https://www.postman.com), [Pact](https://pact.io) e [Swagger](https://swagger.io) são alguns dos principais meios de documentar testes realizados em contratos.

![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/3d131b86-707b-48fb-a9ba-2951d148bd3a)

Para validar um contrato, é necessário testar seus principais requisitos.

![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/ceddf780-eb9b-4ccb-a0b8-083258301ebf)
![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/6aaba072-2584-4199-a070-47f734f2f9ce)

Outra ferramenta é o [Chai Insertion Library](https://www.chaijs.com) que possui vários códigos em javascript para realização de testes que podem ser rodados no Postman.

---
## Cobertura de Código 🎥

Testes de unidade podem ser realizados pelos próprios desenvolvedores usando scripts de teste personalizados.

A cobertura de código consegue informar através de estatísticas quais linhas do código foram executadas durante os testes.

![image](https://github.com/AndreCoutinhom/quality_tests_study/assets/91290799/d36a9531-4969-4023-bf0c-22427785daca)

Dessa forma, testes de unidade conseguem ser realizados durante o desenvolvimento do código. No caso de aplicações de cobertura de código detectarem bugs ou irregularidades, novos testes podem ser formulados.

Existem também formas de cobertura de código através de ramificação durante a execução. Depende bastante da linguagem, mas o PHP é uma das linguagens que mais utilizam esse recurso.

---
## Testes de Mutação - Testando seus testes 🎥

Os testes de mutação introduzem bugs intencionais aos códigos. Isso é feito para garantir que o código possa falhar. Se um código escrito sob o pretexto de falhar acaba dando certo, então há algo de errado.

Existem várias ferramentas de automação de testes de mutação. Isso pode ser muito útil já que a execução de várias mutações ao mesmo tempo, pode comprometer a lógica dos testes. As ferramentas estão, geralmente, contidas nas próprias linguagens de programação, principalmente o PHP.

As ferramentas devem poder demonstrar mutações que "escaparam", ou que não pode ser considerada pelo sistema como um bug. A intenção é que se tenham cada vez menos escapes de mutações, assim permitindo que o sistema esteja menos adepto a bugs.

---
