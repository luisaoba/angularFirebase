# angularFirebase
Estudo de Angular e Firebase de Evelyn Mendes

Eu acessei o site https://braziljs.org/blog/simples-aplicacao-real-time-com-angular-4-e-firebase-parte-1/ e estou estudando.

Para instalar o NODE e NPM, segui o site abaixo e deu certo no Ubuntu 16.

http://blog.locaweb.com.br/artigos/desenvolvimento-artigos/instalando-node-js-6-x-e-npm-no-ubuntu-16-04/<br>
	Funcionou! PPA!<br>
		sudo -i<br>
		apt install python-software-properties<br>
		curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -<br>
		apt-get install nodejs<br>
		node -v<br>
			v7.10.1<br>
		npm -v<br>
			v4.2.0<br>
<br>
E para instalar o angular CLI citado no artigo da Evelyn, usei este site:<br>
https://www.npmjs.com/package/@angular/cli<br>
  npm install -g @angular/cli<br>
  checar se instalou com "ng help"<br>
  Funcionou!<br>
<br>
<br>
Depois criei a pasta angularFirebase<br>
   mkdir angularFirebase<br>
   cd angularFirebase/<br>
    ng new realtimeapp<br>
    cd realtimeapp<br>
<br>
Seguindo o roteiro da parte 1, fiz as seguintes anotações:<br>
    ng serve<br>
    browser http://localhost:4200<br>
    pare o ng serve usando a combinação de teclas Ctrl-C<br>
    ng g c CadastroPessoa<br>
      g=gerar, c=componente<br>
<br>
Quando coloquei formulário com id (#f) deu uma tela em branco. Resolvi com a dica do Giuliano.<br>
<br>
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
<br>
<br>
PARTE 1 OK!<br>
		para rodar<br>
			cd Desktop/angularFirebase/realtimeapp<br>
			ng serve<br>
			browser http://localhost:4200<br>
<br>
<br>
