## Top Clientes

Uma loja quer saber quem são os melhores clientes olhando o histórico de transações. Cada transação tem o nome do cliente e um valor — positivo é compra, negativo é estorno. A ideia é montar um ranking, mas ignorando quem no fim das contas ficou com saldo zero ou negativo (estornou mais do que comprou).

Escreve uma função `topSpenders(transactions, n)` que recebe um array de `{ customer, amount }` e um número `n`, e devolve os `n` clientes que mais gastaram, no formato `{ customer, total }`, do maior pro menor total. Empate resolve por ordem alfabética do nome.

Dois detalhes que costumam passar batido: clientes com total ≤ 0 não entram de jeito nenhum, mesmo que faltem nomes pra completar o `n` — nesse caso retorna só quem sobrou. E o `sort` sozinho não resolve o empate alfabético se você comparar só o total, então presta atenção nisso.

Exemplo:

```js
transactions = [
  { customer: "Ana", amount: 120 },
  { customer: "Bruno", amount: 80 },
  { customer: "Ana", amount: -20 },
  { customer: "Carla", amount: 100 },
  { customer: "Bruno", amount: 20 },
  { customer: "Diego", amount: -50 },
];
topSpenders(transactions, 2);
// [{ customer: "Ana", total: 100 }, { customer: "Bruno", total: 100 }]
```

Diego some do ranking (ficou negativo), e Ana/Bruno/Carla empatam em 100 — como só cabem 2, fica Ana e Bruno pelo desempate alfabético.