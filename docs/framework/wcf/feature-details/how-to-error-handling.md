---
title: 'Vorgehensweise: Fehlerbehandlung'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de566e39-9358-44ff-8244-780f6b799966
caps.latest.revision: "5"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 5bcab65eb98684820a84968f15ba80de3c5b60de
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-error-handling"></a>Vorgehensweise: Fehlerbehandlung
In diesem Thema werden die grundlegenden Schritte beschrieben, die erforderlich sind, um eine Routingkonfiguration mit Fehlerbehandlung zu erstellen. In diesem Beispiel werden Nachrichten an einen Zielendpunkt weitergeleitet. Falls eine Nachricht aufgrund eines Netzwerkfehlers oder kommunikationsbezogenen Fehlers (<xref:System.ServiceModel.CommunicationException>) nicht übermittelt werden kann, wird die Nachricht neu an einen anderen Endpunkt gesendet.  
  
> [!NOTE]
>  Um einen Netzwerkfehler zu simulieren, enthält der in diesem Beispiel verwendete Zielendpunkt eine falsche Adresse. Für die an diesen Endpunkt weitergeleiteten Nachrichten tritt ein Fehler auf, weil kein Dienst eine Überwachung auf die angegebene Adresse durchführt.  
  
> [!NOTE]
>  Anhand des Beispiels in diesem Thema werden zwar nicht explizit die Timeouteinstellungen erläutert, aber Sie müssen diese beim Verwenden der Fehlerbehandlung beachten. Beim Auftreten von Fehlern kommt es zu einer zusätzlichen Verzögerung, bevor der Client eine Antwort erhält. Dies liegt daran, dass der Fehler beim Routingdienst empfangen wird, der dann versucht, die Nachricht an einen Sicherungsendpunkt zu senden. Wenn die den primären Zielendpunkten und Sicherungszielendpunkten zugeordneten Timeoutwerte hoch sind, kann es für den Client zu einer langen Verzögerung kommen, da für die Nachricht bei mehreren Endpunkten in der Sicherungsliste Failovers auftreten, bevor das Senden erfolgreich ist.  
>   
>  Weil es für den Routingdienst im schlimmsten Fall zu einer Verzögerung kommen kann, die der Summe der Timeoutwerte für alle Endpunkte kommen kann, die dem Filter zugeordnet sind, sollten Sie den Wert für den erwarteten Timeout auf dem Client entsprechend erhöhen.  
  
### <a name="implement-error-handling"></a>Implementieren der Fehlerbehandlung  
  
1.  Erstellen Sie die grundlegende Routingdienstkonfiguration, indem Sie den vom Dienst verfügbar gemachten Dienstendpunkt angeben. Im folgenden Beispiel wird ein einzelner Dienstendpunkt definiert, der zum Empfangen von Nachrichten verwendet wird. Außerdem werden die Clientendpunkte definiert, die verwendet werden, um Nachrichten zu senden (deadDestination und realDestination). Der deadDestination-Endpunkt enthält eine Adresse, die nicht auf einen ausgeführten Dienst verweist und zum Simulieren eines Netzwerkfehlers verwendet wird, wenn Nachrichten an diesen Endpunkt gesendet werden.  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/" />  
          </baseAddresses>  
        </host>  
        <!-- Create the Routing Service endpoint -->  
        <endpoint address="router"  
                  binding="basicHttpBinding"  
                  name="RoutingServiceEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
  
    <!-- Create the destination endpoints that we want to send to -->  
    <client>  
      <!-- Create a dummy endpoint that we know will be down -->  
      <endpoint name="deadDestination"   
                address="net.tcp://localhost:9090/servicemodelsamples/fakeDestination"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <!-- Now create the real service endpoint -->  
      <endpoint name="realDestination"   
                address="net.tcp://localhost:8080/servicemodelsamples/service"  
                binding="netTcpBinding"   
                contract="*" />  
    </client>  
    ```  
  
2.  Definieren Sie die Filter, die verwendet werden, um Nachrichten an die Zielendpunkte weiterzuleiten.  Für dieses Beispiel wird ein MatchAll-Filter verwendet, damit sich für alle Nachrichten, die vom Routingdienst empfangen werden, Übereinstimmungen ergeben.  
  
    ```xml  
    <filters>  
      <!-- Create a MatchAll filter which will catch all messages -->  
      <filter name="MatchAllFilter1" filterType="MatchAll" />  
    </filters>  
    ```  
  
3.  Definieren Sie die Sicherungsendpunktliste, in der die Endpunkte enthalten sind, an die eine Nachricht im Fall eines Netzwerk- oder Kommunikationsfehlers gesendet wird, sofern das Senden an den primären Zielendpunkt erfolgt. Im folgenden Beispiel wird eine Sicherungsliste definiert, die einen Endpunkt enthält. Sie können in einer Sicherungsliste jedoch mehrere Endpunkte angeben.  
  
     Falls die Sicherungsliste mehrere Endpunkte enthält, versucht der Routingdienst beim Auftreten eines Netzwerk- oder Kommunikationsfehlers, die Nachricht an den ersten Endpunkt in der Liste zu senden. Falls beim Senden an diesen Endpunkt ein Netzwerk- oder Kommunikationsfehler auftritt, sendet der Routingdienst die Nachricht an den nächsten in der Liste enthaltenen Endpunkt. Der Dienst fährt damit fort, die Nachricht an die einzelnen Endpunkte in der Sicherungsendpunktliste zu senden, bis die Nachricht erfolgreich gesendet wurde, für alle Sicherungsendpunkte ein Netzwerk- oder Kommunikationsfehler zurückgegeben wird oder nach dem Senden der Nachricht ein anderer Fehler als ein Netzwerk- oder Kommunikationsfehler zurückgegeben wird.  
  
    ```xml  
    <backupLists>          
      <backupList name="backupEndpointList">  
          <add endpointName="realDestination" />  
      </backupList>  
    </backupLists>  
    ```  
  
4.  Definieren Sie die Filtertabelle, in der dem Filter der deadDestination-Endpunkt und die Liste der Sicherungsendpunkte zugeordnet wird.  Zuerst versucht der Routingdienst, die Nachricht an den Zielendpunkt zu senden, der dem Filter zugeordnet ist. Da deadDestination eine Adresse enthält, die nicht auf einen ausgeführten Dienst verweist, führt dies zu einem Netzwerkfehler. Danach versucht der Routingdienst, die Nachricht an den Endpunkt zu senden, der in backupEndpointlist angegeben ist.  
  
    ```xml  
    <filterTables>  
            <!-- Set up the Routing Service's Message Filter Table -->  
            <filterTable name="filterTable1">  
                <!-- Add an entity that maps the MatchAllMessageFilter to the dead destination -->  
                <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->  
                <!-- Listed in the backupEndpointList -->  
                <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>  
            </filterTable>  
          </filterTables>  
    ```  
  
5.  Um eingehende Nachrichten anhand des in der Filtertabelle enthaltenen Filters auszuwerten, müssen Sie den Dienstendpunkten die Filtertabelle mithilfe des Routingverhaltens zuordnen.  Das folgende Beispiel veranschaulicht die Zuordnung von "filterTable1" zu den Dienstendpunkten.  
  
    ```xml  
    <behaviors>  
      <serviceBehaviors>  
        <!-- Set up the Routing Behavior -->  
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
<!-- Copyright (c) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/" />  
          </baseAddresses>  
        </host>  
        <!-- Create the Routing Service endpoint -->  
        <endpoint address="router"  
                  binding="basicHttpBinding"  
                  name="RoutingServiceEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <behaviors>  
      <serviceBehaviors>  
        <!-- Set up the Routing Behavior -->  
        <behavior name="routingConfiguration">  
          <routing filterTableName="filterTable1" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <!-- Create the destination endpoints that we want to send to -->  
    <client>  
      <!-- Create a dummy endpoint that we know will be down -->  
      <endpoint name="deadDestination"   
                address="net.tcp://localhost:9090/servicemodelsamples/fakeDestination"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <!-- Now create the real service endpoint -->  
      <endpoint name="realDestination"   
                address="net.tcp://localhost:8080/servicemodelsamples/service"  
                binding="netTcpBinding"   
                contract="*" />  
    </client>  
    <routing>  
      <filters>  
        <!-- Create a MatchAll filter which will catch all messages -->  
        <filter name="MatchAllFilter1" filterType="MatchAll" />  
      </filters>  
      <filterTables>  
        <!-- Set up the Routing Service's Message Filter Table -->  
        <filterTable name="filterTable1">  
            <!-- Add an entrty that maps the MatchAllMessageFilter to the dead destination -->  
            <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->  
            <!-- Listed in the backupEndpointList -->  
            <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>  
        </filterTable>  
      </filterTables>  
      <!-- Create the backup endpoint list -->  
      <backupLists>          
        <backupList name="backupEndpointList">  
            <add endpointName="realDestination" />  
        </backupList>  
      </backupLists>  
      </routing>  
  </system.serviceModel>  
</configuration>  
```
