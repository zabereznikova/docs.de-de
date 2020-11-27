---
title: 'Vorgehensweise: Dienstdatenpartitionierung'
ms.date: 03/30/2017
ms.assetid: 1ccff72e-d76b-4e36-93a2-e51f7b32dc83
ms.openlocfilehash: 7bb5eb6bda8bb2be3dfaaa88eb4b5ad787f47aa7
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268923"
---
# <a name="how-to-service-data-partitioning"></a>Vorgehensweise: Dienstdatenpartitionierung

In diesem Thema werden die grundlegenden Schritte beschrieben, die erforderlich sind, um Meldungen über mehrere Instanzen des gleichen Zieldiensts zu partitionieren. Die Partitionierung von Dienstdaten wird in der Regel verwendet, wenn Sie einen Dienst skalieren müssen, um eine bessere Dienstqualität bereitzustellen, oder wenn Sie Anforderungen verschiedener Kunden jeweils auf bestimmte Art und Weise behandeln müssen. Beispielsweise müssen Nachrichten von hochwertigen oder "Gold"-Kunden möglicherweise mit einer höheren Priorität verarbeitet werden als Nachrichten von einem Standardkunden.  
  
 In diesem Beispiel werden Nachrichten zu einem von zwei Instanzen des regularCalc-Diensts geleitet. Beide Instanzen des Diensts sind identisch. Der vom calculator1-Endpunkt vertretene Dienst verarbeitet jedoch Nachrichten von wichtigen Kunden, und der calculator2-Endpunkt verarbeitet Nachrichten von anderen Kunden.  
  
 Die vom Client gesendete Nachricht enthält keine eindeutigen Daten, anhand denen ermittelt werden kann, an welche Dienstinstanz die Meldung weitergeleitet werden soll. Um es allen Clients zu ermöglichen, Daten an einen bestimmten Zieldienst weiterzuleiten, implementieren wir zwei Dienstendpunkte, die zum Empfangen von Nachrichten verwendet werden.  
  
> [!NOTE]
> In diesem Beispiel werden zwar bestimmte Endpunkte zum Partitionieren von Daten verwendet, aber dies kann auch mit Informationen erreicht werden, die innerhalb der Meldung selbst enthalten sind, z. B. Header- oder Textdaten.  
  
### <a name="implement-service-data-partitioning"></a>Implementieren der Dienstdatenpartitionierung  
  
1. Erstellen Sie die grundlegende Routingdienstkonfiguration, indem Sie die vom Dienst verfügbar gemachten Dienstendpunkte angeben. Im folgenden Beispiel werden zwei Endpunkte definiert, die zum Empfangen von Meldungen verwendet werden. Außerdem werden die Clientendpunkte definiert, die verwendet werden, um Nachrichten an die regularCalc Dienstinstanzen zu senden.  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoints for the Routing Service-->  
        <!--create the endpoints for the calculator service-->  
        <endpoint address="calculator1"  
                  binding="wsHttpBinding"  
                  name="calculator1Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <endpoint address="calculator2"  
                  binding="wsHttpBinding"  
                  name="calculator2Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
       </service>  
    </services>  
    <client>  
    <!--set up the destination endpoints-->  
        <endpoint name="CalcEndpoint1"  
                  address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                  binding="netTcpBinding"  
                  contract="*" />  
  
        <endpoint name="CalcEndpoint2"  
                  address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                  binding="netTcpBinding"  
                  contract="*" />  
     </client>  
    ```  
  
2. Definieren Sie die Filter, die verwendet werden, um Nachrichten an die Zielendpunkte weiterzuleiten.  In diesem Beispiel wird mithilfe des EndpointName-Filters ermittelt, welcher Dienstendpunkt die Nachricht empfangen hat. Im folgenden Beispiel werden der erforderliche Routingabschnitt und die Filter definiert.  
  
    ```xml  
    <filters>  
      <!--define the different message filters-->  
      <!--define endpoint name filters looking for messages that show up on the virtual endpoints-->  
      <filter name="HighPriority" filterType="EndpointName"  
              filterData="calculator1Endpoint"/>  
      <filter name="NormalPriority" filterType="EndpointName"  
              filterData="calculator2Endpoint"/>  
    </filters>  
    ```  
  
3. Definieren Sie die Filtertabelle, in der jedem Filter ein Clientendpunkt zugeordnet wird. In diesem Beispiel wird die Nachricht basierend auf dem jeweiligen Endpunkt weitergeleitet, über den sie empfangen wurde. Da die Nachricht nur mit einem von zwei möglichen Filtern übereinstimmen kann, ist eine Filterpriorität zum Steuern der Reihenfolge, in der Filter ausgewertet werden, nicht erforderlich.  
  
     Der folgende Code definiert die Filtertabelle und fügt die zuvor definierten Filter hinzu.  
  
    ```xml  
    <filterTables>  
       <filterTable name="filterTable1">  
         <!--add the filters to the message filter table-->  
         <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
         <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
       </filterTable>  
    </filterTables>  
    ```  
  
4. Um eingehende Nachrichten anhand der in der Tabelle enthaltenen Filter auszuwerten, müssen Sie den Dienstendpunkten die Filtertabelle mithilfe des Routingverhaltens zuordnen. Das folgende Beispiel veranschaulicht das Zuordnen von "filterTable1" zu den Dienst Endpunkten:  
  
    ```xml  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="example"></a>Beispiel  

 Es folgt eine vollständige Auflistung der Konfigurationsdatei.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright (c) Microsoft Corporation. All rights reserved -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoints for the Routing Service-->  
        <!--create the endpoints for the calculator service-->  
        <endpoint address="calculator1"  
                  binding="wsHttpBinding"  
                  name="calculator1Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <endpoint address="calculator2"  
                  binding="wsHttpBinding"  
                  name="calculator2Endpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
  
      </service>  
    </services>  
    <behaviors>  
      <!--default routing service behavior definition-->  
      <serviceBehaviors>  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
    <client>  
<!--set up the destination endpoints-->  
      <endpoint name="CalcEndpoint1"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <endpoint name="CalcEndpoint2"  
                address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
  
      <filters>  
        <!--define the different message filters-->  
        <!--define endpoint name filters looking for messages that show up on the virtual endpoints-->  
        <filter name="HighPriority" filterType="EndpointName"  
                filterData="calculator1Endpoint"/>  
        <filter name="NormalPriority" filterType="EndpointName"  
                filterData="calculator2Endpoint"/>  
      </filters>  
  
      <filterTables>  
        <filterTable name="filterTable1">  
          <!--add the filters to the message filter table-->  
          <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
          <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
        </filterTable>  
      </filterTables>  
  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Routingdienste](../samples/routing-services.md)
