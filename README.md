# Live TAT 76 - Pergunte-me qualquer coisa #4

✅ -> Perguntas respondidas

❌ -> Perguntas que não soube ou não pude responder

## Gustavo DuaRte

- Você tem experiência com CI no Azure? ✅
    - Não.
- Quão maduro devemos estar para implementar testes em uma pipeline de deploy? ✅
    - Um passo de cada vez, 100 progressos de 1% em vez de um progresso de 100%.
- Na sua opinião, considerando uma aplicação de venda robusta, o que cobrir e por quê? Rotas? Main resources ou tudo? ✅
    - Eu teria testes e2e para as principais e mais importantes jornadas de usuário. Testes alternativos e corner cases eu deixaria para níveis mais baixos, tais como testes de componentes, unidade, etc. Já em casos de integrações com outros serviços (de outros times ou de terceiros), pensaria em alguma estratégia de testes API e/ou contract testing. Em certo grau, visto o tipo de aplicação (venda robusta), testes de carga e estresse podem ser necessários e para cada tipo de teste você precisará de especialidades diferentes.

## André Marçal

- Métricas de automação mais relevantes ✅
    - Gosto muito das métricas disponíveis no Dashboard do Cypress, e creio que as mesmas podem ser usadas, mesmo para projetos que não usam Cypress.
    - Elas são:
        - Run status
            - % de passing and failing tests
            - Useful for comparing progress between time windows
        - Run duration
            - Useful to analyse the need for optimisations and/or parallelization
        - Test suite size
            - Keep track of “test coverage” overtime
        - Top failures
            - Tips for areas of improvements
        - Slowest tests
            - Tests re-evaluations and optimisations
                - Should we retire this tests?
                - Should we move it to a lower layer
                - How many times has it failures during its lifetime?
        - Most common errors
            - Areas of improvements and optimisations
        - E flaky tests
            - Identify bad code and replace it with best practices
            - Educate test writers
            - Eliminate flakiness
            - Keep track of progress in flaky tests reduction (or increase) overtime

## Gustavo Ramos S. Silva

- Conta pra gente se você já teve alguma experiência migrando uma suíte de testes de um framework para outro? Dicas para quem está passando por esse momento? ✅
    - Em 2018 iniciei um green field project com Cypress e depois de dois sprints migramos os poucos testes que tínhamos para Protractor, pois o Cypress não era estável o suficiente para nossas necessidades. Visto que ambos os frameworks usavam estruturas parecidas, a migração foi tranquila. Também havia criado alguns helpers que foram facilmente migrados para custom commands. Foi simplesmente mapear as palavras-chave de um framework pro outro e ir migrando. Tudo foi migrado em mais (no máximo) um sprint de duas semanas.
    - Em 2019 tentei migrar alguns testes feitos no GitLab com Capybara + RSpec para Cypress, e minha idéia não foi comprada, por a maioria dos devs serem “fluentes” em Ruby, algo que não era necessariamente verdade, considerando que todos frontend devs conheciam JS. De qualquer forma, fiz isso como um projeto paralelo e consegui colocar em prática algumas boas práticas interessantes. https://github.com/wlsf82/gitlab-cypress
    - Em 2020 ajudei na migração de uma suite de testes inteira (mais expansão dos cenários cobertos) de Puppeteer + Jest para Cypress, onde além de aumentarmos a cobertura, conseguimos testar todos o frontend desacoplado no backend, com o uso de autenticação programática e uso de fixtures, interceptação de requests, etc.

## Katiana Maia

- Alguma dica para interpretar e aplicar uma documentação, seja de linguagem, de framework? ✅
    - Para interpretar, gosto de documentação com guias e muitas referências. Dessa forma posso entender o quão bem documentada tal ferramenta é. Também penso do ponto de vista de quem desenvolve software para os outros. O quanto documentamos suas mudanças?
    - Para aplicar, de novo, 1% de cada vez. Comece com o mínimo. Tenha exemplos para leigos e então evolua conforme for revisitando a mesma. Revisão de documentação é tão importante quanto revisão de código.

## André Junior Pinheiro Freire

- Você considera que aprender Java em 2022/2023 é uma boa ideia? ✅
    - Pesquisas indicam que sim, mas aprender uma linguagem de programação, na minha opinião, deveria ser como aprender uma outra lingua qualquer, tal como Inglês, Espanhol, Português ou Japonês. A escolha é sua!

## José Duarte

- Quando vai ser lancado uma nova versão do curso intermediário de Cypress? ✅
  - Se tudo correr como o planejado, até o final de 2022, mas sem uma data exata.

- Quais as vantangens do uso do Cypress Custom Commands? ✅

https://youtu.be/6lMy3NXjw7E

## Bruna Lima

- Playwright vs Selenium? ✅
  - Conceitos e forma de escrever testes parecida
  - Async/Await deixa o código poluído na minha visão
  - Ambos mais complexos que Cypress
  - Tem suas vantagens relacionadas a não ter limitações, apesar de que acho que algumas restrições sejam boas.

## Gustavo Duarte

- Já fez um prós e contras entre Cypress e Playwright? ✅
  - Não exatamente, mas na live dando meus primeiros passos com Playwright fiz algumas comparações em tempo real.

https://youtu.be/WzMfeBLxeM4

## Amanda Lima

- Cypress é bastante requisitado fora do Brasil? ✅
  - Sim, muito, no mundo inteiro.

## Neimar Pereira

- Como eu consigo conferir a cor de fundo da página? ✅
  - Recomendo algo como o código abaixo (retirado da documentação oficial do Cypress), para testar propriedades CSS.

```js
cy.get('nav') // yields <nav>
  .should('be.visible') // yields <nav>
  .should('have.css', 'font-family') // yields 'sans-serif'
  .and('match', /serif/)
```

## Beatriz Toledo

- Como faço para utilizar uma condicional e sendo essa a ação para o else que preenche um campo com dados vindos do faker no Cypress...isso é possível? ✅
  - Possível é, mas condicional em testes automatizados normalmente não são uma boa idéia. Recomendo ler a [documentação oficial](https://docs.cypress.io/guides/core-concepts/conditional-testing) e assistir uma live onde falei sobre isso.

https://youtu.be/jwskOz1hTwA

## Ricardo Camacho

- Cypress seria recomendado para testes de serviço e de unidade? ✅
  - Para APIs eu diria que sim, assim como vários outros tipos de testes (e2e, frontend, component, etc.), já para testes de unidade, nada te impede, mas creio que outras ferramentas (ex.: Jest) atendem o problema melhor (de forma mais otimizada).

## Neimar Pereira

- Tem alguma forma de colocar o Electron em inglês? ❌
  - Deve ter, mas nunva tive que resolver tal problema, porém não saberei responder de imediato. Eu teria que experimentar antes, e caso o faça, criei algum documento para repassar os aprendizados.

## Gustavo Duarte

- Fiz um custom command com switch case para navegaçnao entre seções e respectivos links em um menu expandido. Dê suas críticas. ❌
  - Só lendo o código.
