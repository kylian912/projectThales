# hoofdChart met subcharts

Dit is een voorbeeld van hoe een chart met subcharts gebouwd kan worden in Helm 3.
We hebben een Hoofdchart met twee subcharts. Een lokale subchart genaamd: subchart (nginx webserver). De tweede subchart is een mongodb van bitnami, opgehaald van internet.

## Om te installeren:

1. Maak een namespace aan met de naam: thales (Deze wordt gebruikt door subchart)

    ```kubectl create ns thales```

2. Zet de namespace naar: thales

    ```kubectl config set-context --current --namespace thales```

3. Kopiër het mapje hoofdChart en subchart van github naar de Desktop.
4. Open de terminal en navigeer naar het mapje hoofdChart.
5. Met de terminal in hoofdChart, update alle subcharts.

    ```helm dependency update```
    
6. Installeer de hoofdChart, die vervolgens de subcharts gaat uitrollen.

    ```helm install -f values.yaml test123 .```
    
7. Controleer of de subcharts correct geinstalleerd zijn. Als het goed is draaien er nu vier pods. 1x mongodb en 3x subchart.

    ```kubectl get pods```
    
   
