
# Introdução a Detecção de Objetos com YOLOv8

Bem-vindo ao projeto de **Detecção de Objetos com YOLOv8**, desenvolvido para realizar a detecção de diferentes tipos de objetos em imagens e vídeos com precisão e rapidez. Este repositório foi projetado para facilitar a análise de objetos, como carros, capacetes de segurança e balões de quadrinhos, aplicando modelos treinados específicos para cada tipo de objeto.

Acesse o repositorio do projeto em: <https://github.com/unama-aula-yolo/aula>

## Estrutura do Projeto

O projeto está organizado da seguinte forma:

```bash
├── dataset_A            # Modelo treinado para detecção de carros
├── dataset_B            # Modelo treinado para detecção de capacetes de segurança
├── dataset_C            # Modelo treinado para detecção de balões de quadrinhos
├── imagem_quadrinhos    # Imagens para detecção de balões de quadrinhos
├── video_canteiro_obra  # Vídeos para detecção de capacetes de segurança
└── video_carro_na_pista # Vídeos para detecção de carros
```

## Funcionalidades

1. **Detecção de Carros**: Usando o `modelo_A.pt`, treinado para identificar veículos em imagens e vídeos de trânsito.
2. **Detecção de Capacetes de Segurança**: Com o `modelo_B.pt`, o projeto detecta capacetes em canteiros de obras, útil para verificar o uso de EPIs.
3. **Detecção de Balões de Quadrinhos**: O `modelo_C.pt` identifica balões de fala e pensamento em imagens de quadrinhos e cartoons.

## Como Usar

Para aplicar os modelos:

1. **Carregue o modelo desejado**:
   - `modelo_A.pt` para carros, `modelo_B.pt` para capacetes, e `modelo_C.pt` para balões de quadrinhos.

2. **Execute a Inferência**:
   - Aplique o modelo em imagens ou vídeos nas pastas específicas para detectar os objetos correspondentes.

3. **Visualize os Resultados**:
   - Veja as imagens ou vídeos anotados com as detecções usando a biblioteca OpenCV.

## Exemplo Rápido de Uso

Aqui está um exemplo de código para realizar a detecção de carros em uma imagem:

```python
from ultralytics import YOLO
import cv2
from google.colab.patches import cv2_imshow

# Carregar o modelo de detecção de carros
model = YOLO('./dataset_A/modelo_A.pt')

# Caminho da imagem
imagem_path = './video_carro_na_pista/video1.mp4'

# Realizar a inferência
results = model(imagem_path)

# Exibir o frame anotado
annotated_image = results[0].plot()
cv2_imshow(annotated_image)
```

## Requisitos

- **YOLOv8**: Algoritmo de detecção de objetos.
- **OpenCV**: Manipulação e exibição de imagens e vídeos.
- **Google Colab**: (Opcional) Ambiente gratuito com suporte a GPU para treinar e testar os modelos.

## Contribua com o Projeto

Sinta-se à vontade para enviar melhorias, adicionar novos datasets ou otimizar os modelos. Este projeto é aberto para a comunidade e estamos ansiosos para receber suas sugestões!

---

Aproveite o projeto e boa exploração na detecção de objetos com YOLOv8!
