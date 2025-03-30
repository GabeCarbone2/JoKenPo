# JoKenPo em Dart

Este é um simples jogo de JoKenPo (Pedra, Papel e Tesoura) desenvolvido em Dart. O jogo permite que o usuário escolha uma das opções e jogue contra a escolha aleatória do computador.

## Tecnologias Utilizadas
- Dart
- Console para entrada e saída de dados

## Como Jogar
1. Clone este repositório:
   ```sh
   git clone https://github.com/GabeCarbone2/JoKenPo.git
   ```
2. Navegue até o diretório do projeto:
   ```sh
   cd JoKenPo
   ```
3. Execute o jogo:
   ```sh
   dart run
   ```
4. Escolha uma das opções digitando o número correspondente:
   - 1 - Pedra
   - 2 - Papel
   - 3 - Tesoura

O computador também fará sua escolha, e o jogo informará o vencedor.

## Exemplo de Execução
```
Escolha uma opção:
1 - Pedra
2 - Papel
3 - Tesoura
> 1

Computador escolheu: Tesoura
Você venceu!
```

## Código-Fonte
Aqui está a implementação principal do jogo em Dart:
```dart
import 'package:flutter/material.dart';
import 'dart:math';

class Jogo extends StatefulWidget {
  const Jogo({Key? key}) : super(key: key);

  @override
  State<Jogo> createState() => _JogoState();
}

class _JogoState extends State<Jogo> {
  var _imagemApp = AssetImage("images/padrao.png");

  void _opcaoSelecionada(String escolhsUuario) {
    var opcoes = ["pedra", "papel", "tesoura"];
    var numero = Random().nextInt(3);
    var escolhaApp = opcoes[numero];

    print("Escolha do app: " + escolhaApp);
    print("Esolcha do usuário: " + escolhsUuario);
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        backgroundColor: Colors.blue,
        foregroundColor: Colors.white,
        title: const Text('JokenPo'),
      ),
      body: Column(
        crossAxisAlignment: CrossAxisAlignment.center,
        children: <Widget>[
          //1 - escolha do app
          Padding(
            padding: EdgeInsets.only(top: 32, bottom: 16),
            child: Text(
              "Escolha do app",
              textAlign: TextAlign.center,
              style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
            ),
          ),

          //2 - Imagem de escolha do app
          Image(image: _imagemApp),

          //3- Escolha uma opção abaixo
          Padding(
            padding: EdgeInsets.only(top: 32, bottom: 16),
            child: Text(
              "Escolha uma opção abaixo",
              textAlign: TextAlign.center,
              style: TextStyle(fontSize: 20, fontWeight: FontWeight.bold),
            ),
          ),

          Row(
            mainAxisAlignment: MainAxisAlignment.spaceEvenly,
            children: <Widget>[
              GestureDetector(
                onTap: () => _opcaoSelecionada("pedra"),
                child: const Image(
                    image: AssetImage('images/papel.png'), height: 100),
              ),
              GestureDetector(
                onTap: () => _opcaoSelecionada("pedra"),
                child: const Image(
                    image: AssetImage('images/pedra.png'), height: 100),
              ),
              GestureDetector(
                onTap: () => _opcaoSelecionada("tesoura"),
                child: const Image(
                    image: AssetImage('images/tesoura.png'), height: 100),
              )
            ],
          )
        ],
      ),
    );
  }
}
```

## Contribuição
Sinta-se à vontade para contribuir com melhorias! Basta:
1. Fazer um fork do repositório.
2. Criar uma nova branch: `git checkout -b minha-melhoria`
3. Commitar as alterações: `git commit -m 'Melhoria na lógica do jogo'`
4. Enviar para o repositório remoto: `git push origin minha-melhoria`
5. Abrir um Pull Request.
