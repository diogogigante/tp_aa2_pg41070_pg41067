# *Brain MRI Images for Brain Tumor Detection*
## Contextualização
- O tumor cerebral é definido como um crescimento anormal de células no cérebro. É uma doença extretamente mortal e infelizmente, comum. A sua taxa de mortalidade ronda os 90% e, em países como Reino Unido, são detetados em média 11 casos diários. Estes, são alguns dos motivos que nos levaram a escolher este tema e descobrir mais sobre o mesmo.

![Brain Tumor](/images/contextualizacao.jpg)

## Objetivos

- Existiam diversos objetivos possíveis para este trabalho e, decidimos, focar-nos essencialmente nos seguintes três:
    - Dada uma imagem de um ressonância magnética, classificar se a mesma contém um tumor cerebral.
    - Construir um modelo versátil, que seja facilmente implementado num contexto real.
    - Classificar as ressonância com precisões elevadas.

## Abordagem

- Inicialmente, realizamos uma divisão dos dados por pastas correspondentes a treino (75%) e teste (25%) com as respetivas classes (*yes*, *no*).

### Passo 1 - Data Treatment (Split):
- Tratamento de dados e respetiva divisão  
    > [1-Data_Treatment.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/1-Data_Treatment.ipynb)
    
![alt text](/images/data-split.png)
    
- Com a divisão dos dados completa, seguiu-se a exploração e análise dos dados, onde verificamos alguns exemplos das imagens do nosso *dataset* e a sua respetiva classe. Feito isso, consideramos também importante observar se o nosso *dataset* era balanceado.

### Passo 2 - Exploratory Data Analysis (EDA):
- Exploração e análise dos dados
    > [2-EDA.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/2-EDA.ipynb)
    
![alt text](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/tree/master/images/eda.png)
   
- Após termos os dados divididos e explorados, decidimos implementar três modelos que consideramos que podiam resolver o nosso problema. Para isso, começamos com três modelos "básicos" de forma a conferirmos dos três, qual o que à partida, têm melhores resultados. Os modelos considerados foram uma rede neuronal, uma rede convolucional e, por fim, uma máquina de vetores de suporte.

### Passo 3 - Implementação de três possíveis abordagens para o problema
- #### Simple Neural Network:
    - Implementação de uma Rede Neuronal simples
        > [3-Simple_NN.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/3-Simple_NN.ipynb)
       
![alt text](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/tree/master/images/acc_snn.png)

- #### Simple CNN:
    - Implementação de uma Rede Neuronal Convolucional simples
        > [4-Simple_CNN.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/4-Simple_CNN.ipynb)
        
![alt text](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/tree/master/images/acc_cnn.png)

- #### Simple SVM:
    - Implementação de uma Máquina de Vetores de Suporte simples
        > [5-Simple_SVM.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/5-Simple_SVM.ipynb)
        
![alt text](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/tree/master/images/acc_svm.png)

- Concluída a implementação dos três modelos e respetivas avaliações, confirmamos que, tal como esperado, o modelo de redes neuronais convolucionais foi o que nos garantiu melhores resultados. Assim sendo, para este mesmo modelo, decidimos realizar uma otimização dos seus parâmetros e verificar as melhorias.

### Passo 4 - Otimização do modelo

- Após otimizado o modelo, para facilitar a compreensão das *features* que o modelo está a selecionar, implementamos uma visualização dos *feature maps* das várias camadas da nossa arquitetura.

### Passo 5 - *Feature Maps*

- ...
        
### Referências

- #### *Dataset*
    - *Brain MRI Images for Brain Tumor Detection*
        >[Brain MRI for Brain Tumor Detection](https://www.kaggle.com/navoneel/brain-mri-images-for-brain-tumor-detection)

## Realizado por:
- Diogo Silva **PG41070**
    > [GitHub](https://github.com/diogogsilva)
- Daniel Faria **PG41067**
    > [GitHub](https://github.com/DanielCoutinhoFaria)