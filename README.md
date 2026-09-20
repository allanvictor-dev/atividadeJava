# Atividade de Revisão de POO — Loja de Consoles

Atividade de revisão da disciplina GCVA — Gestão do Ciclo de Vida da Aplicação.

O objetivo foi pegar um código com alguns problemas de orientação a objetos e reorganizá-lo aplicando conceitos de POO e alguns princípios do SOLID.

## Sobre o projeto

O programa simula uma loja que trabalha com diferentes tipos de consoles:

- Nintendo
- Playstation
- Playstation Portátil
- Xbox

Cada console possui um nome e um preço base, mas o preço final é calculado de acordo com o tipo do console.

## Estrutura

### IConsole
Interface que define os métodos que todos os consoles precisam possuir:

- `ligar()`
- `calcularPreco()`
- `getNome()`

### DadosConsole
Classe usada para guardar os dados comuns dos consoles:

- nome
- preço base

Os atributos são privados e são acessados através de getters.

### Nintendo
Implementa `IConsole` e adiciona 10% ao preço base.

### Playstation
Implementa `IConsole` e adiciona 20% ao preço base.

### PlaystationPortatil
Herda de `Playstation` e possui um comportamento diferente no método `ligar()` e no cálculo do preço.

Nesse caso, o acréscimo utilizado é de 15%.

### Xbox
Também implementa `IConsole` e adiciona 18% ao preço base.

A classe foi adicionada sem precisar modificar a classe `Loja`.

### Loja
A classe `Loja` trabalha somente com a interface `IConsole`.

Ela possui métodos para:

- vender um console;
- vender vários consoles;
- calcular o faturamento total.

## Conceitos utilizados

Durante a implementação foram utilizados alguns conceitos de orientação a objetos:

- **Encapsulamento:** atributos privados e acesso através de métodos.
- **Construtores:** os objetos já são criados com seus dados necessários.
- **Interfaces:** `IConsole` define o que cada console deve implementar.
- **Composição:** `DadosConsole` é utilizada para guardar os dados dos consoles.
- **Herança:** `PlaystationPortatil` herda de `Playstation`.
- **Polimorfismo:** a `Loja` consegue trabalhar com diferentes tipos de console através de `IConsole`.

Também foi aplicado o princípio **OCP (Open/Closed Principle)**. Um exemplo é a adição do `Xbox`: foi possível criar um novo tipo de console sem precisar alterar a classe `Loja`.

## Como executar

No terminal, dentro da pasta do projeto:

```bash
javac Atividade_POO_Solucao.java
java Atividade_POO_Solucao
