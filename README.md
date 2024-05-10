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
surgiu a necessidade de se adcionar mais imagens. Então, com ajuda de uma extensão de download do Google foram adicionadas mais 2386 imagens novas no dataset, e uma nova raça de cão.
O dataset depois dessas alterações finalizou com `16 raças de cães e 5035 imagens no total`.

![image](https://github.com/VitorEduardoLimaKenor/Dog-Breeds-Classifier/assets/139798373/3745d392-b59f-49c2-b178-ec57ceddb8e5)

# Treinamento do modelo 
## Primeira parte 
No `início do projeto`, foi utilizado a primeira versão do dataset que contava com `15 raças de cães e com um total de 2649 imagens`. 
Ao utilizar uma função do TensorFlow para criar um conjunto de dados de imagens a partir do diretório do dataset, as imagens já 
são redimensionadas e separadas em lotes. Nessa primeira etapa o único pré processamento das imagens foi a normalização. Depois
da normalização o conjunto de dados foi separado em treinamento, validação e teste. Por fim, ao utilizar transferência de aprendizado
com o modelo `InceptionV3` o resultado obtido foi de `99% de precisão no conjunto de treinamento, 97% em validação e 94% em teste`.
Matriz de confusão:

![image](https://github.com/VitorEduardoLimaKenor/Dog-Breeds-Classifier/assets/139798373/163a3476-d3a5-4a65-afdc-dc6966dc648a)

## Segunda e última parte 
Ao colocar o primeiro modelo em ação com imagens coletadas atráves do celular o resultado decaiu bastante. Para conseguir
melhores resultados com as imagens do cotidiano, foi adicionado mais imagens ao dataset. Além de aumentar o dataset, foi utilizado data argumentation
na base de dados de treinamento para melhorar a capacidade de generalização do modelo. Depois desses ajustes, restou aplicar transferência de aprendizado.
O modelo `VGG16` teve um resultado de 92% de precisão no conjunto de treinamento, 77% em validação e 74% em teste. Já o `Xception` teve 93% em treinamento, 95% em validação e 93% em teste.
E o modelo `InceptionV3` teve o melhor resultado, `92% em treinamento, 96% em validação e 95% em teste`. Matriz de confusão:

![image](https://github.com/VitorEduardoLimaKenor/Dog-Breeds-Classifier/assets/139798373/29cd8875-6f7f-4eae-ba45-10b68243cc36)

# Usando o modelo em imagens coletadas pelo celular no cotidiano

Foram coletadas 38 imagens para analisarmos como o modelo se comporta com imagens retiradas do cotidiano.
São 28 imagens da Charlote uma cachorra da raça Shih-tzu, e 10 imagens da Aruska uma cachorra da raça German Shepherd.

## Imagens da Charlote uma cachorra da raça Shih-tzu, modelo teve `92%` de precisão:

![image](https://github.com/VitorEduardoLimaKenor/Dog-Breeds-Classifier/assets/139798373/d164cb1b-14d5-4248-bf13-b2aff9c4d12e)

## Imagens da Aruska uma cachorra da raça German Shepherd, modelo teve `90%` de precisão:

![image](https://github.com/VitorEduardoLimaKenor/Dog-Breeds-Classifier/assets/139798373/d9133961-70b1-4181-a657-0c4df1589d18)

# Sugestões para futuras melhorias
Aumentar o dataset e equilibrar a quantidade de imagens para cada classe. O modelo foi treinado apenas com 30 épocas por falta de poder computacional,
então ao treinar com mais épocas o resultado pode ser superior. Testar outros modelos, ao longo do projeto só foram utilizados os modelos VGG16, Xception e InceptionV3.

