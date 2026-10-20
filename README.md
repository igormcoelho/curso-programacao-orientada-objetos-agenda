# agenda

Demonstração de agenda com Swing em Java.

## Breves Explicações

Esse projeto é organizado em Java, no conceito de Model View Controller (MVC).

Ou seja, na pasta src/br/uff/ic/agenda/ você encontra as pastas view, model e controller, com as respectivas classes.

Leia inicialmente a pasta model, que só tem uma classe chamada Contato.java.
Ela é bem simples e só tem três campos string: nome, telefone e detalhes.

Na pasta view, existe o arquivo Agenda.java, que mostra como construir a tela.
Cada um dos botões da tela e suas ações no Agenda.java estão conectadas a ações descritas classes na pasta controller. Um exemplo é o ControleCarregar, que funciona no JList da esquerda via ListSelectionListener.

Finalmente, o modelo Contato implementa a interface Serializable, que permite que os dados de um objeto Contato sejam automaticamente convertidos para formato binário pelo próprio Java.
Isso viabiliza o controller ControlePersistencia, que é atrelado à janela principal, salvar e retomar o conteúdo do arquivo `agenda.dat` automaticamente, após fechar e reabrir o programa.

## Instruções de Construção

### Manualmente (mais passos)

No shell do linux ou windows wsl:

```
javac -d out $(find src -name "*.java")
mkdir -p out/br/uff/ic/agenda/view/icones
cp src/br/uff/ic/agenda/view/icones/*.gif out/br/uff/ic/agenda/view/icones/
```

Depois execute:

```
java -cp out br.uff.ic.agenda.view.Agenda
```

Caso queira criar um jar, após compilar e copiar os ícones, faça isso:

```
jar --create --file agenda.jar --main-class br.uff.ic.agenda.view.Agenda -C out .
java -jar agenda.jar
```

### Usando o `ant`

No linux ubuntu ou Windows WSL, basta fazer: `apt install ant`

Depois, construa e rode:

```
$ ant jar
$ java -jar dist/agenda.jar
```

## Licença

MIT License

2016-2026 prof. Igor Machado Coelho & prof. Leo Murta