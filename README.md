# Atualização 0.26.0

Três páginas novas, a partir de funções de outro editor de saves (créditos no fim deste arquivo), todas testadas no jogo:

- **Equipamento atual:** mostra, em somente leitura, o que o slot registra como equipado.
- **Trocar equipamento:** troca peitoral, braçadeiras, cintura e talismã por outra peça que o slot já possui.
- **Modificadores de encantamentos:** troca em massa o efeito e/ou o valor dos encantamentos, com filtros, ou edita um a um os equipados em cada peça. Os que o jogo limita são detectados e preservados.

As rotinas anteriores não foram alteradas. Consulte o [histórico de versões](CHANGELOG.md) e o [roteiro da versão](ROTEIRO_0_26_0.md).

# Forja 2018 PC

**Editor de saves de God of War (2018) para PC, com uso offline e interface em português.**

O Forja permite escolher um salvamento dentro do arquivo completo `game.sav`, preparar alterações e exportar uma cópia para usar no jogo. Reúne gerenciamento de subsaves, recursos, equipamentos, encantamentos e progressão de armas em um único arquivo HTML.

**Versão documentada: 0.26.0.** Projeto independente conduzido por **José Murilo**, desenvolvido com análise de amostras reais e testes no jogo.

## Download e início rápido

1. Abra **Releases** neste repositório e escolha a versão desejada.
2. Em **Assets**, baixe o pacote `Forja_2018_PC_0_26_0_SO_EDITOR.zip`.
3. Extraia o ZIP e abra `Forja_2018_PC_0_26_0.html` no navegador do computador.

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
| Desbloquear tudo do catálogo | Preparar em lote os itens ausentes disponíveis, com categorias, variante normal/NG+, etapa e recursos opcionais; preservar os já possuídos. |
| Equipamentos | Adicionar peitorais, braçadeiras, cinturas, pomos, cabos e talismãs disponíveis no catálogo, incluindo variantes normais e NG+. |
| Conjuntos de armadura | Preparar conjuntos e escolher a etapa disponível para as peças ausentes, preservando as já possuídas no lote. |
| Modificadores de encantamentos | Trocar em massa o efeito e/ou o valor dos encantamentos (com filtros) ou editar os equipados em cada peça. Os que o jogo limita são detectados e preservados. Testado no jogo. |
| Níveis de equipamentos | Ajustar as etapas previstas para cada perfil, respeitando a progressão da família. |
| Armas principais | Ajustar níveis reconhecidos do Machado Leviatã e das Lâminas do Caos. |
| Lâminas antecipadas | Adicionar a arma com o cabo padrão e preparar níveis de 1 a 5 desde o início da campanha normal, nos estados reconhecidos. |
| Ataques rúnicos | Adicionar ataques do Machado e das Lâminas conforme o catálogo integrado. |
| Invocações do Atreus | Adicionar as seis invocações ausentes no nível 3, individualmente ou em lote, após obter ao menos uma pelo jogo. |
| Encantamentos | Consultar 107 perfis: 92 do NG normal e 15 do NG+. Filtrar comuns/únicos e preparar perfis ausentes individualmente ou em lote. |
| Atributos e orvalhos | Definir bônus por orvalhos ou calcular a quantidade a partir de uma meta e dos valores informados pelo usuário. |
| Vida e capacidade de fúria | Ajustar totais de Maçãs de Iðunn e Chifres de Hidromel Sangrento reconhecidos. |
| Pedras de ressurreição | Adicionar ou repor pedras superior e berserker nos estados suportados. |
| Cifras dos reinos | Preparar partes de Muspelheim e Niflheim, com o aviso de progressão descrito acima. |
| Dificuldade | Alternar entre Balanced Experience e Challenge quando os campos do save forem reconhecidos. |
| Desequipar armadura | Retirar separadamente peitoral, braçadeiras e cintura reconhecidos, mantendo as peças no inventário. A cintura fica mantida por padrão. |
| Equipamento atual | Consultar, em somente leitura, o que o jogo registra como equipado no slot: machado, lâminas, peitoral, braçadeiras, cintura, talismã, escudo, armadura do Atreus, Mimir e Bifrost, com o nível gravado. |
| Trocar equipamento | Trocar peitoral, braçadeiras, cintura e talismã por outra peça que o slot já possui. Só troca por peças possuídas; não adiciona peças ao inventário. Funciona só com o selecionado do slot e entra na Revisão como qualquer outra alteração. |
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

## Novidades da 0.26.0

**Modificadores de encantamentos.** Escolha o efeito atual, o valor atual (opcional), o novo efeito e/ou o novo valor e o alcance (todos ou só os equipados). A tela mostra antes quantos encantamentos serão alterados e quantos serão ignorados por limite do jogo. Ex.: todos os "Vitalidade 10" viram "Vitalidade 1000" e os demais ficam como estão. Também é possível editar individualmente os encantamentos equipados de cada armadura ou talismã, sem a peça estar em uso.

O editor detecta os encantamentos limitados pelo jogo (os que têm vínculo de origem, comuns entre os únicos encontrados no mundo) e não os altera. A gravação troca só o efeito e o valor dentro do próprio encantamento: nada é criado, removido ou movido, e um efeito repetido no mesmo encantamento é recusado.

**Validação:** sete saves de teste foram abertos no jogo e mostraram os valores gravados (Vitalidade 1000 em massa, Sorte 100 num save natural de 2022, troca de efeito, Força 20.000, Defesa 500 num único incluído pelo Forja, Rúnico e convivência com o Hacksilver). Encantamentos com vínculo de origem permanecem bloqueados e não foram testados.

**Equipamento atual e Trocar equipamento** também foram testados no jogo; os detalhes estão no [histórico de versões](CHANGELOG.md).

## Novidades da 0.25.0

Corrige a seleção de níveis das armas no NG+, aceita fragmentos residuais quando a capacidade de fúria já atingiu o limite e amplia o reconhecimento de armaduras pela sequência nativa e pelos outros slots do arquivo. A remoção dispensa confirmar que a peça está desequipada e preserva sua seleção até a troca no jogo. Novo Jogo+ integrado em Campanha e inventário com o bit 08 aprovado pelo usuário.

## Novidades da 0.24.0

Em **Equipamentos e melhorias → Desbloquear tudo do catálogo**, escolha as categorias e prepare as inclusões de uma vez. O painel reúne armaduras, pomos, cabos, talismãs, rúnicos de Kratos, invocações do Atreus e encantamentos. Permite filtrar normal, NG+ ou ambos e escolher a base ou a última etapa dos equipamentos ausentes.

**Materiais, XP e Hacksilver são opcionais** e começam desmarcados. Quando escolhidos, os estoques são elevados até o mínimo informado, preservando valores maiores. Os itens únicos ausentes recebem total 1.

As peças e os encantamentos já possuídos ficam preservados. Cada inclusão usa os perfis existentes e aparece na revisão. O painel mostra quantos itens podem ser preparados e quais ficaram indisponíveis, com os motivos. As regras próprias de Zeus, dos rúnicos e das invocações do Atreus continuam valendo. O lote trata a incompatibilidade anterior entre o amuleto e a marca de Kvasir sem enfraquecer as verificações individuais.

Os novos lotes passaram pelas conferências locais e precisam do teste no jogo. Consulte [ROTEIRO_0_24_0.md](ROTEIRO_0_24_0.md) e [RELATORIO_0_24_0.md](RELATORIO_0_24_0.md). A função integrada de desequipar armadura da 0.23.0 já recebeu confirmação de funcionamento do usuário.

A ativação da opção **Novo Jogo+ no menu** está em um pacote de ensaios separado. Ainda não foi integrada. Desbloquear itens do catálogo não inicia uma campanha nem altera a história, as cifras, os níveis das armas principais ou os bônus por orvalhos.

## Novidades da 0.23.0

Em **Equipamentos e melhorias → Desequipar armadura**, marque **Retirar peitoral**, **Retirar braçadeiras** e/ou **Retirar cintura**, depois use **Preparar retirada das peças**. Confira a revisão e exporte a cópia. Nenhuma peça é marcada inicialmente; a cintura só sai quando você a escolhe.

A função desequipa, mantendo a posse, as melhorias e os encantamentos de cada peça. Reequipa-se normalmente pelo jogo. Não é uma troca cosmética: os bônus da peça podem deixar de valer quando ela está desequipada. O visual sem cintura pode ficar estranho.

O editor usa os perfis conhecidos e, quando todas as três posições podem ser delimitadas e verificadas, reconhece o bloco completo pela estrutura. Uma seleção parcial desconhecida fica indisponível. Nesse caso, equipe a peça correspondente do **Viajante normal**, salve e reabra o arquivo. O editor não tenta adivinhar posições ausentes.

**Validação:** os três testes de peitoral/braçadeiras foram confirmados pelo usuário, inclusive após salvar pelo jogo. A integração produz exatamente os mesmos arquivos. O par nativo da cintura confirma a seleção independente dessa peça; o inverso foi verificado localmente por dois leitores. Após a entrega, o usuário confirmou o funcionamento da função integrada, incluindo a retirada da cintura. Essa confirmação corresponde às amostras testadas. Consulte [ROTEIRO_0_23_0.md](ROTEIRO_0_23_0.md) e [RELATORIO_0_23_0.md](RELATORIO_0_23_0.md).

As rotinas anteriores de gravação e os catálogos foram preservados. A função do Atreus da 0.22.0 recebeu confirmação de funcionamento pelo usuário; a amostra não identifica individualmente quais das seis inclusões ele testou.

## Novidades da 0.22.0

Acrescenta **Invocações rúnicas · Atreus** ao seletor **Tipo**, dentro de **Equipamentos e melhorias**. O catálogo reúne Bitter Squirrel, Murder of Crows, Wrath of the Wolf, a invocação do cervo (`SummonDeer`), Boar Stampede e Falcon’s Dive. Os mesmos perfis aparecem nos filtros normal e NG+.

A função inclui somente as ausentes no nível **3**, individualmente ou com **Adicionar ausentes deste filtro**. As já possuídas são preservadas, mesmo que estejam em 1 ou 2. Suas melhorias continuam pelo jogo. É necessário já ter conseguido ao menos uma invocação naturalmente.

A inclusão usa modelos nativos de cada identidade, em uma rotina própria do Atreus. Mantém a invocação equipada, receitas, tutorial, história, recursos e instâncias. As chaves de nível só são gravadas para o lobo e o cervo, que possuem evidência individual; as demais não são deduzidas por ordem. O formato máximo das novas linhas vem do subsave nativo com as seis invocações no 3.

**Validação da entrega original:** a escrita, a releitura por outro leitor, a interface e a preservação foram conferidas localmente. Depois, o usuário confirmou o funcionamento da função no jogo. A edição do nível de invocações já possuídas permanece fora desta função. Consulte [ROTEIRO_0_22_0.md](ROTEIRO_0_22_0.md).

## Correção da 0.21.2

Corrige o bloqueio de 8 e 8+ na reinclusão de cabos NG+ removidos. Contadores zerados sem nível anterior conflitante deixam de ser tratados como uma peça ainda registrada. Quando os quatro cabos por molde estão todos ausentes, desequipados e sem vínculos, o editor pode retirar seus quatro registros antigos de nível em conjunto antes de incluir a etapa escolhida. Nenhuma associação individual de chave é deduzida.

O nível 9 mantém a saída anterior. Cabos por molde já possuídos continuam com as melhorias pelo jogo; uma reinclusão parcial com níveis anteriores que não possam ser separados continua restrita ao nível 9. Cursed Flame + e os cabos normais mantêm os controles existentes. Consulte [ROTEIRO_0_21_2.md](ROTEIRO_0_21_2.md). As novas saídas passaram pela conferência local e aguardam a confirmação no jogo.

## Correção da 0.21.1

O reconhecimento das Lâminas deixa de exigir que o cabo padrão esteja equipado. A posse, os níveis, as melhorias e as referências continuam verificados; o cabo escolhido pelo jogador é preservado. Isso corrige o seletor vazio acompanhado da mensagem de propriedade secundária ausente em saves com outro cabo equipado.

O leitor também aceita um valor anterior de cena quando os dois mapas da arma e o histórico contínuo concordam com o nível ativo. Esse valor de cena fica intacto; a gravação usa a progressão reconhecida. Valores adiantados, duplicados ou incompatíveis continuam bloqueados.

No arquivo reportado, os 14 subsaves passaram pelo reconhecimento. No mais recente, as Lâminas aparecem no nível 5 e o Machado no 3, após a melhoria comprada no jogo. O usuário confirmou que reduzir o Machado e melhorá-lo na loja funcionou em uma amostra; a compra equivalente para as Lâminas continua pendente.

Os algoritmos que gravam as armas e a aquisição das Lâminas permanecem iguais à 0.21.0, assim como os catálogos e os demais gravadores. Consulte [ROTEIRO_0_21_1.md](ROTEIRO_0_21_1.md).

## Novidades da 0.21.0

- **Redução do nível das armas principais:** o Machado Leviatã e as Lâminas do Caos passam a ajustar também o histórico das melhorias e as receitas correspondentes. A redução reproduz o método dos saves DW_01 com receitas sincronizadas que foram testados no jogo. Materiais e referências de habilidades são preservados, sem reembolso de chamas.
- **Sincronização de ajustes antigos:** quando o nível exibido e as melhorias não correspondem, ou falta a receita da etapa reconhecida, o botão permite sincronizar esse nível.
- **Cabos NG+:** é possível escolher **8, 8+ ou 9 para novas inclusões** dos cinco cabos disponíveis. Blightguard +, Explosive Grips of Fire +, Grips of the Forgotten Flame + e Grips of the Valkyrie + usam a mesma clonagem já aprovada no nível 9. Suas novas inclusões em 8 e 8+ aguardam confirmação no jogo.
- Nos quatro cabos acima, uma peça já possuída é preservada; suas melhorias continuam pelo jogo. Na 0.21.0, a seleção de etapa dessas quatro peças valia apenas para inclusões sem registros anteriores. A correção da 0.21.2 amplia as reinclusões nos estados descritos acima. Os cabos normais e Cursed Flame + mantêm os controles anteriores.
- O gravador continua respeitando o limite global de **512 registros auxiliares**, inclusive em lotes. As rotinas de recursos, armaduras, pomos, talismãs, rúnicos, encantamentos e remoção mantêm seus formatos anteriores.

**Limites da validação:** a redução foi confirmada nas amostras testadas pelo usuário. A compra de uma nova melhoria do Machado na loja após reduzir foi posteriormente confirmada em uma amostra. O teste equivalente das Lâminas continua pendente. Subidas pelo editor foram verificadas localmente; isso não substitui essa validação da loja.

O seletor mantém as restrições de cada formato: nos saves NG+ reconhecidos apenas a partir do nível 2 do Machado, o nível 1 fica indisponível. A regra do primeiro upgrade do Machado no NG normal permanece quando o registro necessário ainda não existe. Consulte [ROTEIRO_0_21_0.md](ROTEIRO_0_21_0.md).

## Correção da 0.20.1

Corrige o bloqueio do nível das Lâminas após usar a arma e salvar novamente pelo jogo. Um identificador da fila de registros auxiliares era confundido com uma referência desconhecida da propriedade de nível. A leitura agora distingue os tipos de registro, inclusive cópias antigas dessa fila quando sua estrutura é reconhecida.

A correção mantém os mapas e o histórico de melhorias existentes, sem apagar os registros auxiliares ou alterar a história para contornar o bloqueio. Referências fora das estruturas reconhecidas continuam sujeitas às verificações anteriores.

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

Veja o [roteiro da versão](ROTEIRO_0_20_1.md) e o [relatório de verificação](RELATORIO_0_20_1.md).

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

**kg971:** autor do editor de saves de God of War (2018) usado como referência. As páginas **Equipamento atual**, **Trocar equipamento** e **Modificadores de encantamentos** do Forja partem de funções do editor dele, e fica aqui o crédito:

- **Equipamento atual:** a tabela de chaves de equipamento (machado, lâminas, escudos, armaduras, trajes do Atreus, Mimir e Bifrost) e o critério de quais registros de seleção indicam a peça ativa foram conferidos com os dele.
- **Trocar equipamento:** parte da ideia do "salvar equipamento" do editor dele, mas é mais restrita: não concede peças que o slot não possui.
- **Modificadores de encantamentos:** a ideia da troca em massa e da edição por peça, o critério de quais encantamentos o jogo limita (vínculo de origem) e a tabela dos códigos de nível dos encantamentos vêm do editor dele.

O Forja não inclui código nem arquivos do KG971. A leitura e a gravação usam as rotinas próprias do Forja, e os resultados foram comparados com leitores independentes e conferidos no jogo com saves de teste. Os nomes dos talismãs não vêm do KG971, que não os identifica: quase todos foram obtidos em testes no jogo e dois vêm dos perfis do próprio Forja.

O Forja é um projeto independente, sem afiliação com a Santa Monica Studio ou a Sony.
