---
title: 'Vorgehensweise: Dienstversionsverwaltung'
ms.date: 03/30/2017
ms.assetid: 4287b6b3-b207-41cf-aebe-3b1d4363b098
ms.openlocfilehash: f1178a0bedfe8665d7b3ec463e99183809538c28
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81464113"
---
# <a name="how-to-service-versioning"></a>Vorgehensweise: Dienstversionsverwaltung
In diesem Thema werden die grundlegenden Schritte beschrieben, die erforderlich sind, um eine Routingkonfiguration zu erstellen, die Nachrichten an verschiedene Versionen des gleichen Diensts weiterleitet. In diesem Beispiel werden Nachrichten an zwei verschiedene Versionen eines Rechnerdiensts weitergeleitet: `roundingCalc` (v1) und `regularCalc` (v2). Beide Implementierungen unterstützen die gleichen Vorgänge. Der ältere Dienst, `roundingCalc`, rundet vor der Rückgabe jedoch alle Berechnungen auf den nächsten ganzzahligen Wert. Eine Clientanwendung muss angeben können, ob der neuere `regularCalc`-Dienst verwendet werden soll.  
  
> [!WARNING]
> Um eine Nachricht an eine bestimmte Dienstversion weiterzuleiten, muss der Routingdienst das Nachrichtziel anhand des Nachrichteninhalts ermitteln können. In der Methode unten veranschaulichten Methode gibt der Client die Version an, indem er Informationen in einen Nachrichtenheader einfügt. Es gibt Methoden für die Dienstversionsverwaltung, für es nicht erforderlich ist, dass Clients zusätzliche Daten übergeben. Eine Nachricht kann z. B. an die aktuelle Version oder die Version mit dem höchsten Kompatibilitätsgrad eines Diensts weitergeleitet werden, oder der Router kann einen Teil des SOAP-Standardumschlags verwenden.  
  
 Beide Dienste machen die folgenden Vorgänge verfügbar:  
  
- Hinzufügen  
  
- Subtrahieren  
  
- Multiplizieren  
  
- Dividieren  
  
 Da beide Dienstimplementierungen die gleichen Vorgänge behandeln und bis auf die zurückgegebenen Daten im Wesentlichen identisch sind, sind die Basisdaten von Nachrichten, die aus Clientanwendungen gesendet werden, nicht eindeutig genug, um die Weiterleitung der Anforderung einwandfrei bestimmen zu können. Aktionsfilter können z. B. nicht verwendet werden, weil die Standardaktionen für beide Dienste gleich sind.  
  
 Dies kann auf verschiedene Arten gelöst werden. Sie können z. B. für jede Version des Diensts einen bestimmten Endpunkt auf dem Router verfügbar machen, oder Sie können der Nachricht ein benutzerdefiniertes Headerelement hinzufügen, um die Dienstversion anzugeben.  Bei all diesen Ansätzen können Sie eingehende Nachrichten eindeutig an eine bestimmte Version des Diensts weiterleiten. Die bevorzugte Methode zur Unterscheidung zwischen Anforderungen für unterschiedliche Dienstversionen ist jedoch die Verwendung von eindeutigem Nachrichteninhalt.  
  
 In diesem Beispiel fügt die Clientanwendung der Anforderungsnachricht den benutzerdefinierten Header dem "CalcVer" hinzu. Dieser Header enthält einen Wert, der die Version des Diensts angibt, an den die Nachricht weitergeleitet werden soll. Der Wert "1" gibt an, dass die Nachricht vom roundingCalc-Dienst verarbeitet werden muss, und der "2" steht für den regularCalc-Dienst. Auf diese Weise kann die Clientanwendung direkt steuern, welche Version des Diensts die Nachricht verarbeitet.  Da der benutzerdefinierte Header ein in der Nachricht enthaltener Wert ist, können Sie einen Endpunkt zum Empfangen von Nachrichten verwenden, die für beide Versionen des Diensts bestimmt sind. Der folgende Code kann in der Clientanwendung verwendet werden, um der Nachricht diesen benutzerdefinierten Header hinzuzufügen:  
  
```csharp  
messageHeadersElement.Add(MessageHeader.CreateHeader("CalcVer", "http://my.custom.namespace/", "2"));  
```  
  
### <a name="implement-service-versioning"></a>Implementieren der Dienstversionsverwaltung  
  
1. Erstellen Sie die grundlegende Routingdienstkonfiguration, indem Sie den vom Dienst verfügbar gemachten Dienstendpunkt angeben. Im folgenden Beispiel wird ein einzelner Dienstendpunkt definiert, der zum Empfangen von Nachrichten verwendet wird. Außerdem werden die Clientendpunkte definiert, die zum Senden von Nachrichten an die Dienste `roundingCalc` (v1) und `regularCalc` (v2) verwendet werden.  
  
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
    <!--set up the destination endpoints-->  
          <endpoint name="regularCalcEndpoint"  
                    address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
  
          <endpoint name="roundingCalcEndpoint"  
                    address="http://localhost:8080/servicemodelsamples/service/"  
                    binding="wsHttpBinding"  
                    contract="*" />  
        </client>  
    ```  
  
2. Definieren Sie die Filter, die verwendet werden, um Nachrichten an die Zielendpunkte weiterzuleiten.  In diesem Beispiel wird der XPath-Filter verwendet, um den Wert des benutzerdefinierten Headers "CalcVer" zu ermitteln, um zu bestimmen, an welche Version die Nachricht weitergeleitet werden soll. Ein XPath-Filter wird auch verwendet, um Nachrichten zu erkennen, die nicht den "CalcVer"-Header enthalten. Im folgenden Beispiel werden die erforderlichen Filter und die Namespacetabelle definiert.  
  
    ```xml  
    <!-- use the namespace table element to define a prefix for our custom namespace-->  
    <namespaceTable>  
      <add prefix="custom" namespace="http://my.custom.namespace/"/>  
    </namespaceTable>  
    <filters>  
      <!--define the different message filters-->  
      <!--define an xpath message filter to look for the  
          custom header containing a value of 2-->  
      <filter name="XPathFilterRegular" filterType="XPath"  
              filterData="sm:header()/custom:CalcVer = '2'"/>  
      <!--define an xpath message filter to look for the  
          custom header containing a value of 1-->  
      <filter name="XPathFilterRounding" filterType="XPath"  
              filterData="sm:header()/custom:CalcVer = '1'"/>  
       <!--define an xpath message filter to look for  
           messages that do not contain the custom header-->  
       <filter name="XPathFilterNoHeader" filterType="XPath"  
               filterData="count(sm:header()/custom:CalcVer)=0"/>  
    </filters>
    ```  
  
    > [!NOTE]
    > Das Namespacepräfix s12 ist standardmäßig in der Namespacetabelle `http://www.w3.org/2003/05/soap-envelope`definiert und stellt den Namespace dar.
  
3. Definieren Sie die Filtertabelle, in der jedem Filter ein Clientendpunkt zugeordnet wird. Wenn die Nachricht den "CalcVer"-Header mit dem Wert 1 enthält, wird sie an den regularCalc-Dienst gesendet. Enthält der Header den Wert 2, wird sie an den roundingCalc-Dienst gesendet. Falls kein Header vorhanden ist, wird die Nachricht an regularCalc weitergeleitet.  
  
     Der folgende Code definiert die Filtertabelle und fügt die zuvor definierten Filter hinzu.  
  
    ```xml  
    <filterTables>  
      <filterTable name="filterTable1">  
          <!--add the filters to the message filter table-->  
          <!--look for the custom header = 1, and if we find it,  
              send the message to the rounding calc endpoint-->  
          <add filterName="XPathFilterRounding" endpointName="roundingCalcEndpoint"/>  
          <!--look for the custom header = 2, and if we find it,  
              send the message to the rounding calc endpoint-->  
          <add filterName="XPathFilterRegular" endpointName="regularCalcEndpoint"/>  
          <!--look for the absence of the custom header, and if  
              it is not present, assume the v1 endpoint-->  
          <add filterName="XPathFilterNoHeader" endpointName="roundingCalcEndpoint"/>  
      </filterTable>  
    </filterTables>  
    ```  
  
4. Um eingehende Nachrichten anhand der in der Filtertabelle enthaltenen Filter auszuwerten, müssen Sie den Dienstendpunkten die Filtertabelle mithilfe des Routingverhaltens zuordnen. Das folgende Beispiel veranschaulicht `filterTable1` die Zuordnung zu den Dienstendpunkten:  
  
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
<!--set up the destination endpoints-->  
      <endpoint name="regularCalcEndpoint"  
                address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
  
      <endpoint name="roundingCalcEndpoint"  
                address="http://localhost:8080/servicemodelsamples/service/"  
                binding="wsHttpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
      <namespaceTable>  
        <add prefix="custom" namespace="http://my.custom.namespace/"/>  
      </namespaceTable>  
      <filters>  
        <!--define the different message filters-->  
        <!--define an xpath message filter to look for the  
            custom header containing a value of 2-->  
        <filter name="XPathFilterRegular" filterType="XPath"  
                filterData="sm:header()/custom:CalcVer = '2'"/>  
        <!--define an xpath message filter to look for the  
            custom header containing a value of 1-->  
        <filter name="XPathFilterRounding" filterType="XPath"  
                filterData="sm:header()/custom:CalcVer = '1'"/>  
        <!--define an xpath message filter to look for  
            messages that do not contain the custom header-->  
        <filter name="XPathFilterNoHeader" filterType="XPath"  
                filterData="count(sm:header()/custom:CalcVer)=0"/>  
      </filters>  
      <filterTables>  
        <filterTable name="filterTable1">  
            <!--add the filters to the message filter table-->  
            <!--look for the custom header = 1, and if we find it,  
                send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilterRounding" endpointName="roundingCalcEndpoint"/>  
            <!--look for the custom header = 2, and if we find it,  
                send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilterRegular" endpointName="regularCalcEndpoint"/>  
            <!--look for the absence of the custom header, and if  
                it is not present, assume the v1 endpoint-->  
            <add filterName="XPathFilterNoHeader" endpointName="roundingCalcEndpoint"/>  
        </filterTable>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="example"></a>Beispiel  
 Es folgt eine vollständige Auflistung der Clientanwendung.  
  
```csharp  
using System;  
using System.ServiceModel;  
using System.ServiceModel.Channels;  
  
namespace Microsoft.Samples.AdvancedFilters  
{  
    //The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.  
  
    //Client implementation code.  
    class Client  
    {  
        static void Main()  
        {  
            //Print out the welcome text  
            Console.WriteLine("This sample routes the Calculator Sample through the new WCF RoutingService");  
            Console.WriteLine("Wait for all the services to indicate that they've started, then press");  
            Console.WriteLine("<ENTER> to start the client.");  
  
            while (Console.ReadLine() != "quit")  
            {  
                //Offer the Address configuration for the client  
                Console.WriteLine("");  
                Console.WriteLine("Welcome to the Calculator Client!");  
  
                EndpointAddress epa;  
                //set the default address as the general router endpoint  
                epa = new EndpointAddress("http://localhost/routingservice/router/calculator");  
  
                //set up the CalculatorClient with the EndpointAddress, the WSHttpBinding, and the ICalculator contract  
                //We use the WSHttpBinding so that the outgoing has a message envelope, which we'll manipulate in a minute  
                CalculatorClient client = new CalculatorClient(new WSHttpBinding(), epa);  
                //client.Endpoint.Contract = ContractDescription.GetContract(typeof(ICalculator));  
  
                //Ask the customer if they want to add a custom header to the outgoing message.  
                //The Router will look for this header, and if so ignore the endpoint the message was  
                //received on, and instead direct the message to the RoundingCalcService.  
                Console.WriteLine("");  
                Console.WriteLine("Which calculator service should be used?");  
                Console.WriteLine("Enter 1 for the rounding calculator, 2 for the regular calculator.");  
                Console.WriteLine("[1] or [2]?");  
  
                string header = Console.ReadLine();  
  
                //get the current operationContextScope from the client's inner channel  
                using (OperationContextScope ocs = new OperationContextScope((client.InnerChannel)))  
                {  
                    //get the outgoing message headers element (collection) from the context  
                    MessageHeaders messageHeadersElement = OperationContext.Current.OutgoingMessageHeaders;  
  
                    //if they wanted to create the header, go ahead and add it to the outgoing message  
                    if (header != null && (header=="1" || header=="2"))  
                    {  
                        //create a new header "RoundingCalculator", no specific namespace, and set the value to
                        //the value of header.  
                        //the Routing Service will look for this header in order to determine if the message  
                        //should be routed to the RoundingCalculator  
                        messageHeadersElement.Add(MessageHeader.CreateHeader("CalcVer", "http://my.custom.namespace/", header));  
                    }  
                    else //incorrect choice, no header added  
                    {  
                        Console.WriteLine("Incorrect value entered, not adding a header");  
                    }  
  
                        //call the client operations  
                        CallClient(client);  
                }  
  
                //close the client to clean it up  
                client.Close();  
                Console.WriteLine();  
                Console.WriteLine("Press <ENTER> to run the client again or type 'quit' to quit.");  
            }  
        }  
  
        private static void CallClient(CalculatorClient client)  
        {  
            Console.WriteLine("");  
            Console.WriteLine("Sending!");  
            // Call the Add service operation.  
            double value1 = 100.00D;  
            double value2 = 15.99D;  
            double result = client.Add(value1, value2);  
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Subtract service operation.  
            value1 = 145.00D;  
            value2 = 76.54D;  
            result = client.Subtract(value1, value2);  
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Multiply service operation.  
            value1 = 9.00D;  
            value2 = 81.25D;  
            result = client.Multiply(value1, value2);  
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
            // Call the Divide service operation.  
            value1 = 22.00D;  
            value2 = 7.00D;  
            result = client.Divide(value1, value2);  
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a>Weitere Informationen

- [Routingdienste](../../../../docs/framework/wcf/samples/routing-services.md)
