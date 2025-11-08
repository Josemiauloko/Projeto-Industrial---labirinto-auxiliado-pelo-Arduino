# Projeto-Industrial-labirinto-auxiliado-pelo-Arduino
Este repositório contem o nosso projeto da Feira Industrial do 1º ano de Mecatrônica (tema: Jogos Eletrônicos) onde foi desenvolvido um labirinto com um personaguem controlado por motores com redução de torque DC. Que juntos de outros elementos formam um mecanismo que se movimenta nos eixos espaciais X e Y por controle de um Joystick  

### 👥 Equipe (Colaboradores) 
* José Heitor Backhaus Soares 
* [Nome do Aluno 2](https.github.com/usuario-github-2) 
* [Nome do Aluno 3](https.github.com/usuario-github-3)

### 📖 Descrição do Projeto: 
#### Problema: Mover um cervo de MDF por um labirinto de madeira nos eixos X e Y por meio de um joistick.

#### Desafio da Semana Industrial:
Montar um jogo Mecatronico para a feira industial, mantendo um custo relativamente baixo, sem ter sequer uma aula sobre o Arduino.

#### Funcionamento: 
##### Joistick:
Como exemplo digamos que o jogador move o Joistick para direita (X+) afim de passar o cervo pelo labirinto tendo como objetivo chegar ao seu final o mais rapido possivel, assim os Swiches traduzem a informação mecanica em um sinal eletrico de HIGH para LOW, que é interpretado pelo arduino por meio de uma de suas portas digitais. 

##### Fins de Curso:
O arduino verifica o estado atual dos fins de curso para saber se algum deles esta acionado (no nosso caso limitXplus), caso não o sistema permite que o motor avançe.
Mas se o fim de curso estiver ativado o motor para impedindo que o carrinho saia do trilho e/ou quebre alguma parte do projeto.
E como os outros Swiches estão dezativados o arduino permite que os motores façam a reversão do seu curso e ande nos outros eixos não travando o sistema.

##### Motores:
Rotacionam o heixo helicoidal que promove a movimentação de cada carrinho por meio de uma engrenaguem / Porca que tem a sua rotação travada.
Para ir para frente ou tras são energizadas as suas entradas com 12v, promovendo bastante velocidade, se trocando de lado os polos positivos e negativo dos moteres, trabalho feito pela ponte H.

##### Ponte H l298n:
Capta os comandos de acionamento dos motores enviados pelo Arduino, ligando-os e desligando-os. ela esta presente unicamente pelo fato de estes motores consumirem > 40mA que o arduino não suporta fornecer, servindo como um Amplificador.

##### Arduino: 
Processa os imputs e outputs de sistema, fazendo as comparações logicas ------------------------------------------------------

Quais tecnologias (hardware e software) foram centrais? 

### 🔧 Hardware (Componentes Utilizados):

*Arduino UNO 

*Ponte H l298n (Guia de uso: 

*cabos Macho-Macho. 

*2 Motores com redução 12V, 150mA 

*Manche Joystick Fliperama 

*8 Switches 

* Fonte de alimentação arduino 9V, 3A (outras alternativas disponiveis em: https://docs.arduino.cc/learn/electronics/power-pins/ )

*Fonte de alimentação ponte H 12V, 2A 

*Fita adesiva 

*Madeira  

*Parafusos 

*Barras de metal 

*Papelão  

*Tintas de variadas cores 

*Cola quente  

*Eixos com molas de aço  

## 💻 Software e Dependências:
### O que é necessário para rodar o código? 
Todo o Codigo é rodado dentro da Placa Arduino Uno R3 mas também pode ser executado en outros microcontoladores ( como as outras variações do tipo arduino ) desde que este entenda a linguagem C++, contenha a quantidade de pinos de  OUTPUT e IMPUT analogicos e digitais nescessarios além do poder de memoria e processamento caracteristicos do microcontrolador. 

Tambem é nescessario conter uma ponte H L298n que vai traduzir os comandos do arduino aos motores, servindo como amplificador de corrente.
 **Firmware/Código:**
O código principal está na pasta `Codigo-controle motores X e Y`.
O Secundario caso o primeiro não funcione: Codigo-controle motores X e Y 2
E o de texte: Codigo vai e vem de texte
Linguagem: C++ (Arduino) *
Arduino IDE (versão 1.8.19 ou superior)
  
**Bibliotecas (Libraries):**
*Core: padrão do arduino que já vem instalada do programa ide, servindo para as funções DigitalRead, AnalogWrite entre outras presentes no codigo.* 

### Diagrama: 
Diagrama Geral (não comentado):

<img width="1536" height="598" alt="Circuito movimento dos motores " src="https://github.com/user-attachments/assets/d8c10031-4ca1-4cf2-b8a3-a01bd66053e5" />

Controladores:

<img width="662" height="601" alt="Captura de tela 2025-11-08 144059" src="https://github.com/user-attachments/assets/caa1ce85-f53a-45fa-af81-cd4bf228ded9" />

Motores e Alimentação do circuito:

<img width="859" height="690" alt="image" src="https://github.com/user-attachments/assets/741c18dd-6898-4b02-a693-db54bef5afa3" />


### ⚙️ Instalação e Montagem Passo a passo:

![Imagem do WhatsApp de 2025-11-07 à(s) 17 22 19_f7dc66e9](https://github.com/user-attachments/assets/ed9247b3-fddb-4f4f-8e4b-c1ff70bc7217)


1º Crie uma estrutura em madeira com 4 guias de metal retas e igualmente espaçadas entre si, levando em consideração o eixo central do motor para definir suas alturas:

![Imagem do WhatsApp de 2025-11-07 à(s) 17 22 17_c0de00dd](https://github.com/user-attachments/assets/f511722c-dd74-461c-8de6-bfab259ed546)

elas servirão como trilhos que guiarão um carrinho de madeira e peças de metal sendo este o eixo X da maquina que tambem comporta o Y: 

![Imagem do WhatsApp de 2025-11-07 à(s) 17 22 17_ca5a3581](https://github.com/user-attachments/assets/d4a916d6-95e1-4ade-bbb6-ddfa52fc5191)

2º Construa o carrinho de madeira e metal que tambem comporta o motor do eixo Y tendo certeza de que esta tudo alinhado em seu devido lugar e fazendo testes para ver se nenhuma parte que deveria se mexer esta travando, meça bem antes de furar, cortar ou parafusar qualquer parte, fazendo correções na estrutura se nescessario.

3º Intale-o na estrutura e texte se não há travamentos, para facilitar os textes alimentamos os motores usando baterias de 9V:

https://github.com/user-attachments/assets/bc3b539d-ba81-4807-8e67-e46f67662cbd

4º Coloque os 4 Swiches de Fim de curso antes do fim dos eixos dos motores para garantir que o adaptador entre o motor eo eixo não seja forçado (escapando do motor) e o carrinho não perca as hachuras helicoidais do eixo que promovem o seu movimento, veja se eles são acionados testando preferencialmente com as baterias de 9V.

![Imagem do WhatsApp de 2025-11-07 à(s) 17 22 17_2ad4dbd2](https://github.com/user-attachments/assets/0f076575-5c42-48d9-9959-8145377b9ff3)

Tambem defina o tamanho e a posição dos cabos de forma que abranjam todo o movimento de ambos os eixos, não entrem na frente deles, não enrosquem ou sejam danifados.

5º A partir das imaguens do diagrama conecte os componentes abaixo, se atentando aos detalhes e organizando a fiação para que fique claro qual fio pertence a qual componente e parte do circuito com uma simples analise, isso facilita muito na hora de montar, fazer manutenções e atualizações.

* Motores:  Desencape as pontas dos seus dois polos para melhor conecção na ponte H.

* Fins de curso:  Os terras irão para a protoboard e depois para o arduino.
Os Fios de 5V irão se conectar no arduino, sendo possivel se guiar quais pinos representam os limites X+, X- , Y+ e Y- a partir do codigo e do diagrama.
De preferencia solde jumpers tipo macho nos fios dos fim de curso, facilitando a conecção deles no arduino e na protoboard.

* Fonte de Alimentação Ponte H e o Arduino:

Conecte os pinos digitais do Arduino em suas respectivas entradas INT da ponte H.
Ligue a fonde de alimentação para o arduino (no minimo 5v - Maximo recomendado de 7V) 

Se atente a configuração da ponte que é feita com os jumpers externos colocados em V_LOgic e nas Saidas ATV_A e ATV_B.

Configurada desencape os fios da fonte de alimentação, conecte na ponte H e apenas lige na tomada confirmação de que a mesma é capaz de alimentar os motores com no minimo 5V e 2A.

*Guia de Uso Pontes H: https://blog.eletrogate.com/guia-definitivo-de-uso-da-ponte-h-l298n/*

*Metodos de Alimentação do Arduino: https://docs.arduino.cc/learn/electronics/power-pins/*

* Joisticks:  No diagrama os Interruptores representam os Switches do Joystick que são acionados na direção oposta da que se pretende se mover.
Os terras irão para a protoboard e depois para o arduino separados dos terras dos Fins de curso
Os Fios de 5V irão se conectar no arduino, sendo possivel se guiar quais pinos representam X+, X- , Y+ e Y- a partir do codigo e do diagrama.


**Upload do Código:**     
1º Conecte o Arduino ao computador.
2º Abra o arquivo `Codigo-controle motores X e Y, o Arduino Ide e copie e cole no programa.
3º Selecione a Placa (Arduino Uno) e a Porta COM correta.
5º Clique em "Carregar".

# Textes e Ajustes Finais
## Apos tudo conectado vem o texte dos Fins de Curso, Joistick e dos Motores:
1 º Motores: Deixe ambos os eixos da estrutura em uma posição central, carrege um coigo basico como Codigo vai e vem de texte. (coloca os motores para irem e voltarem com um segundo de duração) e inverta a conexão dos polos deles na ponte H caso não estejam indo para o lado correto.

https://github.com/user-attachments/assets/6c203f99-3733-4c18-b905-70877bff4f25

2 º Joistick: Depois disso carrege o Codigo-controle motores X e Y e texte com o joistick se a movimentação se dá para o lado correto, caso contrario verifique se os pinos do joistick no Arduino estão na posição correta se lembrando que no esquema fisico você move a cabeça do Joistick para frente mas quem aciona é o switche trazeiro com isso se aplicando a todas as direções.

Evite de ir até o fim de curso, pois ele ainda pode estar mau configurado travando o movimento do lado errado e tambem você pode acabar danificando a estrutura caso o carrinho não pare.

3 º Fins de Curso: clique manualmente nos fins de curso e veja qual dos lados do joistick ele travou, caso aja problemas mude no software qual é o pino de saida daquele fim de curso, não se esquecendo de trocar o outro pino que tambêm apresenta falha na definição.

Se tudo estiver certo é para o moter que por exemplo estava avançando na direção Y+ (btnYplus no codigo) parar quando ele atingir o Fim de Curso (limitYplus). 
 

▶️ Como Usar Depois de montado e programado, como o projeto funciona? 1.  Ligue a fonte de alimentação externa. 2.  O braço robótico irá para a posição "Home" (inicial). 3.  Abra o "Serial Monitor" na Arduino IDE (Baud Rate 9600). 4.  Envie '1' para iniciar o ciclo automático ou '0' para parar. 

### 🎥 Vídeo/GIF do Projeto em Ação *(É recomendado colocar um GIF ou link para um vídeo curto do projeto funcionando. Isso valoriza muito o README!)* ![Texto alternativo do GIF](link/para/o/video_ou_gif.gif)
