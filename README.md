<h1>
  <span>Modelo de previsão Machine Learning para desafio de projeto</span>  <a href="https://www.dio.me/"> <img align="center" width="40px" src="https://hermes.digitalinnovation.one/assets/diome/logo-minimized.png"></a>    
</h1>
Esse modelo de previsão foi criado e treinado com um conjunto de dados históricos de alugueis de bicicletas, ele prevê um número de alugueis para um determinado dia, as características de base são informações sazonais e meteorologicas. Os dados que são consumidos para o modelo são de propriedades de
<a href="https://capitalbikeshare.com/system-data"> 
   <img align="center" alt="Capital Bikeshare" src="https://img.shields.io/badge/Capital%20Bikeshare-FF4500?style=for-the-badge">
  </a>   e as orientações a seguir estão em <a href="https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html"> 
   <img align="center" alt="Microsoft Learning" src="https://img.shields.io/badge/Microsoft%20Learning-0000FF?style=for-the-badge">
  </a>
<h2> Criar espaço de trabalho:</h2>
Após acessar o portal  <a href="https://portal.azure.com"> 
   <img align="center" alt="Azure Machine Learning" src="https://img.shields.io/badge/Azure%20Machine%20Learning-30A3DC?style=for-the-badge">
  </a> com suas credenciais é necessário criar um espaço de trabalho.
<h3> Selecione  <img align="center" alt="+ Criar um recurso" src="https://img.shields.io/badge/+Criar%20um%20recurso-FFFAFA?style=for-the-badge"></h3>
Pesquise por Azure Machine Learning
Preencha os campos com as configurações:</br>

**Assinatura**: nome da assinatura sugerido no campo.
</br>**Grupo de recursos** : Selecione ou crie um novo
</br>**Nome** : dê um nome para o grupo de recursos. `Exemp:. teste123`.
</br>**Região** : escolha a região mais próxima.
</br>**Conta de armazenamento** : esse campo é preenchido automaticamente, pode deixar.
</br>**Cofre de chaves** : esse campo é preenchido automaticamente, pode deixar.
</br>**Insights de aplicativo** : esse campo é preenchido automaticamente, pode deixar.
</br>**Registro de conteiner** : _nenhum_.
<h4> Selecione  <img align="center" alt="Revisar + criar" src="https://img.shields.io/badge/Revisar%20+%20Criar-FFFAFA?style=for-the-badge"> depois <img align="center" alt="criar" src="https://img.shields.io/badge/Criar-FFFAFA?style=for-the-badge"> </h4>
Aguarde a criação do espaço, isso leva alguns minutos.
<h4> Selecione  <img align="center" alt="Launch Studio" src="https://img.shields.io/badge/Launch%20Studio-0000FF?style=for-the-badge"></h4>
<h4> Selecione  o espaço de trabalho recém-criado</h4>
<h2>Treinando um modelo de previsão com machine learning automatizado</h2>
</br> Para esse exemplo usamos um conjunto de dados consumidos por url, são dados históricos para treinar um modelo de previsão para aluguel de bicicletas.
<h2>Expanda o menu superior e selecione <img align="center" alt=" ML automatizado" src="https://img.shields.io/badge/ML%20automatizado-FFFAFA?style=for-the-badge"> </h2>
<h3>Selecione <img align="center" alt="Criar trabalho ML automatizado" src="https://img.shields.io/badge/+%20novo%20trabalho%20de%20ML%20automatizado-FFFAFA?style=for-the-badge"></h3>
<h2>Configurações básicas</h2>

**Nome do trabalho** : mslearn-bike-automl.
</br>**Novo nome do experimento** :  mslearn-bike-rental
</br>**Descrição** : Aprendizado de máquina automatizado para previsão de aluguel de bicicletas
</br>**Marcadores** : _nenhum_.
</br> <img align="center" alt="Avançar" src="https://img.shields.io/badge/Avançar-0000FF?style=for-the-badge">
<h2>Tipo de tarefa e dados</h2>

**Selecione o tipo de tarefa** : Regressão
</br>**Selecionar conjunto de dados :** : Criar um conjunto de dados
<h2>Tipo de dados</h2>

**Nome** : alugueldebicicletas`(não pode ter espaços em branco)`.
</br>**Descrição** : dados históricos de aluguel de bicicletas
</br>**Tipo** : Tabular
<h2>Fonte de dados</h2>

Selecione **Dos arquivos da web** 
<h2>URL da Web</h2>

</br>**URL da Web** : ``` https://aka.ms/bike-rentals ```
</br>**Ignorar validação de dados** : _não selecionar_
<h2>Configurações :</h2>

**Formato de arquivo** : Delimitado
</br>**Delimitador** : Vírgula
</br>**Codificação** : UTF-8
</br>**Cabeçalhos de coluna** : Somente o primeiro arquivo possui cabeçalhos
</br>**Pular linhas** : _nenhum_ </br>
**O conjunto de dados contém dados multilinhas** : _não selecionar_
<h2>Esquema :</h2>

Deixar todas colunas selecionadas exceto **Path**
</br> <img align="center" alt="Criar" src="https://img.shields.io/badge/Criar-0000FF?style=for-the-badge">
Após a criação selecione o conjunto de dados **alugueldebicicletas** para enviar o trabalho de ML automatizado. 
<h2>Configurações de tarefa :</h2>

**Tipo de tarefa** : Regressão `(já estará definido)`
</br>**Conjunto de dado** :alugueldebicicletas `(já estará definido)`
</br>**Coluna de destino** : Rentals(Integer)
<h2>Configurações adicionais :</h2>

**Métrica primária** : raiz do erro quadrático médio normalizado
</br>**Explique o melhor modelo** : _não selecionar_
</br>**Usar todos os modelos suportados** : _desmarcado_
</br>**Modelos permitidos** : no combo seleciona as opçoes **_LightGBM_**, **_RandomForest_**
<h2>Limites :</h2>

**Máximo de testes** : 3
</br>**Máximo de testes simultâneos** : 3
</br>**Máximo de nós** : 3
</br>**Limite de pontuação da métrica** : 0,085
</br>**Tempo limite** : 15
</br>**Tempo limite de iteração** : 15
</br>**Habilitar rescisão antecipada** : _selecionar_
<h2>Validação e teste  :</h2>

**Tipo de validação** : divisão de validação de treinamento
</br>**Porcentagem de dados de validação** : 10
</br>**Conjunto de dados de teste** : _nenhum_
<h2>Calcular :</h2>

**Selecione o tipo de computação** : sem servidor
</br>**Tipo de máquina virtual ** : CPU
</br>**Camada de máquina virtual** : Dedicada
</br>**Tamanho da máquina virtual** :Standard_DS3_V2* `(Escolha a máquina que melhor te atende, o valor descrito é cobrado por hora em que a instancia do seu modelo estiver disponível)`
</br>**Número de instâncias** : 1 </br>
Enviar o trabalho de treinamento. `Obs.: é inciado automaticamente, demora alguns minutos.`

<h2>Avaliar o melhor modelo :</h2>

Na guia **Visão Geral** voc terá a visão do trabalho de treinamento 
No lado inferior direito vc terá algumas informações, selecione o melhor modelo que esta logo abaixo de **Algorithm name**.
</br>Na guia **Métricas** você poderá analisar os gráficos gerados
<h2>Implantar e testar :</h2>

Na guia **Modelo** no menu lateral estará o melhor modelo de treinamento selecione **Implantar**, opção **serviço Web**
<h2>Configurações:</h2>

**Nome** : prever-aluguéis
</br>**Descrição** :  Prever aluguel de bicicletas
</br>**Tipo de computação** :  Instância de Contêiner do Azure
</br>**Habilitar autenticação** :  selecionado
</br>A implantação leva alguns minutos em quanto isso o **status de implantação** vai estar **Executando** quando filalizado vai estar **sucesso**
<h2>Teste do modelo implantado:</h2>
No menu lateral selecione <img align="center" alt="Pontos de extremidades" src="https://img.shields.io/badge/Pontos%20de%20extremidades-FFFAFA?style=for-the-badge"> 

na aba **Pontos de extremidades em tempo real** e selecione o modelo
</br> Visualize a guia **Teste**
</br> Em **Dados de entrada para testar os pontos de extremidades** substitua os dados de entrada por

```javascript
  {
   "Inputs": { 
     "data": [
       {
         "day": 1,
         "mnth": 1,   
         "year": 2022,
         "season": 2,
         "holiday": 0,
         "weekday": 1,
         "workingday": 1,
         "weathersit": 2, 
         "temp": 0.3, 
         "atemp": 0.3,
         "hum": 0.3,
         "windspeed": 0.3 
       }
     ]    
   },   
   "GlobalParameters": 1.0
 }
 ```
Clique em  <img align="center" alt="Testar" src="https://img.shields.io/badge/Testar-0000FF?style=for-the-badge"> </br>
Resultados do teste `Terá um resultado similar a esse`
O Teste retorna, de acordo com as entradas um número previsto de aluguéis.
```
 {
   "Results": [
     444.27799000000000
   ]
 }
```

<h2>Limpar:</h2>

Você criou um serviço web que está hospedado em uma instância de container da Azure, afim de evitar uso  desnecessário dos recursos, é necessário eliminar o **ponto de extremidades**,
caso sua instãncia permaneça será cobrado pelo uso de recursos.
Selecione **pontos de extremidades** no meu lateral
selecione o ponto de extremidades de previsão de aluguel e selecione **Excluir**








