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
# <a name="how-to-dynamic-update"></a>Vorgehensweise: Dynamisches Update
In diesem Thema werden die grundlegenden Schritte beschrieben, die erforderlich sind, um die Routingkonfiguration zu erstellen und dynamisch zu aktualisieren. In diesem Beispiel wird die ursprüngliche Routingkonfiguration aus der Konfigurationsdatei abgerufen, die alle Nachrichten an den regularCalc-Rechnerdienst weiterleitet. Die Konfiguration wird anschließend jedoch programmgesteuert aktualisiert, um den Zielendpunkt in den roundingCalc-Dienst zu ändern.  
  
> [!NOTE]
> In vielen Implementierungen läuft die Konfiguration komplett dynamisch ab und erfordert keine Standardkonfiguration. Es gibt jedoch einige Szenarien, z. B. die in diesem Thema, in denen es wünschenswert ist, dass beim Starten des Diensts ein Standardkonfigurationszustand herrscht.  
  
> [!NOTE]
> Dynamische Updates treten nur im Arbeitsspeicher auf und führen nicht zur Änderung von Konfigurationsdateien.  
  
 regularCalc und roundingCalc unterstützen die gleichen Vorgänge zum Addieren, Subtrahieren, Mulltiplizieren und Dividieren. roundingCalc rundet alle Berechnungsergebnisse vor der Rückgabe jedoch auf den nächsten ganzzahligen Wert. Es wird eine Konfigurationsdatei verwendet, um den Dienst so zu konfigurieren, dass er alle Nachrichten an den regularCalc-Dienst weiterleitet. Nachdem der Routingdienst gestartet wurde, wird <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> für die Neukonfiguration des Diensts verwendet, um Nachrichten an den roundingCalc-Dienst weiterzuleiten.  
  
### <a name="implement-initial-configuration"></a>Implementieren der Anfangskonfiguration  
  
1. Erstellen Sie die grundlegende Routingdienstkonfiguration, indem Sie die vom Dienst verfügbar gemachten Dienstendpunkte angeben. Im folgenden Beispiel wird ein einzelner Dienstendpunkt definiert, der zum Empfangen von Nachrichten verwendet wird. Außerdem wird ein Clientendpunkt definiert, der zum Senden von Nachrichten an regularCalc verwendet wird.  
  
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
  
2. Definieren Sie den Filter, der verwendet wird, um Nachrichten an die Zielendpunkte weiterzuleiten. In diesem Beispiel wird der MatchAll-Filter verwendet, um alle Nachrichten an den zuvor definierten regularCalcEndpoint weiterzuleiten. Im folgenden Beispiel werden der Filter und die Filtertabelle definiert.  
  
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
  
3. Um eingehende Nachrichten anhand der in der Filtertabelle enthaltenen Filter auszuwerten, müssen Sie den Dienstendpunkten die Filtertabelle mithilfe des Routingverhaltens zuordnen. Im folgenden Beispiel wird veranschaulicht, wie "filterTable1" dem Dienstendpunkt zugeordnet wird.  
  
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
  
## <a name="implement-dynamic-configuration"></a>Implementieren der dynamischen Konfiguration  
 Die dynamische Konfiguration des Routingdiensts kann nur per Code durchgeführt werden, indem ein neues <xref:System.ServiceModel.Routing.RoutingConfiguration>-Objekt erstellt und <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> verwendet wird, um die aktuelle Konfiguration zu ersetzen.  Für dieses Beispiel wird der Routingdienst innerhalb einer Konsolenanwendung selbst gehostet. Nachdem die Anwendung gestartet wurde, können Sie die Routingkonfiguration ändern. Geben Sie dazu am Konsolenfenster "regular" oder "rounding" ein, um den Zielendpunkt zu konfigurieren, an den Nachrichten weitergeleitet werden, also "regularCalc", wenn Sie "regular" eingeben, und "roundingCalc", wenn Sie "rounding" eingeben.  
  
1. Die folgenden using-Anweisungen müssen hinzugefügt werden, um den Routingdienst zu unterstützen.  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.ServiceModel;  
    using System.ServiceModel.Channels;  
    using System.ServiceModel.Description;  
    using System.ServiceModel.Dispatcher;  
    using System.ServiceModel.Routing;  
    ```  
  
2. Der folgende Code wird verwendet, um den Routingdienst selbst als Konsolenanwendung hosten. Dadurch wird der Routingdienst mithilfe der Konfiguration initialisiert, die im vorherigen Schritt beschrieben wurde und in der Anwendungskonfigurationsdatei enthalten ist. Die while-Schleife enthält den Code, der zum Ändern der Routingkonfiguration verwendet wird.  
  
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
  
3. Um die Routingkonfiguration dynamisch zu aktualisieren, muss eine neue Routingkonfiguration erstellt werden. Diese muss alle Endpunkte, Filter und Filtertabellen enthalten, die für die neue Routingkonfiguration erforderlich sind, weil sie die vorhandene Routingkonfiguration vollständig ersetzt. Um die neue Routingkonfiguration zu verwenden, müssen Sie <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> aufrufen und die neue Konfiguration übergeben.  
  
     Fügen Sie der zuvor definierten while-Schleife den folgenden Code hinzu, um es zu ermöglichen, dass der Dienst basierend auf der Benutzereingabe neu konfiguriert wird.  
  
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
    > Da die Methode zum Bereitstellen einer neuen RoutingConfiguration in der RoutingExtension-Diensterweiterung enthalten ist, können neue RoutingConfiguration-Objekte überall im WCF-Erweiterbarkeitsmodell bereitgestellt werden, sofern das Modell über einen Verweis auf ServiceHost oder ServiceExtensions (z. B. in einer anderen ServiceExtension) verfügt oder diesen abrufen kann.
  
## <a name="example"></a>Beispiel  

Im Folgenden finden Sie eine vollständige Auflistung der Konsolenanwendung, die in diesem Beispiel verwendet wird:
  
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
  
## <a name="example"></a>Beispiel  

Im Folgenden finden Sie eine vollständige Auflistung der Konfigurationsdatei, die in diesem Beispiel verwendet wird:
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Routingdienste](../samples/routing-services.md)
