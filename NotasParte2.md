# Notas da Parte 2 do Tutorial da Evelyn sobre Angular Firebase

Site: 
https://braziljs.org/blog/simples-aplicacao-real-time-com-angular-4-e-firebase-parte-2/

Quando o tutorial pedir para instalar NPM qualquer coisa, esteja na pasta raiz do projeto! Ou seja:

- cd (pasta do realtimeapp) !!!!

Como não observei isto, instalou a pasta node_modules no lugar errado e tive um trabalhão para apagar, ainda mais porque eu coloquei no github...vixe..mas consegui.

Então, quando for instalar usando o NPM, coloque NA PASTA do realtimeapp!! rs...

Executei normalmente a instalação do firebase:
- (pasta do realtimeapp) $ npm install firebase --save

Mas ao instalar o angularfire2 deram vários erros:
- $ npm install angularfire2 --save
  - Vários erros...
    - realtimeapp@0.0.0 (pasta do realtimeapp)
      - ├── UNMET DEPENDENCY @angular/common@^4.2.4
      - ├── UNMET DEPENDENCY @angular/core@^4.2.4
      - ├── UNMET DEPENDENCY @angular/platform-browser@^4.2.4
      - ├── UNMET DEPENDENCY @angular/platform-browser-dynamic@^4.2.4
      - ├── angularfire2@5.0.0-rc.3 
      - ├── UNMET DEPENDENCY rxjs@^5.4.2
      - └── UNMET DEPENDENCY zone.js@^0.8.14

    - npm WARN angularfire2@5.0.0-rc.3 requires a peer of @angular/common@^4.0.0 but none was installed.
    - npm WARN angularfire2@5.0.0-rc.3 requires a peer of @angular/core@^4.0.0 but none was installed.
    - npm WARN angularfire2@5.0.0-rc.3 requires a peer of @angular/platform-browser@^4.0.0 but none was installed.
    - npm WARN angularfire2@5.0.0-rc.3 requires a peer of @angular/platform-browser-dynamic@^4.0.0 but none was installed.
    - npm WARN angularfire2@5.0.0-rc.3 requires a peer of rxjs@^5.0.1 but none was installed.
    - npm WARN angularfire2@5.0.0-rc.3 requires a peer of zone.js@^0.8.0 but none was installed.


Fui no site do Firebase cadastrar meu projeto, copiei o texto, mas reparei que as aspas estavam diferentes.

Atenção ao copiar código com ASPAS!!! A ASPAS copiada não é uma "ASPAS..." troque-a pela ASPAS (' ou ")
Atenção ao copiar código com ASPAS!!! A ASPAS copiada não é uma "ASPAS..." troque-a pela ASPAS (' ou ")
Atenção ao copiar código com ASPAS!!! A ASPAS copiada não é uma "ASPAS..." troque-a pela ASPAS (' ou ")

Após "ng serve" deu pau.
- The "@angular/compiler-cli" package was not properly installed. Error: Error: Cannot find module '@angular/compiler-cli'
- Error: The "@angular/compiler-cli" package was not properly installed. Error: Error: Cannot find module '@angular/compiler-cli'
- at Object.<anonymous> (/usr/lib/node_modules/@angular/cli/node_modules/@ngtools/webpack/src/index.js:14:11)
- at Module._compile (module.js:571:32)
- at Object.Module._extensions..js (module.js:580:10)
- at Module.load (module.js:488:32)
- at tryModuleLoad (module.js:447:12)
- at Function.Module._load (module.js:439:3)
- at Module.require (module.js:498:17)
- at require (internal/module.js:20:19)
- at Object.<anonymous> (/usr/lib/node_modules/@angular/cli/tasks/eject.js:10:19)
- at Module._compile (module.js:571:32)
- at Object.Module._extensions..js (module.js:580:10)
- at Module.load (module.js:488:32)
- at tryModuleLoad (module.js:447:12)
- at Function.Module._load (module.js:439:3)
- at Module.require (module.js:498:17)
- at require (internal/module.js:20:19)
			
			
REINSTALAR angular-cli 
- $ npm install --save @angular/compiler-cli

DERAM ERROS...
- realtimeapp@0.0.0 (pasta do realtimeapp)
- ├── UNMET DEPENDENCY @angular/common@^4.2.4
- ├── UNMET DEPENDENCY @angular/compiler@^4.2.4
- ├─┬ @angular/compiler-cli@4.4.6 
- │ ├─┬ @angular/tsc-wrapped@4.4.6 
- │ │ ├─┬ tsickle@0.21.6 
- │ │ │ ├─┬ mkdirp@0.5.1 
- │ │ │ │ └── minimist@0.0.8 
- │ │ │ ├── source-map@0.5.7 
- │ │ │ └── source-map-support@0.4.18 
- │ │ └── UNMET PEER DEPENDENCY typescript@^2.1.0
- │ ├── minimist@1.2.0 
- │ ├── reflect-metadata@0.1.10 
- │ └── UNMET PEER DEPENDENCY typescript@^2.1.5
- ├── UNMET DEPENDENCY @angular/core@^4.2.4
- ├── UNMET DEPENDENCY @angular/platform-browser@^4.2.4
- ├── UNMET DEPENDENCY @angular/platform-browser-dynamic@^4.2.4
- ├── UNMET DEPENDENCY rxjs@^5.4.2
- └── UNMET DEPENDENCY zone.js@^0.8.14

- npm WARN angularfire2@5.0.0-rc.3 requires a peer of @angular/common@^4.0.0 but none was installed.
- npm WARN angularfire2@5.0.0-rc.3 requires a peer of @angular/core@^4.0.0 but none was installed.
- npm WARN angularfire2@5.0.0-rc.3 requires a peer of @angular/platform-browser@^4.0.0 but none was installed.
- npm WARN angularfire2@5.0.0-rc.3 requires a peer of @angular/platform-browser-dynamic@^4.0.0 but none was installed.
- npm WARN angularfire2@5.0.0-rc.3 requires a peer of rxjs@^5.0.1 but none was installed.
- npm WARN angularfire2@5.0.0-rc.3 requires a peer of zone.js@^0.8.0 but none was installed.
- npm WARN @angular/compiler-cli@4.4.6 requires a peer of typescript@^2.0.2 but none was installed.
- npm WARN @angular/compiler-cli@4.4.6 requires a peer of @angular/compiler@4.4.6 but none was installed.
- npm WARN @angular/compiler-cli@4.4.6 requires a peer of @angular/core@4.4.6 but none was installed.
- npm WARN @angular/tsc-wrapped@4.4.6 requires a peer of typescript@^2.1.5 but none was installed.
- npm WARN tsickle@0.21.6 requires a peer of typescript@^2.1.0 but none was installed.

MESMO ASSIM "ng serve" de novo
PAU de novo...
		
Diga do StackOverflow de ruzenhack
https://stackoverflow.com/questions/42925690/angular2-cli-error-angular-compiler-cli-package-was-not-properly-installed

- I had the same problem. I resolved it following the "Updating Angular CLI" process in the npm @angular/cli page, that is:

  - 1. Uninstall and clean (global)
    (cd pasta do realtimeapp)
  - rm -rf node_modules dist
  - (talvez precise de sudo aqui) $ npm uninstall -g @angular/cli
  - (idem sudo) $ npm cache clean

  - 2. Reinstall and play (global)
  - (idem sudo) $ npm install -g @angular/cli@latest
  - (idem sudo) $ npm install
  - ng serve

### Funcionou. Fim parte 2!
