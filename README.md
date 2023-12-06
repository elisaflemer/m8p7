# m8p7

Esta atividade usa a biblioteca TensorFlow para treinar uma rede neural convolucional (CNN) no conjunto de dados MNIST. O MNIST é uma base de dados que contém imagens de dígitos manuscritos de 0 a 9, cada uma com resolução de 28x28 pixels, e é frequentemente utilizado como um benchmark no campo de visão computacional.

O treinamento começa carregando o conjunto de dados MNIST, dividindo-o em conjuntos de treino e teste. Em seguida, as imagens são normalizadas para escalá-las entre 0 e 1. A arquitetura da rede neural é definida como sequencial, consistindo em camadas de achatamento (Flatten) para converter as imagens 2D em um vetor 1D, seguido por duas camadas totalmente conectadas (Dense) com ativação ReLU. A última camada tem 10 unidades com ativação softmax, representando as 10 classes (dígitos de 0 a 9). O modelo é compilado usando o otimizador 'adam', a função de perda 'sparse_categorical_crossentropy', e a métrica de precisão para rastrear o desempenho.

O treinamento é realizado com o método fit, utilizando os dados de treino e especificando o número de épocas como 3. Após o treinamento, o modelo é avaliado no conjunto de teste usando o método evaluate, e os resultados, perda (val_loss) e precisão (val_acc), são impressos. Este código ilustra a construção e treinamento básico de uma CNN para reconhecimento de dígitos manuscritos utilizando TensorFlow.

**Resultados:** 96% de acurácia

## Como rodar

Para retreinar o modelo, basta abrir o notebook "Treinamento.ipynb" e rodar todas as células. Será salvo o modelo final com o nome 'epic_num_reader.model'. Para prever novos itens, basta carregar esse modelo e realizar predições com os seguintes comandos:

'''
new_model = tf.keras.models.load_model('epic_num_reader.model')
predictions = new_model.predict(x_test)
'''
