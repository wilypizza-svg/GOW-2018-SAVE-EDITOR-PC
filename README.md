# Forja 2018 PC

**Editor de saves de God of War (2018) para PC, com uso offline e interface em português.**

O Forja permite escolher um salvamento dentro do arquivo completo `game.sav`, preparar alterações e exportar uma cópia para usar no jogo. Reúne gerenciamento de subsaves, recursos, equipamentos, encantamentos e progressão de armas em um único arquivo HTML.

**Versão documentada: 0.20.0.** Projeto independente conduzido por **José Murilo**, desenvolvido com análise de amostras reais e testes no jogo.

## Download e início rápido

1. Abra **Releases** neste repositório e escolha a versão desejada.
2. Em **Assets**, baixe o pacote `Forja_2018_PC_0_20_0_SO_EDITOR.zip`.
3. Extraia o ZIP e abra `Forja_2018_PC_0_20_0.html` no navegador do computador.

O pacote pronto funciona sem instalar Python, Node.js ou bibliotecas. No código-fonte, o HTML equivalente chama-se `Abrir_Editor.html`.

O processamento do save ocorre no navegador, no próprio computador. O editor pronto funciona offline e não precisa enviar o arquivo a um servidor.

> [!WARNING]
> **Cifras e a primeira viagem a Alfheim:** evite adicionar cifras de Muspelheim ou Niflheim antes dessa viagem. Isso pode travar a cena em que Freya pede para mover a ponte de Týr. Conclua essa sequência antes de usar a função. O editor mostra o aviso, mas não detecta automaticamente esse ponto da história.

## Funcionalidades

| Área | O que o editor permite fazer |
| --- | --- |
| Gerenciamento de saves | Escolher, extrair, importar e excluir subsaves na cópia do arquivo completo, com título e data para identificação. |
| XP e Hacksilver | Definir quantidades personalizadas nos registros reconhecidos. |
| Recursos | Alterar estoques e incluir recursos mapeados que ainda não estejam presentes. |
| Pacotes de recursos | Preparar grupos de materiais de uma vez, conforme o pacote e a quantidade escolhidos. |
| Equipamentos | Adicionar peitorais, braçadeiras, cinturas, pomos, cabos e talismãs disponíveis no catálogo, incluindo variantes normais e NG+. |
| Conjuntos de armadura | Preparar conjuntos e escolher a etapa disponível para as peças ausentes, preservando as já possuídas no lote. |
| Níveis de equipamentos | Ajustar as etapas previstas para cada perfil, respeitando a progressão da família. |
| Armas principais | Ajustar níveis reconhecidos do Machado Leviatã e das Lâminas do Caos. |
| Lâminas antecipadas | Adicionar a arma com o cabo padrão e preparar níveis de 1 a 5 desde o início da campanha normal, nos estados reconhecidos. |
| Ataques rúnicos | Adicionar ataques do Machado e das Lâminas conforme o catálogo integrado. |
| Encantamentos | Consultar 107 perfis: 92 do NG normal e 15 do NG+. Filtrar comuns/únicos e preparar perfis ausentes individualmente ou em lote. |
| Atributos e orvalhos | Definir bônus por orvalhos ou calcular a quantidade a partir de uma meta e dos valores informados pelo usuário. |
| Vida e capacidade de fúria | Ajustar totais de Maçãs de Iðunn e Chifres de Hidromel Sangrento reconhecidos. |
| Pedras de ressurreição | Adicionar ou repor pedras superior e berserker nos estados suportados. |
| Cifras dos reinos | Preparar partes de Muspelheim e Niflheim, com o aviso de progressão descrito acima. |
| Dificuldade | Alternar entre Balanced Experience e Challenge quando os campos do save forem reconhecidos. |
| Remoção | Retirar equipamentos mapeados e instâncias comuns de encantamento reconhecidas, conforme as restrições exibidas. |
| Revisão | Conferir as alterações, desfazer ajustes, baixar o arquivo completo, recuperar o original aberto e exportar um relatório JSON. |

**Catálogo de IDs e inclusão de itens são coisas diferentes:** encontrar um ID não significa que exista um perfil de inclusão para ele. As opções de edição dependem dos modelos e registros reconhecidos pelo editor.

## Como editar um save

1. Feche o jogo e guarde uma cópia do `game.sav` original em outra pasta.
2. Abra o arquivo completo no editor.
3. Em **Gerenciar saves**, escolha o salvamento pelo **título e pela data**. O número interno do slot pode ser diferente da posição na lista do jogo.
4. Prepare os recursos, equipamentos ou outros ajustes desejados.
5. Abra **Alterações** e confira o slot, os valores e os itens de cada linha.
6. Baixe a cópia `game.sav`, coloque-a no local usado pelo jogo e carregue o mesmo salvamento.
7. Confira o resultado no inventário, jogue um pouco, salve e recarregue para verificar a persistência.

Novos encantamentos ficam no inventário para equipar pelo próprio jogo. Os níveis de equipamentos seguem a progressão de cada família; uma etapa como `8+` é intermediária e não identifica, sozinha, um item NG+.

Para as marcas perfeitas, a conversão pelo jogo é **preferível** quando os requisitos estiverem disponíveis. A inclusão pelo editor continua permitida e preserva os equipamentos e materiais associados.

## Novidades da 0.20.0

- Aquisição antecipada das Lâminas do Caos integrada à seção **Níveis**, com o cabo padrão.
- Escolha dos níveis de **1 a 5** para as Lâminas no formato inicial reconhecido, sem exigir o primeiro upgrade pelo jogo.
- Aquisição e nível em linhas separadas na revisão. Desfazer a aquisição também retira o ajuste de nível dependente.
- Aviso de Alfheim nos controles de cifras, na revisão, nas instruções e no relatório JSON.

As rotinas anteriores de recursos, equipamentos, rúnicos, encantamentos e remoção foram preservadas. Consulte o [histórico de versões](CHANGELOG.md).

## Validação e limites conhecidos

A aquisição antecipada das Lâminas foi confirmada no jogo no início da campanha, perto do evento original e após a cutscene de aquisição. A implementação integrada reproduz os arquivos de teste aprovados.

> [!IMPORTANT]
> **Levar as Lâminas diretamente ao nível 5 no início é a parte nova da 0.20.0.** Ela passou nos testes automatizados de escrita, releitura e interface, mas ainda aguarda confirmação no jogo. Isso é distinto da aquisição antecipada, que já foi testada no jogo.

- O primeiro upgrade do Machado no NG normal mantém a regra anterior: deve ser feito no jogo quando o registro necessário ainda não existir.
- A disponibilidade de uma opção depende da coerência do save. Mapas divergentes, histórico incompleto ou estruturas desconhecidas podem bloquear a operação.
- A inclusão de recursos não conclui missões nem garante a liberação de receitas da loja. O jogo também pode limitar o efeito de quantidades e atributos.
- Os testes cobrem as amostras e os cenários descritos nos relatórios. Eles não constituem garantia para todo save ou sequência da campanha.

Veja o [roteiro da versão](ROTEIRO_0_20_0.md) e o [relatório de verificação](RELATORIO_0_20_0.md).

## Código e desenvolvimento

| Caminho | Conteúdo |
| --- | --- |
| `src/` | Interface, leitura, validação e rotinas de edição. |
| `data/` | Catálogos, perfis de itens e modelos de registros. |
| `build.py` | Montagem do editor em um HTML independente. |
| `Abrir_Editor.html` | Editor pronto gerado a partir do projeto. |
| `test_*.cjs` e `test_*.py` | Testes de estrutura, regressão, exportação e interface. |
| `VERIFICACAO_*.json` | Resultados registrados dos testes. |

Para reconstruir o HTML, use Python 3 na pasta do projeto:

```bash
python3 build.py
```

No Windows, se o Python estiver disponível pelo lançador `py`, o comando equivalente é `py -3 build.py`.

Os testes JavaScript usam Node.js. Os testes binários dependem das amostras e das versões de referência indicadas nos scripts; os saves pessoais não acompanham o repositório. Baixar o código e executar os testes sem essas amostras pode resultar em erro de arquivo ausente.

## Relatar problemas e contribuir

Abra uma **Issue** e informe a versão do editor, NG normal ou NG+, o título do subsave, as alterações realizadas e o momento exato da falha: leitura, exportação, carregamento ou inventário. Inclua a mensagem de erro e o resultado esperado.

Sugestões de interface, correções de nomes, novas amostras controladas e melhorias de validação são contribuições úteis. Para mudar rotinas binárias, apresente como a alteração foi verificada e quais funções anteriores foram comparadas.

## Autoria e referências

**José Murilo:** concepção, arquitetura, direção do desenvolvimento, coleta de amostras e validação no jogo. Implementação e análise realizadas com apoio de IA, incluindo o Codex.

Os metadados das listas de IDs e da loot table usadas no desenvolvimento estão em [data/catalog.json](data/catalog.json) e [data/loot-table.json](data/loot-table.json). A identificação de um registro é tratada separadamente da validação de sua edição.

O Forja é um projeto independente, sem afiliação com a Santa Monica Studio ou a Sony.
