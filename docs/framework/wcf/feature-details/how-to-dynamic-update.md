---
title: 'Vorgehensweise: Dynamisches Update'
ms.date: 03/30/2017
ms.assetid: 9b8f6e0d-edab-4a7e-86e3-8c66bebc64bb
ms.openlocfilehash: aaeb4d9d42c289cf34a6aee9212fc2d74b8f8c01
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184966"
---
# <a name="how-to-dynamic-update"></a><span data-ttu-id="246c7-102">Vorgehensweise: Dynamisches Update</span><span class="sxs-lookup"><span data-stu-id="246c7-102">How To: Dynamic Update</span></span>
<span data-ttu-id="246c7-103">In diesem Thema werden die grundlegenden Schritte beschrieben, die erforderlich sind, um die Routingkonfiguration zu erstellen und dynamisch zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="246c7-103">This topic outlines the basic steps required to create and dynamically update the routing configuration.</span></span> <span data-ttu-id="246c7-104">In diesem Beispiel wird die ursprüngliche Routingkonfiguration aus der Konfigurationsdatei abgerufen, die alle Nachrichten an den regularCalc-Rechnerdienst weiterleitet. Die Konfiguration wird anschließend jedoch programmgesteuert aktualisiert, um den Zielendpunkt in den roundingCalc-Dienst zu ändern.</span><span class="sxs-lookup"><span data-stu-id="246c7-104">In this example, the initial routing configuration is obtained from the configuration file and routes all messages to the regularCalc calculator service; however, it is subsequently updated programmatically in order to change the destination endpoint the roundingCalc service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="246c7-105">In vielen Implementierungen läuft die Konfiguration komplett dynamisch ab und erfordert keine Standardkonfiguration. Es gibt jedoch einige Szenarien, z. B. die in diesem Thema, in denen es wünschenswert ist, dass beim Starten des Diensts ein Standardkonfigurationszustand herrscht.</span><span class="sxs-lookup"><span data-stu-id="246c7-105">In many implementations, configuration will be fully dynamic and will not rely on a default configuration; however, there are some scenarios, such as the one in this topic, where it is desirable to have a default configuration state when the service starts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="246c7-106">Dynamische Updates treten nur im Arbeitsspeicher auf und führen nicht zur Änderung von Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="246c7-106">Dynamic updates occur only in memory, and do not result in the modification of configuration files.</span></span>  
  
 <span data-ttu-id="246c7-107">regularCalc und roundingCalc unterstützen die gleichen Vorgänge zum Addieren, Subtrahieren, Mulltiplizieren und Dividieren. roundingCalc rundet alle Berechnungsergebnisse vor der Rückgabe jedoch auf den nächsten ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="246c7-107">Both regularCalc and roundingCalc support the same operations of add, subtract, multiply and divide; however, roundingCalc rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="246c7-108">Es wird eine Konfigurationsdatei verwendet, um den Dienst so zu konfigurieren, dass er alle Nachrichten an den regularCalc-Dienst weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="246c7-108">A configuration file is used to configure the service to route all messages to the regularCalc service.</span></span> <span data-ttu-id="246c7-109">Nachdem der Routingdienst gestartet wurde, wird <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> für die Neukonfiguration des Diensts verwendet, um Nachrichten an den roundingCalc-Dienst weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="246c7-109">After the Routing Service has been started, <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> is used to reconfigure the service to route messages to the roundingCalc service.</span></span>  
  
### <a name="implement-initial-configuration"></a><span data-ttu-id="246c7-110">Implementieren der Anfangskonfiguration</span><span class="sxs-lookup"><span data-stu-id="246c7-110">Implement Initial Configuration</span></span>  
  
1. <span data-ttu-id="246c7-111">Erstellen Sie die grundlegende Routingdienstkonfiguration, indem Sie die vom Dienst verfügbar gemachten Dienstendpunkte angeben.</span><span class="sxs-lookup"><span data-stu-id="246c7-111">Create the basic Routing Service Configuration by specifying the service endpoints exposed by the service.</span></span> <span data-ttu-id="246c7-112">Im folgenden Beispiel wird ein einzelner Dienstendpunkt definiert, der zum Empfangen von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="246c7-112">The following example defines a single service endpoint, which will be used to receive messages.</span></span> <span data-ttu-id="246c7-113">Außerdem wird ein Clientendpunkt definiert, der zum Senden von Nachrichten an regularCalc verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="246c7-113">It also defines a client endpoint that will be used to send messages to the regularCalc.</span></span>  
  
    ```xml  
    <services>  
      <service behaviorConfiguration="routingConfiguration"  
               name="System.ServiceModel.Routing.RoutingService">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost/routingservice/router" />  
          </baseAddresses>  
        </host>  
        <!--Set up the inbound endpoint for the Routing Service-->  
        <endpoint address="calculator"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
      </service>  
    </services>  
    <client>  
    <!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    ```  
  
2. <span data-ttu-id="246c7-114">Definieren Sie den Filter, der verwendet wird, um Nachrichten an die Zielendpunkte weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="246c7-114">Define the filter used to route messages to the destination endpoints.</span></span> <span data-ttu-id="246c7-115">In diesem Beispiel wird der MatchAll-Filter verwendet, um alle Nachrichten an den zuvor definierten regularCalcEndpoint weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="246c7-115">For this example, the MatchAll filter is used to route all messages to the regularCalcEndpoint defined previously.</span></span> <span data-ttu-id="246c7-116">Im folgenden Beispiel werden der Filter und die Filtertabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="246c7-116">The following example defines the filter and filter table.</span></span>  
  
    ```xml  
    <filters>  
      <!--define the message filter-->  
      <filter name="MatchAllFilter" filterType="MatchAll"/>  
    </filters>  
    <filterTables>  
      <filterTable name="filterTable1">  
          <!--add the filter to the message filter table-->  
          <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
      </filterTable>  
    </filterTables>  
    ```  
  
3. <span data-ttu-id="246c7-117">Um eingehende Nachrichten anhand der in der Filtertabelle enthaltenen Filter auszuwerten, müssen Sie den Dienstendpunkten die Filtertabelle mithilfe des Routingverhaltens zuordnen.</span><span class="sxs-lookup"><span data-stu-id="246c7-117">To evaluate incoming messages against the filters contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="246c7-118">Im folgenden Beispiel wird veranschaulicht, wie "filterTable1" dem Dienstendpunkt zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="246c7-118">The following example demonstrates associating "filterTable1" with the service endpoint.</span></span>  
  
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
  
## <a name="implement-dynamic-configuration"></a><span data-ttu-id="246c7-119">Implementieren der dynamischen Konfiguration</span><span class="sxs-lookup"><span data-stu-id="246c7-119">Implement Dynamic Configuration</span></span>  
 <span data-ttu-id="246c7-120">Die dynamische Konfiguration des Routingdiensts kann nur per Code durchgeführt werden, indem ein neues <xref:System.ServiceModel.Routing.RoutingConfiguration>-Objekt erstellt und <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> verwendet wird, um die aktuelle Konfiguration zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="246c7-120">Dynamic configuration of the Routing Service can only be performed in code by creating a new <xref:System.ServiceModel.Routing.RoutingConfiguration> and using <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> to replace the current configuration.</span></span>  <span data-ttu-id="246c7-121">Für dieses Beispiel wird der Routingdienst innerhalb einer Konsolenanwendung selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="246c7-121">For this example, the Routing Service is self-hosted within a console application.</span></span> <span data-ttu-id="246c7-122">Nachdem die Anwendung gestartet wurde, können Sie die Routingkonfiguration ändern. Geben Sie dazu am Konsolenfenster "regular" oder "rounding" ein, um den Zielendpunkt zu konfigurieren, an den Nachrichten weitergeleitet werden, also "regularCalc", wenn Sie "regular" eingeben, und "roundingCalc", wenn Sie "rounding" eingeben.</span><span class="sxs-lookup"><span data-stu-id="246c7-122">After the application has started, you can modify the routing configuration by entering ‘regular’ or ‘rounding’ at the console window to configure the destination endpoint that messages are routed to; regularCalc when ‘regular’ is entered, otherwise roundingCalc when ‘rounding’ is entered.</span></span>  
  
1. <span data-ttu-id="246c7-123">Die folgenden using-Anweisungen müssen hinzugefügt werden, um den Routingdienst zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="246c7-123">The following using statements must be added in order to support the Routing Service.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ServiceModel;  
    using System.ServiceModel.Channels;  
    using System.ServiceModel.Description;  
    using System.ServiceModel.Dispatcher;  
    using System.ServiceModel.Routing;  
    ```  
  
2. <span data-ttu-id="246c7-124">Der folgende Code wird verwendet, um den Routingdienst selbst als Konsolenanwendung hosten.</span><span class="sxs-lookup"><span data-stu-id="246c7-124">The following code is used to self-host the Routing Service as a console application.</span></span> <span data-ttu-id="246c7-125">Dadurch wird der Routingdienst mithilfe der Konfiguration initialisiert, die im vorherigen Schritt beschrieben wurde und in der Anwendungskonfigurationsdatei enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="246c7-125">This initializes the Routing Service using the configuration described in the previous step, which is contained within the application configuration file.</span></span> <span data-ttu-id="246c7-126">Die while-Schleife enthält den Code, der zum Ändern der Routingkonfiguration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="246c7-126">The while loop contains the code used to change the routing configuration.</span></span>  
  
    ```csharp  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost =  
            new ServiceHost(typeof(RoutingService)))  
        {  
            // Open the ServiceHost to create listeners
            // and start listening for messages.  
            Console.WriteLine("The Routing Service configured, opening....");  
            serviceHost.Open();  
            Console.WriteLine("The Routing Service is now running.");  
             Console.WriteLine("Type 'quit' to terminate router.");  
             Console.WriteLine("<ENTER> to change routing configuration.");  
             while (Console.ReadLine() != "quit")  
             {  
            ....  
            }  
        }  
    }  
    ```  
  
3. <span data-ttu-id="246c7-127">Um die Routingkonfiguration dynamisch zu aktualisieren, muss eine neue Routingkonfiguration erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="246c7-127">To dynamically update the routing configuration, a new routing configuration must be created.</span></span> <span data-ttu-id="246c7-128">Diese muss alle Endpunkte, Filter und Filtertabellen enthalten, die für die neue Routingkonfiguration erforderlich sind, weil sie die vorhandene Routingkonfiguration vollständig ersetzt.</span><span class="sxs-lookup"><span data-stu-id="246c7-128">This must contain all endpoints, filters and filter tables that are required for the new routing configuration, as it will completely replace the existing routing configuration.</span></span> <span data-ttu-id="246c7-129">Um die neue Routingkonfiguration zu verwenden, müssen Sie <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> aufrufen und die neue Konfiguration übergeben.</span><span class="sxs-lookup"><span data-stu-id="246c7-129">In order to use the new routing configuration, you must invoke <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> and pass the new configuration.</span></span>  
  
     <span data-ttu-id="246c7-130">Fügen Sie der zuvor definierten while-Schleife den folgenden Code hinzu, um es zu ermöglichen, dass der Dienst basierend auf der Benutzereingabe neu konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="246c7-130">Add the following code to the while loop defined previously to allow the service to be reconfigured based on user input.</span></span>  
  
    ```csharp  
    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
    string destEndpoint = Console.ReadLine();  
    // Create a new RoutingConfiguration  
    RoutingConfiguration rc = new RoutingConfiguration();  
    // Determine the endpoint to configure for  
    switch (destEndpoint)  
    {  
        case "regular":  
            // Define the destination endpoint  
            ServiceEndpoint regularCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        case "rounding":  
            // Define the destination endpoint  
            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
               ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
               new NetTcpBinding(),  
               new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
            // Create a MatchAll filter and add to the filter table  
            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
            // Use ApplyConfiguration to update the Routing Service  
            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
            Console.WriteLine("Applied new routing configuration.");  
            break;  
        default:  
            Console.WriteLine("Incorrect value entered, no change.");  
            break;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="246c7-131">Da die Methode zum Bereitstellen einer neuen RoutingConfiguration in der RoutingExtension-Diensterweiterung enthalten ist, können neue RoutingConfiguration-Objekte überall im WCF-Erweiterbarkeitsmodell bereitgestellt werden, sofern das Modell über einen Verweis auf ServiceHost oder ServiceExtensions (z. B. in einer anderen ServiceExtension) verfügt oder diesen abrufen kann.</span><span class="sxs-lookup"><span data-stu-id="246c7-131">Since the method for providing a new RoutingConfiguration is contained in the RoutingExtension service extension, new RoutingConfiguration objects can be provided anywhere in the WCF extensibility model that has or can obtain a reference to the ServiceHost or ServiceExtensions (such as in another ServiceExtension).</span></span>
  
## <a name="example"></a><span data-ttu-id="246c7-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="246c7-132">Example</span></span>  

<span data-ttu-id="246c7-133">Im Folgenden finden Sie eine vollständige Auflistung der Konsolenanwendung, die in diesem Beispiel verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="246c7-133">The following is a complete listing of the console application used in this example:</span></span>
  
```csharp
//-----------------------------------------------------------------  
//  Copyright (c) Microsoft Corporation.  All Rights Reserved.  
//-----------------------------------------------------------------  
  
using System;  
using System.Collections.Generic;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
using System.ServiceModel.Description;  
using System.ServiceModel.Dispatcher;  
using System.ServiceModel.Routing;  
  
namespace Microsoft.Samples.AdvancedFilters  
{  
    public class Router  
    {  
        // Host the service within this EXE console application.  
        public static void Main()  
        {
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost =  
                new ServiceHost(typeof(RoutingService)))  
            {  
                // Open the ServiceHost to create listeners
                // and start listening for messages.  
                Console.WriteLine("The Routing Service configured, opening....");  
                serviceHost.Open();  
                Console.WriteLine("The Routing Service is now running.");  
                Console.WriteLine("Type 'quit' to terminate router.");  
                Console.WriteLine("<ENTER> to change routing configuration.");  
                while (Console.ReadLine() != "quit")  
                {  
                    Console.WriteLine("Enter 'regular' or 'rounding' to set the destination endpoint:");  
                    string destEndpoint = Console.ReadLine();  
                    // Create a new RoutingConfiguration  
                    RoutingConfiguration rc = new RoutingConfiguration();  
                    // Determine the endpoint to configure for  
                    switch (destEndpoint)  
                    {  
                        case "regular":  
                            // Define the destination endpoint  
                            ServiceEndpoint regularCalc = new ServiceEndpoint(  
                            ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                            new NetTcpBinding(),  
                            new EndpointAddress("net.tcp://localhost:9090/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { regularCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        case "rounding":  
                            // Define the destination endpoint  
                            ServiceEndpoint roundingCalc = new ServiceEndpoint(  
                                ContractDescription.GetContract(typeof(IRequestReplyRouter)),  
                                new NetTcpBinding(),  
                                new EndpointAddress("net.tcp://localhost:8080/servicemodelsamples/service/"));  
                            // Create a MatchAll filter and add to the filter table  
                            rc.FilterTable.Add(new MatchAllMessageFilter(), new List<ServiceEndpoint> { roundingCalc });  
                            // Use ApplyConfiguration to update the Routing Service  
                            serviceHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc);  
                            Console.WriteLine("Applied new routing configuration.");  
                            break;  
                        default:  
                            Console.WriteLine("Incorrect value entered, no change.");  
                            break;  
                    }  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="246c7-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="246c7-134">Example</span></span>  

<span data-ttu-id="246c7-135">Im Folgenden finden Sie eine vollständige Auflistung der Konfigurationsdatei, die in diesem Beispiel verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="246c7-135">The following is a complete listing of the configuration file used in this example:</span></span>
  
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
        <!--Set up the inbound endpoint for the Routing Service-->  
        <endpoint address="calculator"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
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
<!--set up the destination endpoint-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
  
      <filters>  
        <!--define the message filter-->  
        <filter name="MatchAllFilter" filterType="MatchAll"/>  
      </filters>  
      <filterTables>  
        <filterTable name="filterTable1">  
            <!--add the filter to the message filter table-->  
            <add filterName="MatchAllFilter" endpointName="regularCalcEndpoint"/>  
        </filterTable>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="246c7-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="246c7-136">See also</span></span>

- [<span data-ttu-id="246c7-137">Routingdienste</span><span class="sxs-lookup"><span data-stu-id="246c7-137">Routing Services</span></span>](../samples/routing-services.md)
