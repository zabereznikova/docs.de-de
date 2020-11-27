---
title: 'Vorgehensweise: Dienstversionsverwaltung'
ms.date: 03/30/2017
ms.assetid: 4287b6b3-b207-41cf-aebe-3b1d4363b098
ms.openlocfilehash: ec0f776f296e5ab24f4f628a204b04aa8d903d39
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268468"
---
# <a name="how-to-service-versioning"></a><span data-ttu-id="5166a-102">Vorgehensweise: Dienstversionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="5166a-102">How To: Service Versioning</span></span>

<span data-ttu-id="5166a-103">In diesem Thema werden die grundlegenden Schritte beschrieben, die erforderlich sind, um eine Routingkonfiguration zu erstellen, die Nachrichten an verschiedene Versionen des gleichen Diensts weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="5166a-103">This topic outlines the basic steps required to create a routing configuration that routes messages to different versions of the same service.</span></span> <span data-ttu-id="5166a-104">In diesem Beispiel werden Nachrichten an zwei verschiedene Versionen eines Rechnerdiensts weitergeleitet: `roundingCalc` (v1) und `regularCalc` (v2).</span><span class="sxs-lookup"><span data-stu-id="5166a-104">In this example, messages are routed to two different versions of a calculator service, `roundingCalc` (v1) and `regularCalc` (v2).</span></span> <span data-ttu-id="5166a-105">Beide Implementierungen unterstützen die gleichen Vorgänge. Der ältere Dienst, `roundingCalc`, rundet vor der Rückgabe jedoch alle Berechnungen auf den nächsten ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="5166a-105">Both implementations support the same operations; however the older service, `roundingCalc`, rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="5166a-106">Eine Clientanwendung muss angeben können, ob der neuere `regularCalc`-Dienst verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5166a-106">A client application must be able to indicate whether to use the newer `regularCalc` service.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="5166a-107">Um eine Nachricht an eine bestimmte Dienstversion weiterzuleiten, muss der Routingdienst das Nachrichtziel anhand des Nachrichteninhalts ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="5166a-107">In order to route a message to a specific service version, the Routing Service must be able to determine the message destination based on the message content.</span></span> <span data-ttu-id="5166a-108">In der Methode unten veranschaulichten Methode gibt der Client die Version an, indem er Informationen in einen Nachrichtenheader einfügt.</span><span class="sxs-lookup"><span data-stu-id="5166a-108">In the method demonstrated below, the client will specify the version by inserting information into a message header.</span></span> <span data-ttu-id="5166a-109">Es gibt Methoden für die Dienstversionsverwaltung, für es nicht erforderlich ist, dass Clients zusätzliche Daten übergeben.</span><span class="sxs-lookup"><span data-stu-id="5166a-109">There are methods of service versioning that do not require clients to pass additional data.</span></span> <span data-ttu-id="5166a-110">Eine Nachricht kann z. B. an die aktuelle Version oder die Version mit dem höchsten Kompatibilitätsgrad eines Diensts weitergeleitet werden, oder der Router kann einen Teil des SOAP-Standardumschlags verwenden.</span><span class="sxs-lookup"><span data-stu-id="5166a-110">For example, a message could be routed to the most recent or most compatible version of a service or the router could use a part of the standard SOAP envelope.</span></span>  
  
 <span data-ttu-id="5166a-111">Beide Dienste machen die folgenden Vorgänge verfügbar:</span><span class="sxs-lookup"><span data-stu-id="5166a-111">The operations exposed by both services are:</span></span>  
  
- <span data-ttu-id="5166a-112">Add</span><span class="sxs-lookup"><span data-stu-id="5166a-112">Add</span></span>  
  
- <span data-ttu-id="5166a-113">Subtrahieren</span><span class="sxs-lookup"><span data-stu-id="5166a-113">Subtract</span></span>  
  
- <span data-ttu-id="5166a-114">Multiplizieren</span><span class="sxs-lookup"><span data-stu-id="5166a-114">Multiply</span></span>  
  
- <span data-ttu-id="5166a-115">Dividieren</span><span class="sxs-lookup"><span data-stu-id="5166a-115">Divide</span></span>  
  
 <span data-ttu-id="5166a-116">Da beide Dienstimplementierungen die gleichen Vorgänge behandeln und bis auf die zurückgegebenen Daten im Wesentlichen identisch sind, sind die Basisdaten von Nachrichten, die aus Clientanwendungen gesendet werden, nicht eindeutig genug, um die Weiterleitung der Anforderung einwandfrei bestimmen zu können.</span><span class="sxs-lookup"><span data-stu-id="5166a-116">Because both service implementations handle the same operations, and are essentially identical other than the data that they return, the base data contained in messages sent from client applications is not unique enough to allow you to determine how to route the request.</span></span> <span data-ttu-id="5166a-117">Aktionsfilter können z. B. nicht verwendet werden, weil die Standardaktionen für beide Dienste gleich sind.</span><span class="sxs-lookup"><span data-stu-id="5166a-117">For example, Action filters cannot be used because the default actions for both services are the same.</span></span>  
  
 <span data-ttu-id="5166a-118">Dies kann auf verschiedene Arten gelöst werden. Sie können z. B. für jede Version des Diensts einen bestimmten Endpunkt auf dem Router verfügbar machen, oder Sie können der Nachricht ein benutzerdefiniertes Headerelement hinzufügen, um die Dienstversion anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5166a-118">This can be resolved in several ways, such as exposing a specific endpoint on the router for each version of the service or adding a custom header element to the message to indicate service version.</span></span>  <span data-ttu-id="5166a-119">Bei all diesen Ansätzen können Sie eingehende Nachrichten eindeutig an eine bestimmte Version des Diensts weiterleiten. Die bevorzugte Methode zur Unterscheidung zwischen Anforderungen für unterschiedliche Dienstversionen ist jedoch die Verwendung von eindeutigem Nachrichteninhalt.</span><span class="sxs-lookup"><span data-stu-id="5166a-119">Each of these approaches allows you to uniquely route incoming messages to a specific version of the service, but utilizing unique message content is the preferred method of differentiating between requests for different service versions.</span></span>  
  
 <span data-ttu-id="5166a-120">In diesem Beispiel fügt die Clientanwendung der Anforderungsnachricht den benutzerdefinierten Header dem "CalcVer" hinzu.</span><span class="sxs-lookup"><span data-stu-id="5166a-120">In this example, the client application adds the ‘CalcVer’ custom header to the request message.</span></span> <span data-ttu-id="5166a-121">Dieser Header enthält einen Wert, der die Version des Diensts angibt, an den die Nachricht weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5166a-121">This header will contain a value that indicates the version of the service that the message should be routed to.</span></span> <span data-ttu-id="5166a-122">Der Wert "1" gibt an, dass die Nachricht vom roundingCalc-Dienst verarbeitet werden muss, und der "2" steht für den regularCalc-Dienst.</span><span class="sxs-lookup"><span data-stu-id="5166a-122">A value of ‘1’ indicates that the message must be processed by the roundingCalc service, while a value of ‘2’ indicates the regularCalc service.</span></span> <span data-ttu-id="5166a-123">Auf diese Weise kann die Clientanwendung direkt steuern, welche Version des Diensts die Nachricht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="5166a-123">This allows the client application to directly control which version of the service will process the message.</span></span>  <span data-ttu-id="5166a-124">Da der benutzerdefinierte Header ein in der Nachricht enthaltener Wert ist, können Sie einen Endpunkt zum Empfangen von Nachrichten verwenden, die für beide Versionen des Diensts bestimmt sind.</span><span class="sxs-lookup"><span data-stu-id="5166a-124">Since the custom header is a value contained within the message, you can use one endpoint to receive messages destined for both versions of the service.</span></span> <span data-ttu-id="5166a-125">Der folgende Code kann in der Clientanwendung verwendet werden, um der Nachricht diesen benutzerdefinierten Header hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="5166a-125">The following code can be used in the client application to add this custom header to the message:</span></span>  
  
```csharp  
messageHeadersElement.Add(MessageHeader.CreateHeader("CalcVer", "http://my.custom.namespace/", "2"));  
```  
  
### <a name="implement-service-versioning"></a><span data-ttu-id="5166a-126">Implementieren der Dienstversionsverwaltung</span><span class="sxs-lookup"><span data-stu-id="5166a-126">Implement Service Versioning</span></span>  
  
1. <span data-ttu-id="5166a-127">Erstellen Sie die grundlegende Routingdienstkonfiguration, indem Sie den vom Dienst verfügbar gemachten Dienstendpunkt angeben.</span><span class="sxs-lookup"><span data-stu-id="5166a-127">Create the basic Routing Service configuration by specifying the service endpoint exposed by the service.</span></span> <span data-ttu-id="5166a-128">Im folgenden Beispiel wird ein einzelner Dienstendpunkt definiert, der zum Empfangen von Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5166a-128">The following example defines a single service endpoint, which will be used to receive messages.</span></span> <span data-ttu-id="5166a-129">Außerdem werden die Clientendpunkte definiert, die zum Senden von Nachrichten an die Dienste `roundingCalc` (v1) und `regularCalc` (v2) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5166a-129">It also defines the client endpoints which will be used to send messages to the `roundingCalc` (v1) and the `regularCalc` (v2) services.</span></span>  
  
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
  
2. <span data-ttu-id="5166a-130">Definieren Sie die Filter, die verwendet werden, um Nachrichten an die Zielendpunkte weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="5166a-130">Define the filters used to route messages to the destination endpoints.</span></span>  <span data-ttu-id="5166a-131">In diesem Beispiel wird der XPath-Filter verwendet, um den Wert des benutzerdefinierten Headers "calcver" zu erkennen, um zu bestimmen, an welche Version die Nachricht weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5166a-131">For this example, the XPath filter is used to detect the value of the "CalcVer" custom header to determine which version the message should be routed to.</span></span> <span data-ttu-id="5166a-132">Ein XPath-Filter wird auch verwendet, um Nachrichten zu erkennen, die den Header "calcver" nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="5166a-132">An XPath filter is also used to detect messages that do not contain the "CalcVer" header.</span></span> <span data-ttu-id="5166a-133">Im folgenden Beispiel werden die erforderlichen Filter und die Namespacetabelle definiert.</span><span class="sxs-lookup"><span data-stu-id="5166a-133">The following example defines the required filters and namespace table.</span></span>  
  
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
    > <span data-ttu-id="5166a-134">Das Namespace Präfix "S12" ist standardmäßig in der Namespace Tabelle definiert und stellt den Namespace dar `http://www.w3.org/2003/05/soap-envelope` .</span><span class="sxs-lookup"><span data-stu-id="5166a-134">The s12 namespace prefix is defined by default in the namespace table, and represents the namespace `http://www.w3.org/2003/05/soap-envelope`.</span></span>
  
3. <span data-ttu-id="5166a-135">Definieren Sie die Filtertabelle, in der jedem Filter ein Clientendpunkt zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="5166a-135">Define the filter table, which associates each filter with a client endpoint.</span></span> <span data-ttu-id="5166a-136">Wenn die Nachricht den Header "calcver" mit dem Wert "1" enthält, wird Sie an den RegularCalc-Dienst gesendet.</span><span class="sxs-lookup"><span data-stu-id="5166a-136">If the message contains the "CalcVer" header with a value of 1, it will be sent to the regularCalc service.</span></span> <span data-ttu-id="5166a-137">Enthält der Header den Wert 2, wird sie an den roundingCalc-Dienst gesendet.</span><span class="sxs-lookup"><span data-stu-id="5166a-137">If the header contains a value of 2, it will be sent to the roundingCalc service.</span></span> <span data-ttu-id="5166a-138">Falls kein Header vorhanden ist, wird die Nachricht an regularCalc weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="5166a-138">If no header is present, the message will be routed to the regularCalc.</span></span>  
  
     <span data-ttu-id="5166a-139">Der folgende Code definiert die Filtertabelle und fügt die zuvor definierten Filter hinzu.</span><span class="sxs-lookup"><span data-stu-id="5166a-139">The following defines the filter table and adds the filters defined earlier.</span></span>  
  
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
  
4. <span data-ttu-id="5166a-140">Um eingehende Nachrichten anhand der in der Filtertabelle enthaltenen Filter auszuwerten, müssen Sie den Dienstendpunkten die Filtertabelle mithilfe des Routingverhaltens zuordnen.</span><span class="sxs-lookup"><span data-stu-id="5166a-140">To evaluate incoming messages against the filters contained in the filter table, you must associate the filter table with the service endpoints by using the routing behavior.</span></span> <span data-ttu-id="5166a-141">Das folgende Beispiel veranschaulicht die Zuordnung `filterTable1` zu den Dienst Endpunkten:</span><span class="sxs-lookup"><span data-stu-id="5166a-141">The following example demonstrates associating `filterTable1` with the service endpoints:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="5166a-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5166a-142">Example</span></span>  

 <span data-ttu-id="5166a-143">Es folgt eine vollständige Auflistung der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="5166a-143">The following is a complete listing of the configuration file.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="5166a-144">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5166a-144">Example</span></span>  

 <span data-ttu-id="5166a-145">Es folgt eine vollständige Auflistung der Clientanwendung.</span><span class="sxs-lookup"><span data-stu-id="5166a-145">The following is a complete listing of the client application.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5166a-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5166a-146">See also</span></span>

- [<span data-ttu-id="5166a-147">Routingdienste</span><span class="sxs-lookup"><span data-stu-id="5166a-147">Routing Services</span></span>](../samples/routing-services.md)
