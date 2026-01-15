## *Modelagem Conceitual*

### *->* A modelagem conceitual é o passo inicial para se criar o banco de dados, nessa etapa serão projetadas todas as tabelas e os relacionamentos entre elas.

### Desta forma, os seguintes relacionamentos foram propostos:

*1_ACAD_HORA_PROF_MOD_MUSC* - Envolve os relacionamentos das tabelas: ACADEMIAS - HORARIOS - PROFESSORES - MODALIDADES: Neste relacionamento, cada unidade possui um
gerente cadastrado (1x1), e em cada unidade, várias modalidades podem ser oferecidas em vários horários por diferentes professores. No entando cada professor
pode oferecer apenas um tipo de modalidade, mas diferentes academias e diferentes horários, desde que não iguais.

*2_CHECKINS_ALUNOS_ACAD* - Envolve os relacionamentos das tabelas: ACADEMIAS - CHECK_INS - ALUNOS - CHECKINS_CONTAGEM: Neste grupo, um checkin pode pertencer a 
somente um aluno e uma academia, mas um aluno ou uma academia podem ter muitos checkins, portanto formam relacionamentos 1xN. A tabela de contagem de checkins 
guarda unicamente o ID de cada aluno, portanto o relacionamento com a tabela de alunos é 1x1.

*3_TREINOS_OBJETIVOS_METAS* - Envolve os relacionamentos das tabelas: ACADEMIAS - TREINOS - MODALIDADES - ALUNOS - OBJETIVOS - METAS - METAS_ALUNOS_COMPLETAS:
Neste grupo, um treino só pode ser registrado em uma academia para uma modalidadee por um aluno, no entanto, um aluno pode registrar ao longo do tempo muitos
treinos em diferentes academias e modalidades, caracterizando relacionamentos 1xN entre treinos e academias, treinos e modalidades e treinos e alunos. Os alunos
podem ter somente um objetivo cadastrado em seu perfil, mas o mesmo objetivo pode ser registrado para outros alunos, portanto surge um relacionamento 1xN. Os alunos
podem cadastrar várias metas e nesse caso, cada meta pertence a somente um aluno, já que é um registro pessoal e portanto, um relacionamento 1xN. Por fim, a tabela
METAS_ALUNOS_COMPLETAS registra cada aluno somente uma vez e desta forma, é feito um relacionamento 1x1 com a tabela alunos.

*4_MATRICULAS_PAGAMENTOS* - Envolve os relacionamentos das tabelas: MATRICULAS - PLANOS - ALUNOS - MODALIDADES E PAGAMENTOS. Uma matricula pode conter somente
um aluno, um plano específico e uma modalidade, no entanto, estes podem aparecer em diferentes matrículas, assim formam relacionamentos 1xN entre matriculas e
planos, matriculas e alunos e entre matriculas e modalidades. Da mesma forma ocorre com o relacionamento 1xN entre matriculas e pagamentos, uma vez que um registro
de pagamento é feito somente para uma única matrícula, mas cada matrícula terá diferentes registros na tabela de pagamentos, dada a recorrência deste processo.

*5_DESAFIOS_ALUNOS_MODALIDADES* - Envolve os relaciomentos das tabelas: DESAFIOS - DESAFIOS_TIPOS - ALUNOS E MODALIDADES. Nesse cenário, cada desafio pertence
a somente um tipo, mas cada tipo pode possuir diferentes desafios, portanto um relacionamento 1xN é definido. Quando relacionamos alunos com a tabela de desafios,
surge uma entidade relacional NxN uma vez que um desafio pode ser registrado para muitos alunos, e cada aluno pode realizar diferentes desafios ao longo do tempo.
No entanto, surge uma particularidade aqui nesse cenário, pois os desafios que contabilizam treinos para a mesma modalidade guardam não apenas o id do desafio,
mas o id da modalidade, e então quando relacionamos alunos com desafios e modalidades, cria-se uma outra entidade relacional tripla NxNxN que guarda o progresso
dos alunos justamente nesses desafios.

*6_SORTEIOS_RECOMPENSAS_RESGATES* - Envolve os relacionamentos das tabelas: ALUNOS - PONTOS - RECOMPENSAS E SORTEIOS: Os alunos recebem pontos ao interagirem com
a academia, esses pontos são registrados de forma única para cada aluno na tabela de pontos, portanto cria-se um relacionamento 1x1 entre as tabelas. As academias
podem realizar sorteios de recompensas e nesse caso, um sorteio contém apenas uma recompensa mas uma recompensa pode ser sorteada várias vezes, portanto um 
relacionamento 1xN entre essas duas tabelas. Por fim, os alunos podem realizar o resgate de recompensas usando seus pontos e cada aluno pode resgatar diferentes
recompensas e estas podem ser resgatadas diversas vezes por diferentes alunos, portanto cria-se uma entidade relacional NxN para esse relacionamento.  