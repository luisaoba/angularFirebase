# Notas da Parte 3 do Tutorial da Evelyn sobre Angular Firebase

Site: 
https://braziljs.org/blog/simples-aplicacao-real-time-com-angular-4-e-firebase-parte-3/		

Quando o tutorial pedir para instalar NPM qualquer coisa, esteja na pasta raiz do projeto! Ou seja:
- cd (pasta do realtimeapp) !!!!
- ng serve

Aqui ele não mostrou nada, ficou parado, ou lento demais...

No browser, digite: http://localhost:4200
Deu erro a primeira vez. E reparei que no terminal, AGORA SIM, está carregando o servidor...estranho.
Esperei acabar de carregar e voltei no browser. Ah, beleza! 
Agora sim! Apareceu o formulário. Continua funcionando!
		
- ng g m cadastro-pessoa
- Obs: (g=gerar, m=módulo (e c=componente))

Criou módulo OK
- ng g c cadastro-pessoa/cadastro-pessoa-form
- ng g c cadastro-pessoa/cadastro-pessoa-lista
			
Continuando, tudo OK, até que falou em DATABASE do Firebase...
Na coluna da esquerda tem o menu 'Database'. Como eu não tinha criado, cliquei 'Primeiros Passos'.
Depois cliquei na aba 'Regras'
Troquei de: "auth != null" para "true" como pede no tutorial. E apertei Control+S (acostumei com isso para Salvar...
E não é que funcionou? Na verdade ele "publicou", enfim...continuando...
				
Pequeno vacilo ao digitar "AngularFireDataBase" em alguns lugares e digitar 'AngularFireDatabase' em outros...deu erro pacas..
Corrigido para "AngularFireDatabase" com "b" minúsculo em TODOS os lugares. Agora sim!
	
Funcionou a gravação no Firebase. Estranho que HORA NENHUMA eu defini tabelas, campos, tamanho de variável...enfim...vamos simbora..
	
## Listagem com Firebase
Obs: pule para "Dicas Evelyn 2" caso não queira ter erros de atualização do Angular, pois desde a confecção do artigo da Evelyn
até hoje (30-10-2017) algumas coisas mudaram no Angular/Firebase.
	
Continuando...
Quando foi a listagem, deu erro. A palavra "FirebaseListObservable" NÃO EXISTE MAIS!!
	
Em cadastro-pessoa-lista.component.ts, troque:
- de: import { AngularFireDatabase, FirebaseListObservable } from 'angularfire2/database';
- para: 
  - import { AngularFireDatabase, AngularFireList } from 'angularfire2/database';
  - import { Observable } from 'rxjs/Observable';
		
- de: pessoas: FirebaseListObservable<any[]>;
- para: ????
		
### Dicas Evelyn 1

Peguei telas 'correcaoParte3', mas não deu certo
- ERROR in .../realtimeapp/src/app/cadastro-pessoa/
	cadastro-pessoa-lista/cadastro-pessoa-lista.component.ts (1,33): 
	Cannot find module '@angularfire2/database/interfaces'.
- ERROR in .../realtimeapp/src/app/cadastro-pessoa/
	cadastro-pessoa-lista/cadastro-pessoa-lista.component.ts (20,15): 
	Type '(result: any) => void' cannot be used as an index type.

Tentativa 1: Pesquisei o problema e Iarssn (https://github.com/angular/angularfire2/issues/1155) fez assim:
- rm -rf node_modules #or your OS equivalent
- npm install
- npm install angularfire2@latest --save
Mesmo erro!!

### Dicas Evelyn 2:

Após várias tentativas e comunicações com a Evelyn, deu certo!
Cometi 3 erros:
1 em ".subscribe(result =>" parênteses () por colchetes []... o correto é parênteses.
2 tirei o import do AngularFireList.
3 troquei parênteses () por colchetes [] em ".list('pessoas')". O correto é parênteses. E ele tinha me mostrou OUTRO erro em ".valueChanges()...";


Veja como ficou cadastro-pessoa-lista.component.ts<br>
+++++++++++++++++++

	import { Observable } from 'rxjs/Rx';

	import { Component, OnInit } from '@angular/core';
	import { AngularFireDatabase } from 'angularfire2/database';


	@Component({
	  selector: 'app-cadastro-pessoa-lista',
	  templateUrl: './cadastro-pessoa-lista.component.html',
	  styleUrls: ['./cadastro-pessoa-lista.component.css']
	})
	export class CadastroPessoaListaComponent implements OnInit {

		pessoas: any;

		constructor(db: AngularFireDatabase) {
			db
				.list('pessoas')
				.valueChanges()
				.subscribe(result => {
					this.pessoas = result;
				})
		}
		
		ngOnInit() { }
	}

+++++++++++++++++++

E meu package.json atual

+++++++++++++++++++
	{<br>
	  "name": "realtimeapp",<br>
	  "version": "0.0.0",<br>
	  "license": "MIT",<br>
	  "scripts": {<br>
		"ng": "ng",<br>
		"start": "ng serve",<br>
		"build": "ng build",<br>
		"test": "ng test",<br>
		"lint": "ng lint",<br>
		"e2e": "ng e2e"<br>
	  },<br>
	  "private": true,<br>
	  "dependencies": {<br>
		"@angular/animations": "^4.2.4",<br>
		"@angular/common": "^4.2.4",<br>
		"@angular/compiler": "^4.2.4",<br>
		"@angular/compiler-cli": "^4.4.6",<br>
		"@angular/core": "^4.2.4",<br>
		"@angular/forms": "^4.2.4",<br>
		"@angular/http": "^4.2.4",<br>
		"@angular/platform-browser": "^4.2.4",<br>
		"@angular/platform-browser-dynamic": "^4.2.4",<br>
		"@angular/router": "^4.2.4",<br>
		"angularfire2": "^5.0.0-rc.3",<br>
		"core-js": "^2.4.1",<br>
		"firebase": "^4.6.0",<br>
		"rxjs": "^5.4.2",<br>
		"zone.js": "^0.8.14"<br>
	  },<br>
	  "devDependencies": {<br>
		"@angular/cli": "1.4.9",<br>
		"@angular/compiler-cli": "^4.2.4",<br>
		"@angular/language-service": "^4.2.4",<br>
		"@types/jasmine": "~2.5.53",<br>
		"@types/jasminewd2": "~2.0.2",<br>
		"@types/node": "~6.0.60",<br>
		"codelyzer": "~3.2.0",<br>
		"jasmine-core": "~2.6.2",<br>
		"jasmine-spec-reporter": "~4.1.0",<br>
		"karma": "~1.7.0",<br>
		"karma-chrome-launcher": "~2.1.1",<br>
		"karma-cli": "~1.0.1",<br>
		"karma-coverage-istanbul-reporter": "^1.2.1",<br>
		"karma-jasmine": "~1.1.0",<br>
		"karma-jasmine-html-reporter": "^0.2.2",<br>
		"protractor": "~5.1.2",<br>
		"ts-node": "~3.2.0",<br>
		"tslint": "~5.7.0",<br>
		"typescript": "~2.3.3"<br>
	  }<br>
	}<br>
+++++++++++++++++++<br>

FIM-Tudo certo e tudo funcionando como o vídeo da parte 3 de Evelyn!

Agradecimentos: queria agradecer a Evelyn Mendes a paciência e presteza em tirar minhas dúvidas, à turma do stackoverflow que
	tirou dúvidas sobre a instalação, reinstalção do node_modules (npm...) e a Internet.

Hardware e Softwares utilizados: 
- Ubuntu 16.04 64bits, Geany 1.27
- Desktop com 8GB RAM intel i5-2400 3.1 Ghz x 4 
