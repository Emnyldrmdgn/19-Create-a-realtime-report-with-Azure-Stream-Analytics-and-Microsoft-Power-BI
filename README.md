# 19-Create-a-realtime-report-with-Azure-Stream-Analytics-and-Microsoft-Power-BI
In this exercise, you'll use A. Stream Analytics to process a stream of sales order data, such as might be generated from an online retail application. The order data will be sent to A. Event Hubs, from where your Azure Stream Analytics job will read and summarize the data before sending it to Power BI,where you will visualize the data in a report.
# Realtime rapporten maken met Azure Stream Analytics

Dit project omvat realtime gegevensverwerking met behulp van **Azure Stream Analytics** en visualisatie met behulp van **Microsoft Power BI**. We maken een realtimerapport in Power BI door de gegevensstroom van **Azure Event Hubs** te verwerken.

## 📌 Vereisten
- Azure-abonnement
- **Azure Event Hubs** een gestructureerde gegevensbron
- Een werkruimte voor **Azure Stream Analytics**
- **Microsoft Power BI**-account

## 🚀 Installatie en stappen

### 1️⃣ **Azure Event Hubs maken**
1. Meld u aan bij de **Azure Portal**.
2. **Event Hubs**-resource aanmaken:
- Maak een **Event Hub-naamruimte**. 
- Maak er een **Event Hub** in. 
- **Configureer relevante toegangsbeleidsregels**.

### 2️⃣ **Azure Stream Analytics-taak maken**
1. Maak een **Stream Analytics**-resource in de **Azure Portal**.
2. Maak een **Stream Analytics-taak**.
3. Geef **Event Hub** op als invoerbron.

### 3️⃣ **Stream Analytics-query definiëren**
1. Definieer een SQL-query met de **Query-editor** als volgt:

``sql
SELECT
COUNT(*) ALS TotaalOrders,
Systeem.Tijdstempel AS TimeGenerated
NAAR BINNEN
[Power BI-uitvoer]
VAN
[EventHubInput]
GROEPEREN OP
TumblingWindow(minuut, 1)

### 4️⃣ Uitvoer verbinden met Power BI
Ga in Azure Portal naar het tabblad Uitvoer.
Voeg een nieuwe Uitvoer toe en stel het doel in op Power BI.
Selecteer Power BI Workspace en controleer de verbinding.

### 5️⃣ Stream Analytics-taak uitvoeren
Start uw Azure Stream Analytics-taak.
Zodra de realtimegegevensstroom start, worden de gegevens naar Power BI verzonden.

### 6️⃣ Realtime rapportvisualisatie in Power BI
Maak een nieuw rapport in Power BI.
Realtime-dataset verbinden.
Maak rapporten door grafieken en visualisatiecomponenten toe te voegen.

## 🎯 Conclusie
In deze studie hebben we een realtimerapport over Power BI gemaakt door de gegevensstroom te verwerken met Azure Stream Analytics. We hebben de bestelgegevens met tijdstempels geanalyseerd en in een rapport samengevoegd.

## ❗ Aanvullende opmerkingen
Foutopsporing: Als de gegevensstroom niet binnenkomt, controleer dan de Event Hub-verbinding en de Stream Analytics Query.
Schaalbaarheid: met partitionering kunt u grote gegevensstromen effectiever verwerken.

## Screenshots

![lab19powerBI](https://github.com/user-attachments/assets/8dcd2626-84ae-4110-a196-b5795e48460f)
![lab191dp](https://github.com/user-attachments/assets/d7d59348-c166-47a1-8ba8-334c066a6e90)
![lab193streamaltkjop](https://github.com/user-attachments/assets/ba2fb44c-7dde-4a70-a954-8a328902a020)
![lab194input](https://github.com/user-attachments/assets/c3d22ba6-38e6-411a-959e-968b7263f537)
![lab194output](https://github.com/user-attachments/assets/ee0b0fef-b1ba-410c-bbe6-dab3b4843f27)
![lab195start](https://github.com/user-attachments/assets/8ba7158d-84ac-4883-8d28-eb4906405e26)
![lab196BI](https://github.com/user-attachments/assets/85642746-b0c5-4f20-8c3d-70879b2dfc47)
![lab19powerBI2](https://github.com/user-attachments/assets/4318bf19-2293-4821-a0c0-f2eb5885c8fd)
![lab19powerBI3](https://github.com/user-attachments/assets/1c31b076-b33f-495c-a640-ea5f113efb81)

