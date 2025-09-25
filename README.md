### **Ementa da Disciplina: Programação para Dispositivos Móveis**  

#### **Objetivo Geral**  
Capacitar os alunos no desenvolvimento de aplicações móveis multiplataforma utilizando o framework Flutter, explorando conceitos fundamentais de programação, boas práticas de desenvolvimento e a criação de interfaces interativas e responsivas, aplicadas a soluções reais.

---

#### **Conteúdo Programático**

1. **Introdução ao Desenvolvimento Mobile**  
   - Panorama sobre o mercado de aplicativos móveis.  
   - Principais plataformas (iOS, Android) e a abordagem multiplataforma com Flutter.  
   - Configuração do ambiente de desenvolvimento (Dart, Flutter SDK, emuladores e IDEs).  

2. **Fundamentos do Framework Flutter**  
   - Arquitetura do Flutter: Widgets, Renderização e Dart.  
   - Estrutura de projetos Flutter e organização de pastas.  
   - Ciclo de vida de um aplicativo Flutter.  

3. **Construção de Interfaces Gráficas (UI)**  
   - Introdução aos Widgets: Stateless e Stateful.  
   - Criação de layouts com widgets básicos: Containers, Texts, Buttons e Images.  
   - Gerenciamento de layout com Rows, Columns e Stacks.  
   - Personalização de estilos e temas no Flutter.  

4. **Gerenciamento de Estados**  
   - Conceitos de gerenciamento de estado.  
   - Uso de `setState` para estados locais.  
   - Introdução a soluções avançadas (Provider, Riverpod - opcional).  

5. **Manipulação de Dados e Navegação**  
   - Navegação entre páginas (Navigator e rotas nomeadas).  
   - Passagem de dados entre telas.  
   - Validação e controle de formulários.  

6. **Integração com Recursos do Dispositivo**  
   - Utilização de bibliotecas para acesso a sensores, câmera e GPS.  
   - Manipulação de armazenamento local (SharedPreferences e SQLite).  

7. **Desenvolvimento de Funcionalidades Avançadas**  
   - Consumo de APIs REST com HTTP/Dio.  
   - Exibição de listas e scrolls dinâmicos.  
   - Gráficos e visualização de dados com pacotes do Flutter.  

8. **Boas Práticas no Desenvolvimento Mobile**  
   - Padrões de projeto aplicados ao Flutter.  
   - Modularização e reuso de componentes.  
   - Testes de interface e funcionalidades no Flutter.  

9. **Empacotamento e Publicação de Aplicativos**  
   - Geração de builds para Android e iOS.  
   - Publicação na Play Store e App Store.  

10. **Projeto Prático Final**  
    - Desenvolvimento de uma aplicação completa que integre os conteúdos abordados.  
    - Apresentação do projeto com documentação e vídeo demonstrativo.

---

#### **Metodologia de Ensino**  
- **Aulas expositivas e práticas:** Combinação de explicação teórica e implementação direta de conceitos no código.  
- **Trabalhos práticos:** Desenvolvimento incremental de aplicativos, simulando desafios reais do mercado.  
- **Estudo de casos:** Análise de aplicativos populares para identificar boas práticas.  
- **Projeto final:** Desenvolvimento de um aplicativo completo como avaliação integradora.  

---

#### **Recursos Didáticos**  
- Flutter SDK e Dart Programming Language.  
- IDEs sugeridas: Visual Studio Code e Android Studio.  
- Documentação oficial do Flutter (flutter.dev).  
- Emuladores ou dispositivos reais para testes.  

---

#### **Resultados Esperados**  
Ao final da disciplina, os alunos deverão ser capazes de:  
1. Configurar e utilizar o Flutter para desenvolver aplicações móveis.  
2. Projetar e implementar interfaces gráficas responsivas e interativas.  
3. Gerenciar estados e dados em aplicativos móveis.  
4. Integrar funcionalidades avançadas, como APIs externas e armazenamento local.  
5. Publicar e distribuir aplicativos nas principais plataformas móveis.  

**Carga Horária:** 80 horas (ou conforme regulamento do curso).  

# Introdução ao Flutter - Guia Passo a Passo

Este guia apresenta os conceitos fundamentais do Flutter através de exemplos práticos, desde um simples "Olá, Mundo!" até widgets com estado.

## 📋 Pré-requisitos

- Flutter SDK instalado
- Editor de código (VS Code, Android Studio, etc.)
- Conhecimento básico de programação Dart

## 🚀 Passo 1: Primeiro App - Olá Mundo Simples

````dart
main() => runApp( 
  Center( // O widget que alinha o conteúdo no centro
    child: Text( 
      'Olá, Mundo!!!',
    textDirection: TextDirection.ltr,
    ),
  ),
);
````

## Conceitos aprendidos:

- Função main() como ponto de entrada

- Widget Center para centralização

- Widget Text para exibir texto

- Propriedade textDirection obrigatória

## 🎨 Passo 2: Estilizando o Texto

````dart
void main(){
  runApp(Center(
    child: Text(
      'Olá, Mundo!!!',
      textDirection: TextDirection.ltr,
      style: TextStyle(
        color: Colors.blue,
        fontSize: 40,
        fontWeight: FontWeight.bold,
        fontStyle: FontStyle.italic,
        decorationColor: Colors.red,
        decorationStyle: TextDecorationStyle.wavy ,
    ),
  )));
}
````


## Conceitos aprendidos:

- Widget TextStyle para estilização

- Propriedades de cor, tamanho e peso da fonte

- Decorações de texto

## 🏗️ Passo 3: Criando um Widget Personalizado (StatelessWidget)

````
void main(){
  runApp(Directionality(
    textDirection: TextDirection.ltr, 
    child: WidgetSemEstado(),
    )
  );
}

class WidgetSemEstado extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Center(
      child: Text(
        'Olá, Mundo!!!',
        style: TextStyle(
          color: Colors.blue,
          fontSize: 40,
          fontWeight: FontWeight.bold,
          fontStyle: FontStyle.italic,
          decorationColor: Colors.red,
          decorationStyle: TextDecorationStyle.wavy ,
      ),
    ));
  }
}
````

## Conceitos aprendidos:

- Widget Directionality para definir direção do texto

- Criação de widgets personalizados com StatelessWidget

- Método build() obrigatório

- Organização do código em classes

## 📝 Passo 4: Widget com Parâmetros
````dart
void main(){
  runApp(Directionality(
    textDirection: TextDirection.ltr, 
    child: WidgetSemEstado('Olá, Mundo!!!'),
    )
  );
}

class WidgetSemEstado extends StatelessWidget {
  final String texto;

  WidgetSemEstado(this.texto);

  @override
  Widget build(BuildContext context) {
    return Center(
      child: Text(
        'Olá, Mundo!!!',
        style: TextStyle(
          color: Colors.blue,
          fontSize: 40,
          fontWeight: FontWeight.bold,
          fontStyle: FontStyle.italic,
          decorationColor: Colors.red,
          decorationStyle: TextDecorationStyle.wavy ,
      ),
    ));
  }
}
````

## Conceitos aprendidos:

- Passagem de parâmetros para widgets

- Construtor personalizado

- Propriedades final em widgets

## 👆 Passo 5: Adicionando Interatividade com GestureDetector

```dart
void main(){
  runApp(Directionality(
    textDirection: TextDirection.ltr, 
    child: WidgetSemEstado(),
    )
  );
}

class WidgetSemEstado extends StatelessWidget {

  @override
  Widget build(BuildContext context) {
    return Center(
      child: GestureDetector(
        onTap: (){
          print('O texto foi clicado!!!');
        },
        child: Container(
          decoration: BoxDecoration(
            shape: BoxShape.circle, 
            color: Colors.amber,
          ),
        width: 100,
        height: 100,
        ),
      ),
    );
  }
}
````

## Conceitos aprendidos:

- Widget GestureDetector para capturar gestos

- Widget Container para layout e decoração

- BoxDecoration para estilização avançada

- Callback onTap para interações

## 🔄 Passo 6: Widget com Estado (StatefulWidget)
```dart
void main(){
  runApp(Directionality(
    textDirection: TextDirection.ltr, 
    child: Container(color: Color(0xFFFFFFFF), child: Contador()),
    )
  );
}

class Contador extends StatefulWidget {

  @override
  State<Contador> createState() => _ContadorState();
}

class _ContadorState extends State<Contador>{
  int contador = 0;

  @override
  Widget build(BuildContext context) {
    return Center(
      child: GestureDetector(
        onTap: (){
          setState((){
            ++contador;
            print('Contador: $contador'); 
          });
        },
        child: Container(
          decoration: BoxDecoration(
            shape: BoxShape.circle, 
            color: Color(0xFF17A2B8),
          ),
        width: 100,
        height: 100,
        child: Center(
          child: Text('$contador'),
          ),
        ),
      ),
    );
  }
}
````

## Conceitos aprendidos:

- StatefulWidget para widgets com estado mutável

- Método createState() obrigatório

- Classe State separada para gerenciar o estado

- Método setState() para atualizar a interface

- Interpolação de strings com $

# 🔍 StatelessWidget vs StatefulWidget

## StatelessWidget

- Imutável: Não pode alterar seu estado após ser criado

- Performance: Mais eficiente, pois não precisa ser reconstruído

- Uso: Para widgets que exibem informações estáticas

- Estrutura: Apenas o método build() é necessário

````dart
class MeuWidgetEstatico extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return Text('Conteúdo fixo');
  }
}
````

## StatefulWidget

- Mutável: Pode alterar seu estado durante o ciclo de vida

- Performance: Menos eficiente, pois pode ser reconstruído várias vezes

- Uso: Para widgets que precisam responder a interações ou mudanças

- Estrutura: Requer duas classes - o widget e seu estado

````dart
class MeuWidgetDinamico extends StatefulWidget {
  @override
  State<MeuWidgetDinamico> createState() => _MeuWidgetDinamicoState();
}

class _MeuWidgetDinamicoState extends State<MeuWidgetDinamico> {
  String texto = 'Inicial';
  
  @override
  Widget build(BuildContext context) {
    return Text(texto);
  }
}
````

# 📚 Próximos Passos

### Layouts: Aprenda sobre Row, Column, Stack

### Navegação: Implemente navegação entre telas

### Formulários: Crie formulários com validação

### APIs: Integre com serviços web

### Estado Global: Use Provider ou Bloc para gerenciamento de estado

# 🛠️ Comandos Úteis
### Criar novo projeto
flutter create meu_app

### Executar o app
flutter run

### Verificar dependências
flutter doctor

### Limpar build
flutter clean

# 📖 Recursos Adicionais

- Documentação Oficial do Flutter

- Dart Language Tour

- Flutter Widget Catalog

Dica: Pratique cada passo e experimente modificar os valores para entender melhor como cada widget funciona!
