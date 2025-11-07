# Projeto-Industrial-labirinto-auxiliado-pelo-Arduino
Este repositório contem o nosso projeto da Feira Industrial do 1º ano de Mecatrônica (tema: Jogos Eletrônicos) onde foi desenvolvido um labirinto com um personaguem controlado por motores com redução de torque DC. Que juntos de outros elementos formam um mecanismo que se movimenta nos eixos espaciais X e Y por controle de um Joystick  

### 👥 Equipe (Colaboradores) * [Nome do Aluno 1](https.github.com/usuario-github-1) * [Nome do Aluno 2](https.github.com/usuario-github-2) * [Nome do Aluno 3](https.github.com/usuario-github-3)

### 📖 Descrição do Projeto Aqui vocês devem detalhar melhor o projeto. * Qual problema ele resolve? * Qual era o desafio da Semana Industrial? * Como ele funciona (visão geral)? * Quais tecnologias (hardware e software) foram centrais? 

### 🔧 Hardware (Componentes Utilizados) Lista de todos os componentes físicos necessários para montar o projeto. * **Controlador:** 1x Arduino Uno R3 (ou Raspberry Pi, ESP32, etc.) * **Sensores:**     * 1x Sensor Ultrassônico HC-SR04     * 2x Sensores de Fim de Curso * **Atuadores:**     * 3x Servo Motores MG996R (Eixo X, Y, Garra)     * 1x Motor de Passo NEMA 17 * **Outros:**     * 1x Protoboard     * Jumpers (Macho-Macho, Macho-Fêmea)     * Fonte de alimentação externa 5V/2A     * Peças 3D (disponibilizar o .STL se possível)

### 💻 Software e Dependências:
# O que é necessário para rodar o código? 
Todo o Codigo é rodado dentro da Placa Arduino Uno R3 mas também pode ser executado en outros microcontoladores ( como as outras variações do tipo arduino )
desde que este entenda a linguagem C++, contenha a quantidade de pinos de  OUTPUT e IMPUT analogicos e digitais nescessarios além do poder de memoria e processamento caracteristicos do microcontrolador. 
 **Firmware/Código:**
* O código principal está na pasta `/Codigo-controle motores X e Y/`.
     
* Linguagem: C++ (Arduino) *
* Arduino IDE (versão 1.8.19 ou superior)
* 
* **Bibliotecas (Libraries):**
*Core: padrão do arduino que já vem instalada do programa ide, servindo para as funções DigitalRead, AnalogWrite entre outras presentes no codigo.* 

###  diagrama: 
<img width="1536" height="598" alt="Circuito movimento dos motores " src="https://github.com/user-attachments/assets/d8c10031-4ca1-4cf2-b8a3-a01bd66053e5" />

### ⚙️ Instalação e Montagem Passo a passo de como alguém pode replicar o projeto de vocês. 1. 

**Montagem:** Siga o esquema elétrico acima para conectar todos os componentes. 2. 

**Bibliotecas:** Abra a Arduino IDE, vá em "Sketch" > "Include Library" > "Manage Libraries" e instale a `AccelStepper` e `NewPing`. 3.  

**Upload do Código:**     * Conecte o Arduino ao computador.     * Abra o arquivo `projeto_semana_industrial/projeto_semana_industrial.ino`.     * Selecione a Placa (Arduino Uno) e a Porta COM correta.     * Clique em "Upload". 

▶️ Como Usar Depois de montado e programado, como o projeto funciona? 1.  Ligue a fonte de alimentação externa. 2.  O braço robótico irá para a posição "Home" (inicial). 3.  Abra o "Serial Monitor" na Arduino IDE (Baud Rate 9600). 4.  Envie '1' para iniciar o ciclo automático ou '0' para parar. 

### 🎥 Vídeo/GIF do Projeto em Ação *(É recomendado colocar um GIF ou link para um vídeo curto do projeto funcionando. Isso valoriza muito o README!)* ![Texto alternativo do GIF](link/para/o/video_ou_gif.gif)
