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

### Passo 1 - Data Treatment (Split)

- Inicialmente, realizamos uma divisão dos dados por pastas correspondentes a treino (75%) e teste (25%) com as respetivas classes (*yes*, *no*).
    > [1-Data_Treatment.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/1-Data_Treatment.ipynb)
    
![Data in Folders](/images/data-split.png)

### Passo 2 - Exploratory Data Analysis (EDA)
- Com a divisão dos dados completa, seguiu-se a exploração e análise dos dados, onde verificamos alguns exemplos das imagens do nosso *dataset* e a sua respetiva classe. Feito isso, consideramos também importante observar se o nosso *dataset* era balanceado. Ao observarmos isto, verificamos que 61% dos casos são positivos, ou seja, podemos considerar este valor como uma *baseline* para os futuros valores de *accuracy*.
    > [2-EDA.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/2-EDA.ipynb)
        
![Examples of Image](/images/eda2.PNG)
![Data Distribution](/images/eda.PNG)

### Passo 3 - *Data Augmentation*
- Como o nosso *dataset* continha apenas 253 imagens, decidimos realizar *data augmentation*. Este processo foi realizado com transformações horizontais e verticais.
    > [3-Data_Augmentation.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/3-Data_Augmentation.ipynb)

![Example of Data Augmentation](/images/data_augmentation.PNG)

### Passo 4 - Implementação de três possíveis abordagens para o problema
Após termos os dados divididos, explorados e *data augmentation* introduzida, decidimos implementar três modelos que consideramos que podiam resolver o nosso problema. Para isso, começamos com três modelos "básicos" de forma a conferirmos dos três, qual o que à partida, têm melhores resultados. Os modelos considerados foram uma rede neuronal, uma rede convolucional e, por fim, uma máquina de vetores de suporte.

- #### Neural Network:
    - Implementação de uma Rede Neuronal
        > [4.1-NN.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/4.1-NN.ipynb)
       
![Result NN](/images/nn_result.PNG)

- #### Convolutional Neural Network:
    - Implementação de uma Rede Neuronal Convolucional
        > [4.2-CNN.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/4.2-CNN.ipynb)
        
![Result CNN](/images/cnn_result.PNG)

- #### SVM:
    - Implementação de uma Máquina de Vetores de Suporte
        > [4.3-SVM.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/4.3-SVM.ipynb)
           
![Result SVM](/images/svm_result.PNG)

Conseguimos observar que os valores de *accuracy* nos dados de validação da rede neuronal convolucional são os mais elevados, rondando maioritariamente valores superiores a 80%. A *SVM* também obteve resultados bastante positivos com três dos *kernels*. Por fim, a rede neuronal, foi a que obteve piores resultados, porém, não significativamente.

### Passo 5 - Otimização do modelo, Modelo Final e *Feature Maps*
- Concluída a implementação dos três modelos e respetivas avaliações, confirmamos que, tal como esperado, o modelo de redes neuronais convolucionais foi o que nos garantiu melhores resultados. Assim sendo, para este mesmo modelo, decidimos realizar uma otimização dos seus parâmetros e verificar as melhorias. Para além disso, com os resultados obtidos na otimização, conseguimos então construir o nosso modelo final que, para além de ser mais versátil, garante-nos resultados mais precisos. Com este modelo final, decidimos, para facilitar a compreensão das *features* que estão a ser selecionadas, implementar uma visualização dos *feature maps* das várias camadas da nossa arquitetura.
    > [5-Otimization_Final_Model_Feature_Maps.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/5-Otimization_Final_Model_Feature_Maps.ipynb)
    
![Optimization](/images/otimizacao.PNG)
![Best Model](/images/best_model.PNG)
![Feature Maps](/images/feature_maps.PNG)

### Passo 6 - *Transfer Learning*
- Como extra, decidimos implementar uma solução recorrendo a *transfer learning*. Foi utilizada a aplicação do *Keras VGG16*, que consiste numa rede convolucional, para criar um modelo mais robusto. Com esta implementação, conseguimos resultados equiparáveis à nossa implementação do passo 5. 
    > [6-Transfer_Learning.ipynb](https://github.com/diogogsilva/tp_aa2_pg41070_pg41067/blob/master/6-Transfer_Learning.ipynb)
    
![Transfer Learning Model](/images/tl_model.PNG)

## Conclusão
- Concluimos que conseguimos cumprir todos os objetivos inicialmente definidos e, todos os problemas e dificuldades foram ultrapassados com sucesso. Tendo em conta o tamanho do *dataset* inicial, e, que o vencedor da competição do *Kaggle* obteve 90% de *accuracy* (cerca de mais 7%) consideramos que os resultados foram muito satisfatórios.
- Foi um processo desafiante mas muito gratificante porque conseguimos aprofundar o nosso conhecimento em diversos algoritmos e técnicas de aprendizagem automática e *machine learning*.

## Referências

- #### *Keras*
    - *Keras Documentation*
        >[keras.io](https://keras.io/api/)

- #### *Dataset*
    - *Brain MRI Images for Brain Tumor Detection*
        >[Brain MRI for Brain Tumor Detection (Kaggle)](https://www.kaggle.com/navoneel/brain-mri-images-for-brain-tumor-detection)
        
## Realizado por:
- Diogo Silva **PG41070**
    > [GitHub](https://github.com/diogogsilva)
- Daniel Faria **PG41067**
    > [GitHub](https://github.com/DanielCoutinhoFaria)