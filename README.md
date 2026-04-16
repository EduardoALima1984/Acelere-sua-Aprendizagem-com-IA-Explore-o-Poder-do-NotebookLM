# Acelere-sua-Aprendizagem-com-IA-Explore-o-Poder-do-NotebookLM
Desafio bootcamp

*Descrição do Projeto
Este projeto consiste na construção de um NotebookLM com foco em atuar como treinador de corrida personalizado, utilizando IA para gerar planos de treino com base em dados individuais do atleta.

*Objetivo:
Criar planos de treino personalizados
Simular comportamento de um treinador profissional
Garantir segurança (perguntas obrigatórias antes do plano)
Testar engenharia de prompts para controle de respostas
Curadoria de Fontes: 
Fontes de Video:
a) LIMIAR DE LACTATO: o treino que te faz evoluir - https://www.youtube.com/watch?v=Ev9NJOt5UdQ
b) Melhore sua Corrida com Estes 4 Exercícios Educativos! https://www.youtube.com/shorts/gig8rFgtAdo
c) como começar a correr com uma Planilha de corrida gratuita - https://www.youtube.com/shorts/Pu9sn1R2MTo

Foram adicionados mais links como fontes, mas os citados acima são os mais relevantes

Fonte Texto:
a) Atletis Blog: https://www.atletis.com.br/plano-de-treinos-para-corredores
b) Site Olympics.com: https://www.olympics.com/pt/noticias/treino-de-corrida-conheca-tipos
c) O2 corre, Planilha de treino: https://www.o2corre.com.br/planilhas-de-treinos/

Fonte Texto Colado:
a) texto colado: " Quero que atue como um treinador de corrida profissional, com experiência técnica e profissional para elaboração de um plano de corrida para uma data determinada e uma distancia a ser completada nesse dia. Tenha foco em questionar o peso, se a pessoa já corre, qual a distancia máxima que já percorreu, o tempo que levou, se tem problema de saúde ou alguma restrição e o tempo e dias disponível que tem para elaborar o treino."
b) Sempre que um novo corredor solicitar um plano, precisa obrigatoriamente solicitar as perguntas passada já anteriormente para a elaboração do plano. não emita de forma nenhuma o plano ou comentários sem ter todas as informações, de modo que seu retorno do plano seja focado no atleta a correr.  caso ainda fique faltando alguma resposta, solicite que seja respondido as perguntas pendentes e aguarde as respostas. somente com todas as respostas, sem exceção você pode responder com o plano de treino.

*Critério de seleção
  a)Conteúdo técnico confiável
  b)Experiência prática de atletas
  c)Materiais com aplicação real

* Engenharia de Prompts e “Cicatrizes”
Prompt 1 (Teste inicial)
"Irei realizar uma corrida de 5km no dia 26/04/2026, elabore um plano de treino para chegar na corrida em boas condições"

Resultado:
✔ Fez perguntas corretamente conforme Texto colado
✔ Identificou curto prazo
✔ Gerou plano coerente

Problema identificado:
Não conseguiu distinguir um corredor de outro e manteve o plano com base no primeiro corredor,

Solução: Incluir um novo texto colado com reset de atleta

Prompt 2 (correção para plano de um novo atleta)
" um novo atleta irá correr também no dia 26/04 5km, monte um plano para ele"

Resultado:
✔ Resetou o atleta
✔ Realizou as perguntas novamente
✔ Gerou o plano coerente

Problema identificado:
Retornou com plano de treino, mesmo sem saber todas as informações necessárias estabelecidas

Solução:
Revisão do reset do atleta, com um texto revisado passando que é vetado passar um plano de treino sem ter todas as informações por completo"

Prompt 3  (regra do bloqueio de emitir o plano sem ter todas as informações)

Resultado:
✔ Resetou o atleta
✔ Realizou as perguntas novamente
✔ não respondeu sem ter todas as perguntas chaves respondidas
✔ Gerou o plano coerente

Miniguia de Estudo (Entrega Final)
Resumo estruturado:
O treino de corrida deve ser organizado considerando o perfil de cada atleta, desde sua saúde, restrição de mobilidade, peso, se é um atrela iniciante ou avançado, de modo a evitar lesões ou afastamento
Tipos de treinos:
- Treino contínuo: corrida realizada num ritmo constante para aumento de resistencia
- Treino Intervalado (tiro): treina intervalado definido normalmente por uma distancia em ritmo alto e um intervalor de tempo para recuperação, corrida realizada para aumento do VO2
- Treino Regenerativo: Corrida em ritmo leve para recuperação muscular
- Longão: corrida de maior distância, focada na adaptação física e mental

Princiípios fundamentais:
- Progressão de Carga - aumento gradual do volume e intensidade do treino
- Especificidade: Treino destinado ao objetivo da prova a ser realizada
- Recuperação: Descanso para não perder o desempenho por sobrecarga
- Individualidade: Cada Atleta responde de forma diferente

Estratégias pré-prova
-Redução do volume de treino (tapering)
-Manutenção da intensidade
-Foco em descanso e alimentação
-Hidratação adequada

 Glossário ed Termos:
- Pace: ritmo de corrida (tempo por km)
- Tiros: treinos curtos em alta intensidade
- Volume: quantidade total de treino (km ou tempo)
- Periodização: organização do treino ao longo do tempo
- Tapering: redução do treino antes da prova
- Zona de esforço: intensidade do treino (leve, moderado, intenso)

Prompt Reutilizáveis:
1 - Coleta de dados do Atleta
Quero que atue como um treinador de corrida profissional. Antes de montar qualquer plano, faça perguntas obrigatórias para entender o perfil do atleta, incluindo:
- Peso
- Experiência com corrida
- Distância máxima já percorrida
- Tempo médio
- Restrições de saúde ou lesões
- Disponibilidade semanal de treinos

Não gere nenhum plano até que todas as informações sejam respondidas.

2- Geração do plano de treino
Com base nas informações fornecidas, elabore um plano de treino detalhado até a data da prova. Inclua:
- Treinos por dia da semana
- Tempo ou distância de cada treino
- Tipo de treino (leve, tiro, longo, etc.)
- Ritmo sugerido
- Tempo de aquecimento e desaquecimento
- Progressão ao longo das semanas

3 - Refinamento do plano
O plano está muito genérico. Quero um detalhamento completo por dia, incluindo:
- Distância exata ou tempo
- Ritmo (pace)
- Estrutura do treino (ex: tiros, descanso, recuperação)
- Objetivo de cada treino

4 – Regra de validação (segurança)
Não gere nenhum plano de treino sem ter todas as informações do atleta. Caso falte alguma resposta, solicite explicitamente os dados pendentes e aguarde. Só continue após todas as informações serem fornecidas.

5 - Novo Atleta
Considere que este é um novo atleta. Reinicie completamente a coleta de informações e não utilize dados anteriores. Siga todas as regras de validação antes de montar o plano.

Lições aprendidas
- A IA gera as respostas mesmo sem todas as variaveis respondidas, sem restrições claras, isso pode gerar planos ineficientes
- Prompts inicias tendem a gerar respostas genéricas
- Com interações constante é possivel refinar a qualidade das respostas
- Regras explicitas  (não gerar planos sem dados) teve o retorno desajado não alcançado com regras não tão explicitas
- Regras não tão explicitas, principalmente relacionado a informações obrigatórias pode levar a IA a responder , isso exige um ajuste mais rígidos para os próximos desenvolvimentos.

Resultado Final:
Com a estrutura de prompts definida consegui criar um sistema que:
- Simula um treinador de corrida
- Personaliza planos de acordo com o atleta
- Evita respostas genpericas
- Garante maior segurança nas recomnedações de acordo com o perfil e caractéristicas de cada atleta.
