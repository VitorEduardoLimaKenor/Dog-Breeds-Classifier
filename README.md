<h1 align="center">Classificador de Raças de Cães 🐶</h1>

[![MasterHead](https://www.racoesreis.com.br/wordpress/wp-content/uploads/imagem_do_post-105.jpg)]()

# Sobre o projeto
Este projeto, realizado em Python, faz uso das bibliotecas TensorFlow, scikit-learn e Keras para o treinamento de um modelo de aprendizado profundo.
O objetivo é criar um sistema capaz de identificar a raça de um cão a partir de uma imagem fornecida como entrada.

O modelo é treinado com uma base de dados que compreende 16 raças distintas de cães, incluindo:
- Beagle
- Boxer
- Chihuahua
- Corgi
- Dachshund
- French Bulldog
- German Shepherd
- Golden Retriever
- Husky
- Pomeranian
- Poodle
- Pug
- Rottweiler
- Shiba Inu
- Shih-tzu
- Yorkshire Terrier

# Montagem do dataset
Inicialmente a composição do dataset se resumia a união de dois conjuntos de dados disponibilizados no Kaggle.

O primeiro deles é o "[23 Pet Breeds Image Classification](https://www.kaggle.com/datasets/aseemdandgaval/23-pet-breeds-image-classification)":

![image](https://github.com/VitorEduardoLimaKenor/Dog-Breeds-Classifier/assets/139798373/a915908a-e59f-4f47-891c-26f918077090)

Esse dataset contém imagens de cães e gatos, são 15 raças de cães e 8 raças de gatos. Cada uma das classes possui 170 imagens.

Pegando somente as imagens de cães desse conjunto eu mesclei ele com o segundo dataset chamado "[Dog's Breed Dataset](https://www.kaggle.com/datasets/yapwh1208/dogs-breed-dataset)": 

![image](https://github.com/VitorEduardoLimaKenor/Dog-Breeds-Classifier/assets/139798373/94d92606-38a5-405e-b6be-79eacc93b5f5)

Esse dataset contém imagens de 5 raças de cães que já existiam no outro dataset, portanto serviram para aumentar o número de imagens dessas raças.
Quando eu fiz a união desses dois conjuntos de dados eu consegui 15 raças de cães, com um total de 2649 imagens. Ao longo do projeto, em busca de melhores resultados
surgiu a necessidade de se adcionar mais imagens. Então, com ajuda de uma extensão de download do Google foram adicionadas mais 2686 imagens novas no dataset, e uma nova raça de cão.
O dataset depois dessas alterações ficou com 16 raças de cães e 5335 imagens no total.
