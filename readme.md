# Atendimento

## Fluxo de Atendimento

- Toolbar: pega CPF e joga no Siebel.
- Já abre Prot. De At. no Siebel e deixa em branco, e então faz verificação de dados.
- Após cada atendimento, refresh em todas as páginas.

## Dicas de Trato ao Cliente

- Não ficar rebatendo, deixar o cliente reclamar e desabafar e então trazer para o problema.
- Não remoer o problema, focar na solução.

## Fraseologia

1. “Suporte Técnico Fibra, bom dia. Meu nome é Diego, com quem eu falo?”
2. “_Nome_, caso a ligação caia, peço que aguarde alguns segundos para eu fazer o retorno. Como posso te ajudar hoje?”
3. “Certo. Pra abrir seu atendimento, preciso confirmar algumas informações.
    1. CPF
    2. Telefone
    3. Banda Larga + Fixo”
4. “Os dados estão corretos?”
5. Tratativa...
6. “Te ajudo em algo mais”
7. “_Nome_, aproveito para lembrar que a OI oferece a assistente virtual Joice no whatapp e o aplicativo Minha OI, que são canais por onde você pode verificar dados da sua fatura, pedir segunda via e acessar funcionalidades de suporte técnico.”
8. “Aproveito também pra alertar que caso receba mensagens avisando que a OI irá acabar, desconsidere, pois, é provável tentativa de golpe ou fraude. Só realize contato conosco através dos canais oficiais.”
9. “Ficou alguma dúvida?”
10. “_Nome_, agradeço o contato. Vou te encaminhar para uma rápida pesquisa de satisfação, onde a primeira nota é sobre o meu atendimento e as demais notas são para a empresa. Uma boa semana, tchau, tchau!”

# Reparo e Remanejamento

## 2 Tipos de Tratativa

- Ordem de Serviço (OS): Remanejamento de Modem
  - Tem que ser mesma residência
  - Cliente tem que ter sinal
- Reparo (BD)
  - Quando cliente não tem sinal
- Se remanejamento aberto, não abrir reparo, e vice versa.
- OS nunca é cobrada, mas falar que pode se visita improdutiva.
- Não abre reparo para fixo. Manda pro avançado.
  - Só abre se cliente exigir. Avisar de visita improdutiva.
- Validar cancelamento de reparo:
  - Nome completo
  - Nome da mãe completo

## Reparo

### Abrir Reparo

- Abre-se reparo para
  - ONT desalinhada
  - LOSS
  - ONT desligada
  - Cliente pedindo VOIP para ONT Techcolor
- Confirmar endereço
  - Se esquina, pode ter 2 endereços, confirmar
  - Perfilar no Tela Única
  - Se endereço errado:
    - Corend

### Reagendar Reparo

- Na aba Reparos em Andamento
- Clica no número do reparo – Encaminhamentos
- Checar se está no prazo
- Ofertar o primeiro turno disponível
- Status fechado = não reabre, abre outro.
- Reagendar:
  - Cria protocolo no Vetor p/ Off
  - Faz reagendamento no SIEBEL
  - Endereço divergente: COREND

### Abrir Protocolo para Reparo

- Abre-se protocolo com máscara do TU
  - Dar tab até chegar nos números
  - 2001
  - Descrição: vem da Máscara Verde. Gera lá e cola aqui.
  - Se Máscara Verde Off, tem o formato no Conecta.
  - Clicar fora = salvou.

### Máscara Manual

- Input Manual ST Fibra (no Conecta)
- Célula: ST Fibra
- Máscara: o defeito do cliente
- Skill: disponível no Toolbar
  - Canto superior direito, painel azul
- Telefone Binado
  - Bloco de notas do toolbar
- Hierarquia
- Quando for abrir reparo, cola todos os defeitos que aparecem no NetQ

### Após Abrir reparo

1. Agendar: pode dar um de 3 erros
    - Sem slot = sem horário disponível = prazo de 48h
    - Erro de hierarquia – falha sistêmica
    - Fibra PE (Planta Externa)
    - Nesses casos, abre um ST OFF para agendar
        - Encaminha Protocolo
        - Prazo para retorno:
            - 24h PF
            - 8h PJ
2. Enviar

### Workflow

- Siebel: agenda ou reagenda
- TU: produz protocolo
- Vehtor: checa protocolo ou produz se TU down

## Remanejamento de Ponto

- Deve ter sinal
- Não pode ter inadimplência
- Cenários abarcados por remanejamento no Conecta OI
- Tudo depende do endereço
  - Endereço Divergente:
    - Manda pro SAC
  - Endereço Correto:
    - Abre OS
- Abrir Protocolo de Remanejamento no Tela Única
- Siebel:
  - Bundle Geral
  - Modificar
  - Linha amarela, procurar internet
  - Personalizar
  - Segue passo a passo no conecta
  - Agendar e enviar
  - Se sem data, envia sem agendar e comunica o prazo de 48h.

## Serviços

- ONT = modem
- VOIP: = fixo
  - Nunca abre reparo. Manda para suporte avançado.
- HSI = Internet
- IPTV / STB / Decoder = Televisão
  - Se cliente exigir visita, tem que abrir reparo

## Inadimplência

- 20 dias de atraso: bloqueio parcial
  - TV: total
  - Fixo: parcial (só recebe chamadas)
  - Internet: parcial;

## Informações da Fibra

### Três tipos de caixa

- Caixa CDOE (externa): rua
- Caixa CDOI (interna): residência
- Caixa CDOIA (andar): prédio

### Falha Massiva / Vulto / Evento

- Falha regional
- Após investigar, abre BA (reparo)

### Tipos de Fio

- Raiser: CDOI => ONTs do condomínio
- Drop: da CDOE à ONT do domicílio

### Tipos de Modem

- Huawei: 6T. Q2, VS
- ALCTL / Nokia: h40, 240, 1425, 2425
- ZTE: F670
- Só troca se queimar, não se o cliente pedir.
- Huawei e ZTE tem luzes iguais

# Sistemas

## NetQ

### Geral

- Pesquisar NetQ por GPON, por CPF pode ser que não funcione para mostrar vulto
- Se cliente tem mais de uma linha
  - Confirma com ele o endereço
  - Pega o GPON respectivo no SIEBEl
  - Acessa a linha correspondente no NetQ
- Se problema for lentidão, NeTQ não detecta
- Se Vulto: clica nele para pegar info do cliente e segue pelo OI Conecta
- Se HGW está cinza, pode-se acessar, na Aba Cadastro:
  - ID GPON
  - N série do equipamento
  - Na aba Cadastro

### Histórico de Operações

- - Mostra tudo que foi feito dentro do NetQ
    - Se o cliente fez algo na casa dele
    - Quando o modem foi reiniciado
      - No processo de VOIP ou lentidão, tem-se que dar o reboot na ONT. No histórico, pode-se ver se já foi reiniciado dentro da última hora.
    - Se uptime do modem for curto, significa que fez reboot recentemente

### Abas do NetQ

- - **DAL**: reabre ultimo diagnostico fechado
    - **Rede VTal**: apenas para fazer reboot
      - Atualizar pagina após reboot
      - Nunca orientar o cliente a apertar o botão reset no modem. Se o cliente fez isso antes da ligação, o atendente deve fazer as reconfigurações do modem.
    - **Rede Cliente**
      - Diagnóstico WAN:
        - Verificar uptime
        - Queda de Sinal :
          - Se houver, o IP reseta
          - E zera o uptime
          - Se o uptime for alto (+ de um dia), o problema não é queda de sinal, mas de navegação.
        - Queda de Navegação :
          - wifi não conectando ou muito lento
          - não está chegando na distância
          - site específico não está conectando
      - Diagnostico Lan – para conexões via cabo
        - Mostra as portas. Se aparece com o ícone verde do certinho, é por que tem algo conectado na porta.
        - Se o ícone é cinza, a porta está livre.
        - Clicar na porta dá dados sobre o que está concetado.
      - Diagnóstico WLAN
        - Exibe dispositivos ativos e inativos
        - Aqui não aparece conexões via cabo
        - Nunca clicar em desativar wi-fi
        - Se WLAN estiver desligada, orientar cliente a achar o botão WLAN e apertar
        - Se houver botão “Ativar Rádio”
        - Bandsteering: oferecer se
          - Nomes wifi forem diferentes
          - Modem suporta
          - Agiliza a internet e evita falhas de conexão/lentidão
        - Para teste de lentidão, pedir para desconectar tudo via cabo/wifi. Para isso usa essa aba e a anterior (LAN).
        - Aqui vê-se as duas conexões
          - 2.4 – conecta mais longe, com menos velocidade
          - 5 – conecta mais perto, com mais velocidade
        - Abaixo do nome da rede há um botão que pode estar de duas formas
          - Desativar rádio – JAMAIS CLICAR
          - Ativar rádio – pode clicar.

Caso dê problema de rede, deve-se orientar o cliente a fazer isso manualmente apertando o botão W-Lan no Wifi. Aperta 1 vez para ver se a luz acendeu. Se acendeu, checar no NetQ nessa aba, se a rede voltou a ficar verde. Aguarda com o cliente em linha alguns minutos para ter certeza de que o sinal do wifi vai ficar funcionando.

- - - - Tudo que fizer na 2.4 tem que fazer na 5. Só altera 4 itens
                - SSD (Nome da Rede WiFi)

Cliente informa

Pode ser feito no app Tecnico Virtual pelo cliente

- - - - - Beacon Type (Criptografia de Seg da Rede)

Huawey – WPA / WPA2

Nokia / ZTE - WPA

- - - - - Canal

Ativação do wifi: 2.4ghz:11 (Auto) / 5ghz: 149 (Auto)

Lentidão: aqui deixa em 1 e troca no final da ligação

- - - - - Password

Cliente informa

Pode ser feito no app Tecnico Virtual pelo cliente

Dica: trocou senha, recomenda a troca de nome também pois só trocar a senha exige que o cliente saiba esquecer a conexão nos aparelhos. Para evitar essa dor de cabeça, troca nome do wifi e pede para o cliene procurar o novo nome e concetar com a nova senha.

- BNG vermelho no NetQ = limpar sessão e reiniciar o modem. Se não resolver, mandar pro avançado. Se avançado não responder, mandar pro avançado.

### Alarmes NetQ

- São falhas identificadas no NetQ
- 83446 – Alarmes NetQ
- Tem a ver comn as cores do NetQ
  - Verde: conexão está funcionando, tem sinal = se cliente tem falha = falha não identificada
  - Vermelho: sem sinal ou conexão
  - Amarelo: está funcionando, mas pode parar
  - Cinza: NetQ não conseguiu a informação
  - Azul: informativo de possível falha
- Quando for analisar linha do cliente, analisa pela ordem que aparece na tela. Os 3 primeiros tem a ver com a internet.
  - GPON – força de conexão. Se este estiver vermelho, o restante não estará funcionando.
    - Potência Óptica: deve estar entre -7 e -27. Se fora, sinal está ruim.
    - OLT é a mesma coisa
    - Só clicar me estado da ONT para ver se tem algum erro já identificado.
  - NASS - programação
  - BNG – configuração de velocidade
  - VOIP - Telefone
  - HGW – Wifi
- Começa a analisar pelo item que estiver vermelho e desce. De cima para baixo.
- Se o número de série da ONT estiver diferente, manda para o avançado.
- Se a ONT queimada, reparo.
- Voit/IPTV: sempre avançado
- Serviços de internet: campo, sistematicamente ou avançado.
- Se falha identificada no sistema, não fale de visita improdutiva. Se está tudo verde, e cliente quer visita técnica.
- Se abrir reparo, não abre avançado.
- Se tudo verde no NetQ mas cliente ainda tem problema: checklist de reparo no Conecta.

## Vehtor

- Encaminhar para avançado ou ST Off
- Se TU funcionando, Vehtor é só para consulta
- Se TU não funcionando, Vehtor é para abrir protocolo
  - Avançado
  - ST Off
  - ST Off Prioridade
- Na abertura de protocolo
  - Fila: é para onde o protocolo está sendo encaminhado
  - Status: se estiver finalizado, precisa abrir outro
  - DT Vencimento: prazo para darem resposta (não para enviar técnico)
- Se Avançado tiver Prot fora do prazo
  - Abrir conferência, passa protocolo e transfere ligação
  - Se ninguém atender, manda pro supervisor e diz que vão entrar em contato

## ESOC

- NetQ: mostra a situação atual da conexão
- ESOC: mostra uma média mensal do status da conexão
- Traz informações do status da fibra
  - GPON
  - Velocidade
  - Se é cliente legado
  - Nível de perda do sinal
- Como pesquisar
  - Joga CPF do cliente no canto
- O que importa ao nosso departamento
  - Status da Fibra: qualidade do sinal.
    - Se vermelho: há uma falha física e obrigatoriamente deve encaminhar técnico na casa do cliente (mesmo que tudo estiver verde no NetQ), exceto:
      - Evento em andamento
      - Bloquei financeiro (NetQ vai estar vermelho)
      - OS em andamento (depende)
      - Reparo aberto nas últimas 48h
    - Se verde:
      - O cliente já ligou duas dentro de 30 dias (ou seja, tem 2 ou mais protocolos): obrigado fazer os testes de atendimento
      - Mais de 3 vezes: pergunta se quer fazer testes, se não quer, obrigatório mandar técnico.
    - Esses protocolos estão disponíveis no SIEBEL

## Conecta

- Pesquisar

## Tela única

- Perfilar chamada
- Encaminhar para avançado ou ST OFF
- NO CCD, é acessível por “Automação DRC”
- Se não disponível, pegar arquivo de mesmo nome na pasta wallace
- Cliente NAF vermelho = mandar técnico.
- Posse do Cliente:
  - Nova Fibra não aparece aqui
  - CNPJ não aparece aqui, mas perfila normalmente
- Não precisa adicionar Máscara Verde para avançado no TU
- Fazer máscara com dados pedidos no OI Conecta para Reparo
- Para Endereço Divergente
  - Tela Única gera um número, copia e cola no Vetor
  - Confirma se protocolo foi aberto no Vehtor
  - Copia a máscara para abrir protocolo no SIEBEL antes de transferir
    - Prot de Atendimento => Novo => Descrição => cola máscara
  - Informa ao cliente o prazo
    - 5 dias para entrar em contato e fazer mudança de endereço. Só então pode abrir para reparo.
  - Transferir para BO Fibra Corend

## Siebel / Salesforce

- Validar Atendimento Inicial
  - 3 primeiros números CPF
  - Número contato com wpp
  - Confirmar Pacote contratado (velocidade internet + fixo)
- Abrir remanejamento / reparo
  - Confirmar endereço
  - Se já houver reparo aberto: obrigatório oferecer nova data
- Duas abas
  - Contas: 99%
  - Contatos: apenas para atualizar telefone com WPP
- Verificar impedimentos
  - Inadimplência
  - Ativo diferente
  - Fraude
  - Bloqueio Cliente
  - OS em aberto (pedidos)
- Protocolo de Atendimento
  - Obrigatório em qualquer chamada

## Toolbar

- Bater ponto de entrada e saída
- Pausas
- Cair ligação = call-back
- Transferência de ligação
- Conferência
  - Para conectar a outro telefone sem cair a ligação;
- Smile
  - Verde: 1º ligação;
  - Amarelo: 2º ligação
  - Vermelho: já ligou 3 vezes ou mais

# Informações

## Para mim

- Ligação produtiva: entre 2min e 10 min;
- Identificar documento:
  - CPF: 11 números
  - CNPJ: 14 números
- Não atendemos TV: 10631
- Callback: ligar 3 vezes

## Para o Cliente

- Número de protocolo é enviado por SMS;
- Para atendimento humano, escolher lentidão;

# Cliente quer

## ...adquirir/cancelar serviços OI

- Entrar em contato com 4002 – 0888
- 0800 642 0 888

## ...liberar Portas

- Aparelho a liberar deve conectar no cabo.
- Cliente precisa de um segundo aparelho a cabo/wifi para fazer abertura de porta
- Se ONT não tiver etiqueta com dados de acesso, reparo p/ troca
- Se a abertura não funcionar, mandar para Avançado
- Se as luzes não resolverem, mandar para Avançado

# Máscaras

- OFF Avançado: só no Máscara Verde
- Reparo: tem no Conecta
- Máscara Verde: ao salvar um protocolo, o número do mesmo aparece lá em cima.

# Protocolos

- Encaminhar para Avançado
  - Se fizer no TU, basta
  - Se fizer manual no Vehtor, tem que adicionar Máscara Verde
  - Para ONT desalinhada, tem que adicionar máscara verde
- Checa no Vehtor
- Clica na folhinha, copia conteúdo e cola no SIEBEL
  - Em Protocolo de Atendimento
  - Com número do protocolo do Vetor
- Máscara do Conecta = Máscara Verde p/ abertura manual no Vehtor
  - Servem para abrir reparo
    - Cola a máscara na descrição do reparo
  - Ou para Avançado e Off
- TU: usado para
  - Protocolo de Atendimento no Siebel
    - Se TU down, usa Máscara Verde
  - OFF
  - Avançado
- Abrir reparo no Siebel
  - Se TU up, usa ele para copiar e colar na descrição
  - Se TU down, Máscara Verde para copiar e colar na descrição
- Off: somente para reparo

# Testes de velocidade

- Acima de 80% de download é aceitável
- Ping: precisa estar entre 18 e 60
- Celulares tem diferentes classificações para velocidade
  - A/B/G – só funciona 2.ghz
  - A/B/G/N – conecta 5ghz mas não alcança velocidade máxima
  - A/B/G/AC e AX: alcança velocidade máxima no 5ghz