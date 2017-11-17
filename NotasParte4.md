# Notas da Parte 4 do Tutorial da Evelyn sobre Angular Firebase

Site: 
https://braziljs.org/blog/simples-aplicacao-real-time-com-angular-4-e-firebase-parte-4/

Quando o tutorial pedir para instalar NPM qualquer coisa, esteja na pasta raiz do projeto! Ou seja:
- cd (pasta do realtimeapp) !!!!

No meu caso, tive que colocar "sudo", pois deu erro de permissão em pastas.

"firebase init" deu erro. Precisa de LOGIN primeiro
Após login, dar permissões para o Firebase.
Selecionar DATABASE FUNCTIONS E ROSTING...

No BUILD deu erro.

Em cadastro-pessoa-lista.component.ts altere o constructor de:
        constructor(db: AngularFireDatabase) {
		this.pessoas = db.list ('pessoas');
	}

Para:
        constructor(db: AngularFireDatabase) {
		db
			.list('pessoas')
			.valueChanges()
			.subscribe(result => {
				this.pessoas = result;
			})
	}




Em /app/cadastro-pessoa/cadastro-pessoa.component.ts faltou declarar 'pessoas'
- export class CadastroPessoaFormComponent implements OnInit {
  - "pessoas: any;"

Fiz o Build de novo e deu certo!!

Após a mudança de 'dist' para 'public', depois do outro build, cheque a pasta public com
- ls -la public/
- deve aparecer vários arquivos agora.

no .gitignore, adicionei as pastas
/dist
/e2e
/functions
/node_modules
/public


FIM-Tudo certo e tudo funcionando como o vídeo da parte 4 de Evelyn!

Agradecimentos: queria agradecer a Evelyn Mendes a paciência e presteza em tirar minhas dúvidas, à turma do stackoverflow que
	tirou dúvidas sobre a instalação, reinstalção do node_modules (npm...) e a Internet.

Hardware e Softwares utilizados: 
- Ubuntu 16.04 64bits, Geany 1.27
- Desktop com 8GB RAM intel i5-2400 3.1 Ghz x 4 
