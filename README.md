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
import 'dart:io';
import 'dart:math';

void main() {
  List<String> opcoes = ['Pedra', 'Papel', 'Tesoura'];
  Random random = Random();

  print('Escolha uma opção:');
  print('1 - Pedra');
  print('2 - Papel');
  print('3 - Tesoura');
  stdout.write('> ');
  
  int? escolhaUsuario = int.tryParse(stdin.readLineSync() ?? '');
  if (escolhaUsuario == null || escolhaUsuario < 1 || escolhaUsuario > 3) {
    print('Escolha inválida!');
    return;
  }

  int escolhaComputador = random.nextInt(3) + 1;
  
  print('\nVocê escolheu: ${opcoes[escolhaUsuario - 1]}');
  print('Computador escolheu: ${opcoes[escolhaComputador - 1]}');
  
  if (escolhaUsuario == escolhaComputador) {
    print('Empate!');
  } else if ((escolhaUsuario == 1 && escolhaComputador == 3) ||
             (escolhaUsuario == 2 && escolhaComputador == 1) ||
             (escolhaUsuario == 3 && escolhaComputador == 2)) {
    print('Você venceu!');
  } else {
    print('Computador venceu!');
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
