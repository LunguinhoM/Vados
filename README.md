# Vados

Vados (Virtual Assistant for Dynamic Operations in the System) é um assistente virtual para desktop feito em C#. Ele permite que a pessoa execute tarefas comuns do computador, como criar pastas, mover arquivos ou abrir um site, escrevendo ou falando o que quer fazer, sem precisar navegar por menus ou conhecer atalhos.

O projeto foi desenvolvido como Trabalho de Conclusão de Curso do curso Técnico em Desenvolvimento de Sistemas da Etec Profª Anna de Oliveira Ferraz (Araraquara), e aprovado pela banca em 26 de novembro de 2025.

## Por que o Vados existe

Assistentes de voz para computador já existem. Cortana, Simon, XULIA e Dragon NaturallySpeaking foram alguns dos que analisamos durante a pesquisa. Todos têm reconhecimento de voz, mas percebemos que muitos deles pesam na mão de quem não tem familiaridade com tecnologia: excesso de funções, comandos personalizáveis que exigem configuração, telas com mais opções do que o usuário precisa.

A ideia do Vados foi ir na direção contrária. Ele faz menos coisas, mas a pessoa consegue entender o que está acontecendo desde o primeiro uso. O público principal são pessoas com pouca experiência com computadores.

## Como funciona

A tela principal tem um botão de microfone no centro e, logo abaixo, uma caixa para digitar o comando. Na parte superior ficam os atalhos para o histórico, o manual e as configurações.

O fluxo de um comando é sempre o mesmo:

1. A pessoa fala (ou escreve) o que quer fazer, em linguagem natural.
2. O Vados interpreta e mostra uma janela de confirmação com o que entendeu, por exemplo: "Você deseja renomear a pasta chamada viagens para fotos?".
3. Se a pessoa confirmar, o comando é executado, com uma mensagem indicando o andamento.
4. Se algo der errado, aparece o motivo do erro. A pessoa pode descartar a mensagem ou clicar em "Editar", que devolve o comando para a caixa de texto para ser corrigido.

Durante a gravação por voz, o áudio aparece como barras animadas, junto com a duração e os botões de pausar e encerrar.

## Funcionalidades

Comandos disponíveis:

- Pastas: criar, abrir, renomear, excluir, mover e duplicar.
- Arquivos: criar, abrir, renomear, excluir, mover, duplicar e operar sobre vários arquivos de uma vez.
- Aplicativos e sites: abrir programas instalados e endereços da web.

Um mesmo comando pode ser dito de mais de uma forma. Alguns exemplos:

```
criar uma pasta chamada Videos dentro da pasta praia
renomear a pasta chamada "viagens" para "fotos"
mover todos os arquivos com nome praia da pasta viagens para a pasta praia
criar um arquivo de texto chamado teste
abrir o site youtube
abrir o programa gamemaker
```

Outros recursos do aplicativo:

- Reconhecimento de voz e entrada por texto.
- Confirmação antes de executar qualquer comando, para evitar acidentes.
- Histórico de comandos com título, texto original e data e hora. Cada item pode ser editado (volta para a caixa de texto) ou apagado.
- Manual integrado, com uma página por comando contendo descrição, imagem ilustrativa e exemplos. Os comandos ficam listados em uma barra lateral, separados por categoria. Esse manual embutido é o que mais nos diferenciou dos programas que pesquisamos, que em geral dependem de documentação externa.

As pastas criadas pelo Vados ficam, por padrão, em uma pasta chamada `Vados` no disco local. Se já existir uma pasta com o mesmo nome, o Vados acrescenta um número ao final para diferenciá-las.

## Estrutura de dados

O histórico é a única informação persistida. O modelo é simples: cada usuário (identificado por um UUID) tem vários comandos, e cada comando guarda seu identificador, o tipo, a data e hora de execução e os caminhos alvo. O diagrama entidade-relacionamento completo está na seção 2.2 do documento do TCC.

## Como executar

O aplicativo foi desenvolvido para Windows e precisa de um microfone configurado para os comandos de voz. Os comandos por texto funcionam sem ele.

```
https://github.com/LunguinhoM/Vados
```

Depois, abra a solução no Visual Studio, restaure os pacotes NuGet, compile e execute.

## Limitações conhecidas

Por falta de tempo, e por termos priorizado as funções principais, algumas coisas previstas ficaram de fora:

- A tela de configurações existe na interface, mas não tem funcionamento. Ficaram de fora a escolha do dispositivo de entrada de áudio, o teste de microfone, a escolha de tema, a escolha de idioma e a aba "Sobre nós".
- Os comandos de alterar volume, brilho e horário não foram implementados.

## Próximos passos

- Ampliar a variedade de comandos.
- Implementar a tela de configurações (teste de microfone, dispositivo de entrada de áudio e informações de contato para dúvidas)

## Equipe

- Luiz André Almeida dos Santos
- Matheus Lunguinho de Moura
- Miguel Sievert Rodrigues
- Pedro de Oliveira Pelegrino

Orientadora: Profª Erica Scache Fabri
Avaliadora: Profª Gabriela dos Santos Gimenes

Etec Profª Anna de Oliveira Ferraz, Centro Paula Souza, 2025.
