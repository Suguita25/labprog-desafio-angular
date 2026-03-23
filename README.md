# Desafio Angular: Dashboard colaborativa com APIs públicas

![Screenshot](https://raw.githubusercontent.com/matheusvanzan/labprog-desafio-angular/refs/heads/master/screenshot.png)


## Objetivo

Neste desafio, a turma irá construir uma dashboard Angular de forma colaborativa. O projeto base já está pronto, e cada grupo será responsável por implementar **um único widget** da interface.

Ao final, todos os widgets deverão funcionar juntos dentro da mesma dashboard.

## Estrutura do projeto

O projeto já possui:

- aplicação Angular criada
- dashboard principal pronta
- layout em grid
- componentes já criados:
  - `Widget1`
  - `Widget2`
  - `Widget3`
  - `Widget4`
  - `Widget5`
  - `Widget6`
  - `Widget7`

Cada grupo deve trabalhar **somente no seu próprio widget**.

## Regras do desafio

- Cada grupo ficará responsável por **1 widget**.
- Cada grupo deve editar **apenas os arquivos do seu widget**.
- Não altere os widgets dos outros grupos.
- Não renomeie componentes, arquivos ou pastas.
- Não crie um novo projeto Angular.
- Não use bibliotecas externas de interface.
- Não use backend.
- Cada widget deve consumir **uma API pública**.
- O widget deve funcionar de forma independente.
- O widget deve ter aparência de card de dashboard.
- O código deve ser simples, legível e organizado.

## Estado global disponível

Todos os widgets receberão via `@Input` um objeto `user` no formato:

```ts
{
  username: string;
  email: string;
}
````

Esse objeto já será passado pelo componente principal para todos os widgets.

Quando fizer sentido, o widget deve usar esses dados na interface ou na chamada da API.

## Git e integração

O desafio será feito em um repositório compartilhado no GitHub.

Cada grupo deve:

* criar sua própria branch
* implementar seu widget
* atualizar sua branch com a `master` mais recente antes de finalizar
* resolver conflitos, se houver
* testar se o app continua funcionando
* enviar sua solução para o repositório

Se alguma integração quebrar a aplicação, o grupo responsável deverá corrigir o problema.

## Comandos úteis

Para facilitar, use um fluxo semelhante ao fluxo abaixo:

```bash
# clonar o repositório
git clone git@github.com:matheusvanzan/labprog-desafio-angular.git
cd nome-do-repo

# criar e mudar para branch do grupo
git checkout -b feature/widget6

# fazer alterações e commitar
git add .
git commit -m "Implementa Widget6: Agify"

# atualizar a branch principal antes do merge
git checkout master
git pull origin master
git checkout feature/widget6
git rebase master

# resolver conflitos caso existam (manual)
# depois:
# git add <arquivos-resolvidos>
# git rebase --continue

# enviar para o repositório remoto
git push origin feature/widget6

# criar Pull Request no GitHub
```

### Iniciar localmente

```bash
npm install
npm run start
```

## Requisitos técnicos mínimos

Todos os widgets devem:

* fazer uma requisição HTTP GET para a API definida
* exibir os dados principais retornados pela API
* ter um botão para recarregar ou buscar novamente
* mostrar estado de carregamento
* mostrar mensagem de erro em caso de falha
* funcionar dentro do layout da dashboard
* receber o objeto `user` por `@Input`

## Widgets

### Widget1: Advice Slip

Consuma a API:

`https://api.adviceslip.com/advice`

**Objetivo:** exibir um conselho aleatório.

**Requisitos:**

* mostrar um título para o widget
* buscar um conselho da API
* exibir o texto do conselho
* ter botão para carregar outro conselho
* mostrar loading e erro

---

### Widget2: Dad Joke

Consuma a API:

`https://icanhazdadjoke.com/`

**Importante:** use o header:

`Accept: application/json`

**Objetivo:** exibir uma piada aleatória.

**Requisitos:**

* mostrar um título para o widget
* buscar uma piada da API
* exibir o texto da piada
* ter botão para carregar outra piada
* mostrar loading e erro

---

### Widget3: Dog CEO

Consuma a API:

`https://dog.ceo/api/breeds/image/random`

**Objetivo:** exibir uma imagem aleatória de cachorro.

**Requisitos:**

* mostrar um título para o widget
* buscar a imagem na API
* exibir a imagem retornada
* ter botão para carregar outra imagem
* mostrar loading e erro

---

### Widget4: Useless Facts

Consuma a API:

`https://uselessfacts.jsph.pl/api/v2/facts/random?language=en`

**Objetivo:** exibir um fato curioso aleatório.

**Requisitos:**

* mostrar um título para o widget
* buscar um fato da API
* exibir o texto retornado
* ter botão para carregar outro fato
* mostrar loading e erro

---

### Widget5: Random Quote

Consuma a API:

`https://dummyjson.com/quotes/random`

**Objetivo:** exibir uma citação aleatória.

**Requisitos:**

* mostrar um título para o widget
* buscar uma citação da API
* exibir a frase
* exibir o autor
* ter botão para carregar outra citação
* mostrar loading e erro

---

### Widget6: Agify

Consuma a API:

`https://api.agify.io?name=<username>`

**Objetivo:** estimar idade com base no `username` recebido via `@Input`.

**Requisitos:**

* usar `user.username` na URL da requisição
* mostrar um título para o widget
* exibir o nome consultado
* exibir a idade estimada
* ter botão para recarregar a consulta
* mostrar loading e erro

---

### Widget7: Genderize

Consuma a API:

`https://api.genderize.io?name=<username>`

**Objetivo:** estimar gênero com base no `username` recebido via `@Input`.

**Requisitos:**

* usar `user.username` na URL da requisição
* mostrar um título para o widget
* exibir o nome consultado
* exibir o gênero retornado
* exibir a probabilidade, se disponível
* ter botão para recarregar a consulta
* mostrar loading e erro

## Restrições importantes

* Não altere a estrutura do projeto sem necessidade.
* Não edite arquivos de outros widgets.
* Não adicione dependências externas.
* Não complique a solução.
* Foque em entregar um widget funcional, visualmente organizado e integrado ao app.

## Critérios de avaliação

Serão considerados:

* funcionamento correto do widget
* respeito ao enunciado
* consumo correto da API
* uso correto do `@Input user`
* organização visual
* clareza do código
* integração sem quebrar a aplicação
* uso correto dos conceitos trabalhados em aula

## Entrega esperada

Ao final do desafio, o widget do grupo deve:

* compilar normalmente junto com o restante do projeto
* aparecer corretamente na dashboard
* respeitar os requisitos definidos
* consumir corretamente a API designada
* estar pronto para integração com a versão final da turma