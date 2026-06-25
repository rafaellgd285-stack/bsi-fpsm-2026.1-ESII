# Diagnóstico do Sistema de Empréstimo — Rafael Assunção

## Problema 1

- O que a documentação diz:
A RN02 informa que o prazo mínimo de empréstimo deve ser de 1 dia.

- O que o código faz:
O método registrar() aceita qualquer valor informado para os dias do empréstimo, sem verificar se é maior que zero.

- Por que é um problema:
Isso permite criar empréstimos com prazo inválido, como 0 ou números negativos.

- (Já documentado? não)

---

## Problema 2

- O que a documentação diz:
No caso de uso UC03, quando não houver empréstimos em atraso, o sistema deve exibir a mensagem "Nenhum empréstimo em atraso".

- O que o código faz:
O método listar_atrasados() não mostra nenhuma mensagem quando a lista de atrasados está vazia.

- Por que é um problema:
O usuário pode pensar que o sistema travou ou não executou a consulta corretamente.

- (Já documentado? não)

---

## Problema 3

- O que a documentação diz:
O requisito RI02 determina que toda operação realizada com sucesso deve exibir uma confirmação clara ao usuário.

- O que o código faz:
Após registrar um empréstimo, o sistema não apresenta uma mensagem explícita informando que a operação foi concluída com sucesso.

- Por que é um problema:
O usuário não recebe confirmação e pode ficar em dúvida se o empréstimo foi realmente registrado.

- (Já documentado? não)

---

## Problema 4

- O que a documentação diz:
O requisito RI03 informa que toda operação inválida deve apresentar uma mensagem de erro descritiva.

- O que o código faz:
Quando o usuário digita uma opção inexistente no menu, o sistema não exibe uma mensagem de erro adequada.

- Por que é um problema:
O usuário não entende o que aconteceu e pode repetir o erro várias vezes.

- (Já documentado? não)

---

## Problema 5

- O que a documentação diz:
No documento projeto.md, a dívida técnica DT04 informa que o cálculo de multa está duplicado em dois métodos.

- O que o código faz:
O mesmo bloco de cálculo de multa aparece nos métodos devolver() e listar_atrasados().

- Por que é um problema:
Se a regra de cálculo mudar, será necessário alterar os dois locais, aumentando o risco de inconsistências.

- (Já documentado? sim)

---

## Problema 6

- O que a documentação diz:
A tabela de dívida técnica (DT01) aponta que o sistema deveria evitar o uso excessivo de variáveis globais.

- O que o código faz:
Diversas informações importantes são armazenadas em variáveis globais acessadas por diferentes partes do sistema.

- Por que é um problema:
Isso dificulta a manutenção e aumenta as chances de erros quando o sistema crescer.

- (Já documentado? sim)

---

## Problema 7

- O que a documentação diz:
A observação RNF04 destaca que o sistema deveria ser fácil de testar.

- O que o código faz:
O projeto não possui testes automatizados e mistura entrada de dados com a lógica principal.

- Por que é um problema:
Fica mais difícil verificar se alterações futuras quebraram alguma funcionalidade.

- (Já documentado? sim)