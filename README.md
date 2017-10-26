# angularFirebase
Estudo de Angular e Firebase de Evelyn Mendes

Eu acessei o site https://braziljs.org/blog/simples-aplicacao-real-time-com-angular-4-e-firebase-parte-1/ e estou estudando.

Para instalar o NODE e NPM, segui o site abaixo e deu certo no Ubuntu 16.
  http://blog.locaweb.com.br/artigos/desenvolvimento-artigos/instalando-node-js-6-x-e-npm-no-ubuntu-16-04/
    Funcionou! PPA!
    sudo -i
    apt install python-software-properties
    curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
    apt-get install nodejs
    node -v
      v7.10.1
    npm -v
      v4.2.0
				
E para instalar o angular CLI citado no artigo da Evelyn, usei este site:
https://www.npmjs.com/package/@angular/cli
  npm install -g @angular/cli
  checar se instalou com "ng help"
  Funcionou!			


Depois criei a pasta angularFirebase
   mkdir angularFirebase
   cd angularFirebase/
    ng new realtimeapp
    cd realtimeapp

Seguindo o roteiro da parte 1, fiz as seguintes anotações:
ng serve
    browser http://localhost:4200
    pare o ng serve usando a combinação de teclas Ctrl-C
    ng g c CadastroPessoa 
      g=gerar, c=componente

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
		para rodar
			cd Desktop/angularFirebase/realtimeapp
			ng serve
			browser http://localhost:4200

