# Caso de uso: Professor cria uma nova Prova

Um professor deseja aplicar uma prova. Para isso ele precisa antes prepará-la. Esse caso de uso descreve como ele pode preparar um aprova e deixá-la salva no sistema para posterior aplicação.

Esta é uma versão muito simplificada. Veja no final desse documento algumas coisas que ainda podem ser melhoradas.

## Requisitos funcionais relacionados

* Professores podem criar provas
* Uma prova pode ser aplicada várias vezes
* Questões podem ser de múltipla escolha

## Pré-requisitos

* O professor deve estar autenticado (caso de uso [Autenticação de professores](autenticacao.md) )
* O professor está no índice para professores ( página index_professores.jsp )

## Fluxo principal

1. O professor clica na opção para criar uma prova
1. O sistema apresenta ao professor um formulário onde ele pode inserir o tema/assunto da prova.
1. O professor clica na opção para adicionar uma questão
1. O sistema lhe apresenta um formulário para adicionar uma questão
1. O professor insere o enunciado da questão
1. O professor insere as diferentes alternativas
1. O professor escolhe qual será a questão verdadeira
1. O professor clica na opção para enviar a nova questão
1. O sistema apresenta uma tela com a prova até então criada.
1. O professor pode escolher entre adicionar uma outra questão (volta para o ponto 4) ou terminar de preparar a prova (continua)
1. O sistema apresenta novamente a página de índice do professor

## Problemas que podem acontecer

### O professor se ausenta por muito tempo do sistema

O sistema deve bloquar a próxima requisição e redirecioná-lo para o índice incial (página index.jsp).

### O tema inserido já foi usado

O sistema deve apresentar uma mensagem informando o ocorrido e solicitando outro tema.

### O enunciado ou alguma alternativa foi esquecida

O sistema deve reapresentar a questão como estava com uma mensagem avisando da falha e intruindo o professor a como a corrigir.

### O professor sai para alguma página fora do fluxo padrão

Não é necessário fazer nada.

## Páginas

### Formulário para iniciar a criação de uma prova (formulario_prova.jsp)

* Deve conter um cabeçalho explicativo
* Contém um campo para inserção do tema da questão comm um rótulo de identificação
* Deve conter um botão com o texto "Adicionar Questão"

### Formulário para adicionar uma questão (formulario_questao_multipla_escolha.jsp)

* Deve conter um cabeçalho explicativo
* Deve conter um campo para inserção do enunciado da questão
* Deve conter 5 campos em que serão inseridos as alternativas da questão
* Deve conter 5 seletores ao lado de cada campo onde o professor pode escolher qual será a alternativa certa.
* Por padrão, a alternativa correta é a primeira
* Deve ter um botão escrito "Adicionar"

### Tela de apresentação da prova

* Deve conter um cabeçalho explicativo
* Deve conter duas opções em links ou botões:
  * A primeira é para adicionar outra questão, com o texto "Adicionar outra questão"
  * A segunda é para finalizar a contrução da prova, com o texto "Finalizar"

## Coisas que podem ser melhoradas

* Só pode ser feito um tipo de questão até agora (múltipla escolha)
* Só podem ser feitas questões com 5 alternativas
* Não pode ser inserido nada além de texto nas questões e afirmativas
* Todo o visual e dinâmica poderia ser feito em apenas uma página
