# Projeto-Industrial-labirinto-auxiliado-pelo-Arduino
Este repositório contem o nosso projeto da Feira Industrial do 1º ano de Mecatrônica (tema: Jogos Eletrônicos) onde foi desenvolvido um labirinto com um personaguem controlado por motores com redução de torque DC. Que juntos de outros elementos formam um mecanismo que se movimenta nos eixos espaciais X e Y por controle de um Joystick  

### 👥 Equipe (Colaboradores) * [Nome do Aluno 1](https.github.com/usuario-github-1) * [Nome do Aluno 2](https.github.com/usuario-github-2) * [Nome do Aluno 3](https.github.com/usuario-github-3)

### 📖 Descrição do Projeto Aqui vocês devem detalhar melhor o projeto. * Qual problema ele resolve? * Qual era o desafio da Semana Industrial? * Como ele funciona (visão geral)? * Quais tecnologias (hardware e software) foram centrais? 

### 🔧 Hardware (Componentes Utilizados) Lista de todos os componentes físicos necessários para montar o projeto. * **Controlador:** 1x Arduino Uno R3 (ou Raspberry Pi, ESP32, etc.) * **Sensores:**     * 1x Sensor Ultrassônico HC-SR04     * 2x Sensores de Fim de Curso * **Atuadores:**     * 3x Servo Motores MG996R (Eixo X, Y, Garra)     * 1x Motor de Passo NEMA 17 * **Outros:**     * 1x Protoboard     * Jumpers (Macho-Macho, Macho-Fêmea)     * Fonte de alimentação externa 5V/2A     * Peças 3D (disponibilizar o .STL se possível)

### 💻 Software e Dependências:
# O que é necessário para rodar o código? 
Todo o Codigo é rodado dentro da Placa Arduino Uno R3 mas também pode ser executado en outros microcontoladores ( como as outras variações do tipo arduino )
desde que este entenda a linguagem C++, contenha a quantidade de pinos de  OUTPUT e IMPUT analogicos e digitais nescessarios além do poder de memoria e processamento caracteristicos do microcontrolador. 

Tambem é nescessario conter uma ponte H L298n que vai traduzir os comandos do arduino aos motores, servindo como amplificador de corrente.
 **Firmware/Código:**
* O código principal está na pasta `/Codigo-controle motores X e Y/`.
   
* Linguagem: C++ (Arduino) *
* Arduino IDE (versão 1.8.19 ou superior)
  
**Bibliotecas (Libraries):**
*Core: padrão do arduino que já vem instalada do programa ide, servindo para as funções DigitalRead, AnalogWrite entre outras presentes no codigo.* 

### Diagrama: 
<img width="1536" height="598" alt="Circuito movimento dos motores " src="https://github.com/user-attachments/assets/d8c10031-4ca1-4cf2-b8a3-a01bd66053e5" />

### por as duas imaguens comentadas 

### ⚙️ Instalação e Montagem Passo a passo:
1º Crie uma estrutura em madeira com 4 guias de metal retas e igualmente espaçadas entre si, levando em consideração o eixo central do motor para definir suas alturas; elas servirão como trilhos que guiarão um carrinho de madeira e peças de metal sendo este o eixo X da maquina que tambem comporta o Y: 

2º Contrua o carrinho de madeira e metal que tambem comporta o motor do eixo Y tendo certeza de que esta tudo alinhado em seu devido lugar e fazendo testes para ver se nenhuma parte que deveria se mexer esta travando, meça bem antes de furar, cortar ou parafusar qualquer parte, fazendo correções na estrutura se nescessario.

3º Intale-o na estrutura e texte se não há travamentos, para facilitar os textes alimentamos os motores usando baterias de 9V:

https://github.com/user-attachments/assets/bc3b539d-ba81-4807-8e67-e46f67662cbd

4º Coloque os 4 Swiches de Fim de curso antes do fim dos eixos dos motores para garantir que o adaptador entre o motor eo eixo não seja forçado (escapando do motor) e o carrinho não perca as hachuras helicoidais do eixo que promovem o seu movimento, veja se eles são acionados testando preferencialmente com as baterias de 9V.

Tambem defina o tamanho e a posição dos cabos de forma que abranjam todo o movimento de ambos os eixos, não entrem na frente deles, não enrosquem ou sejam danifados.

5º A partir das imaguens do diagrama conecte os motores, fins de curso, ponte H eo Arduino organizando a fiação para que fique claro qual fio pertence a qual componente e parte do circuito com uma simples analise, isso facilita muito na hora de fazer manutenções e atualizações.


 

**Bibliotecas:** Abra a Arduino IDE, vá em "Sketch" > "Include Library" > "Manage Libraries" e instale a `AccelStepper` e `NewPing`. 3.  

**Upload do Código:**     * Conecte o Arduino ao computador.     * Abra o arquivo `projeto_semana_industrial/projeto_semana_industrial.ino`.     * Selecione a Placa (Arduino Uno) e a Porta COM correta.     * Clique em "Upload". 

▶️ Como Usar Depois de montado e programado, como o projeto funciona? 1.  Ligue a fonte de alimentação externa. 2.  O braço robótico irá para a posição "Home" (inicial). 3.  Abra o "Serial Monitor" na Arduino IDE (Baud Rate 9600). 4.  Envie '1' para iniciar o ciclo automático ou '0' para parar. 

### 🎥 Vídeo/GIF do Projeto em Ação *(É recomendado colocar um GIF ou link para um vídeo curto do projeto funcionando. Isso valoriza muito o README!)* ![Texto alternativo do GIF](link/para/o/video_ou_gif.gif)
