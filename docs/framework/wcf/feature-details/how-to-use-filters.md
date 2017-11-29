---
title: 'Vorgehensweise: Verwenden von Filtern'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2c7255f-c376-460e-aa20-14071f1666e5
caps.latest.revision: "12"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 20e9fd7bd962adb20d2c4bc394012603c7e0f2ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-filters"></a><span data-ttu-id="40f34-102">Vorgehensweise: Verwenden von Filtern</span><span class="sxs-lookup"><span data-stu-id="40f34-102">How To: Use Filters</span></span>
<span data-ttu-id="40f34-103">In diesem Thema werden die grundlegenden Schritte beschrieben, die erforderlich sind, um eine Routingkonfiguration mit mehreren Filtern zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="40f34-103">This topic outlines the basic steps required to create a routing configuration that uses multiple filters.</span></span> <span data-ttu-id="40f34-104">In diesem Beispiel werden Nachrichten an zwei Implementierungen eines Rechnerdiensts weitergeleitet: regularCalc und roundingCalc.</span><span class="sxs-lookup"><span data-stu-id="40f34-104">In this example, messages are routed to two implementations of a calculator service, regularCalc and roundingCalc.</span></span> <span data-ttu-id="40f34-105">Beide Implementierungen unterstützen die gleichen Vorgänge. Ein Dienst rundet vor der Rückgabe jedoch alle Berechnungen auf den nächsten ganzzahligen Wert.</span><span class="sxs-lookup"><span data-stu-id="40f34-105">Both implementations support the same operations; however one service rounds all calculations to the nearest integer value before returning.</span></span> <span data-ttu-id="40f34-106">Eine Clientanwendung muss angeben können, ob die Rundungsversion des Diensts verwendet werden soll. Falls kein bevorzugter Dienst angegeben wird, wird für die Nachricht ein Lastenausgleich zwischen beiden Diensten durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="40f34-106">A client application must be able to indicate whether to  use the rounding version of the service; if no service preference is expressed then the message is load balanced between the two services.</span></span> <span data-ttu-id="40f34-107">Beide Dienste machen die folgenden Vorgänge verfügbar:</span><span class="sxs-lookup"><span data-stu-id="40f34-107">The operations exposed by both services are:</span></span>  
  
-   <span data-ttu-id="40f34-108">Hinzufügen</span><span class="sxs-lookup"><span data-stu-id="40f34-108">Add</span></span>  
  
-   <span data-ttu-id="40f34-109">Subtrahieren</span><span class="sxs-lookup"><span data-stu-id="40f34-109">Subtract</span></span>  
  
-   <span data-ttu-id="40f34-110">Multiplizieren</span><span class="sxs-lookup"><span data-stu-id="40f34-110">Multiply</span></span>  
  
-   <span data-ttu-id="40f34-111">Trennen</span><span class="sxs-lookup"><span data-stu-id="40f34-111">Divide</span></span>  
  
 <span data-ttu-id="40f34-112">Da beide Dienste die gleichen Vorgänge implementieren, können Sie den Aktionsfilter nicht verwenden, weil die in der Nachricht angegebene Aktion nicht eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="40f34-112">Because both services implement the same operations, you cannot use the Action filter, because the action specified in the message will not be unique.</span></span> <span data-ttu-id="40f34-113">Stattdessen müssen Sie weitere Schritte unternehmen, um sicherzustellen, dass die Nachrichten an die entsprechenden Endpunkte weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="40f34-113">Instead you must do additional work to ensure that the messages are routed to the appropriate endpoints.</span></span>  
  
### <a name="determine-unique-data"></a><span data-ttu-id="40f34-114">Bestimmen von eindeutigen Daten</span><span class="sxs-lookup"><span data-stu-id="40f34-114">Determine Unique Data</span></span>  
  
1.  <span data-ttu-id="40f34-115">Da beide Dienstimplementierungen die gleichen Vorgänge behandeln und bis auf die zurückgegebenen Daten im Wesentlichen identisch sind, sind die Basisdaten von Nachrichten, die aus Clientanwendungen gesendet werden, nicht eindeutig genug, um die Weiterleitung der Anforderung einwandfrei bestimmen zu können.</span><span class="sxs-lookup"><span data-stu-id="40f34-115">Because both service implementations handle the same operations, and are essentially identical other than the data that they return, the base data contained in messages sent from client applications is not unique enough to allow you to determine how to route the request.</span></span> <span data-ttu-id="40f34-116">Aber wenn die Clientanwendung der Nachricht einen eindeutigen Headerwert hinzufügt, können Sie anhand dieses Werts bestimmen, auf welche Weise die Nachricht weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="40f34-116">But if the client application adds a unique header value to the message, then you can use this value to determine how the message should be routed.</span></span>  
  
     <span data-ttu-id="40f34-117">Für dieses Beispiel gilt, dass mit dem folgenden Code ein benutzerdefinierter Header hinzugefügt wird, wenn die Clientanwendung eine Verarbeitung der Nachricht mit dem Rundungsrechner erfordert:</span><span class="sxs-lookup"><span data-stu-id="40f34-117">For this example, if the client application needs the message to be processed by the rounding calculator, it adds a custom header by using the following code:</span></span>  
  
    ```csharp  
    messageHeadersElement.Add(MessageHeader.CreateHeader("RoundingCalculator",   
                                   "http://my.custom.namespace/", "rounding"));  
    ```  
  
     <span data-ttu-id="40f34-118">Sie können Nachrichten für diesen Header jetzt mithilfe des XPath-Filters überprüfen und Nachrichten, die den Header enthalten, an den roundCalc-Dienst weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="40f34-118">You can now use the XPath filter to inspect messages for this header, and route messages containing the header to the roundCalc service.</span></span>  
  
2.  <span data-ttu-id="40f34-119">Darüber hinaus macht der Routingdienst zwei virtuelle Dienstendpunkte verfügbar, die mit den Filtern EndpointName, EndpointAddress oder PrefixEndpointAddress verwendet werden können. Damit ist das eindeutige Weiterleiten eingehender Nachrichten an eine bestimmte Rechnerimplementierung basierend auf dem Endpunkt erforderlich, an den die Clientanwendung die Anforderung sendet.</span><span class="sxs-lookup"><span data-stu-id="40f34-119">Additionally the Routing Service exposes two virtual service endpoints that can be used with the EndpointName, EndpointAddress, or PrefixEndpointAddress filters to uniquely route incoming messages to a specific calculator implementation based on the endpoint to which the client application submits the request.</span></span>  
  
### <a name="define-endpoints"></a><span data-ttu-id="40f34-120">Definieren von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="40f34-120">Define Endpoints</span></span>  
  
1.  <span data-ttu-id="40f34-121">Beim Definieren der vom Routingdienst verwendeten Endpunkte sollten Sie zuerst die Form des Kanals bestimmen, der von den Clients und Diensten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="40f34-121">When defining the endpoints used by the Routing Service, you should first determine the shape of the channel used by your clients and services.</span></span> <span data-ttu-id="40f34-122">In diesem Szenario verwenden beide Zieldienste ein Anforderung-Antwort-Muster. Es wird also <xref:System.ServiceModel.Routing.IRequestReplyRouter> verwendet.</span><span class="sxs-lookup"><span data-stu-id="40f34-122">In this scenario both the destination services use a request-reply pattern, so the <xref:System.ServiceModel.Routing.IRequestReplyRouter> is used.</span></span> <span data-ttu-id="40f34-123">Im folgenden Beispiel werden die vom Routingdienst verfügbar gemachten Dienstendpunkte definiert.</span><span class="sxs-lookup"><span data-stu-id="40f34-123">The following example defines the service endpoints exposed by the Routing Service.</span></span>  
  
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
            <!--first create the general router endpoint-->  
            <endpoint address="general"  
                      binding="wsHttpBinding"  
                      name="routerEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
            <!--create a virtual endpoint for the regular calculator service-->  
            <endpoint address="regular/calculator"  
                      binding="wsHttpBinding"  
                      name="calculatorEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
            <!--now create a virtual endpoint for the rounding calculator-->  
            <endpoint address="rounding/calculator"  
                      binding="wsHttpBinding"  
                      name="roundingEndpoint"  
                      contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
  
          </service>  
    </services>  
    ```  
  
     <span data-ttu-id="40f34-124">Mit dieser Konfiguration macht der Routingdienst drei separate Endpunkte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="40f34-124">With this configuration, the Routing Service exposes three separate endpoints.</span></span> <span data-ttu-id="40f34-125">Je nach den ausgewählten Optionen für die Laufzeit sendet die Clientanwendung Nachrichten an eine dieser Adressen.</span><span class="sxs-lookup"><span data-stu-id="40f34-125">Depending on run-time choices, the client application sends messages to one of these addresses.</span></span> <span data-ttu-id="40f34-126">Nachrichten, die bei einer "virtuellen" Dienstendpunkte ("rounding/Calculator" oder "Regular/Calculator") werden an die entsprechende rechnerimplementierung weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="40f34-126">Messages arriving at one of the "virtual" service endpoints ("rounding/calculator" or "regular/calculator") are forwarded to the corresponding calculator implementation.</span></span> <span data-ttu-id="40f34-127">Falls die Clientanwendung die Anforderung nicht an einen bestimmten Endpunkt sendet, wird die Nachricht an den allgemeinen Endpunkt adressiert.</span><span class="sxs-lookup"><span data-stu-id="40f34-127">If the client application doesn’t send the request to a particular endpoint, the message is addressed to the general endpoint.</span></span> <span data-ttu-id="40f34-128">Unabhängig vom ausgewählten Endpunkt kann sich die Clientanwendung auch für die Einbeziehung des benutzerdefinierten Headers entscheiden, um anzugeben, dass die Nachricht an die Implementierung des Rundungsrechners weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="40f34-128">Regardless of the endpoint chosen, the client application may also choose to include the custom header to indicate that the message should be forwarded to the rounding calculator implementation.</span></span>  
  
2.  <span data-ttu-id="40f34-129">Im folgenden Beispiel werden die Endpunkte des Clients (Zielendpunkte) definiert, an die der Routingdienst Nachrichten weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="40f34-129">The following example defines the client (destination) endpoints that the Routing Service routes messages to.</span></span>  
  
    ```xml  
    <client>  
          <endpoint name="regularCalcEndpoint"  
                    address="net.tcp://localhost:9090/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
  
          <endpoint name="roundingCalcEndpoint"  
                    address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                    binding="netTcpBinding"  
                    contract="*" />  
    </client>  
    ```  
  
     <span data-ttu-id="40f34-130">Mit diesen Endpunkten wird in der Filtertabelle der Zielendpunkt angegeben, an den die Nachricht gesendet wird, wenn sich dafür eine Übereinstimmung mit einem bestimmten Filter ergibt.</span><span class="sxs-lookup"><span data-stu-id="40f34-130">These endpoints are used in the filter table to indicate the destination endpoint the message is sent to when it matches a specific filter.</span></span>  
  
### <a name="define-filters"></a><span data-ttu-id="40f34-131">Definieren von Filtern</span><span class="sxs-lookup"><span data-stu-id="40f34-131">Define Filters</span></span>  
  
1.  <span data-ttu-id="40f34-132">Zum Weiterleiten von Nachrichten basierend auf dem "RoundingCalculator" benutzerdefinierte Header, den die Clientanwendung der Nachricht hinzufügt, definieren Sie einen Filter, der mit einer XPath-Abfrage das Vorhandensein dieses Headers.</span><span class="sxs-lookup"><span data-stu-id="40f34-132">To route messages based on the "RoundingCalculator" custom header that the client application adds to the message, define a filter that uses an XPath query to check for the presence of this header.</span></span> <span data-ttu-id="40f34-133">Da dieser Header mit einem benutzerdefinierten Namespace definiert wird, müssen Sie auch fügen Sie einen Namespaceeintrag hinzu, der eine benutzerdefinierte Namespacepräfix "Custom" zur Verwendung in der XPath-Abfrage definiert.</span><span class="sxs-lookup"><span data-stu-id="40f34-133">Because this header is defined by using a custom namespace, also add a namespace entry that defines a custom namespace prefix of "custom" that is used in the XPath query.</span></span> <span data-ttu-id="40f34-134">Im folgenden Beispiel werden der erforderliche Routingabschnitt, die Namespacetabelle und der XPath-Filter definiert.</span><span class="sxs-lookup"><span data-stu-id="40f34-134">The following example defines the necessary routing section, namespace table, and XPath filter.</span></span>  
  
    ```xml  
    <routing>  
          <!-- use the namespace table element to define a prefix for our custom namespace-->  
          <namespaceTable>  
            <add prefix="custom" namespace="http://my.custom.namespace/"/>  
          </namespaceTable>  
          <filters>  
            <!--define the different message filters-->  
            <!--define an xpath message filter to look for the custom header coming from the client-->  
            <filter name="XPathFilter" filterType="XPath"   
                    filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 'rounding'"/>  
          </filters>  
    </routing>  
    ```  
  
     <span data-ttu-id="40f34-135">Dies **MessageFilter** sucht nach einem RoundingCalculator-Header in der Nachricht, die den Wert "rounding" enthält.</span><span class="sxs-lookup"><span data-stu-id="40f34-135">This **MessageFilter** looks for a RoundingCalculator header in the message that contains a value of "rounding".</span></span> <span data-ttu-id="40f34-136">Dieser Header wird vom Client festgelegt, um anzugeben, dass die Nachricht an den roundingCalc-Dienst weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="40f34-136">This header is set by the client to indicate that the message should be routed to the roundingCalc service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="40f34-137">Das Namespacepräfix s12 wird in der namespacetabelle standardmäßig definiert und steht für den Namespace "http://www.w3.org/2003/05/soap-envelope".</span><span class="sxs-lookup"><span data-stu-id="40f34-137">The s12 namespace prefix is defined by default in the namespace table, and represents the namespace "http://www.w3.org/2003/05/soap-envelope".</span></span>  
  
2.  <span data-ttu-id="40f34-138">Sie müssen auch Filter definieren, die nach Nachrichten suchen, die an den beiden virtuellen Endpunkten empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="40f34-138">You must also define filters that look for messages received on the two virtual endpoints.</span></span> <span data-ttu-id="40f34-139">Der erste virtuelle Endpunkt ist der "Regular/Calculator"-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="40f34-139">The first virtual endpoint is the "regular/calculator" endpoint.</span></span> <span data-ttu-id="40f34-140">Der Client kann Anforderungen an diesen Endpunkt senden, um anzugeben, dass die Nachricht an den regularCalc-Dienst weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="40f34-140">The client can send requests to this endpoint to indicate that the message should be routed to the regularCalc service.</span></span> <span data-ttu-id="40f34-141">In der folgenden Konfiguration wird ein Filter definiert, der anhand von <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter> bestimmt, ob die Nachricht an einem Endpunkt empfangen wurde, dessen Name unter filterData angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="40f34-141">The following configuration defines a filter that uses the <xref:System.ServiceModel.Dispatcher.EndpointNameMessageFilter> to determine if the message arrived through an endpoint with the name specified in filterData.</span></span>  
  
    ```xml  
    <!--define an endpoint name filter looking for messages that show up on the virtual regular calculator endpoint-->  
    <filter name="EndpointNameFilter" filterType="EndpointName" filterData="calculatorEndpoint"/>  
    ```  
  
     <span data-ttu-id="40f34-142">Wenn eine Nachricht am Dienstendpunkt mit dem Namen "CalculatorEndpoint" empfangen wird, verwendet dieser Filter ergibt `true`.</span><span class="sxs-lookup"><span data-stu-id="40f34-142">If a message is received by the service endpoint named "calculatorEndpoint", this filter evaluates to `true`.</span></span>  
  
3.  <span data-ttu-id="40f34-143">Definieren Sie als Nächstes einen Filter, der nach Nachrichten sucht, die an die Adresse von roundingEndpoint gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="40f34-143">Next, define a filter that looks for messages sent to the address of the roundingEndpoint.</span></span> <span data-ttu-id="40f34-144">Der Client kann Anforderungen an diesen Endpunkt senden, um anzugeben, dass die Nachricht an den roundingCalc-Dienst weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="40f34-144">The client can send requests to this endpoint to indicate that the message should be routed to the roundingCalc service.</span></span> <span data-ttu-id="40f34-145">Die folgende Konfiguration definiert einen Filter, der mit der <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> zu bestimmen, ob die Nachricht am Endpunkt "rounding/Calculator" empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="40f34-145">The following configuration defines a filter that uses the <xref:System.ServiceModel.Dispatcher.PrefixEndpointAddressMessageFilter> to determine if the message arrived at the "rounding/calculator" endpoint.</span></span>  
  
    ```xml  
    <!--define a filter looking for messages that show up with the address prefix.  The corresponds to the rounding calc virtual endpoint-->  
    <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress"  
            filterData="http://localhost/routingservice/router/rounding/"/>  
    ```  
  
     <span data-ttu-id="40f34-146">Wenn eine Nachricht empfangen wird, eine Adresse, die mit "http://localhost/routingservice/router/rounding/" beginnt, und klicken Sie dann diesen Filter ergibt **"true"**.</span><span class="sxs-lookup"><span data-stu-id="40f34-146">If a message is received at an address that begins with "http://localhost/routingservice/router/rounding/" then this filter evaluates to **true**.</span></span> <span data-ttu-id="40f34-147">Da die von dieser Konfiguration verwendete Basisadresse "http://localhost/routingservice/router" und die für die RoundingEndpoint angegebene Adresse "rounding/Calculator", ist die vollständige Adresse, die für die Kommunkation mit diesem Endpunkt verwendete "http://localhost/ Routingservice/Router/rounding/Calculator", die dieser Filter entspricht.</span><span class="sxs-lookup"><span data-stu-id="40f34-147">Because the base address used by this configuration is "http://localhost/routingservice/router" and the address specified for the roundingEndpoint is "rounding/calculator", the full address used to communicate with this endpoint is "http://localhost/routingservice/router/rounding/calculator", which matches this filter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="40f34-148">Bei der Ermittlung einer Übereinstimmung wertet der PrefixEndpointAddress-Filter den Hostnamen nicht aus, weil auf einen einzelnen Host mit einer Vielzahl von Hostnamen verwiesen werden kann, die alle zulässige Möglichkeiten zum Verweisen auf den Host aus der Clientanwendung darstellen können.</span><span class="sxs-lookup"><span data-stu-id="40f34-148">The PrefixEndpointAddress filter does not evaluate the host name when performing a match, because a single host can be referred to by using a variety of host names that may all be valid ways of referring to the host from the client application.</span></span> <span data-ttu-id="40f34-149">Es kann z. B. sein, dass alle unten aufgeführten Adressen auf den gleichen Host verweisen:</span><span class="sxs-lookup"><span data-stu-id="40f34-149">For example, all of the following may refer to the same host:</span></span>  
    >   
    >  -   <span data-ttu-id="40f34-150">localhost</span><span class="sxs-lookup"><span data-stu-id="40f34-150">localhost</span></span>  
    > -   <span data-ttu-id="40f34-151">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="40f34-151">127.0.0.1</span></span>  
    > -   <span data-ttu-id="40f34-152">www.contoso.com</span><span class="sxs-lookup"><span data-stu-id="40f34-152">www.contoso.com</span></span>  
    > -   <span data-ttu-id="40f34-153">ContosoWeb01</span><span class="sxs-lookup"><span data-stu-id="40f34-153">ContosoWeb01</span></span>  
  
4.  <span data-ttu-id="40f34-154">Der abschließende Filter muss das Routing von Nachrichten unterstützen, die ohne den benutzerdefinierten Header am allgemeinen Endpunkt ankommen.</span><span class="sxs-lookup"><span data-stu-id="40f34-154">The final filter must support the routing of messages that arrive at the general endpoint without the custom header.</span></span> <span data-ttu-id="40f34-155">Für dieses Szenario sollten die Nachrichten zwischen dem regularCalc-Dienst und dem roundingCalc-Dienste wechseln.</span><span class="sxs-lookup"><span data-stu-id="40f34-155">For this scenario, the messages should alternate between the regularCalc and roundingCalc services.</span></span> <span data-ttu-id="40f34-156">Verwenden Sie einen benutzerdefinierten Filter, der können eine Filterinstanz, die für jede verarbeitete Nachricht übereinstimmen, zur Unterstützung von "Roundrobin"-routing dieser Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="40f34-156">To support the "round robin" routing of these messages,  use a custom filter that allows one filter instance to match for each message processed.</span></span>  <span data-ttu-id="40f34-157">Im folgenden Code werden zwei Instanzen von RoundRobinMessageFilter definiert, die gruppiert werden und auf diese Weise angeben, dass dazwischen gewechselt werden soll.</span><span class="sxs-lookup"><span data-stu-id="40f34-157">The following defines two instances of a RoundRobinMessageFilter, which are grouped together to indicate that they should alternate between each other.</span></span>  
  
    ```xml  
    <!-- Set up the custom message filters.  In this example,   
         we'll use the example round robin message filter,   
         which alternates between the references-->  
    <filter name="RoundRobinFilter1" filterType="Custom"  
                    customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly"  
                    filterData="group1"/>  
    <filter name="RoundRobinFilter2" filterType="Custom"  
                    customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly"  
                    filterData="group1"/>  
    ```  
  
     <span data-ttu-id="40f34-158">Während der Laufzeit wechselt der Filtertyp zwischen allen definierten Filterinstanzen dieses Typs, die als Gruppe in einer Auflistung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="40f34-158">During run time, this filter type alternates between all defined filter instances of this type that are configured as the same group into one collection.</span></span> <span data-ttu-id="40f34-159">Dies bewirkt, dass von diesem benutzerdefinierten Filter verarbeitete Nachrichten zwischen der Rückgabe von `true` für RoundRobinFilter1 und RoundRobinFilter2 wechseln.</span><span class="sxs-lookup"><span data-stu-id="40f34-159">This causes messages processed by this custom filter to alternate between returning `true` for RoundRobinFilter1 and RoundRobinFilter2.</span></span>  
  
### <a name="define-filter-tables"></a><span data-ttu-id="40f34-160">Definieren von Filtertabellen</span><span class="sxs-lookup"><span data-stu-id="40f34-160">Define Filter Tables</span></span>  
  
1.  <span data-ttu-id="40f34-161">Um die Filter bestimmten Clientendpunkten zuzuordnen, müssen Sie diese in eine Filtertabelle einfügen.</span><span class="sxs-lookup"><span data-stu-id="40f34-161">To associate the filters with specific client endpoints, you must place them within a filter table.</span></span> <span data-ttu-id="40f34-162">In diesem Beispielszenario werden außerdem Filterprioritätseinstellungen verwendet. Dies ist eine optionale Einstellung, mit der Sie die Reihenfolge angeben können, in der Filter verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="40f34-162">This example scenario also uses filter priority settings, which is an optional setting that allows you to indicate the order in which filters are processed.</span></span> <span data-ttu-id="40f34-163">Falls keine Filterpriorität angegeben wird, werden alle Filter gleichzeitig ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="40f34-163">If no filter priority is specified, all filters are evaluated simultaneously.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="40f34-164">Mit der Angabe einer Filterpriorität können Sie zwar die Reihenfolge steuern, in der Filter verarbeitet werden, aber dies kann sich auch negativ auf die Leistung des Routingdiensts auswirken.</span><span class="sxs-lookup"><span data-stu-id="40f34-164">While specifying a filter priority allows you to control the order in which filters are processed, it can adversely affect the performance of the Routing Service.</span></span> <span data-ttu-id="40f34-165">Erstellen Sie die Filterlogik nach Möglichkeit so, dass die Verwendung von Filterprioritäten nicht erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="40f34-165">When possible, construct filter logic so that the use of filter priorities is not required.</span></span>  
  
     <span data-ttu-id="40f34-166">Der folgende Code definiert die Filtertabelle und fügt der zuvor in der Tabelle mit einer Priorität von 2 definierten "XPathFilter".</span><span class="sxs-lookup"><span data-stu-id="40f34-166">The following defines the filter table and adds the "XPathFilter" defined earlier to the table with a priority of 2.</span></span> <span data-ttu-id="40f34-167">Dieser Eintrag gibt auch an, wenn der "XPathFilter" die Nachricht übereinstimmt, wird die Nachricht an die "RoundingCalcEndpoint" weitergeleitet</span><span class="sxs-lookup"><span data-stu-id="40f34-167">This entry also specifies that if the "XPathFilter" matches the message, the message will be routed to the "roundingCalcEndpoint"</span></span>  
  
    ```xml  
    <routing>  
    ...      <filters>  
    ...      </filters>  
          <filterTables>  
            <table name="filterTable1">  
              <entries>  
                <!--add the filters to the message filter table-->  
                <!--first look for the custom header, and if we find it,  
                    send the message to the rounding calc endpoint-->  
                <add filterName="XPathFilter" endpointName="roundingCalcEndpoint" priority="2"/>  
              </entries>  
            </table>  
          <filterTables>  
    </routing>  
    ```  
  
     <span data-ttu-id="40f34-168">Beim Angeben einer Filterpriorität werden die Filter mit der höchsten Priorität zuerst ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="40f34-168">When specifying a filter priority, the highest priority filters are evaluated first.</span></span> <span data-ttu-id="40f34-169">Wenn sich für einen oder mehrere Filter mit einer bestimmten Prioritätsstufen ein Übereinstimmung ergibt, werden keine Filter mit niedrigeren Prioritätsstufen ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="40f34-169">If one or more filters at a specific priority level match, no filters at lower priority levels will be evaluated.</span></span> <span data-ttu-id="40f34-170">Bei diesem Szenario ist 2 die höchste angegebene Priorität, und dies ist der einzige Filtereintrag auf dieser Stufe.</span><span class="sxs-lookup"><span data-stu-id="40f34-170">For this scenario, 2 is the highest priority specified and this is the only filter entry at this level.</span></span>  
  
2.  <span data-ttu-id="40f34-171">Filtereinträge wurden definiert, um eine Nachricht darauf zu überprüfen, ob diese an einem bestimmten Endpunkt empfangen wird, indem der Endpunktname oder das Adresspräfix untersucht wird.</span><span class="sxs-lookup"><span data-stu-id="40f34-171">Filter entries were defined to check to see if a message is received on a specific endpoint by inspecting the endpoint name or the address prefix.</span></span> <span data-ttu-id="40f34-172">Die folgenden Einträge fügen diese beiden Filtereinträge der Filtertabelle hinzu und ordnen sie den Zielendpunkten zu, an die die Nachricht weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="40f34-172">The following entries add both of these filter entries to the filter table and associate them with the destination endpoints that the message will be routed to.</span></span> <span data-ttu-id="40f34-173">Für diese Filter ist eine Priorität von 1 festgelegt, um anzugeben, dass sie nur ausgeführt werden sollen, wenn sich für den vorherigen XPath-Filter keine Übereinstimmung mit der Nachricht ergeben hat.</span><span class="sxs-lookup"><span data-stu-id="40f34-173">These filters are set to a priority of 1 to indicate that they should only run if the previous XPath filter did not match the message.</span></span>  
  
    ```xml  
    <!--if the header wasn't there, send the message based on which virtual endpoint it arrived at-->  
    <!--we determine this through the endpoint name, or through the address prefix-->  
    <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint" priority="1"/>  
    <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint" priority="1"/>  
    ```  
  
     <span data-ttu-id="40f34-174">Da diese Filter eine Filterpriorität von 1 aufweisen, werden diese nur ausgewertet, wenn sich für den Filter auf der Prioritätsstufe 2 keine Übereinstimmung mit der Nachricht ergeben hat.</span><span class="sxs-lookup"><span data-stu-id="40f34-174">Because these filters have a filter priority of 1, they will only be evaluated if the filter at priority level 2 does not match the message.</span></span> <span data-ttu-id="40f34-175">Da beide Filter außerdem die gleiche Prioritätsstufe aufweisen, werden sie gleichzeitig ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="40f34-175">Also, because both filters have the same priority level they will be evaluated simultaneously.</span></span> <span data-ttu-id="40f34-176">Weil sich beide Filter gegenseitig ausschließen, kann sich nur für einen von beiden eine Übereinstimmung mit der Nachricht ergeben.</span><span class="sxs-lookup"><span data-stu-id="40f34-176">Because both filters are mutually exclusive, it is possible for only one or the other to match a message.</span></span>  
  
3.  <span data-ttu-id="40f34-177">Falls sich für eine Nachricht keine Übereinstimmung mit den vorherigen Filtern ergibt, wurde die Nachricht über den generischen Dienstendpunkt empfangen und hat keine Headerinformationen enthalten, die das Ziel für die Weiterleitung angeben.</span><span class="sxs-lookup"><span data-stu-id="40f34-177">If a message does not match any of the previous filters, then the message was received through the generic service endpoint and contained no header information that indicates where to route it.</span></span> <span data-ttu-id="40f34-178">Diese Nachrichten werden vom benutzerdefinierten Filter behandelt, der dafür den Lastenausgleich zwischen den beiden Rechnerdiensten durchführt.</span><span class="sxs-lookup"><span data-stu-id="40f34-178">These messages are to be handled by the custom filter, which load balances them between the two calculator services.</span></span> <span data-ttu-id="40f34-179">Im folgenden Beispiel wird veranschaulicht, wie Sie der Filtertabelle die Filtereinträge hinzufügen. Jedem Filter wird einer der beiden Zielendpunkte zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="40f34-179">The following example demonstrates how to add the filter entries to the filter table; each filter is associated with one of the two destination endpoints.</span></span>  
  
    ```xml  
    <!--if none of the other filters have matched,   
        this message showed up on the default router endpoint,   
        with no custom header-->  
    <!--round robin these requests between the two services-->  
    <add filterName="RoundRobinFilter1" endpointName="regularCalcEndpoint" priority="0"/>  
    <add filterName="RoundRobinFilter2" endpointName="roundingCalcEndpoint" priority="0"/>  
    ```  
  
     <span data-ttu-id="40f34-180">Da diese Einträge eine Priorität von 0 angeben, werden sie nur ausgewertet, sofern sich für keinen Filter mit einer höheren Priorität eine Übereinstimmung ergibt.</span><span class="sxs-lookup"><span data-stu-id="40f34-180">Because these entries specify a priority of 0, they will only be evaluated if no filter of a higher priority matches the message.</span></span> <span data-ttu-id="40f34-181">Da beide außerdem die gleiche Priorität aufweisen, werden sie gleichzeitig ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="40f34-181">Also, since both are of the same priority, they are evaluated simultaneously.</span></span>  
  
     <span data-ttu-id="40f34-182">Wie bereits erwähnt, wertet der von diesen Filterdefinitionen verwendete benutzerdefinierte Filter für die empfangenen Nachrichten jeweils nur einen Eintrag als `true` aus.</span><span class="sxs-lookup"><span data-stu-id="40f34-182">As mentioned previously, the custom filter used by these filter definitions only evaluates one or the other as `true` for each message received.</span></span> <span data-ttu-id="40f34-183">Da mit diesem Filter nur zwei Filter mit der gleichen angegebenen Gruppeneinstellung definiert werden, führt dies dazu, dass der Routingdienst zwischen dem Senden an regularCalcEndpoint und RoundingCalcEndpoint wechselt.</span><span class="sxs-lookup"><span data-stu-id="40f34-183">Because only two filters are defined using this filter, with the same specified group setting, the effect is that the Routing Service alternates between sending to the regularCalcEndpoint and the RoundingCalcEndpoint.</span></span>  
  
4.  <span data-ttu-id="40f34-184">Um Nachrichten mithilfe von Filtern auswerten zu können, muss die Filtertabelle den Dienstendpunkten zugeordnet sein, die zum Empfangen von Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="40f34-184">To evaluate messages against the filters, the filter table must first be associated with the service endpoints that will be used to receive messages.</span></span>  <span data-ttu-id="40f34-185">Im folgenden Beispiel wird veranschaulicht, wie Sie die Routingtabelle mithilfe des Routingverhaltens den Dienstendpunkten zuordnen:</span><span class="sxs-lookup"><span data-stu-id="40f34-185">The following example demonstrates how to associate the routing table with the service endpoints by using the routing behavior:</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="40f34-186">Beispiel</span><span class="sxs-lookup"><span data-stu-id="40f34-186">Example</span></span>  
 <span data-ttu-id="40f34-187">Es folgt eine vollständige Auflistung der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="40f34-187">The following is a complete listing of the configuration file.</span></span>  
  
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
        <!--first create the general router endpoint-->  
        <endpoint address="general"  
                  binding="wsHttpBinding"  
                  name="routerEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <!--create a virtual endpoint for the regular calculator service-->  
        <endpoint address="regular/calculator"  
                  binding="wsHttpBinding"  
                  name="calculatorEndpoint"  
                  contract="System.ServiceModel.Routing.IRequestReplyRouter" />  
        <!--now create a virtual endpoint for the rounding calculator-->  
        <endpoint address="rounding/calculator"  
                  binding="wsHttpBinding"  
                  name="roundingEndpoint"  
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
                address="net.tcp://localhost:8080/servicemodelsamples/service/"  
                binding="netTcpBinding"  
                contract="*" />  
    </client>  
    <routing>  
      <!-- use the namespace table element to define a prefix for our custom namespace-->  
      <namespaceTable>  
        <add prefix="custom" namespace="http://my.custom.namespace/"/>  
      </namespaceTable>  
      <filters>  
        <!--define the different message filters-->  
        <!--define an xpath message filter to look for the custom header coming from the client-->  
        <filter name="XPathFilter" filterType="XPath" filterData="/s12:Envelope/s12:Header/custom:RoundingCalculator = 'rounding'"/>  
  
        <!--define an endpoint name filter looking for messages that show up on the virtual regular calculator endpoint-->  
        <filter name="EndpointNameFilter" filterType="EndpointName" filterData="calculatorEndpoint"/>  
  
        <!--define a filter looking for messages that show up with the address prefix.  The corresponds to the rounding calc virtual endpoint-->  
        <filter name="PrefixAddressFilter" filterType="PrefixEndpointAddress" filterData="http://localhost/routingservice/router/rounding/"/>  
  
        <!--Set up the custom message filters.  In this example, we'll use the example round robin message filter, which alternates between the references-->  
        <filter name="RoundRobinFilter1" filterType="Custom" customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly" filterData="group1"/>  
        <filter name="RoundRobinFilter2" filterType="Custom" customType="CustomFilterAssembly.RoundRobinMessageFilter, CustomFilterAssembly" filterData="group1"/>  
      </filters>  
      <filterTables>  
        <table name="filterTable1">  
          <entries>  
            <!--add the filters to the message filter table-->  
            <!--first look for the custom header, and if we find it, send the message to the rounding calc endpoint-->  
            <add filterName="XPathFilter" endpointName="roundingCalcEndpoint" priority="2"/>  
  
            <!--if the header wasn't there, send the message based on which virtual endpoint it arrived at-->  
            <!--we determine this through the endpoint name, or through the address prefix-->  
            <add filterName="EndpointNameFilter" endpointName="regularCalcEndpoint" priority="1"/>  
            <add filterName="PrefixAddressFilter" endpointName="roundingCalcEndpoint" priority="1"/>  
  
            <!--if none of the other filters have matched, this message showed up on the default router endpoint, with no custom header-->  
            <!--round robin these requests between the two services-->  
            <add filterName="RoundRobinFilter1" endpointName="regularCalcEndpoint" priority="0"/>  
            <add filterName="RoundRobinFilter2" endpointName="roundingCalcEndpoint" priority="0"/>  
          </entries>  
        </table>  
      </filterTables>  
    </routing>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="40f34-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40f34-188">See Also</span></span>  
 [<span data-ttu-id="40f34-189">Routingdienste</span><span class="sxs-lookup"><span data-stu-id="40f34-189">Routing Services</span></span>](../../../../docs/framework/wcf/samples/routing-services.md)
