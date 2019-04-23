---
title: 'Vorgehensweise: Fehlerbehandlung'
ms.date: 03/30/2017
ms.assetid: de566e39-9358-44ff-8244-780f6b799966
ms.openlocfilehash: 3752e358230b76d8984fa8e6a2ded43ad0eb2c6c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979393"
---
# <a name="how-to-error-handling"></a><span data-ttu-id="bae18-102">Vorgehensweise: Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="bae18-102">How To: Error Handling</span></span>
<span data-ttu-id="bae18-103">In diesem Thema werden die grundlegenden Schritte beschrieben, die erforderlich sind, um eine Routingkonfiguration mit Fehlerbehandlung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bae18-103">This topic outlines the basic steps required to create a routing configuration that uses error handling.</span></span> <span data-ttu-id="bae18-104">In diesem Beispiel werden Nachrichten an einen Zielendpunkt weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="bae18-104">In this example, messages are routed to a destination endpoint.</span></span> <span data-ttu-id="bae18-105">Falls eine Nachricht aufgrund eines Netzwerkfehlers oder kommunikationsbezogenen Fehlers (<xref:System.ServiceModel.CommunicationException>) nicht übermittelt werden kann, wird die Nachricht neu an einen anderen Endpunkt gesendet.</span><span class="sxs-lookup"><span data-stu-id="bae18-105">If a message cannot be delivered due to a network or communications-related failure (<xref:System.ServiceModel.CommunicationException>), the message is resent to an alternate endpoint.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bae18-106">Um einen Netzwerkfehler zu simulieren, enthält der in diesem Beispiel verwendete Zielendpunkt eine falsche Adresse.</span><span class="sxs-lookup"><span data-stu-id="bae18-106">To simulate a network failure, the destination endpoint used in this example contains an incorrect address.</span></span> <span data-ttu-id="bae18-107">Für die an diesen Endpunkt weitergeleiteten Nachrichten tritt ein Fehler auf, weil kein Dienst eine Überwachung auf die angegebene Adresse durchführt.</span><span class="sxs-lookup"><span data-stu-id="bae18-107">Messages routed to this endpoint fail as no service is listening on the specified address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bae18-108">Anhand des Beispiels in diesem Thema werden zwar nicht explizit die Timeouteinstellungen erläutert, aber Sie müssen diese beim Verwenden der Fehlerbehandlung beachten.</span><span class="sxs-lookup"><span data-stu-id="bae18-108">While the example contained in this topic does not explicitly discuss time-out settings, you must take these into consideration when using error handling.</span></span> <span data-ttu-id="bae18-109">Beim Auftreten von Fehlern kommt es zu einer zusätzlichen Verzögerung, bevor der Client eine Antwort erhält.</span><span class="sxs-lookup"><span data-stu-id="bae18-109">When errors are encountered, there will be an additional delay encountered before the client receives a response.</span></span> <span data-ttu-id="bae18-110">Dies liegt daran, dass der Fehler beim Routingdienst empfangen wird, der dann versucht, die Nachricht an einen Sicherungsendpunkt zu senden.</span><span class="sxs-lookup"><span data-stu-id="bae18-110">This is because the error is received at the Routing Service, which then attempts to send the message to a backup endpoint.</span></span> <span data-ttu-id="bae18-111">Wenn die den primären Zielendpunkten und Sicherungszielendpunkten zugeordneten Timeoutwerte hoch sind, kann es für den Client zu einer langen Verzögerung kommen, da für die Nachricht bei mehreren Endpunkten in der Sicherungsliste Failovers auftreten, bevor das Senden erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="bae18-111">If the time-out values associated with the primary and backup destination endpoints are large, the client could experience a long delay as the message fails over multiple endpoints in the backup list before being successfully sent.</span></span>  
>   
>  <span data-ttu-id="bae18-112">Weil es für den Routingdienst im schlimmsten Fall zu einer Verzögerung kommen kann, die der Summe der Timeoutwerte für alle Endpunkte kommen kann, die dem Filter zugeordnet sind, sollten Sie den Wert für den erwarteten Timeout auf dem Client entsprechend erhöhen.</span><span class="sxs-lookup"><span data-stu-id="bae18-112">Since the Routing Service could encounter a maximum delay equal to the sum of the time-out value for all endpoints associated with a filter, we recommend that you increase the expected time-out at the client accordingly.</span></span>  
  
### <a name="implement-error-handling"></a><span data-ttu-id="bae18-113">Implementieren der Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="bae18-113">Implement Error Handling</span></span>  
  
1. <span data-ttu-id="bae18-114">Erstellen Sie die grundlegende Routingdienstkonfiguration, indem Sie den vom Dienst verfügbar gemachten Dienstendpunkt angeben.</span><span class="sxs-lookup"><span data-stu-id="bae18-114">Create the basic Routing Service configuration by specifying the service endpoint exposed by the service.</span></span> <span data-ttu-id="bae18-115">Im folgenden Beispiel wird ein einzelner Dienstendpunkt definiert, der zum Empfangen von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bae18-115">The following example defines a single service endpoint, which is used to receive messages.</span></span> <span data-ttu-id="bae18-116">Außerdem werden die Clientendpunkte definiert, die verwendet werden, um Nachrichten zu senden (deadDestination und realDestination).</span><span class="sxs-lookup"><span data-stu-id="bae18-116">It also defines the client endpoints that are used to send messages; deadDestination and realDestination.</span></span> <span data-ttu-id="bae18-117">Der deadDestination-Endpunkt enthält eine Adresse, die nicht auf einen ausgeführten Dienst verweist und zum Simulieren eines Netzwerkfehlers verwendet wird, wenn Nachrichten an diesen Endpunkt gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="bae18-117">The deadDestination endpoint contains an address that does not reference a running service and is used to simulate a network failure when sending messages to this endpoint.</span></span>  
  
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
  
2. <span data-ttu-id="bae18-118">Definieren Sie die Filter, die verwendet werden, um Nachrichten an die Zielendpunkte weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="bae18-118">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="bae18-119">Für dieses Beispiel wird ein MatchAll-Filter verwendet, damit sich für alle Nachrichten, die vom Routingdienst empfangen werden, Übereinstimmungen ergeben.</span><span class="sxs-lookup"><span data-stu-id="bae18-119">For this example, a MatchAll filter is used to match all messages received by the Routing Service.</span></span>  
  
    ```xml  
    <filters>  
      <!-- Create a MatchAll filter which will catch all messages -->  
      <filter name="MatchAllFilter1" filterType="MatchAll" />  
    </filters>  
    ```  
  
3. <span data-ttu-id="bae18-120">Definieren Sie die Sicherungsendpunktliste, in der die Endpunkte enthalten sind, an die eine Nachricht im Fall eines Netzwerk- oder Kommunikationsfehlers gesendet wird, sofern das Senden an den primären Zielendpunkt erfolgt.</span><span class="sxs-lookup"><span data-stu-id="bae18-120">Define the backup endpoint list, which contains the endpoints that a message is sent to in the event of a network or communications failure when sending to the primary destination endpoint.</span></span> <span data-ttu-id="bae18-121">Im folgenden Beispiel wird eine Sicherungsliste definiert, die einen Endpunkt enthält. Sie können in einer Sicherungsliste jedoch mehrere Endpunkte angeben.</span><span class="sxs-lookup"><span data-stu-id="bae18-121">The following example defines a backup list that contains one endpoint; however, multiple endpoints can be specified in a backup list.</span></span>  
  
     <span data-ttu-id="bae18-122">Falls die Sicherungsliste mehrere Endpunkte enthält, versucht der Routingdienst beim Auftreten eines Netzwerk- oder Kommunikationsfehlers, die Nachricht an den ersten Endpunkt in der Liste zu senden.</span><span class="sxs-lookup"><span data-stu-id="bae18-122">If the backup list contains multiple endpoints, when a network or communications failure occurs the Routing Service attempts to send the message to the first endpoint in the list.</span></span> <span data-ttu-id="bae18-123">Falls beim Senden an diesen Endpunkt ein Netzwerk- oder Kommunikationsfehler auftritt, sendet der Routingdienst die Nachricht an den nächsten in der Liste enthaltenen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="bae18-123">If a network or communications failure occurs when sending to this endpoint, the Routing Service attempts to send the message to the next endpoint contained in the list.</span></span> <span data-ttu-id="bae18-124">Der Dienst fährt damit fort, die Nachricht an die einzelnen Endpunkte in der Sicherungsendpunktliste zu senden, bis die Nachricht erfolgreich gesendet wurde, für alle Sicherungsendpunkte ein Netzwerk- oder Kommunikationsfehler zurückgegeben wird oder nach dem Senden der Nachricht ein anderer Fehler als ein Netzwerk- oder Kommunikationsfehler zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="bae18-124">The service continues sending the message to each endpoint in the backup endpoint list until the message is successfully sent, all backup endpoints return a network or communications-related error, or the message is sent and the endpoint returns a non-network, non-communications-related error.</span></span>  
  
    ```xml  
    <backupLists>          
      <backupList name="backupEndpointList">  
          <add endpointName="realDestination" />  
      </backupList>  
    </backupLists>  
    ```  
  
4. <span data-ttu-id="bae18-125">Definieren Sie die Filtertabelle, in der dem Filter der deadDestination-Endpunkt und die Liste der Sicherungsendpunkte zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="bae18-125">Define the filter table, which associates the filter with the deadDestination endpoint and the backup endpoint list.</span></span>  <span data-ttu-id="bae18-126">Zuerst versucht der Routingdienst, die Nachricht an den Zielendpunkt zu senden, der dem Filter zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="bae18-126">The Routing Service first attempts to send the message to the destination endpoint associated with the filter.</span></span> <span data-ttu-id="bae18-127">Da deadDestination eine Adresse enthält, die nicht auf einen ausgeführten Dienst verweist, führt dies zu einem Netzwerkfehler.</span><span class="sxs-lookup"><span data-stu-id="bae18-127">Since the deadDestination contains an address that does not refer to a running service, this results in a network error.</span></span> <span data-ttu-id="bae18-128">Danach versucht der Routingdienst, die Nachricht an den Endpunkt zu senden, der in backupEndpointlist angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="bae18-128">The Routing Service then attempts to send the message to the endpoint specified in the backupEndpointlist.</span></span>  
  
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
  
5. <span data-ttu-id="bae18-129">Um eingehende Nachrichten anhand des in der Filtertabelle enthaltenen Filters auszuwerten, müssen Sie den Dienstendpunkten die Filtertabelle mithilfe des Routingverhaltens zuordnen.</span><span class="sxs-lookup"><span data-stu-id="bae18-129">To evaluate incoming messages against the filter contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span>  <span data-ttu-id="bae18-130">Das folgende Beispiel veranschaulicht die Zuordnung von "filterTable1" zu den Dienstendpunkten.</span><span class="sxs-lookup"><span data-stu-id="bae18-130">The following example demonstrates associating "filterTable1" with the service endpoints.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="bae18-131">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bae18-131">Example</span></span>  
 <span data-ttu-id="bae18-132">Es folgt eine vollständige Auflistung der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="bae18-132">Following is a complete listing of the configuration file.</span></span>  
  
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
