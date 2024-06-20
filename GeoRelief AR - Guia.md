

<div align="center">
  <h1>🌍 GeoRelief AR 🌍</h1>
</div>


<br>

Para fazer o download do guia em PDF, basta clicar no link abaixo.
<br>
[Guia de montagem em PDF](https://drive.google.com/file/d/1QcmQQUmcYwLkjb4AWOyQnwIEUz1kNtnV/view?usp=sharing).
<br>
<br>

## 1 - REQUISITOS 


Como base de estudo e consulta foi utilizado o ‘SARndbox’, projeto desenvolvido em parceria pela Universidade da Califórnia, Centro de Pesquisa Ambiental de Tahoe, e Aquário e Centro de Ciências ECHO Lake. Para que seja realizada a montagem da ferramenta são necessários:

- **Computador** com placa gráfica offboard, que possua pelo menos 1 GB (gigabytes) de memória dedicada, placa recomendada Geforce GTX 970. Caso as configurações possíveis não atinjam esses requisitos recomendados, é possível desativar a chuva para minimizar o consumo da GPU.
- **Sistema operacional (SO)** Linux Mint versão MATE de 64-bit, com requisito mínimo de 2 GB de RAM e 25 GB de disco rígido, suficiente para o Linux, e também, para a aplicação.
- **Processador** de no mínimo 2,4 GHz, recomendado que seja usado um Intel I5 3330 ou AMD Ryzen 3 3200 G, ou versões superiores.
- **Projetor** com uma resolução em HD (720p), ou seja, um projetor de 1024x768 já é o suficiente, desde que possuam saída DVI, HDMI ou Display port. Recomenda-se que não seja usado VGA, pois pode prejudicar a qualidade de imagem.
- **Sensor Kinect** do Xbox 360. A versão v2 do Kinect usado para o Xbox One e Windows não é compatível com o software que será usado no AR GeoRelief.
- **Estrutura** para que o sensor Kinect e projetor fiquem dispostos na distância ideal até a areia, e também, a caixa que será usada para alojar a areia, onde serão feitos os relevos.
<br>
<br>

## 2 - INSTALAÇÃO DE SOFTWARES NECESSÁRIOS

Todos os passos ou guias necessários para a instalação do AR GeoRelief serão passados neste trabalho. Os softwares necessários para a instalação são:

- **Sistema Operacional Linux Mint 17.3 "Rosa"** com interface MATE e arquitetura de 64 bits, para melhor compreensão no idioma português do Brasil. Disponível em [Linux Mint](http://blog.linuxmint.com/?p=2946).
- **Vrui Vr Toolkit 3.1-004**, é preciso também, o script do Ubuntu 14.04 denominado Build-Ubuntu.sh. Disponível em [Vrui Toolkit](https://web.cs.ucdavis.edu/~okreylos/ResDev/Vrui/LinkDownload.html).
- **Softwares para interface com o sensor Kinect-2,8-002.**
- **Softwares do sistema SARndbox-1.6.**

Importante ser mantido as versões citadas, pois existem interdependências entre esses pacotes de softwares. Por exemplo, a versão 1.6 do software SARndbox requer a versão "Kinect-2,8-002" e a versão "Vrui 3.1-004".

Os próximos passos serão voltados à instalação de cada um dos softwares requeridos para o perfeito funcionamento do AR GeoRelief.

### 2.1 Sistema Operacional Linux

Alguns passos serão tratados de forma mais geral, mas é fornecido um material de apoio bem detalhado para auxílio no processo de instalação dos mesmos. O link abaixo servirá como um guia mais aprofundado para a instalação do Linux Mint, por ser uma documentação voltada somente para o software, contém comandos e dicas para facilitar o uso após a instalação. Documentação disponível em [Documentação Linux Mint](https://www.linuxmint.com/documentation.php).

Lembrando que a instalação do SO deve ser diretamente na máquina, pois o software possui funcionalidades que deixam de funcionar corretamente, caso seja instalado em uma máquina virtual. Caso não tenha sido feita a instalação da placa de vídeo, deve ser realizada antes do próximo passo. Lembrando que a placa de vídeo precisa ser Offboard, ou seja, são as placas de vídeo instaladas nos slots da placa mãe. Após a instalação da placa de vídeo, deve-se iniciar a máquina com o SO Linux.

Para evitar quebras de imagem ou a perda de pixels, deve-se atualizar os Drivers
de vídeo. Para a atualização dos Drivers, tomaremos como ponto inicial a área de trabalho,
ver Figura 3, então clique no botão Menu (1°), após clique em ’Tudo’ (2°), depois podemos
digitar Gerenciador de Drivers na barra de pesquisa (3°).
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/e2031f32-b37a-464d-9feb-cd657b632e96" width="800px" />
   </div>   

<br>
Para acessar a tela com os Drivers será solicitada a senha do root, que é o perfil administrador do Linux. Em seguida, será apresentado um painel com uma lista de Drivers disponíveis para instalação, conforme Figura abaixo (1°). Selecione o Driver que
estiver com a informação recommended, esse Driver pode variar conforme a placa gráfica
que está sendo usada no computador. Após a seleção, clique em Apply Changes, conforme
passo (2°), então aguarde a instalação e reinicie o computador para concluir seja instalação
dos Drivers da placa de vídeo.          
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/ba607460-eab8-450b-86ab-5c134042fd46" width="800px" />
   </div> 

<br>

### 2.2 Instalação dos Softwares

Quando estava sendo feita a instalação do SO Linux, foi solicitada uma senha para o usuário root. Essa senha será usada novamente para entrar no terminal como root, permitindo que sejam executados os comandos necessários para o download e instalação dos softwares, bem como para a configuração e execução do AR GeoRelief.

Para a instalação dos softwares, precisamos abrir o console. Isso pode ser feito pelo botão **Menu** ou pressionando as três teclas juntas (CTRL + ALT + T). Será solicitada a senha do root. Após realizar o login, execute a sequência de comandos para fazer o download dos softwares, uma linha de cada vez:

```bash
1. su
2. senha: (nesse campo deve ser digitada a senha do root)
3. cd ~
4. git clone https://github.com/projetossar/SARndbox.git
5. cd SARndbox
6. mv Build-Ubuntu.sh ..
````

Esse bloco de comandos é responsável pelo download dos softwares Vrui, Kinect e SARndbox. Após o término do download desses softwares, pode-se avançar para os próximos passos.
   
```bash
1. cd ~
2. bash Build-Ubuntu.sh
````

Ao executar esse segundo bloco, será solicitado a senha do administrador (root),
para ser instalado as bibliotecas e requisitos necessários para a instalação do Vrui VR toolkit,
um passo que normalmente demanda um pouco mais de tempo, diretamente influenciado
pela conexão de internet e velocidade de processamento da máquina onde está sendo feito
esse download e instalação, caso tenha êxito nesses passos será exibido uma imagem de
um globo rodando, caso apareça deve-se fechar essa janela e voltar ao terminal, onde será
digitado os próximos comandos.

```bash
1 cd ~/SARndbox/
2 mv Kinect-2.8-002.tar ~/src/
3 cd ~/src
4 tar xfz Kinect-2.8-002.tar
5 cd Kinect-2.8-002
6 make
7 make install
8 make installudevrule
````

Após a execução de cada linha acima, será iniciado o download do software respon-
sável pela comunicação com o sensor Kinect, restando somente o download do software
SARndbox que fará a integração entre todas as partes e a aplicação por onde será iniciado
o software posteriormente.

```bash
1 cd ~/SARndbox
2 mv SARndbox-1.6.tar ~/src/
3 cd ~/src
4 rm ~/SARndbox/ -rf
5 tar xfz SARndbox-1.6.tar
6 cd SARndbox-1.6
7 make
````

Com esse último bloco de comandos será feito o download e instalação do software
SARndbox, responsável pela comunicação entre todos os hardwares e por onde será feita a
execução antes do uso do AR GeoRelief. Após todos esses passos realizados já temos o
download de todos os softwares necessários, partindo então para a montagem e calibragem
dos aparelhos.
<br>
<br>
<br>

## 3 - Montagem da Caixa de Areia

A construção da bancada pode ser feita com vários materiais diferentes, como madeira, metais em geral, plástico, fibra de vidro, fibra de carbono e resina. Deve-se levar em conta se será possível fazer a locomoção de toda a estrutura, pois a estrutura e a areia podem acumular um peso considerável.

A caixa do AR GeoRelief deve possuir bordas para que a areia não caia da caixa devido aos movimentos realizados na mesma. Essas bordas devem ter uma altura de 10 a 15 centímetros em relação ao restante da caixa, pois essa altura define a quantidade de areia a ser alocada dentro da bancada do AR GeoRelief. É necessário manter uma distância mínima de 5 centímetros da areia até a borda, já que relevos serão feitos na areia.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/a6170b16-9dee-4a8f-ba5c-2c7e6c235fe4" width="800px" />
   </div> 

<br>
<br>
<br>

## 4 - Montagem do Suporte do Sensor e do Projetor

O suporte que é usado para alocar o projetor e o sensor deve ficar a uma distância
de que pode variar dependendo dos equipamentos utilizados. Deve-se atentar para as
saídas de ar tanto do sensor como do projetor, as quais não podem ser obstruídas pela
estrutura, visto que são usadas para a refrigeração destes equipamentos, o que pode afetar
o desempenho e até mesmo o funcionamento.

Para dar sustentação à caixa que abrigará os equipamentos de leitura e projeção,
deve-se montar uma conexão com a caixa de areia por meio de um braço de apoio que
somente será fixado após a calibragem sumária dos sensores, para que se tenha a distância
correta dos sensores até a areia. Esse suporte pode ser feito de madeira, como também de
outros materiais mais tecnológicos
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/8f798cb8-166a-4f8a-9659-1ec42fb57908" width="800px" />
   </div> 
<br>

### 4.1 - Posicionamento do Projetor

Primeiro passo, é necessário verificar o modo como o projetor faz a projeção da
imagem, alguns projetam diretamente à frente, enquanto outros possuem um pequeno
ângulo na projeção. Projetores mais modernos possuem configurações que permitem a
alteração nessa forma de projeção. Essa forma de projeção é o que vai ditar o posicionamento
desse suporte dos equipamentos, conforme figura abaixo.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/7e70e885-6da5-4b62-8bfd-af48de88e3b0" width="800px" />
   </div> 
<br>

Recomendado o uso de um projetor com uma projeção reta, pois facilita a montagem
da caixa para o suporte e também a melhora visual da ferramenta como um todo, em
termos de funcionalidades tanto o reto como a projeção em ângulo suprem a necessidade.
Deve-se atentar à distância de projeção para ficar o mais nítido possível, e também, que a
projeção fique perpendicular à areia para evitar distorções de pixels.

A distância do projetor até a areia pode variar dependendo do projetor disponí-
vel, é normalmente usado a uma distância entre 100 e 120 centímetros da areia, essa é uma distância que vai aumentar conforme a resolução do projetor, essa distância de 120
centímetros é usada em projetores de 800x600 (resolução menor que a recomendada).

### 4.2 - Posicionamento do Sensor Kinect

Para a montagem do sensor Kinect é necessário posicioná-lo a 100 centímetros da
areia e exatamente acima do centro da nossa caixa de areia, como na imagem abaixo.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/84bfeebd-c23f-4fd9-8a80-e644e568ab73" width="800px" />
   </div> 
<br>

A essa distância o sensor consegue pegar todos os pontos de nossa caixa, evitando
assim pontos cego. O sensor Kinect também possui uma distância ideal para a correta
captura e leitura dos movimentos que serão realizados na areia, então mesmo que o projetor
fique acima de 100 centímetros, o sensor Kinect deve ficar a essa altura da areia.

Após realizada a montagem tanto do suporte como da bancada, agora vem a parte
de conexão entre os equipamentos através dos cabeamentos, esses que devem ser fixados no
suporte de modo que não fiquem a vista, para uma melhora estética do AR GeoRelief, após
esses passos já pode ser feito o aperto para a fixação desse suporte onde os equipamentos
estão alojados.

Como o AR GeoRelief pode ser construído com materiais que podem ser pesados,
e também teremos a areia, uma melhoria que pode ser feita para facilitar o deslocamento é
colocar rodinhas sob os pés do AR GeoRelief, conforme a figura abaixo.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/b5902a18-bde8-4af9-ae56-fc89a4c5b8d0" width="800px" />
   </div> 
<br>

Após a finalização da montagem, teremos finalizado a parte física do AR GeoRelief, conforme
a próxima imagem, faltando somente a calibragem e ajustes finais para que o software
esteja pronto para ser utilizado no auxílio de ensino de geografia, o qual são os próximos
passos a serem abordados.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/c718989f-594e-452f-8506-770e23eeb636" width="800px" />
   </div> 
<br>

## 5 - Calibragem

Esse é um passo muito importante, pois sem a calibragem correta o AR GeoRelief
pode ficar com a leitura dos relevos e movimentos realizados na areia, de forma imprecisa
ou ficando com pontos cegos nos cantos da caixa.

### 5.1 - Medição da superfície

Primeiro passo para iniciar a calibragem é definir qual é o tamanho da superfície
que será utilizada, essa medição é realizada através do software RawKinectViewer, que
usará a câmera do sensor para que seja delimitado a área da superfície, para inicializar o
software devemos digitar os seguintes comandos.

```bash
1 cd ~/src/SARndbox-1.6
2 ~/Vrui-3.1/bin/RawKinectViewer -compress 0
````

A aplicação será iniciada com a mesma interface presente na Figura abaixo,
se todos os equipamentos estiverem perfeitamente posicionados, nesta tela será apresen-
tado duas imagens, uma gerada pela câmera do sensor Kinect e a outra gerada pelo
RawKinectViewer.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/1cab2715-7e29-4147-97fe-5cc12a445923" width="800px" />
   </div> 
<br>

Caso a imagem da direita esteja um pouco inclinada, deve-se ajustar o posicio-
namento do sensor Kinect no suporte. Primeiro devemos ajustar para que a imagem da
esquerda fique maior e centralizada, para uma melhor visualização das conFigurações que
serão executadas a seguir.

Com a imagem já centralizada, posicione o cursor (ponteiro) do mouse sobre a
imagem gerada pelo RawKinectViewer (imagem da esquerda), então pressione o botão
CTRL (control, presente nas extremidades inferiores do teclado) e selecionar a opção
Extract Planes, conforme a Figura abaixo.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/ef65aaa8-2c23-445d-8c10-1f8430d86e50" width="800px" />
   </div> 
<br>

Após esse passo deve-se clicar com o botão direito do mouse, devendo surgir outro
menu, conforme a imagem abaixo, então selecione a opção Average Frames essa ação
fará a ação de tirar uma captura de tela da área fazendo com que a imagem da caixa de
areia congele.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/32f8a9d9-6c47-4c0e-b9f3-089b2b500582" width="800px" />
   </div> 
<br>

Delimite a área que será usada, levando o ponteiro do mouse até o canto superior
esquerdo, então segure a tecla CTRL e clique no botão esquerdo do mouse (mantenha
os dois botões pressionados) arraste até o canto inferior direito da areia, formando um
retângulo somente na área onde se encontra a areia, ou seja, somente a área em verde
evitando selecionar áreas em preto, como na Figura abaixo.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/5283e15f-d5c0-4df2-a4cf-54bb97934231" width="800px" />
   </div> 
<br>

Se o procedimento foi executado de forma correta, aparecerá dois valores no terminal,
Depth-Space e o Camera Space, valores que expressam em números a área selecionada,
deve-se desmarcar a opção Average Frames.
Após já ter essas áreas definidas, deve-se criar uma ferramenta de medição 3D,
posicionando o ponteiro do mouse no meio da tela verde e clicar com o botão direito do
mouse, selecionando a opção Measure 3D Positions, em seguida, clique novamente com o
botão direito para surgir o menu, e escolha novamente a opção Average Frames, repetindo o passo ja realizado anteriormente.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/32f8a9d9-6c47-4c0e-b9f3-089b2b500582" width="800px" />
   </div> 
<br>

Nesse passo, deve ser executado com bastante atenção, pois existe uma sequência
de cliques, que precisam obedecidas, posicione o mouse no canto inferior esquerdo e clique
com o botão esquerdo do mouse, esse clique do mouse deve acontecer em todos os quatro
cantos, canto inferior direito, canto superior esquerdo, canto superior direito.
Ao final desse procedimento, no terminal devem aparecer 6 linhas, duas com os
valores de Camera Space e Average Frames e as outras quatro linhas são as coordenadas
dos cantos em que foram clicadas pelo mouse, caso possua uma quantidade de linhas diferentes de seis, conforme a imagem abaixo, o passo de realizar os cliques nos cantos
da tela devem ser refeitos.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/27d9b274-40a5-460e-8176-03ebc2596b03" width="800px" />
   </div> 
<br>

Em seguida, pode fechar o software RawKinectViewer, volte ao terminal, onde será
salvar os valores dessas coordenadas em um arquivo de texto, chamado de BoxLayout.txt,
esse arquivo de texto se encontra dentro da pasta SARndbox-1.6, realize a gravação dos
valores, em conformidade com a Figura abaixo, troque o simbolo de ’=’ por ’,’, após
essa alteração salve esse arquivo de texto.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/501a2145-3458-4994-bc25-57ab2afeda45" width="800px" />
   </div> 
<br>

Para um acompanhamento mais visual de como são realizados os passos acima, há um vídeo de apoio usado como base para a elaboração deste artigo. O link do vídeo está disponível [Video da montagem](https://www.youtube.com/watch?v=EW2PtRsQQr0).

### 5.2 - Cálculo da Matriz

O processo que para realizar o cálculo da matriz, é o processo mais técnico e
que requer mais atenção e cautela do responsável pela calibragem do equipamento, esse
processo normalmente requer que seja feito mais de uma medição, pois qualquer movimento
pode causar a imprecisão das cores e causando quebras de imagem, quebrando os pixels os
deixando esticados, prejudicando a visualização das cores, prejudicando o aprendizado e o
acabamento visuais da ferramenta.

Durante toda a calibragem tanto o sensor Kinect como o projetor devem ficar
imóveis, para garantir a precisão das leituras, caso ocorra qualquer tipo de movimento no sensor ou no projetor, os passos a seguir devem ser refeitos.
Para realizar essa calibragem, é necessário a utilização do software chamado CalibrateProjector, para iniciar o software deve-se voltar ao terminal (console) e digitar os
seguintes comandos.

```bash
1 cd ~/src/SARndbox-1.6
2 ./bin/CalibrateProjector -s <width> <height>
````

Na segunda linha temos as palavras width (largura) e height (altura), esses valores
podem alterar dependendo do projetor que será utilizado no AR GeoRelief, seguindo a
recomendação presente neste documento, usaremos como exemplo um projetor de 1024 x
768 pixels (HD), ficando os comandos da seguinte forma.

```bash
1 cd ~/src/SARndbox-1.6
2 ./bin/CalibrateProjector -s 1024 768
````

Para esse próximo passo precisamos que seja utilizado um objeto circular, que
possua uma marcação em seu centro, para servir como um alvo, esse objeto pode ser feito
com um CD, onde um lado é coberto com uma folha branca e nessa folha seja cruzado
linhas para definir o ponto central desse disco, pode ser como exemplo a figura abaixo.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/adcbc7ba-800b-45d1-a5ff-5f4bfa18bc5d" width="800px" />
   </div> 
<br>

Aconselhasse colocar uma extensão fina, que seja firme, pois nossa mão não pode
ficar muito próxima ao disco, use esse alvo ao iniciar o CalibrateProjector, onde será
indicado uma sequência de pontos na areia, durante esse processo é importante não deixar
objetos sobre a areia.

Quando iniciamos o CalibrateProjector, ele nos traz uma tela toda vermelha, como
na próxima figura, ao sair essa tela vermelha, será solicitado que seja
definida uma tecla para ser feito o atalho para que seja feito a captação das leituras quando
usarmos o CD, esse atalho não pode ser os botões do mouse, neste trabalho foi usado o
tecla numeral "1".
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/313dfcca-55e0-4608-bd11-f34c4f2a7ff4" width="800px" />
   </div> 
<br>

Após definirmos um atalho para a captação das leituras quando usarmos o CD, a
pressionamos fazendo surgir um novo menu, então clicamos
na última opção Capture.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/15fa31f4-fa13-4702-878a-81287f5df920" width="800px" />
   </div> 
<br>

Quando selecionado a opção Capture, deve surgir um novo menu, conforme a
Figura abaixo, onde é selecionado a primeira opção Creating Capture
tool, ao seleciona-lo novamente escolher uma tecla de atalho, mas dessa vez é para fazer a
captura do background.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/2905ceb8-6c15-418e-bf63-a737795b508c" width="800px" />
   </div> 
<br>

Já possui a ferramenta para ser realizada as leituras, e também, os atalhos para
podermos começar a calibragem. O disco deve estar na cor verde, mostrando que está sendo reconhecido, nesse momento já estão sendo projetadas duas linhas que se cruzam em
um determinado ponto, é nessa intersecção que deve ficar o
centro do CD, a altura que deve ser mantida é a altura em que o CD fique completamente
na cor verde, a altura do CD vai ser modificada a cada leitura, serão definidos pontos
de leituras até mesmo em níveis abaixo da areia, realizando um buraco na mesma para
conseguir acesso à altura recomendada e consiga manter o CD imóvel.
<br>
<br>
   <div align="center">
    <img src="https://github.com/GeoReliefAR/Imagens/assets/169377616/54c96bf4-aee1-4122-9296-1a2798671ecc" width="800px" />
   </div> 
<br>

Ao ser encontrado essa altura ideal, deve-se alinhar a intersecção das linhas com
o centro do CD que será usado como ferramenta para a calibragem e então pressione o
atalho que definimos para captar a leitura, caso a leitura seja bem sucedida, as linhas
mudarão de posição, ponto onde deve ser feita a próxima leitura.

Esse processo exige no mínimo a captura de doze pontos diferentes, mas pode se
fazer indeterminadas leituras, quanto mais leituras forem feitas mais precisas serão as
leituras.

Após realizar a calibragem de todos os pontos, a leitura serão feitas automaticamente
pelo CalibrateProjector através de linhas vermelhas, caso queira verificar a precisão da
calibragem do mesmo, devesse soltar o CD em um ponto desejado, as linhas vermelhas
devem apontar automaticamente para o centro de CD, mostrando a calibragem ideal da
ferramenta, caso os leitura automática não seja realiza ou imprecisa devesse realizar o
passo de calibragem usando o CD novamente, pode ser fechado o CalibrateProjector.

Recomenda-se que seja usado o vídeo de apoio para acompanhar os passos de forma mais visual. O material de apoio está disponível no seguinte link: [Fazendo a Calibragem](https://www.youtube.com/watch?v=EW2PtRsQQr0).

## 6 - Execução

Com todos os passos acima realizados, :clap: finalmente nosso software já está pronto para a execução :clap:,
o software que deve ser iniciado é o SARndbox, ele é o responsável por fazer a integração e
comunicação entre todas as partes, para que seja iniciado execute os seguintes comandos
no terminal:

```bash
1 cd ~/src/SARndbox-1.6/bin
2 ./SARndbox
````

Após os comandos apresentados, será iniciado o software com configuração default,
as projeções e leituras serão iniciadas, já apresentando as cores conforme os relevos feitos
na areia, lembrando que para simular a água, deve-se colocar a mão a uma altura de
aproximadamente 30 - 50 centímetros da areia, fazendo a simulação de uma chuva.
<br>
<br>


