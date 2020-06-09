---
title: 'Vorgehensweise: Dienstdatenpartitionierung'
ms.date: 03/30/2017
ms.assetid: 1ccff72e-d76b-4e36-93a2-e51f7b32dc83
ms.openlocfilehash: 3b2f86ee6a4dea25fb5c972d4cecb1b9ed411b29
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84601191"
---
# <a name="how-to-service-data-partitioning"></a><span data-ttu-id="527ab-102">Vorgehensweise: Dienstdatenpartitionierung</span><span class="sxs-lookup"><span data-stu-id="527ab-102">How To: Service Data Partitioning</span></span>
<span data-ttu-id="527ab-103">In diesem Thema werden die grundlegenden Schritte beschrieben, die erforderlich sind, um Meldungen über mehrere Instanzen des gleichen Zieldiensts zu partitionieren.</span><span class="sxs-lookup"><span data-stu-id="527ab-103">This topic outlines the basic steps required to partition messages across multiple instances of the same destination service.</span></span> <span data-ttu-id="527ab-104">Die Partitionierung von Dienstdaten wird in der Regel verwendet, wenn Sie einen Dienst skalieren müssen, um eine bessere Dienstqualität bereitzustellen, oder wenn Sie Anforderungen verschiedener Kunden jeweils auf bestimmte Art und Weise behandeln müssen.</span><span class="sxs-lookup"><span data-stu-id="527ab-104">Service data partitioning is typically used when you need to scale a service in order to provide better quality of service, or when you need to handle requests from different customers in a specific way.</span></span> <span data-ttu-id="527ab-105">Beispielsweise müssen Nachrichten von hochwertigen oder "Gold"-Kunden möglicherweise mit einer höheren Priorität verarbeitet werden als Nachrichten von einem Standardkunden.</span><span class="sxs-lookup"><span data-stu-id="527ab-105">For example, messages from high value or "Gold" customers may need to be processed at a higher priority than messages from a standard customer.</span></span>  
  
 <span data-ttu-id="527ab-106">In diesem Beispiel werden Nachrichten zu einem von zwei Instanzen des regularCalc-Diensts geleitet.</span><span class="sxs-lookup"><span data-stu-id="527ab-106">In this example, messages are routed to one of two instances of the regularCalc service.</span></span> <span data-ttu-id="527ab-107">Beide Instanzen des Diensts sind identisch. Der vom calculator1-Endpunkt vertretene Dienst verarbeitet jedoch Nachrichten von wichtigen Kunden, und der calculator2-Endpunkt verarbeitet Nachrichten von anderen Kunden.</span><span class="sxs-lookup"><span data-stu-id="527ab-107">Both instances of the service are identical; however the service represented by the calculator1 endpoint processes messages received from high value customers, the calculator 2 endpoint processes messages from other customers</span></span>  
  
 <span data-ttu-id="527ab-108">Die vom Client gesendete Nachricht enthält keine eindeutigen Daten, anhand denen ermittelt werden kann, an welche Dienstinstanz die Meldung weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="527ab-108">The message sent from the client does not have any unique data that can be used to identify which service instance the message should be routed to.</span></span> <span data-ttu-id="527ab-109">Um es allen Clients zu ermöglichen, Daten an einen bestimmten Zieldienst weiterzuleiten, implementieren wir zwei Dienstendpunkte, die zum Empfangen von Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="527ab-109">To allow each client to route data to a specific destination service we will implement two service endpoints that will be used to receive messages.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="527ab-110">In diesem Beispiel werden zwar bestimmte Endpunkte zum Partitionieren von Daten verwendet, aber dies kann auch mit Informationen erreicht werden, die innerhalb der Meldung selbst enthalten sind, z. B. Header- oder Textdaten.</span><span class="sxs-lookup"><span data-stu-id="527ab-110">While this example uses specific endpoints to partition data, this could also be accomplished using information contained within the message itself such as header or body data.</span></span>  
  
### <a name="implement-service-data-partitioning"></a><span data-ttu-id="527ab-111">Implementieren der Dienstdatenpartitionierung</span><span class="sxs-lookup"><span data-stu-id="527ab-111">Implement Service Data Partitioning</span></span>  
  
1. <span data-ttu-id="527ab-112">Erstellen Sie die grundlegende Routingdienstkonfiguration, indem Sie die vom Dienst verfügbar gemachten Dienstendpunkte angeben.</span><span class="sxs-lookup"><span data-stu-id="527ab-112">Create the basic Routing Service configuration by specifying the service endpoints exposed by the service.</span></span> <span data-ttu-id="527ab-113">Im folgenden Beispiel werden zwei Endpunkte definiert, die zum Empfangen von Meldungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="527ab-113">The following example defines two endpoints, which will be used to receive messages.</span></span> <span data-ttu-id="527ab-114">Außerdem werden die Clientendpunkte definiert, die verwendet werden, um Nachrichten an die regularCalc Dienstinstanzen zu senden.</span><span class="sxs-lookup"><span data-stu-id="527ab-114">It also defines the client endpoints, which are used to send messages to the regularCalc service instances.</span></span>  
  
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
  
2. <span data-ttu-id="527ab-115">Definieren Sie die Filter, die verwendet werden, um Nachrichten an die Zielendpunkte weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="527ab-115">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="527ab-116">In diesem Beispiel wird mithilfe des EndpointName-Filters ermittelt, welcher Dienstendpunkt die Nachricht empfangen hat.</span><span class="sxs-lookup"><span data-stu-id="527ab-116">For this example, the EndpointName filter is used to determine which service endpoint received the message.</span></span> <span data-ttu-id="527ab-117">Im folgenden Beispiel werden der erforderliche Routingabschnitt und die Filter definiert.</span><span class="sxs-lookup"><span data-stu-id="527ab-117">The following example defines the necessary routing section and filters.</span></span>  
  
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
  
3. <span data-ttu-id="527ab-118">Definieren Sie die Filtertabelle, in der jedem Filter ein Clientendpunkt zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="527ab-118">Define the filter table, which associates each filter with a client endpoint.</span></span> <span data-ttu-id="527ab-119">In diesem Beispiel wird die Nachricht basierend auf dem jeweiligen Endpunkt weitergeleitet, über den sie empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="527ab-119">In this example, the message will be routed based on the specific endpoint it was received over.</span></span> <span data-ttu-id="527ab-120">Da die Nachricht nur mit einem von zwei möglichen Filtern übereinstimmen kann, ist eine Filterpriorität zum Steuern der Reihenfolge, in der Filter ausgewertet werden, nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="527ab-120">Since the message can only match one of the two possible filters, there is no need for using filter priority to control to the order in which filters are evaluated.</span></span>  
  
     <span data-ttu-id="527ab-121">Der folgende Code definiert die Filtertabelle und fügt die zuvor definierten Filter hinzu.</span><span class="sxs-lookup"><span data-stu-id="527ab-121">The following defines the filter table and adds the filters defined earlier.</span></span>  
  
    ```xml  
    <filterTables>  
       <filterTable name="filterTable1">  
         <!--add the filters to the message filter table-->  
         <add filterName="HighPriority" endpointName="CalcEndpoint1"/>  
         <add filterName="NormalPriority" endpointName="CalcEndpoint2"/>  
       </filterTable>  
    </filterTables>  
    ```  
  
4. <span data-ttu-id="527ab-122">Um eingehende Nachrichten anhand der in der Tabelle enthaltenen Filter auszuwerten, müssen Sie den Dienstendpunkten die Filtertabelle mithilfe des Routingverhaltens zuordnen.</span><span class="sxs-lookup"><span data-stu-id="527ab-122">To evaluate incoming messages against the filters contained in the table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="527ab-123">Das folgende Beispiel veranschaulicht das Zuordnen von "filterTable1" zu den Dienst Endpunkten:</span><span class="sxs-lookup"><span data-stu-id="527ab-123">The following example demonstrates associating "filterTable1" with the service endpoints:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="527ab-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="527ab-124">Example</span></span>  
 <span data-ttu-id="527ab-125">Es folgt eine vollständige Auflistung der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="527ab-125">The following is a complete listing of the configuration file.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="527ab-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="527ab-126">See also</span></span>

- [<span data-ttu-id="527ab-127">Routingdienste</span><span class="sxs-lookup"><span data-stu-id="527ab-127">Routing Services</span></span>](../samples/routing-services.md)
