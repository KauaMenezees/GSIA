# GSIA

# Projeto CleanWave
# 🌍 Visão Geral
Este projeto tem como objetivo melhorar a saúde dos ecossistemas marinhos através da implementação de lixeiras inteligentes nas praias. As lixeiras identificam os usuários e os tipos de resíduos, incentivando o descarte consciente através de um sistema de recompensas.

# 🚀 Funcionalidades
Identificação de Usuários via QR Code: Cada lixeira possui um QR Code que, quando escaneado pelo aplicativo do projeto, identifica o usuário.
Reconhecimento Automático de Resíduos: Um scanner integrado analisa o tipo de resíduo e abre a lixeira automaticamente se o item for reconhecido.
Sistema de Pontuação e Recompensas: Pontos são concedidos por cada item descartado corretamente, que podem ser trocados por recompensas no aplicativo.
🛠 Tecnologias
Roboflow: Utilizado para o treinamento de modelos de inteligência artificial para reconhecimento de resíduos.
IoT: Emprega sensores e atuadores para gerenciar as funções das lixeiras.
Aplicativo Móvel: Interface para que os usuários interajam com o sistema.

# 🌳 Impacto Ambiental
Espera-se que a implementação das lixeiras inteligentes resulte em uma significativa redução dos resíduos nas praias, contribuindo diretamente para a saúde dos ecossistemas marinhos. Ao facilitar o descarte correto e incentivar a reciclagem, o projeto tem o potencial de diminuir a poluição marinha, proteger a vida marinha e promover um ambiente mais limpo e sustentável.

# 🤳 Engajamento da Comunidade
O sistema de pontos e recompensas é projetado para motivar tanto a comunidade local quanto os visitantes das praias a engajar-se ativamente na limpeza e conservação. Ao transformar a coleta de lixo em uma atividade recompensadora, o projeto não só educa o público sobre práticas ambientais corretas, mas também fomenta um sentido de responsabilidade e orgulho comunitário.

# 📦 Instalação do a Opção 1 de Deep Learning
Instale as dependências necessárias usando pip:

pip install roboflow

# 🔧 Configuração
Inicialize o projeto com suas configurações de API e workspace:

from roboflow import Roboflow

rf = Roboflow(api_key="206yLtqXls5wCb8kq7L3")

project = rf.workspace("unuja").project("deteksiplastik")

version = project.version("your_version")

model = version.model

dataset = version.download("coco")

# 🚀 Uso
Para realizar uma predição com o modelo:

print(model.predict("copiar endereço da imagem ex: imagem1", confidence=40, overlap=30).json())

model.predict("copiar mesmo endereço da imagem usada acima 'imagem1' ", confidence=40, overlap=30).save("copiar outro endereço de imagem exemplo: imagem2")


import cv2

import matplotlib.pyplot as plt

import os

from PIL import Image

from google.colab.patches import cv2_imshow

resultado = cv2.imread('copiar endereço da 'imagem2' usada acima')

cv2_imshow(resultado)

# 📎 Anexo
⚠️⚠️⚠️Caso o programa não rode por causa de versão o problema esta relacionado ao Dataset do Universe do Roboflow, para resolver o problema tem que entrar neste link do dataset

https://universe.roboflow.com/unuja/deteksiplastik/dataset/4#

Ao entrar no link ir em "Dataset"

![image](https://github.com/KauaMenezees/GSIA/assets/130618063/d6acf622-f53d-47b8-9804-dad227047a24)

Depois ir em "Download Dataset"

![image](https://github.com/KauaMenezees/GSIA/assets/130618063/5319ce8a-d2b3-488a-8dc7-8e2148737386)

Quando você clicar em "Download Dataset" abrira esta tela abaixo para selecionar o "Format" e o tipo de codigo, selecione o format "COCO" e deixe o "show download code", depois prossiga para "Continue"

![image](https://github.com/KauaMenezees/GSIA/assets/130618063/843c6ced-c29c-4e92-8bf6-a6b95551dcd4)

Depois de prossigir aparecer o seu codigo junto com sua API, deixe selecionado "Jupyter" e copie o codigo

![image](https://github.com/KauaMenezees/GSIA/assets/130618063/3a00143d-0ffe-417a-a3ac-656a94f7e584)

Depois disso é so copiar o codigo e colocar na primeira opção do projeto, adendo ao colar o codigo do Roboflow Universe coloque junto o "model = project.version(4).model" como esta na imagem logo abaixo

![image](https://github.com/KauaMenezees/GSIA/assets/130618063/2472c0b0-da1f-4477-b972-3af93e9153e8)

(⚠️⚠somente realizar este processo caso o programa não rode por causa de version de dataset)

# Criação de um Ambiente Simulado de IOT no Wowki

# 🔗 Link do Projeto no Wowki

https://wokwi.com/projects/399948180229675009

# 🤖 Uso

# ESP23
Este código Python simula um sistema utilizando um microcontrolador compatível com o framework
de software MicroPython, que está interagindo com um display OLED e um sensor de distância
ultrassônico HC-SR04. Aqui está uma explicação detalhada do que o código faz:

# Componentes Utilizados:
Display SSD1306 (OLED): Conectado via I2C, usado para exibir a contagem de objetos detectados.

![image](https://github.com/KauaMenezees/GSIA/assets/130618063/47563417-2d97-41de-90fe-0b2c2986560d)

Sensor Ultrassônico HC-SR04: 

![image](https://github.com/KauaMenezees/GSIA/assets/130618063/6480dcac-644e-4622-af3a-ed4a99a8ce94)

Utilizado para medir a distância até um objeto.

O código conta quantos objetos foram detectados a uma distância inferior a 50 cm. Cada vez que um
objeto é detectado pela primeira vez, a contagem é incrementada e o display OLED é atualizado
para mostrar o novo valor da contagem. A flag objectDetected garante que a contagem só seja
incrementada uma vez por objeto, mesmo que ele permaneça na frente do sensor por um período
prolongado.

# Teste:
1. Rodar o código
2. Clicar no sensor ( Vai abri o controlador de distancia que simula a distancia do objeto)
   
![image](https://github.com/KauaMenezees/GSIA/assets/130618063/831dc3c0-637e-42de-b251-07c02c0e8bcf)

No código esta estabelecido que ele só vai adicionar o objeto a contagem se a distancia for menor
que 10cm:
```
 if distance < 10 and not objectDetected:
 count += 1
 objectDetected = True
 update_display(count)
```
3. Arrastar distancia para menos que 10, depois para mais que 10. Assim é simulado que um objeto
se aproximou do sensor e depois saiu.

Cada vez que um objeto é detectado pela primeira vez, a contagem é incrementada e o display OLED
é atualizado para mostrar o novo valor da contagem. 

![image](https://github.com/KauaMenezees/GSIA/assets/130618063/e9a0f157-ae14-4b52-aedf-1ff7575e28c3)

A flag objectDetected garante que a contagem só seja incrementada uma vez por objeto, mesmo
que ele permaneça na frente do sensor por um período prolongado.

# 🌊 Conexão com nosso projeto
Nosso projeto consiste em desenvolver uma lixeira inteligente de praia, projetada para incentivar as
pessoas a descartarem corretamente os resíduos recicláveis e, assim, ajudar a evitar a poluição. O
objetivo é criar uma solução que não só melhore a gestão de resíduos nas praias, mas também
conscientize os usuários sobre a importância da reciclagem.
Para isso, foi construído um protótipo funcional, que é uma versão mínima viável (MVP) do produto
final. Este protótipo utiliza um sensor ultrassônico HC-SR04 e um display OLED SSD1306 para contar
e exibir a quantidade de objetos recicláveis depositados na lixeira.

# ⛱️ Próximos Passos
Este protótipo é apenas o primeiro passo para o desenvolvimento da lixeira inteligente de praia. Com
base nos testes e no feedback, serão adicionadas funcionalidades adicionais, como reconhecimento
de diferentes tipos de resíduos e comunicação com uma base de dados central para monitoramento
remoto.
Em resumo, este MVP permite validar o conceito e testar a funcionalidade básica do produto. Ele
serve como uma base sólida para futuras melhorias e refinamentos, com o objetivo final de criar uma
solução eficiente e eficaz para a gestão de resíduos recicláveis nas praias.


