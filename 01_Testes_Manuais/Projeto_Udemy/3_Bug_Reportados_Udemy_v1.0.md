# 🐞 Bug Reports - Udemy

## 🧩 BUG-1

| Campo | Valor |
|-------|-------|
| CT Relacionado | CT.05 |
| ID do Bug | QAUDEMY-13 |
| Título do Bug | BUG - [Frontend] Erro 404 na Busca: Sistema envia parâmetro "undefined" na URL |
| Severidade | Alta (Porque o sistema quebrou e mostrou uma tela de erro em vez de só avisar o usuário que não podia pesquisar vazio.) |
| Prioridade | Alta (Porque pesquisar é a coisa mais importante do site, e dar erro logo na cara assusta quem quer achar um curso.) |
| Descrição do Problema | Ao tentar realizar uma busca vazia, o sistema monta a URL incorretamente inserindo a string "undefined", gerando erro 404. |
| Passos para Reproduzir | # Acessar a Home Page da Udemy (deslogado).
# Abrir o DevTools (F12) > aba Network.
# Clicar no botão de busca (lupa) sem digitar nada. |
| Resultado Esperado | O sistema deveria ignorar a ação ou solicitar um termo válido. |
| Resultado Atual | Redirecionamento para ".../courses/search/undefined/" com erro 404.

*Evidência Técnica:*
Log: GET [https://www.udemy.com/courses/search/undefined/|https://www.udemy.com/courses/search/undefined/] 404 (Not Found) |
| Ambiente de Teste | S.O: Windows 11

Navegador: Google Chrome 143.0.7499.170 (64 bits)

Modo: Guia Anônima

Resolução: Desktop

Ferramentas: DevTools (Console e Network) |
| Evidências/Anexos | CT05_CT.05 – [Filtros] – Validar exclusão de cursos gratuitos ao filtrar por Preço (Pago).mp4
CT05_CT.05 – [Filtros] – Validar exclusão de cursos gratuitos ao filtrar por Preço (Pago).png |
| Observações Técnicas | nan |

---

## 🧩 BUG-2

| Campo | Valor |
|-------|-------|
| CT Relacionado | CT.07 |
| ID do Bug | QAUDEMY-14 |
| Título do Bug | BUG - [Busca/Backend] Perda de Relevância e Erro de Autenticação em Paginação Profunda (Pág 220+) |
| Severidade | Média (Porque dá um erro nos bastidores que faz a pesquisa perder o sentido, mas o site todo não cai, dá para continuar navegando.) |
| Prioridade | Baixa (Porque é muito difícil alguém ir clicando até a página 220 de resultados na vida real, então poucos usuários vão ver isso.) |
| Descrição do Problema | Ao navegar para uma página de resultados muito avançada (p=220) na busca por "javascript", o sistema perde o contexto da pesquisa devido a uma falha de autenticação na API de busca ({{Not signed in with the identity provider}}). Como resultado, o motor de busca para de filtrar pelo termo pesquisado e retorna cursos genéricos e irrelevantes (Unity, Unreal, Kintone), quebrando a regra de negócio de busca. |
| Passos para Reproduzir | # Acessar a Home Page da Udemy (em modo anônimo/deslogado).
# Digitar "javascript" no campo de busca e pressionar Enter.
# Aplicar o filtro de nível "Iniciante" (Instructional Level).
# No campo de URL, alterar o parâmetro de paginação para {{&p=220}} (ou navegar manualmente até o limite da paginação).
# Abrir o DevTools (F12) > aba Console. |
| Resultado Esperado | O sistema deve continuar exibindo cursos relacionados a "javascript" ou informar que não existem mais resultados para este termo. |
| Resultado Atual | O sistema ignora o termo "javascript" e exibe cursos de tecnologias distintas (Unity/Unreal), caracterizando falha de relevância no motor de busca.

*Evidência Técnica:*

* *Erro de Console:* {{FedCM get() rejects with NetworkError: Error retrieving a token.}}
* *Evidência Visual:* Cards de curso de "Unity" sendo exibidos para uma busca de "Javascript". |
| Ambiente de Teste | S.O: Windows 11 pro

Navegador: Google Chrome 143.0.7499.170 (64 bits)

Modo: Guia Anônima

Resolução: Desktop (Janela Redimensionada com Console) |
| Evidências/Anexos | CT.07 - [Filtros] - Validar segmentação por nível Iniciante.mp4
CT.07 - [Filtros] - Validar segmentação por nível Iniciante.png |
| Observações Técnicas | nan |

---

## 🧩 BUG-3

| Campo | Valor |
|-------|-------|
| CT Relacionado | CT.08 |
| ID do Bug | QAUDEMY-15 |
| Título do Bug | Bug - [Busca] Quebra de Relevância: Termo "Excel" retorna conteúdo não relacionado. |
| Severidade | Média (Porque o site continua funcionando normal, mas a inteligência da busca está falhando ao trazer coisas muito erradas.) |
| Prioridade | Alta (Porque pode atrapalhar o aluno a achar o curso certo e a plataforma pode acabar perdendo algumas vendas por causa da confusão.) |
| Descrição do Problema | Ao realizar uma busca específica pela palavra-chave "Excel" e aplicar filtros de refinamento (Gratuito + Iniciante + Alta Avaliação), o sistema apresenta nos resultados um curso de idioma/caligrafia árabe. Isso caracteriza uma falha na precisão do motor de busca, entregando conteúdo sem relação semântica ou contextual com o termo pesquisado. |
| Passos para Reproduzir | # Acessar a Home Page da Udemy (em modo anônimo/deslogado).
# Digitar "Excel" no campo de busca e pressionar Enter.
# No menu lateral, aplicar a interseção de filtros:
#* Preço: *Gratuito*
#* Nível: *Iniciante*
#* Classificação: *4.5 ou mais*
# Realizar o scroll e analisar os cards apresentados na lista de resultados. |
| Resultado Esperado | O sistema deve exibir estritamente cursos relacionados a planilhas eletrônicas ou ao ecossistema Microsoft Excel. Cursos de outros idiomas ou tópicos (como caligrafia) devem ser excluídos pelo algoritmo de relevância. |
| Resultado Atual | O sistema exibe um card de curso com título e descrição em caracteres árabes (focado em ensino da escrita árabe), poluindo a lista de resultados técnicos e diminuindo a confiança na ferramenta de busca. |
| Ambiente de Teste | S.O: Windows 11 Pro

Navegador: Google Chrome 143.0.7499.170 (64 bits)

Modo: Guia Anônima

Dispositivo: Notebook desktop |
| Evidências/Anexos | CT.08 - [Filtros] - Validar combinação de filtros (Interseção).mp4 |
| Observações Técnicas | nan |

---

## 🧩 BUG-4

| Campo | Valor |
|-------|-------|
| CT Relacionado | CT.09 |
| ID do Bug | QAUDEMY-16 |
| Título do Bug | Bug - [Busca] - Falha Crítica de Relevância e Persistência de Filtro Pós-Remoção. |
| Severidade | Alta (Porque a tela mente para o usuário, mostrando que tirou o filtro, mas não tira de verdade, travando os resultados antigos.) |
| Prioridade | Média (Porque quem usa bastante os filtros vai ficar confuso achando que está vendo cursos novos, e vai ter que atualizar a página na mão.) |
| Descrição do Problema | Ao realizar uma busca pela palavra-chave *"Excel"* e navegar até a página 3 com os filtros *Gratuito + Classificação 4.5+* ativos, o sistema apresenta cursos de caligrafia árabe e renda fixa, ignorando o termo de busca original. Adicionalmente, ao tentar remover o filtro de classificação no final da execução, o sistema retira a tag visual e atualiza a URL, mas falha em atualizar os resultados, mantendo a lista de cursos idêntica à anterior. |
| Passos para Reproduzir | # Acessar a Home Page da Udemy (em modo anônimo/deslogado).
# Digitar *"Excel"* no campo de busca e pressionar Enter.
# No menu lateral, aplicar a combinação de filtros:
#* *Preço:* Gratuito
#* *Classificação:* 4,5 e acima
#* *Nível:* Iniciante
# Remover o filtro de *Nível: Iniciante* através do painel lateral.
# Navegar até a *Página 3*.
# Analisar os cards de cursos apresentados (Notar presença de cursos de Árabe e Renda Fixa). |
| Resultado Esperado | O sistema deve exibir estritamente cursos relacionados a "Excel" em todas as páginas, respeitando a palavra-chave. Ao remover o filtro de classificação, a interface deve atualizar imediatamente (Refresh) para incluir cursos com avaliações inferiores a 4.5 que sejam gratuitos. |
| Resultado Atual | O sistema apresenta cursos de *"Escrita Árabe"* e *"Renda Fixa"* na página 3 *[01:37s]*, mesmo com a palavra-chave "Excel" ativa na URL. Após o comando de remoção do filtro de classificação *[01:51s]*, a tag é removida, mas os resultados na tela *[01:52s]* permanecem estagnados e idênticos aos anteriores, ignorando a expansão do critério de busca. |
| Ambiente de Teste | S.O: Windows 11 Pro

Navegador: Google Chrome 143.0.7499.170 (64 bits)

Modo: Guia Anônima

Dispositivo: Notebook desktop |
| Evidências/Anexos | CT.09 Limpeza Individual de Filtro.mp4
CT.09 Limpeza Individual de Filtro.png |
| Observações Técnicas | nan |

---

## 🧩 BUG-5

| Campo | Valor |
|-------|-------|
| CT Relacionado | CT.10 |
| ID do Bug | QAUDEMY-17 |
| Título do Bug | Bug - [Busca/Filtros] - Perda de persistência do filtro de preço ao alterar o termo de pesquisa na barra superior. |
| Severidade | Baixa (Porque não é um erro grave do sistema, é só o jeito que o site lida com buscas novas que é um pouco chato para quem usa.) |
| Prioridade | Baixa (Porque dá para usar o site tranquilo, é só o usuário marcar o filtro de novo se quiser. Não impede ninguém de comprar curso.) |
| Descrição do Problema | Ao aplicar um filtro de refinamento (ex: "Gratuito") em uma busca inicial, o sistema não retém esse estado de filtragem ao realizar uma nova consulta. Quando o usuário digita um novo termo na barra de pesquisa, o motor de busca realiza um "reset" completo da _Query String_, ignorando as preferências já selecionadas pelo usuário. Isso gera uma falha de usabilidade (UX) e obriga o usuário a repetir ações manuais desnecessárias a cada nova pesquisa. |
| Passos para Reproduzir | # Acessar a Home Page da Udemy (em modo anônimo/deslogado).
# Digitar *"Javascript"* no campo de busca e pressionar Enter.
# No menu lateral, aplicar o filtro de *Preço: Gratuito*.
# Validar que a página carregou apenas cursos gratuitos (Selo "Gratuito" visível).
# Sem fechar a página, clicar na barra de busca superior, apagar o termo "Javascript" e digitar *"React"*.
# Pressionar Enter e observar o comportamento do filtro lateral e da URL. |
| Resultado Esperado | O sistema deve realizar a nova busca mantendo o filtro "Gratuito" ativo. A URL resultante deveria ser uma combinação do novo termo com o parâmetro de preço (ex: {{q=React&price=price-free}}). |
| Resultado Atual | O sistema limpa todos os filtros ativos. A tag "Gratuito" desaparece e a lista de resultados passa a exibir cursos pagos para o termo "React". A URL é limpa de qualquer parâmetro de filtragem pré-existente, mantendo apenas o parâmetro de busca {{q=React}}. |
| Ambiente de Teste | S.O: Windows 11

Navegador: Google Chrome 143.0.7499.170 (64 bits)

Modo: Guia Anônima

Dispositivo: Desktop |
| Evidências/Anexos | CT010 - Nova Busca com Filtro Ativo.mp4
CT010 - Nova Busca com Filtro Ativo.png |
| Observações Técnicas | nan |

---

## 🧩 BUG-6

| Campo | Valor |
|-------|-------|
| CT Relacionado | CT.11 |
| ID do Bug | QAUDEMY-18 |
| Título do Bug | Bug - [Busca/UX] - Inexistência de estado "Zero Resultados". |
| Severidade | Baixa (Porque não é um defeito no código. O site foi feito para preferir empurrar qualquer curso em vez de falar que não achou.) |
| Prioridade | Baixa (Porque a empresa quer vender, então exibir qualquer curso é até uma estratégia deles. Eles não vão querer mudar isso com urgência.) |
| Descrição do Problema | O sistema de busca da Udemy opera com uma lógica de _fallback_ (contingência) extremamente agressiva que impede a visualização da página de "Nenhum resultado encontrado", conforme planejado no *CT.11*. Ao inserir termos aleatórios ou aplicar filtros contraditórios, o motor de busca ignora a especificidade da consulta e força a exibição de cursos populares ou vagamente relacionados, em vez de admitir a ausência de conteúdo. Além disso, a interface lateral desabilita a seleção de filtros que resultariam em zero resultados, bloqueando a execução de cenários de exceção. |
| Passos para Reproduzir | # Acessar a Home Page da Udemy em modo anônimo e deslogado.
# Digitar uma string aleatória na barra de busca (ex: {{null_results_qa_test_999}} ou {{jkqlpzm123_test_zero}}).
# Pressionar Enter.
# Tentar aplicar interseções de filtros restritivos no menu lateral (ex: Preço: *Gratuito* + Nível: *Especialista*).
# Analisar o comportamento da página de resultados e do menu lateral. |
| Resultado Esperado | O sistema deve exibir uma mensagem clara informando que não foram encontrados cursos para o termo exato pesquisado. A interface deve oferecer opções de recuperação, como um botão para "Limpar todos os filtros". |
| Resultado Atual | O sistema apresenta "falsos positivos", exibindo cards de cursos de "Teste e QA" para strings aleatórias. O menu lateral impede ativamente a seleção de filtros que levariam ao estado de "Zero Match", exibindo {{(0)}} ao lado da opção e desativando o clique. |
| Ambiente de Teste | S.O: Windows 11

Navegador: Google Chrome 143.0.7499.170 (64 bits)

Modo: Guia Anônima

Dispositivo: Desktop |
| Evidências/Anexos | CT.11 - Filtro sem Resultados (Zero Match). image_01.jpg
CT.11 - Filtro sem Resultados (Zero Match). image_02.png
CT.11 - Filtro sem Resultados (Zero Match). image_03.jpg
CT.11 - Filtro sem Resultados (Zero Match). image_04.jpg
CT.11 - Filtro sem Resultados (Zero Match)..mp4
CT.11 - Filtro sem Resultados (Zero Match)..png |
| Observações Técnicas | nan |

---





## 💾 Download da Planilha Completa
Para auditar o documento original em Excel com todos os logs e métricas originais:

[👉 Baixar Report_Bugs_Udemy_v1.0.xlsx](./3_Bug_Reportados_Udemy_v1.0.xlsx)

---
[⬅️ Voltar para a Página Principal](index.html)
