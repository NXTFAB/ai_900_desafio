# 🚀 **Aprendendo com Azure Machine Learning**

**Tempo estimado:** ~35 minutos 🕒  
**Objetivo:** Treinar, avaliar e implantar um modelo de machine learning usando o Azure ML. 🌟

## 🛠️ **Passo a Passo**

### 1️⃣ **Configurar o Workspace**
1. Acesse o portal do [Azure](https://portal.azure.com). 🌐  
2. Crie um recurso de **Machine Learning** com estas configurações:
   - Grupo de recursos: escolha ou crie um 🗂️.
   - Nome: algo único 🧩.
   - Região: `East US`.
3. Clique em `Review + Create` e aguarde a criação. ⏳  
4. Vá no recurso criado e selecione **Launch Studio**. 🚪

### 2️⃣ **Treinar o Modelo (Automated ML)**
1. No Azure ML Studio, vá em **Automated ML**.  
2. Crie um trabalho (`Job`) com estas configs:  
   - Nome do experimento: `mslearn-bike-rental` 🚴‍♂️  
   - Dados: Baixe e suba os arquivos da [base de dados](https://aka.ms/bike-rentals).  
     - **Dataset**: histórico de aluguel de bicicletas.  
   - Alvos e tarefas:  
     - Tipo: `Regressão`.  
     - Alvo: `rentals`.  
   - Modelos permitidos: `RandomForest` e `LightGBM`. 🌲✨  
   - Tempo máximo: `15 minutos`.  
3. Submeta e tome aquele café enquanto roda! ☕  

### 3️⃣ **Revisar o Melhor Modelo**
1. Após finalizado, veja o melhor modelo. 🏆  
2. Explore as métricas: `residuals` e `predicted_true` gráficos 📊.

### 4️⃣ **Implantar e Testar**
1. Vá na aba **Model** do melhor modelo:  
   - Implantação: `Real-time endpoint`.  
   - VM: `Standard_DS3_v2`.  
2. Aguarde o status `Succeeded`. ✅  
3. Teste o endpoint com este JSON (ajuste se precisar):
   ```json
   {
       "input_data": {
           "columns": ["day", "mnth", "year", "season", "holiday", "weekday", "workingday", "weathersit", "temp", "atemp", "hum", "windspeed"],
           "index": [0],
           "data": [[1, 1, 2022, 2, 0, 1, 1, 2, 0.3, 0.3, 0.3, 0.3]]
       }
   }
   ```

### 5️⃣ **Limpeza Final**
1. Exclua o endpoint para evitar custos extras. 🗑️  
2. Apague o workspace, se não for mais usar. 🚮  
