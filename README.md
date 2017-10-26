# angularFirebase
Estudo de Angular e Firebase de Evelyn Mendes

Eu acessei o site https://braziljs.org/blog/simples-aplicacao-real-time-com-angular-4-e-firebase-parte-1/ e estou estudando. Mas antes, precisei instalar algumas coisas (pra variar...). Aqui tem as anotações. Acompanhe o site da parte 1 e tenha este aberto também para ver as anotações.

## NODE e NPM
Para instalar o NODE e NPM, segui o site abaixo e deu certo no Ubuntu 16.
http://blog.locaweb.com.br/artigos/desenvolvimento-artigos/instalando-node-js-6-x-e-npm-no-ubuntu-16-04/
- Funcionou com PPA!
  - sudo -i
  - apt install python-software-properties
  - curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
  - apt-get install nodejs
  - node -v
    - v7.10.1
  - npm -v
    - v4.2.0

## Angular CLI
E para instalar o angular CLI citado no artigo da Evelyn, usei este site:
https://www.npmjs.com/package/@angular/cli
- npm install -g @angular/cli

Checar se instalou com "ng help". Deve aparecer um help gigantesco. Apareceu. Funcionou!

Falando em AngularCLI, a imagem do localhost que está na parte 1 está diferente da que eu obtive. Segundo a Evelyn Mendes, a versão do AngularCLI mudou, mas funciona do mesmo jeito. (veja a imagem aqui).


## Pasta angularFirebase
Depois criei a pasta angularFirebase
- mkdir angularFirebase
- cd angularFirebase/
- ng new realtimeapp
- cd realtimeapp


Seguindo o roteiro da parte 1, fiz mais anotações:
- ng serve
- browser http://localhost:4200

Pare o ng serve usando a combinação de teclas Ctrl-C

Criar componente com
- ng g c CadastroPessoa
  - g=gerar, c=componente

Quando coloquei formulário com id (#f) deu uma tela em branco. Resolvi com a dica do Giuliano.

    Giuliano Massaro • há 3 meses
    Comecei agora, seguindo os passos apanhei um pouco na declaração #f="ngForm", mas consegui resolver.
    Para resolver tive que adicionar uns códigos no arquivo app.module.ts, abaixo estão as alterações que fiz, espero que ajude quem estiver com o mesmo problema.

    No início do arquivo app.module.ts, na área de import, adicionei essa linha:
    import { FormsModule } from '@angular/forms';

    Depois, no mesmo arquivo, o imports no @NgModule ficou assim:
    imports: [
    BrowserModule,
    FormsModule
    ],

PARTE 1 OK!
- para rodar
- cd Desktop/angularFirebase/realtimeapp
- ng serve
- vá no browser http://localhost:4200
fim parte 1.
