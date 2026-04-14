# Projeto-Industrial-labirinto-auxiliado-pelo-Arduino
Este repositório contém o nosso projeto da Feira Industrial do 1º ano de Mecatrônica (tema: Jogos Eletrônicos) no qual foi desenvolvido um labirinto com um personagem controlado por motores com redução de torque DC. Que, juntos com outros elementos, formam um mecanismo que se movimenta nos eixos espaciais X e Y controlado por um joystick.  

### 👥 Equipe (Colaboradores) 
* [José Heitor Backhaus Soares](https.github.com/Josemiauloko-github-1)  
* [Nicollas Abraão](https.github.com/NLLL-03-github-2)
* [Pietro Renato](https.github.com/Kayanabi-github)
* [Lívia Oliveira](https.github.com/livxkhw-github)
* Murilo Henrique

### 📖 Descrição do Projeto: 
#### Problema: Mover um cervo de MDF por um labirinto de madeira nos eixos X e Y por meio de um joystick.

#### Desafio da Semana Industrial:
Montar um jogo mecatrônico para a feira industrial, mantendo um custo relativamente baixo, sem ter sequer uma aula sobre o Arduino.

#### Funcionamento: 
##### Joystick:
O jogador utiliza o Joystick o movendo para a direita (X+) a fim de passar o cervo por um caminho do labirinto com o objetivo de chegar ao seu final o mais rápido possível, assim os Switches traduzem a informação mecânica dada pelo joystick em um sinal elétrico de LOW para HIGHT ou HIGHT para LOW, que é interpretado pelo Arduino por meio de suas portas digitais. O Arduino, após passar as informações para o código interpretar as possíveis situações do sistema, as transforma novamente em um comando para a ponte H que enfim aciona os motores. 

##### Fins de Curso:
O Arduino verifica o estado atual dos fins de curso para saber se algum deles está acionado (no nosso exemplo limitXplus), caso não, o sistema permite que o motor avance.
Mas se o fim de curso estiver ativado, o motor para. Impedindo que o carrinho saia do trilho e/ou quebre alguma parte do projeto.
E como os outros Swiches estão desativados, o Arduino permite que os motores façam a reversão do seu curso e andem nos outros eixos não travando o sistema.

##### Motores:
Rotacionam o eixo helicoidal que promove a movimentação de cada carrinho por meio de uma engrenagem / porca que tem a sua rotação travada na placa de madeira que forma o carrinho.
Para ir para frente ou para trás são energizadas as suas entradas com 12 V, promovendo bastante velocidade. Se trocados os polos dos motores, a reversão de sentido é feita, trabalho da ponte H.

##### Ponte H l298n:
Capta os comandos de acionamento dos motores enviados pelo Arduino, ligando-os e desligando-os. Ela está presente por estes motores consumirem uma corrente > 40 mA que o Arduino não suporta fornecer, servindo como um amplificador.

##### Arduino: 
Processa os inputs e outputs do sistema, fazendo as comparações lógicas “ife e else” para verificar se o joystick e o fim de curso estão ativados em algum sentido, promovendo ou interrompendo o movimento dos motores.

Para o fim de fazer um jogo controlado por um joystick, o Arduino e a ponte H poderiam ser dispensados do Projeto por meio da ligação em série de uma fonte de tensão nos Joysticks, nos Fins de curso e depois nos Motores, porém pretendemos utilizar a estrutura e as funções do Arduino em projetos futuros e o aprendizado pela prática era a principal proposta formulada pela feira.

### 🔧 Hardware (Componentes Utilizados):

* Arduino UNO 

* Ponte H l298n (Guía de uso: https://blog.eletrogate.com/guia-definitivo-de-uso-da-ponte-h-l298n/)

* cabos Macho-Macho. 

* 2 Motores com redução 12V, 150mA 

* Manche Joystick Fliperama 

* 8 Switches 

* Fonte de alimentação Arduino 9V, 3A (alternativas disponíveis em: https://docs.arduino.cc/learn/electronics/power-pins/ )

* Fonte de alimentação ponte H 12V, 2A 

* Fita adesiva 

* Madeira compensada e MDF  

* Parafusos 

* Porcas e Arruelas de Metal

* Varões de metal

* Arrame fino

* Papelão  

* Tintas de variadas cores 

* Cola quente  

* Hastes parafusadas + adaptadores maleáveis  

## 💻 Software e Dependências:
### O que é necessário para rodar o código? 
Todo o Código é rodado dentro da Placa Arduino Uno R3, mas também pode ser executado em outros microcontroladores (como as outras variações do tipo Arduino, ESP 32, Raspberry PI etc.) desde que este entenda a linguagem C++, contenha a quantidade de pinos de OUTPUT e INPUT analógicos e digitais necessários. Poder de memória e processamento característicos do microcontrolador além da biblioteca padrão do Arduino instalada, denominada Core.  

Também é necessário conter uma ponte H L298n que vai traduzir os comandos do Arduino para os motores, servindo como amplificador de corrente. 

**Firmware/Código:**
*O código principal está na pasta `Codigo-controle motores X e Y`.
*Código Secundário caso o primeiro não funcione: Codigo-controle motores X e Y 2
*E o de texte: Codigo vai e vem de texte
Linguagem: C++ (Arduino)
Arduino IDE (versão 1.8.19 ou superior)
  
**Bibliotecas (Libraries):**
*Core: padrão do Arduino já é instalada no programa Arduino Ide servindo para as funções DigitalRead, AnalogWrite, entre outras presentes no código.* 

### Diagrama: 
Diagrama Geral (não comentado):

<img width="1536" height="598" alt="Circuito movimento dos motores " src="https://github.com/user-attachments/assets/d8c10031-4ca1-4cf2-b8a3-a01bd66053e5" />

Controladores:

<img width="662" height="601" alt="Captura de tela 2025-11-08 144059" src="https://github.com/user-attachments/assets/caa1ce85-f53a-45fa-af81-cd4bf228ded9" />

Motores e Alimentação do circuito:

<img width="859" height="690" alt="image" src="https://github.com/user-attachments/assets/741c18dd-6898-4b02-a693-db54bef5afa3" />




## ⚙️ Instalação e Montagem Passo a passo:

![Imagem do WhatsApp de 2025-11-07 à(s) 17 22 19_f7dc66e9](https://github.com/user-attachments/assets/ed9247b3-fddb-4f4f-8e4b-c1ff70bc7217)


1º Crie uma estrutura em madeira com 4 guias de metal retas e igualmente espaçadas entre si, levando em consideração o eixo central do motor para definir suas alturas:

![Imagem do WhatsApp de 2025-11-07 à(s) 17 22 17_c0de00dd](https://github.com/user-attachments/assets/f511722c-dd74-461c-8de6-bfab259ed546)


Elas servirão como trilhos que guiarão um carrinho de madeira e peças de metal sendo este o eixo X da máquina, que também comporta o Y: 

![Imagem do WhatsApp de 2025-11-07 à(s) 17 22 17_ca5a3581](https://github.com/user-attachments/assets/d4a916d6-95e1-4ade-bbb6-ddfa52fc5191)


2º Construa o carrinho de madeira e metal que também comporta o motor do eixo Y tendo certeza de que está tudo alinhado em seu devido lugar e fazendo testes para ver se nenhuma parte que deveria se mexer está travando, meça bem com um paquímetro ou instrumentos mais precisos antes de furar, cortar ou parafusar qualquer parte, fazendo correções se necessário.

3º Instale-o na estrutura e teste se não há travamentos.
Para facilitar os testes, alimentamos os motores usando baterias de 9 V:

https://github.com/user-attachments/assets/bc3b539d-ba81-4807-8e67-e46f67662cbd


4º Coloque os 4 Switches de Fim de curso antes do fim dos eixos dos motores para garantir que o adaptador entre o motor e o eixo não seja forçado (escapando do motor) e o carrinho não perca as hachuras helicoidais do eixo que promovem o seu movimento, veja se eles são acionados testando preferencialmente com as baterias de 9V.

![Imagem do WhatsApp de 2025-11-07 à(s) 17 22 17_2ad4dbd2](https://github.com/user-attachments/assets/0f076575-5c42-48d9-9959-8145377b9ff3)


Também defina o tamanho e a posição dos cabos de forma que abranjam todo o movimento de ambos os eixos, não enrosquem, entrem na frente deles ou sejam danificados.

5º A partir das imagens do diagrama conecte os componentes abaixo, atentando aos detalhes e organizando a fiação para que fique claro qual fio pertence a qual componente e parte do circuito com uma simples análise. Isso facilita muito na hora de montar, fazer manutenções e atualizações.

* Motores: Desencape as pontas dos seus dois polos para melhor conexão na ponte H.

* Fins de curso:  Os terras irão para a protoboard e depois para o Arduino.
Os Fios de 5V irão se conectar no Arduino, sendo possível se guiar quais pinos representam os limites X+, X- , Y+ e Y- a partir do código e do diagrama.
De preferência, solde jumpers tipo macho nos fios de curso, facilitando a conexão deles no Arduino e na protoboard.

* Fonte de Alimentação Ponte H e o Arduino:

Conecte os pinos digitais do Arduino às respectivas entradas INT da ponte H.
Ligue a fonte de alimentação para o Arduino (no mínimo 5V - máximo recomendado de 7V) 

Atente à configuração da ponte que é feita com os jumpers externos colocados em V_LOgic e nas Saídas ATV_A e ATV_B.

Configurada, selecione a fonte de alimentação que seja capaz de alimentar os motores com no mínimo 5V e 2A, conecte na ponte H e apenas ligue na tomada quando tiver total certeza de que nenhuma parte do circuito pode dar curto, revise-o inteiramente, ajuste o que for necessário e, enfim, ligue-o na tomada.

*Guia de Uso Pontes H: https://blog.eletrogate.com/guia-definitivo-de-uso-da-ponte-h-l298n/*

*Métodos de Alimentação do Arduino: https://docs.arduino.cc/learn/electronics/power-pins/*

* Joysticks:  No diagrama os Interruptores representam os Switches do Joystick que são acionados na direção oposta da que se pretende se mover.
Os terras irão para a protoboard e depois para o Arduino separados dos terras dos Fins de curso
Os Fios de 5V irão se conectar no Arduino, sendo possível se guiar sobre quais pinos representam X+, X- , Y+ e Y- a partir do código e do diagrama.

6º: Pense em como será o seu labirinto sabendo que as suas trilhas são simples furos de 1 cm de diâmetro fazendo um esquema que depois será passado para o MDF e cortado.

![Imagem do WhatsApp de 2025-10-29 à(s) 23 28 04_0590e6eb](https://github.com/user-attachments/assets/e66e56f0-ca2e-45d9-af6f-6e975c662893)



7º Faça o personagem que irá andar no labirinto. Ele será sustentado por uma haste de metal pequena que passa pelos furos de 1 cm.

![Imagem do WhatsApp de 2025-10-27 à(s) 21 13 39_9aec21e9](https://github.com/user-attachments/assets/9591c3e2-e577-4910-a6a5-c9395635ab99)


8º Construa a Caixa de madeira, papelão ou outros materiais que comportarão toda a estrutura. É recomendada madeira pela durabilidade, mas também pelo peso do resto da estrutura principal.

![Imagem do WhatsApp de 2025-10-23 à(s) 19 27 24_db064115](https://github.com/user-attachments/assets/2e623871-9e40-496a-a5d0-516d3ba604fa)


9º Transfira a estrutura para a caixa, se quiser antes de fazer isso, decore-a .


Decoração:

https://github.com/user-attachments/assets/d7e7e5df-c390-4ed9-b336-b95a4e8cced6

**Upload do Código:**     
1º Conecte o Arduino ao computador.
2º Abra o arquivo `Código-controle motores X e Y, o Arduino Ide e copie e cole no programa.
3º Selecione a Placa (Arduino Uno) e a Porta COM correta.
5º Clique em "Carregar".

# Testes e Ajustes Finais
##### Após tudo conectado, vem o teste dos Fins de Curso, do Joystick e dos Motores:
1º Motores: Deixe ambos os eixos da estrutura em uma posição central, carregue um código básico como “Código vai e vem de teste”. (coloca os motores para irem e voltarem com um segundo de duração.) E inverta a conexão dos polos deles na ponte H caso não estejam indo para o lado correto.

https://github.com/user-attachments/assets/6c203f99-3733-4c18-b905-70877bff4f25

2º Joystick: Depois disso carregue o “Código-controle motores X e Y” e teste com o Joystick se a movimentação se dá para o lado correto, caso contrário verifique se os pinos do Joystick no Arduino estão na posição correta se lembrando que no esquema físico você move a cabeça do Joystick para frente, mas quem aciona é o Switch traseiro com isso se aplicando a todas as direções.

Evite ir até o fim de curso, pois ele ainda pode estar mal configurado travando o movimento do lado errado e também você pode acabar danificando a estrutura caso o carrinho não pare.

3º Fins de Curso: clique manualmente nos fins de curso e veja qual dos lados do joystick ele travou, caso haja problemas, mude no software qual é o pino de saída daquele fim de curso, não se esquecendo de trocar o outro pino que também apresenta falha na definição.

Se tudo estiver certo, é para o motor que, por exemplo, estava avançando na direção Y+ (btnYplus no código) parar quando ele atingir o Fim de Curso (limitYplus). 
 

▶️ Como Usar:
1.  Ligue a fonte de alimentação externa de 9V do Arduino na tomada e também a alimentação da ponte H.

2.  Lubrifique as guias de aço para garantir melhor coordenação e velocidade para o cervo.

3. Pegue um celular ou cronômetro para marcar o tempo com que você e seus amigos conseguem passar pelo labirinto, tente ser o mais rápido!
   
4.  Aproveite a diversão!

Resultado: 

* [Video do Projeto](https://youtube.com/shorts/7V9YcSOVFJ0?feature=share)

![Imagem do WhatsApp de 2025-11-07 à(s) 17 22 16_45989f6b](https://github.com/user-attachments/assets/7f686f21-1734-4e7c-82f7-4e471df61c5e)

![Imagem do WhatsApp de 2025-11-07 à(s) 17 22 16_06d94053](https://github.com/user-attachments/assets/bd00f38c-2a04-4731-b53d-8471acd4fe98)

![Imagem do WhatsApp de 2025-11-07 à(s) 17 22 16_194ad676](https://github.com/user-attachments/assets/40da5bb1-c234-4509-870f-291d50dae43f)

### Obrigado Por Ler!!! 

Espero que tenha ficado claro como replicar o projeto 😊

