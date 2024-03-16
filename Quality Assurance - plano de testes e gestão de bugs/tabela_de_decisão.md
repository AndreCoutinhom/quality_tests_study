# Tabela de decisão

O modelo abaixo segue o exemplo tratado em aula. Pode haver diferentes dados dependendo do teste a ser rodado.

| Variáveis              | 1                  | 2                 | 3                 | 4                               |
|------------------------|--------------------|-------------------|-------------------|---------------------------------|
| Login válido?          | Sim                | Não               | Sim               | Sim                             |
| Senha válida?          | Sim                | Não               | Não               | Não                             |
| Errou a senha 3 vezes? | Não                | Não               | Não               | Sim                             |
| Saída esperada         | Logar no AluraPic	 | Mensagem de erro	 | Mensagem de erro	 | Bloqueio no sistema por 15 min. |
