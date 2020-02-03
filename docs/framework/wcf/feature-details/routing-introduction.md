---
title: Einführung in das Routing
ms.date: 03/30/2017
ms.assetid: bf6ceb38-6622-433b-9ee7-f79bc93497a1
ms.openlocfilehash: 8ce98aab2ed14401fa7c2cbf43eb92a633fa96b0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746470"
---
# <a name="routing-introduction"></a><span data-ttu-id="3a975-102">Einführung in das Routing</span><span class="sxs-lookup"><span data-stu-id="3a975-102">Routing Introduction</span></span>

<span data-ttu-id="3a975-103">Der Routingdienst stellt einen generischen austauschbaren SOAP-Vermittler bereit, der Nachrichten basierend auf dem Nachrichteninhalts weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="3a975-103">The Routing Service provides a generic pluggable SOAP intermediary that is capable of routing messages based on message content.</span></span> <span data-ttu-id="3a975-104">Mit dem Routingdienst können Sie eine komplexe Routinglogik erstellen, mit der Sie Szenarios wie Dienstaggregation, Dienstversionsverwaltung, Prioritätsrouting und Multicastrouting implementieren können.</span><span class="sxs-lookup"><span data-stu-id="3a975-104">With the Routing Service, you can create complex routing logic that allows you to implement scenarios such as service aggregation, service versioning, priority routing, and multicast routing.</span></span> <span data-ttu-id="3a975-105">Außerdem stellt der Routingdienst eine Fehlerbehandlung bereit. Damit können Sie Listen von Sicherungsendpunkten einrichten, an die Nachrichten gesendet werden, falls beim Senden an den primären Zielendpunkt ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="3a975-105">The Routing Service also provides error handling that allows you to set up lists of backup endpoints, to which messages are sent if a failure occurs when sending to the primary destination endpoint.</span></span>

<span data-ttu-id="3a975-106">Dieses Thema richtet sich an Personen, die mit dem Routingdienst noch nicht vertraut sind, und behandelt die grundlegende Konfiguration und das Hosten des Routingdiensts.</span><span class="sxs-lookup"><span data-stu-id="3a975-106">This topic is intended for those new to the Routing Service and covers basic configuration and hosting of the Routing Service.</span></span>

## <a name="configuration"></a><span data-ttu-id="3a975-107">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3a975-107">Configuration</span></span>

<span data-ttu-id="3a975-108">Der Routingdienst wird als WCF-Dienst implementiert, der einen oder mehrere Dienstendpunkte verfügbar macht, die Nachrichten von Clientanwendungen empfangen und die Nachrichten an einen oder mehrere Zielendpunkte weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="3a975-108">The Routing Service is implemented as a WCF service that exposes one or more service endpoints that receive messages from client applications and route the messages to one or more destination endpoints.</span></span> <span data-ttu-id="3a975-109">Der Dienst stellt ein <xref:System.ServiceModel.Routing.RoutingBehavior>-Objekt bereit, das auf die vom Dienst verfügbar gemachten Dienstendpunkte angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a975-109">The service provides a <xref:System.ServiceModel.Routing.RoutingBehavior>, which is applied to the service endpoints exposed by the service.</span></span> <span data-ttu-id="3a975-110">Dieses Verhalten wird verwendet, um verschiedene Aspekte in Bezug auf die Funktionsweise des Diensts zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3a975-110">This behavior is used to configure various aspects of how the service operates.</span></span> <span data-ttu-id="3a975-111">Zur Erleichterung der Konfiguration bei Verwendung einer Konfigurationsdatei werden die Parameter für **Routing Behavior**angegeben.</span><span class="sxs-lookup"><span data-stu-id="3a975-111">For ease of configuration when using a configuration file, the parameters are specified on the **RoutingBehavior**.</span></span> <span data-ttu-id="3a975-112">In Code basierten Szenarien werden diese Parameter als Teil eines <xref:System.ServiceModel.Routing.RoutingConfiguration> Objekts angegeben, das dann an ein **RoutingBehavior**-Objekt weitergeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3a975-112">In code-based scenarios, these parameters would be specified as part of a <xref:System.ServiceModel.Routing.RoutingConfiguration> object, which can then be passed to a **RoutingBehavior**.</span></span>

<span data-ttu-id="3a975-113">Beim Starten fügt dieses Verhalten den Clientendpunkten das <xref:System.ServiceModel.Routing.SoapProcessingBehavior> hinzu. Dieses Verhalten wird für die SOAP-Verarbeitung von Nachrichten verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a975-113">When starting, this behavior adds the <xref:System.ServiceModel.Routing.SoapProcessingBehavior>, which is used to perform SOAP processing of messages, to the client endpoints.</span></span> <span data-ttu-id="3a975-114">Dadurch kann der Routing Dienst Nachrichten an Endpunkte übertragen, die eine andere **MessageVersion** benötigen als der Endpunkt, über den die Nachricht empfangen wurde.</span><span class="sxs-lookup"><span data-stu-id="3a975-114">This allows the Routing Service to transmit messages to endpoints that require a different **MessageVersion** than the endpoint the message was received over.</span></span> <span data-ttu-id="3a975-115">Das **RoutingBehavior** registriert auch eine Dienst Erweiterung, die <xref:System.ServiceModel.Routing.RoutingExtension>, die einen Barrierefreiheits Punkt zum Ändern der Routing Dienst Konfiguration zur Laufzeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="3a975-115">The **RoutingBehavior** also registers a service extension, the <xref:System.ServiceModel.Routing.RoutingExtension>, which provides an accessibility point for modifying the Routing Service configuration at run time.</span></span>

<span data-ttu-id="3a975-116">Die **RoutingConfiguration** -Klasse bietet eine konsistente Möglichkeit, die Konfiguration des Routing Dienstanbieter zu konfigurieren und zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3a975-116">The **RoutingConfiguration** class provides a consistent means of configuring and updating the configuration of the Routing Service.</span></span>  <span data-ttu-id="3a975-117">Sie enthält Parameter, die als Einstellungen für den Routing Dienst fungieren und zum Konfigurieren des **RoutingBehavior** verwendet werden, wenn der Dienst gestartet wird. Sie wird auch verwendet, um die Routing Konfiguration zur **Laufzeit zu ändern** .</span><span class="sxs-lookup"><span data-stu-id="3a975-117">It contains parameters that act as the settings for the Routing Service and is used to configure the **RoutingBehavior** when the service starts, or is passed to the **RoutingExtension** to modify routing configuration at run time.</span></span>

<span data-ttu-id="3a975-118">Die Routinglogik, mit der das inhaltsbasierte Routing von Nachrichten durchgeführt wird, wird definiert, indem mehrere <xref:System.ServiceModel.Dispatcher.MessageFilter>-Objekte zu Filtertabellen (<xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>-Objekten) gruppiert werden.</span><span class="sxs-lookup"><span data-stu-id="3a975-118">The routing logic used to perform content-based routing of messages is defined by grouping multiple <xref:System.ServiceModel.Dispatcher.MessageFilter> objects together into filter tables (<xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> objects).</span></span> <span data-ttu-id="3a975-119">Eingehende Nachrichten werden anhand der in der Filter Tabelle enthaltenen Nachrichtenfilter und für jeden **MessageFilter** , der mit der Nachricht übereinstimmt, an einen Ziel Endpunkt weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="3a975-119">Incoming messages are evaluated against the message filters contained in the filter table, and for each **MessageFilter** that matches the message, forwarded to a destination endpoint.</span></span> <span data-ttu-id="3a975-120">Die Filter Tabelle, die zum Weiterleiten von Nachrichten verwendet werden soll, wird entweder mithilfe des **RoutingBehavior** in der Konfiguration oder durch Code mithilfe des **RoutingConfiguration** -Objekts angegeben.</span><span class="sxs-lookup"><span data-stu-id="3a975-120">The filter table that should be used to route messages is specified by using either the **RoutingBehavior** in configuration or through code by using the **RoutingConfiguration** object.</span></span>

### <a name="defining-endpoints"></a><span data-ttu-id="3a975-121">Definieren von Endpunkten</span><span class="sxs-lookup"><span data-stu-id="3a975-121">Defining Endpoints</span></span>

<span data-ttu-id="3a975-122">Es scheint so zu sein, als ob Sie die Konfiguration beginnen sollten, indem Sie die zu verwendende Routinglogik definieren. Stattdessen sollte der erste Schritt darin bestehen, die Form der Endpunkte zu ermitteln, an die Sie Nachrichten weiterleiten möchten.</span><span class="sxs-lookup"><span data-stu-id="3a975-122">While it may seem that you should start your configuration by defining the routing logic you will use, your first step should actually be to determine the shape of the endpoints you will be routing messages to.</span></span> <span data-ttu-id="3a975-123">Der Routingdienst verwendet Verträge, die die Form der Kanäle definieren, die zum Empfangen und Senden von Nachrichten verwendet werden. Aus diesem Grund muss die Form des Eingabekanals mit der Form des Ausgabekanals übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="3a975-123">The Routing Service uses contracts that define the shape of the channels used to receive and send messages, and therefore the shape of the input channel must match that of the output channel.</span></span>  <span data-ttu-id="3a975-124">Wenn Sie die Weiterleitung z. B. an Endpunkte durchführen, die die Anforderung-Antwort-Kanalform verwenden, müssen Sie an den Eingangsendpunkten einen kompatiblen Vertrag verwenden, z. B. <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span><span class="sxs-lookup"><span data-stu-id="3a975-124">For example, if you are routing to endpoints that use the request-reply channel shape, then you must use a compatible contract on the inbound endpoints, such as the <xref:System.ServiceModel.Routing.IRequestReplyRouter>.</span></span>

<span data-ttu-id="3a975-125">Wenn die Zielendpunkte Verträge mit mehreren Kommunikationsmustern verwenden (z. B. eine Mischung aus unidirektionalen und bidirektionalen Vorgängen), können Sie also keinen einzelnen Dienstendpunkt erstellen, der Nachrichten empfängt und an all diese Zielendpunkte weiterleitet.</span><span class="sxs-lookup"><span data-stu-id="3a975-125">This means that if your destination endpoints use contracts with multiple communication patterns (such as mixing one-way and two-way operations,) you cannot create a single service endpoint that can receive and route messages to all of them.</span></span> <span data-ttu-id="3a975-126">Sie müssen bestimmen, welche Endpunkte über kompatible Formen verfügen, und einen oder mehrere Dienstendpunkte definieren, an denen die Nachrichten empfangen werden, die an die Zielendpunkten weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3a975-126">You must determine which endpoints have compatible shapes and define one or more service endpoints that will be used to receive messages to be routed to the destination endpoints.</span></span>

> [!NOTE]
> <span data-ttu-id="3a975-127">Beim Arbeiten mit Verträgen, die mehrere Kommunikationsmuster angeben (z. B. eine Mischung aus unidirektionalen und bidirektionalen Vorgängen), besteht eine Problemumgehung in der Verwendung eines Duplexvertrags für den Routingdienst, z. B. <xref:System.ServiceModel.Routing.IDuplexSessionRouter>.</span><span class="sxs-lookup"><span data-stu-id="3a975-127">When working with contracts that specify multiple communication patterns (such as a mix of one-way and two-way operations,) a workaround is to use a duplex contract at the Routing Service such as <xref:System.ServiceModel.Routing.IDuplexSessionRouter>.</span></span> <span data-ttu-id="3a975-128">Dies bedeutet jedoch, dass die Bindung für die Duplexkommunikation geeignet sein muss, was ggf. nicht für alle Szenarios der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="3a975-128">However this means that the binding must be capable of duplex communication, which may not be possible for all scenarios.</span></span> <span data-ttu-id="3a975-129">In Szenarios, in denen dies nicht möglich ist, kann das Verteilen der Kommunikation auf mehrere Endpunkte oder das Ändern der Anwendung erforderlich sein.</span><span class="sxs-lookup"><span data-stu-id="3a975-129">In scenarios where this is not possible, factoring the communication into multiple endpoints or modifying the application may be necessary.</span></span>

<span data-ttu-id="3a975-130">Weitere Informationen zu Routing Verträgen finden Sie unter [Routing Verträge](routing-contracts.md).</span><span class="sxs-lookup"><span data-stu-id="3a975-130">For more information about routing contracts, see [Routing Contracts](routing-contracts.md).</span></span>

<span data-ttu-id="3a975-131">Nachdem der Dienst Endpunkt definiert wurde, können Sie das **Routing Behavior-Verhalten** verwenden, um dem Endpunkt eine bestimmte **RoutingConfiguration** zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3a975-131">After the service endpoint is defined, you can use the **RoutingBehavior** to associate a specific **RoutingConfiguration** with the endpoint.</span></span> <span data-ttu-id="3a975-132">Beim Konfigurieren des Routing Dienstanbieter mithilfe einer Konfigurationsdatei wird **RoutingBehavior** verwendet, um die Filter Tabelle anzugeben, die die Routing Logik zum Verarbeiten von Nachrichten enthält, die an diesem Endpunkt empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="3a975-132">When configuring the Routing Service by using a configuration file, the **RoutingBehavior** is used to specify the filter table that contains the routing logic used to process messages received on this endpoint.</span></span> <span data-ttu-id="3a975-133">Wenn Sie den Routing Dienstprogramm gesteuert konfigurieren, können Sie die Filter Tabelle mithilfe von **RoutingConfiguration**angeben.</span><span class="sxs-lookup"><span data-stu-id="3a975-133">If you are configuring the Routing Service programmatically you can specify the filter table by using the **RoutingConfiguration**.</span></span>

<span data-ttu-id="3a975-134">Im folgenden Beispiel werden die Dienst- und Clientendpunkte, die vom Routingdienst verwendet werden, sowohl programmgesteuert als auch unter Verwendung einer Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="3a975-134">The following example defines the service and client endpoints that are used by the Routing Service both programmatically and by using a configuration file.</span></span>

```xml
<services>
  <!--ROUTING SERVICE -->
  <service behaviorConfiguration="routingData"
            name="System.ServiceModel.Routing.RoutingService">
    <host>
      <baseAddresses>
        <add baseAddress="http://localhost:8000/routingservice/router"/>
      </baseAddresses>
    </host>
    <!-- Define the service endpoints that are receive messages -->
    <endpoint address=""
              binding="wsHttpBinding"
              name="reqReplyEndpoint"
              contract="System.ServiceModel.Routing.IRequestReplyRouter" />
  </service>
</services>
<behaviors>
  <serviceBehaviors>
    <behavior name="routingData">
      <serviceMetadata httpGetEnabled="True"/>
      <!-- Add the RoutingBehavior and specify the Routing Table to use -->
      <routing filterTableName="routingTable1" />
    </behavior>
  </serviceBehaviors>
</behaviors>
<client>
<!-- Define the client endpoint(s) to route messages to -->
  <endpoint name="CalculatorService"
            address="http://localhost:8000/servicemodelsamples/service"
            binding="wsHttpBinding" contract="*" />
</client>
```

```csharp
//set up some communication defaults
string clientAddress = "http://localhost:8000/servicemodelsamples/service";
string routerAddress = "http://localhost:8000/routingservice/router";
Binding routerBinding = new WSHttpBinding();
Binding clientBinding = new WSHttpBinding();
//add the endpoint the router uses to receive messages
serviceHost.AddServiceEndpoint(
     typeof(IRequestReplyRouter),
     routerBinding,
     routerAddress);
//create the client endpoint the router routes messages to
ContractDescription contract = ContractDescription.GetContract(
     typeof(IRequestReplyRouter));
ServiceEndpoint client = new ServiceEndpoint(
     contract,
     clientBinding,
     new EndpointAddress(clientAddress));
//create a new routing configuration object
RoutingConfiguration rc = new RoutingConfiguration();
….
rc.FilterTable.Add(new MatchAllMessageFilter(), endpointList);
//attach the behavior to the service host
serviceHost.Description.Behaviors.Add(
     new RoutingBehavior(rc));
```

<span data-ttu-id="3a975-135">In diesem Beispiel wird der Routing Dienst so konfiguriert, dass ein einzelner Endpunkt mit der Adresse `http://localhost:8000/routingservice/router`verfügbar gemacht wird, der zum Empfangen von Nachrichten verwendet wird, die weitergeleitet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3a975-135">This example configures the Routing Service to expose a single endpoint with an address of `http://localhost:8000/routingservice/router`, which is used to receive messages to be routed.</span></span> <span data-ttu-id="3a975-136">Da die Nachrichten an die Anforderung-Antwort-Endpunkte weitergeleitet werden, verwendet der Dienstendpunkt den <xref:System.ServiceModel.Routing.IRequestReplyRouter>-Vertrag.</span><span class="sxs-lookup"><span data-stu-id="3a975-136">Because the messages are routed to request-reply endpoints, the service endpoint uses the <xref:System.ServiceModel.Routing.IRequestReplyRouter> contract.</span></span> <span data-ttu-id="3a975-137">Diese Konfiguration definiert auch einen einzelnen Client Endpunkt `http://localhost:8000/servicemodelsample/service`, an die Nachrichten weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3a975-137">This configuration also defines a single client endpoint of `http://localhost:8000/servicemodelsample/service` that messages are routed to.</span></span> <span data-ttu-id="3a975-138">Die Filter Tabelle (nicht angezeigt) mit dem Namen "routingTable1" enthält die Routing Logik, die zum Weiterleiten von Nachrichten verwendet wird, und ist mit dem Dienst Endpunkt verknüpft, indem Routing **Verhalten** (für eine Konfigurationsdatei) oder **RoutingConfiguration** (für die programmgesteuerte Konfiguration) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a975-138">The filter table (not shown) named "routingTable1" contains the routing logic used to route messages, and is associated with the service endpoint by using the **RoutingBehavior** (for a configuration file) or **RoutingConfiguration** (for programmatic configuration).</span></span>

### <a name="routing-logic"></a><span data-ttu-id="3a975-139">Routinglogik</span><span class="sxs-lookup"><span data-stu-id="3a975-139">Routing Logic</span></span>

<span data-ttu-id="3a975-140">Um die Routinglogik zum Weiterleiten von Nachrichten zu definieren, müssen Sie ermitteln, welche in den eingehenden Nachrichten enthaltenen Daten eindeutig verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="3a975-140">To define the routing logic used to route messages, you must determine what data contained within the incoming messages can be uniquely acted upon.</span></span> <span data-ttu-id="3a975-141">Wenn beispielsweise alle Zielendpunkte der Weiterleitung die gleichen SOAP-Aktionen verwenden, ist der Wert von "Action" innerhalb der Nachricht kein guter Indikator dafür, an welchen Endpunkt die Nachricht jeweils genau weitergeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a975-141">For example, if all the destination endpoints you are routing to share the same SOAP Actions, the value of the Action contained within the message is not a good indicator of which specific endpoint the message should be routed to.</span></span> <span data-ttu-id="3a975-142">Falls Sie Nachrichten nur an einen bestimmten Endpunkt weiterleiten müssen, sollten Sie nach Daten filtern, die den Zielendpunkt eindeutig identifizieren, an den die Nachricht weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="3a975-142">If you must uniquely route messages to one specific endpoint, you should filter upon data that uniquely identifies the destination endpoint that the message is routed to.</span></span>

<span data-ttu-id="3a975-143">Der Routing Dienst stellt mehrere **MessageFilter** -Implementierungen bereit, die bestimmte Werte innerhalb der Nachricht überprüfen, z. b. Adresse, Aktion, Endpunkt Name oder sogar eine XPath-Abfrage.</span><span class="sxs-lookup"><span data-stu-id="3a975-143">The Routing Service provides several **MessageFilter** implementations that inspect specific values within the message, such as the address, action, endpoint name, or even an XPath query.</span></span> <span data-ttu-id="3a975-144">Wenn keine dieser Implementierungen Ihren Anforderungen entspricht, können Sie eine benutzerdefinierte **MessageFilter** -Implementierung erstellen.</span><span class="sxs-lookup"><span data-stu-id="3a975-144">If none of these implementations meet your needs you can create a custom **MessageFilter** implementation.</span></span> <span data-ttu-id="3a975-145">Weitere Informationen zu Nachrichten filtern und einen Vergleich der vom Routing Dienst verwendeten Implementierungen finden Sie unter [Nachrichtenfilter](message-filters.md) und [Auswählen eines Filters](choosing-a-filter.md).</span><span class="sxs-lookup"><span data-stu-id="3a975-145">For more information about message filters and a comparison of the implementations used by the Routing Service, see [Message Filters](message-filters.md) and [Choosing a Filter](choosing-a-filter.md).</span></span>

<span data-ttu-id="3a975-146">Mehrere Nachrichtenfilter sind in Filter Tabellen organisiert, die jeden **MessageFilter** einem Ziel Endpunkt zuordnen.</span><span class="sxs-lookup"><span data-stu-id="3a975-146">Multiple message filters are organized together into filter tables, which associate each **MessageFilter** with a destination endpoint.</span></span> <span data-ttu-id="3a975-147">Optional kann die Filtertabelle auch verwendet werden, um auch eine Liste mit Sicherungsendpunkten anzugeben. Der Routingdienst versucht dann, die Nachricht bei einem Übertragungsfehler an diese Endpunkte zu senden.</span><span class="sxs-lookup"><span data-stu-id="3a975-147">Optionally, the filter table can also be used to specify a list of back-up endpoints that the Routing Service will attempt to send the message to in the event of a transmission failure.</span></span>

<span data-ttu-id="3a975-148">Standardmäßig werden alle Nachrichtenfilter einer Filtertabelle gleichzeitig ausgewertet. Sie können jedoch eine <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A>-Eigenschaft angeben, die bewirkt, dass die Nachrichtenfilter in einer bestimmten Reihenfolge ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="3a975-148">By default all message filters within a filter table are evaluated simultaneously; however, you can specify a <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A> that causes the message filters to be evaluated in a specific order.</span></span> <span data-ttu-id="3a975-149">Alle Einträge mit der höchsten Priorität werden zuerst ausgewertet, und Nachrichtenfilter mit niedrigeren Prioritäten werden nicht ausgewertet, wenn eine Übereinstimmung mit einer höheren Prioritätsstufe gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="3a975-149">All entries with the highest priority are evaluated first, and message filters of lower priorities are not evaluated if a match is found at a higher priority level.</span></span> <span data-ttu-id="3a975-150">Weitere Informationen zu Filter Tabellen finden Sie unter [Nachrichtenfilter](message-filters.md).</span><span class="sxs-lookup"><span data-stu-id="3a975-150">For more information about filter tables, see [Message Filters](message-filters.md).</span></span>

<span data-ttu-id="3a975-151">In den folgenden Beispielen wird das <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>-Objekt verwendet, das für alle Nachrichten `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="3a975-151">The following examples use the <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>, which evaluates to `true` for all messages.</span></span> <span data-ttu-id="3a975-152">Dieser **MessageFilter** wird der Filter Tabelle "routingTable1" hinzugefügt, die den **MessageFilter** dem Client Endpunkt mit dem Namen "CalculatorService" zuordnet.</span><span class="sxs-lookup"><span data-stu-id="3a975-152">This **MessageFilter** is added to the "routingTable1" filter table, which associates the **MessageFilter** with the client endpoint named "CalculatorService".</span></span> <span data-ttu-id="3a975-153">Das **RoutingBehavior** gibt dann an, dass diese Tabelle zum Weiterleiten von Nachrichten verwendet werden soll, die vom Dienst Endpunkt verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="3a975-153">The **RoutingBehavior** then specifies that this table should be used to route messages processed by the service endpoint.</span></span>

```xml
<behaviors>
  <serviceBehaviors>
    <behavior name="routingData">
      <serviceMetadata httpGetEnabled="True"/>
      <!-- Add the RoutingBehavior and specify the Routing Table to use -->
      <routing filterTableName="routingTable1" />
    </behavior>
  </serviceBehaviors>
</behaviors>
<!--ROUTING SECTION -->
<routing>
  <filters>
    <filter name="MatchAllFilter1" filterType="MatchAll" />
  </filters>
  <filterTables>
    <table name="routingTable1">
      <filters>
        <add filterName="MatchAllFilter1" endpointName="CalculatorService" />
      </filters>
    </table>
  </filterTables>
</routing>
```

```csharp
//create a new routing configuration object
RoutingConfiguration rc = new RoutingConfiguration();
//create the endpoint list that contains the endpoints to route to
//in this case we have only one
List<ServiceEndpoint> endpointList = new List<ServiceEndpoint>();
endpointList.Add(client);
//add a MatchAll filter to the Router's filter table
//map it to the endpoint list defined earlier
//when a message matches this filter, it is sent to the endpoint contained in the list
rc.FilterTable.Add(new MatchAllMessageFilter(), endpointList);
```

> [!NOTE]
> <span data-ttu-id="3a975-154">Standardmäßig wertet der Routingdienst nur die Header der Nachricht aus.</span><span class="sxs-lookup"><span data-stu-id="3a975-154">By default, the Routing Service only evaluates the headers of the message.</span></span> <span data-ttu-id="3a975-155">Um den Filtern den Zugriff auf den Text der Nachricht zu ermöglichen, müssen Sie <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> auf `false` festlegen.</span><span class="sxs-lookup"><span data-stu-id="3a975-155">To allow the filters to access the message body, you must set <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> to `false`.</span></span>

<span data-ttu-id="3a975-156">**Multicast**</span><span class="sxs-lookup"><span data-stu-id="3a975-156">**Multicast**</span></span>

<span data-ttu-id="3a975-157">Viele Routingdienstkonfigurationen verwenden zwar eine exklusive Filterlogik, die Nachrichten an nur einen bestimmten Endpunkt weiterleitet, aber es kann erforderlich sein, dass Sie eine bestimmte Nachricht an mehrere Zielendpunkte weiterleiten müssen.</span><span class="sxs-lookup"><span data-stu-id="3a975-157">While many Routing Service configurations use exclusive filter logic that routes messages to only one specific endpoint, you may need to route a given message to multiple destination endpoints.</span></span> <span data-ttu-id="3a975-158">Um für eine Nachricht per Multicast an mehrere Ziele zu senden, müssen die folgenden Bedingungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="3a975-158">To multicast a message to multiple destinations, the following conditions must be true:</span></span>

- <span data-ttu-id="3a975-159">Die Kanalform darf nicht vom Typ "Anforderung-Antwort" sein (unidirektional oder duplex ist jedoch möglich), weil die Clientanwendung als Antwort auf die Anforderung nur eine Antwort empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="3a975-159">The channel shape must not be request-reply (though may be one-way or duplex,) because only one reply can be received by the client application in response to the request.</span></span>

- <span data-ttu-id="3a975-160">Mehrere Filter müssen beim Auswerten der Nachricht `true` zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="3a975-160">Multiple filters must return `true` when evaluating the message.</span></span>

<span data-ttu-id="3a975-161">Falls diese Bedingungen erfüllt sind, wird die Nachricht an alle Endpunkte aller Filter weitergeleitet, für die die Auswertung `true` ergibt.</span><span class="sxs-lookup"><span data-stu-id="3a975-161">If these conditions are met, the message is routed to all endpoints of all filters that evaluate to `true`.</span></span> <span data-ttu-id="3a975-162">Im folgenden Beispiel wird eine Routing Konfiguration definiert, die dazu führt, dass Nachrichten an beide Endpunkte weitergeleitet werden, wenn die Endpunkt Adresse in der Nachricht `http://localhost:8000/routingservice/router/rounding`ist.</span><span class="sxs-lookup"><span data-stu-id="3a975-162">The following example defines a routing configuration that results in messages being routed to both endpoints if the endpoint address in the message is `http://localhost:8000/routingservice/router/rounding`.</span></span>

```xml
<!--ROUTING SECTION -->
<routing>
  <filters>
    <filter name="MatchAllFilter1" filterType="MatchAll" />
    <filter name="RoundingFilter1" filterType="EndpointAddress"
            filterData="http://localhost:8000/routingservice/router/rounding" />
  </filters>
  <filterTables>
    <table name="routingTable1">
      <filters>
        <add filterName="MatchAllFilter1" endpointName="CalculatorService" />
        <add filterName="RoundingFilter1" endpointName="RoundingCalcService" />
      </filters>
    </table>
  </filterTables>
</routing>
```

```csharp
rc.FilterTable.Add(new MatchAllMessageFilter(), calculatorEndpointList);
rc.FilterTable.Add(new EndpointAddressMessageFilter(new EndpointAddress(
    "http://localhost:8000/routingservice/router/rounding")),
    roundingCalcEndpointList);
```

### <a name="soap-processing"></a><span data-ttu-id="3a975-163">SOAP-Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="3a975-163">SOAP Processing</span></span>

<span data-ttu-id="3a975-164">Um das Routing von Nachrichten zwischen unterschiedlichen Protokollen zu unterstützen, fügt das **RoutingBehavior** standardmäßig den <xref:System.ServiceModel.Routing.SoapProcessingBehavior> allen Client Endpunkten hinzu, an die Nachrichten weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="3a975-164">To support the routing of messages between dissimilar protocols, the **RoutingBehavior** by default adds the <xref:System.ServiceModel.Routing.SoapProcessingBehavior> to all client endpoint(s) that messages are routed to.</span></span> <span data-ttu-id="3a975-165">Dieses Verhalten erstellt automatisch eine neue **MessageVersion** , bevor die Nachricht an den Endpunkt weitergegeben wird, und erstellt eine kompatible **MessageVersion** für jedes Antwortdokument, bevor es an die anfordernde Client Anwendung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3a975-165">This behavior automatically creates a new **MessageVersion** before routing the message to the endpoint, as well as creating a compatible **MessageVersion** for any response document before returning it to the requesting client application.</span></span>

<span data-ttu-id="3a975-166">Die Schritte zum Erstellen einer neuen **MessageVersion** für die ausgehende Nachricht lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3a975-166">The steps taken to create a new **MessageVersion** for the outbound message are as follows:</span></span>

<span data-ttu-id="3a975-167">**Anforderungs Verarbeitung**</span><span class="sxs-lookup"><span data-stu-id="3a975-167">**Request processing**</span></span>

- <span data-ttu-id="3a975-168">Holen Sie sich die **MessageVersion** der ausgehenden Bindung/des Kanals.</span><span class="sxs-lookup"><span data-stu-id="3a975-168">Get the **MessageVersion** of the outbound binding/channel.</span></span>

- <span data-ttu-id="3a975-169">Rufen Sie den Textreader für die ursprüngliche Nachricht ab.</span><span class="sxs-lookup"><span data-stu-id="3a975-169">Get the body reader for the original message.</span></span>

- <span data-ttu-id="3a975-170">Erstellen Sie eine neue Nachricht mit der gleichen Aktion, dem Text Reader und einer neuen **MessageVersion**.</span><span class="sxs-lookup"><span data-stu-id="3a975-170">Create a new message with the same action, body reader, and a new **MessageVersion**.</span></span>

- <span data-ttu-id="3a975-171">Wenn <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>! = **Adressierung. None**, kopieren Sie die Header in, from, FaultTo und RelatesTo in die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3a975-171">If <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> != **Addressing.None**, copy the To, From, FaultTo, and RelatesTo headers to the new message.</span></span>

- <span data-ttu-id="3a975-172">Kopieren Sie alle Eigenschaften der Nachricht in die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3a975-172">Copy all message properties to the new message.</span></span>

- <span data-ttu-id="3a975-173">Speichern Sie die ursprüngliche Anforderungsnachricht, die zum Verarbeiten der Antwort verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a975-173">Store the original request message to use when processing the response.</span></span>

- <span data-ttu-id="3a975-174">Geben Sie die neue Anforderungsnachricht zurück.</span><span class="sxs-lookup"><span data-stu-id="3a975-174">Return the new request message.</span></span>

<span data-ttu-id="3a975-175">**Antwort Verarbeitung**</span><span class="sxs-lookup"><span data-stu-id="3a975-175">**Response processing**</span></span>

- <span data-ttu-id="3a975-176">Holen Sie sich die **MessageVersion** der ursprünglichen Anforderungs Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3a975-176">Get the **MessageVersion** of the original request message.</span></span>

- <span data-ttu-id="3a975-177">Rufen Sie den Textreader für die empfangene Antwortnachricht ab.</span><span class="sxs-lookup"><span data-stu-id="3a975-177">Get the body reader for the received response message.</span></span>

- <span data-ttu-id="3a975-178">Erstellen Sie eine neue Antwortnachricht mit der gleichen Aktion, dem Text Reader und der **MessageVersion** der ursprünglichen Anforderungs Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3a975-178">Create a new response message with the same action, body reader, and the **MessageVersion** of the original request message.</span></span>

- <span data-ttu-id="3a975-179">Wenn <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>! = **Adressierung. None**, kopieren Sie die Header in, from, FaultTo und RelatesTo in die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3a975-179">If <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A> != **Addressing.None**, copy the To, From, FaultTo, and RelatesTo headers to the new message.</span></span>

- <span data-ttu-id="3a975-180">Kopieren Sie die Eigenschaften der Nachricht in die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3a975-180">Copy the message properties to the new message.</span></span>

- <span data-ttu-id="3a975-181">Geben Sie die neue Antwortnachricht zurück.</span><span class="sxs-lookup"><span data-stu-id="3a975-181">Return the new response message.</span></span>

<span data-ttu-id="3a975-182">Standardmäßig wird das **soapprocessingbehavior** automatisch den Client Endpunkten von der <xref:System.ServiceModel.Routing.RoutingBehavior> hinzugefügt, wenn der Dienst gestartet wird. Sie können jedoch steuern, ob die SOAP-Verarbeitung allen Client Endpunkten mithilfe der <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A>-Eigenschaft hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3a975-182">By default, the **SoapProcessingBehavior** is automatically added to the client endpoints by the <xref:System.ServiceModel.Routing.RoutingBehavior> when the service starts; however, you can control whether SOAP processing is added to all client endpoints by using the <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A> property.</span></span> <span data-ttu-id="3a975-183">Sie können das Verhalten auch direkt einem bestimmten Endpunkt hinzufügen und es auf Endpunktebene aktivieren oder deaktivieren, falls eine präzisere Steuerung der SOAP-Verarbeitung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3a975-183">You can also add the behavior directly to a specific endpoint and enable or disable this behavior at the endpoint level if a more granular control of SOAP processing is required.</span></span>

> [!NOTE]
> <span data-ttu-id="3a975-184">Wenn die SOAP-Verarbeitung für einen Endpunkt deaktiviert ist, der eine andere MessageVersion als die der ursprünglichen Anforderungsnachricht erfordert, müssen Sie einen benutzerdefinierten Mechanismus zum Ausführen aller SOAP-Änderungen bereitstellen, die vor dem Senden der Nachricht an den Zielendpunkt erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="3a975-184">If SOAP processing is disabled for an endpoint that requires a different MessageVersion than that of the original request message, you must provide a custom mechanism for performing any SOAP modifications that are required before sending the message to the destination endpoint.</span></span>

<span data-ttu-id="3a975-185">In den folgenden Beispielen wird die **soapprocessingenabled** -Eigenschaft verwendet, um zu verhindern, dass **soapprocessingbehavior** automatisch allen Client Endpunkten hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="3a975-185">In the following examples, the **soapProcessingEnabled** property is used to prevent the **SoapProcessingBehavior** from being automatically added to all client endpoints.</span></span>

```xml
<behaviors>
  <!--default routing service behavior definition-->
  <serviceBehaviors>
    <behavior name="routingConfiguration">
      <routing filterTableName="filterTable1" soapProcessingEnabled="false"/>
    </behavior>
  </serviceBehaviors>
</behaviors>
```

```csharp
//create the default RoutingConfiguration
RoutingConfiguration rc = new RoutingConfiguration();
rc.SoapProcessingEnabled = false;
```

### <a name="dynamic-configuration"></a><span data-ttu-id="3a975-186">Dynamische Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3a975-186">Dynamic Configuration</span></span>

<span data-ttu-id="3a975-187">Wenn Sie zusätzliche Clientendpunkte hinzufügen oder die Filter zum Weiterleiten von Nachrichten ändern, müssen Sie eine Möglichkeit schaffen, die Konfiguration zur Laufzeit dynamisch zu aktualisieren. Auf diese Weise verhindern Sie die Unterbrechung des Diensts zu den Endpunkten, die momentan Nachrichten über den Routingdienst empfangen.</span><span class="sxs-lookup"><span data-stu-id="3a975-187">When you add additional client endpoints, or need to modify the filters that are used to route messages, you must have a way to update the configuration dynamically at run time to prevent interrupting the service to the endpoints currently receiving messages through the Routing Service.</span></span> <span data-ttu-id="3a975-188">Das Ändern einer Konfigurationsdatei oder des Codes der Hostanwendung ist nicht immer ausreichend, weil bei beiden Verfahren die Wiederverwendung der Anwendung erforderlich ist. Dies kann zum Verlust aller Nachrichten führen, die gerade übertragen werden, und es kann beim Warten auf den Neustart des Diensts zu einer Ausfallzeit kommen.</span><span class="sxs-lookup"><span data-stu-id="3a975-188">Modifying a configuration file or the code of the host application is not always sufficient, because either method requires recycling the application, which would lead to the potential loss of any messages currently in transit and the potential for downtime while waiting on the service to restart.</span></span>

<span data-ttu-id="3a975-189">Sie können **RoutingConfiguration** nur Programm gesteuert ändern.</span><span class="sxs-lookup"><span data-stu-id="3a975-189">You can only modify the **RoutingConfiguration** programmatically.</span></span> <span data-ttu-id="3a975-190">Obwohl Sie den Dienst anfänglich mithilfe einer Konfigurationsdatei konfigurieren können, können Sie die Konfiguration nur zur Laufzeit ändern, indem Sie eine neue **RoutingConfiguration** erstellen und Sie als Parameter an die <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> Methode übergeben, die von der <xref:System.ServiceModel.Routing.RoutingExtension> Dienst Erweiterung verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="3a975-190">While you can initially configure the service by using a configuration file, you can only modify the configuration at run time by constructing a new **RoutingConfiguration** and passing it as a parameter to the <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> method exposed by the <xref:System.ServiceModel.Routing.RoutingExtension> service extension.</span></span> <span data-ttu-id="3a975-191">Alle Nachrichten, die zurzeit übertragen werden, werden weiterhin mithilfe der vorherigen Konfiguration weitergeleitet, während Nachrichten, die nach dem aufzurufen von **ApplyConfiguration** empfangen werden, die neue Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3a975-191">Any messages currently in transit continue to be routed using the previous configuration, while messages received after the call to **ApplyConfiguration** use the new configuration.</span></span> <span data-ttu-id="3a975-192">Im folgenden Beispiel wird das Erstellen einer Instanz des Routingdiensts und anschließend das Ändern der Konfiguration veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3a975-192">The following example demonstrates creating an instance of the Routing Service and then subsequently modifying the configuration.</span></span>

```csharp
RoutingConfiguration routingConfig = new RoutingConfiguration();
routingConfig.RouteOnHeadersOnly = true;
routingConfig.FilterTable.Add(new MatchAllMessageFilter(), endpointList);
RoutingBehavior routing = new RoutingBehavior(routingConfig);
routerHost.Description.Behaviors.Add(routing);
routerHost.Open();
// Construct a new RoutingConfiguration
RoutingConfiguration rc2 = new RoutingConfiguration();
ServiceEndpoint clientEndpoint = new ServiceEndpoint();
ServiceEndpoint clientEndpoint2 = new ServiceEndpoint();
// Add filters to the FilterTable in the new configuration
rc2.FilterTable.add(new MatchAllMessageFilter(),
       new List<ServiceEndpoint>() { clientEndpoint });
rc2.FilterTable.add(new MatchAllMessageFilter(),
       new List<ServiceEndpoint>() { clientEndpoint2 });
rc2.RouteOnHeadersOnly = false;
// Apply the new configuration to the Routing Service hosted in
routerHost.routerHost.Extensions.Find<RoutingExtension>().ApplyConfiguration(rc2);
```

> [!NOTE]
> <span data-ttu-id="3a975-193">Beim Aktualisieren des Routingdiensts auf diese Weise ist es nur möglich, eine neue Konfiguration zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="3a975-193">When updating the Routing Service in this manner it is only possible to pass a new configuration.</span></span> <span data-ttu-id="3a975-194">Es ist nicht möglich, nur bestimmte Elemente der aktuellen Konfiguration zu ändern oder neue Einträge an die aktuelle Konfiguration anzufügen. Sie müssen eine neue Konfiguration erstellen und übergeben, die die vorhandene Konfiguration ersetzt.</span><span class="sxs-lookup"><span data-stu-id="3a975-194">It is not possible to modify only select elements of the current configuration or append new entries to the current configuration; you must create and pass a new configuration that replaces the existing one.</span></span>

> [!NOTE]
> <span data-ttu-id="3a975-195">Alle Sitzungen, die mit der vorherigen Konfiguration geöffnet wurden, verwenden weiterhin die vorherige Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="3a975-195">Any sessions opened using the previous configuration continue using the previous configuration.</span></span> <span data-ttu-id="3a975-196">Die neue Konfiguration wird nur von neuen Sitzungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a975-196">The new configuration is only used by new sessions.</span></span>

## <a name="error-handling"></a><span data-ttu-id="3a975-197">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="3a975-197">Error Handling</span></span>

<span data-ttu-id="3a975-198">Wenn beim versuchten Senden einer Nachricht eine <xref:System.ServiceModel.CommunicationException> auftritt, wird die Fehlerbehandlung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a975-198">If any <xref:System.ServiceModel.CommunicationException> is encountered while attempting to send a message, error handling take place.</span></span> <span data-ttu-id="3a975-199">Diese Ausnahmen weisen in der Regel darauf hin, dass beim Versuch der Kommunikation mit dem definierten Clientendpunkt ein Problem aufgetreten ist, z. B. <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> oder <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span><span class="sxs-lookup"><span data-stu-id="3a975-199">These exceptions typically indicate that a problem was encountered while attempting to communicate with the defined client endpoint, such as an <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException>, or <xref:System.ServiceModel.CommunicationObjectFaultedException>.</span></span> <span data-ttu-id="3a975-200">Der Fehler Behandlungs Code fängt auch auf und versucht, den Sendevorgang zu wiederholen, wenn ein <xref:System.TimeoutException> auftritt. Dies ist eine andere häufige Ausnahme, die nicht von **CommunicationException**abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="3a975-200">The error handling-code will also catch and attempt to retry sending when a <xref:System.TimeoutException> occurs, which is another common exception that is not derived from **CommunicationException**.</span></span>

<span data-ttu-id="3a975-201">Wenn eine der vorangehenden Ausnahmen auftritt, führt der Routingdienst ein Failover zu einer Liste von Sicherungsendpunkten aus.</span><span class="sxs-lookup"><span data-stu-id="3a975-201">When one of the preceding exceptions occurs, the Routing Service fails over to a list of backup endpoints.</span></span> <span data-ttu-id="3a975-202">Falls für alle Sicherungsendpunkte ein Kommunikationsfehler auftritt oder falls ein Endpunkt eine Ausnahme zurückgibt, die einen Fehler beim Zieldienst angibt, gibt der Routingdienst einen Fehler an die Clientanwendung zurück.</span><span class="sxs-lookup"><span data-stu-id="3a975-202">If all backup endpoints fail with a communications failure, or if an endpoint returns an exception that indicates a failure within the destination service, the Routing Service returns a fault to the client application.</span></span>

> [!NOTE]
> <span data-ttu-id="3a975-203">Die Fehlerbehandlungsfunktion erfasst und behandelt Ausnahmen, die beim versuchten Senden einer Nachricht oder Schließen eines Kanals auftreten.</span><span class="sxs-lookup"><span data-stu-id="3a975-203">The error-handling functionality captures and handles exceptions that occur when attempting to send a message and when attempting to close a channel.</span></span> <span data-ttu-id="3a975-204">Der Fehler Behandlungs Code dient nicht zum erkennen oder behandeln von Ausnahmen, die von den Anwendungs Endpunkten erstellt werden, mit denen er kommuniziert. eine <xref:System.ServiceModel.FaultException>, die von einem Dienst ausgelöst wird, wird als **Fehlermeldung** am Routing Dienst angezeigt und an den Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3a975-204">The error-handling code is not intended to detect or handle exceptions created by the application endpoints it is communicating with; a <xref:System.ServiceModel.FaultException> thrown by a service appears at the Routing Service as a **FaultMessage** and is flowed back to the client.</span></span>
>
> <span data-ttu-id="3a975-205">Wenn beim Weiterleiten einer Nachricht durch den Routingdienst ein Fehler auftritt, erhalten Sie eventuell auf der Clientseite eine <xref:System.ServiceModel.FaultException> und keine <xref:System.ServiceModel.EndpointNotFoundException>, die Sie normalerweise bei nicht vorhandenem Routingdienst erhalten.</span><span class="sxs-lookup"><span data-stu-id="3a975-205">If an error occurs when the routing service tries to relay a message, you may  get a <xref:System.ServiceModel.FaultException> on the client side, rather than a <xref:System.ServiceModel.EndpointNotFoundException> you would normally get in the absence of the routing service.</span></span> <span data-ttu-id="3a975-206">Daher maskiert der Routingdienst möglicherweise Ausnahmen und bietet keine vollständige Transparenz, es sei denn, Sie überprüfen geschachtelte Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="3a975-206">A routing service may thus mask exceptions and not provide full transparency unless you examine nested exceptions.</span></span>

### <a name="tracing-exceptions"></a><span data-ttu-id="3a975-207">Nachverfolgen von Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="3a975-207">Tracing Exceptions</span></span>

<span data-ttu-id="3a975-208">Wenn beim Senden einer Nachricht an einen Endpunkt in einer Liste ein Fehler auftritt, verfolgt der Routing Dienst die resultierenden Ausnahme Daten und fügt die Ausnahme Details als Nachrichten Eigenschaft mit dem Namen " **Exceptions**" an.</span><span class="sxs-lookup"><span data-stu-id="3a975-208">When sending a message to an endpoint in a list fails, the Routing Service traces the resulting exception data and attaches the exception details as a message property named **Exceptions**.</span></span> <span data-ttu-id="3a975-209">Dabei werden die Ausnahmedaten beibehalten, und Benutzern wird der programmgesteuerte Zugriff über einen Nachrichteninspektor ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="3a975-209">This preserves the exception data and allows a user programmatic access through a message inspector.</span></span>  <span data-ttu-id="3a975-210">Die Ausnahmedaten werden pro Nachricht in einem Wörterbuch gespeichert. Das Wörterbuch ordnet den Endpunktnamen den Ausnahmedetails zu, die beim versuchten Senden einer Nachricht an diesen Endpunkt auftreten.</span><span class="sxs-lookup"><span data-stu-id="3a975-210">The exception data is stored per message in a dictionary that maps the endpoint name to the exception details encountered when trying to send a message to it.</span></span>

### <a name="backup-endpoints"></a><span data-ttu-id="3a975-211">Sicherungsendpunkte</span><span class="sxs-lookup"><span data-stu-id="3a975-211">Backup Endpoints</span></span>

<span data-ttu-id="3a975-212">Jeder Filtereintrag innerhalb der Filtertabelle kann optional eine Liste mit Sicherungsendpunkten angeben, die verwendet werden, wenn beim Senden an den primären Endpunkt ein Übertragungsfehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="3a975-212">Each filter entry within the filter table can optionally specify a list of backup endpoints, which are used in the event of a transmission failure when sending to the primary endpoint.</span></span> <span data-ttu-id="3a975-213">Bei einem Fehler dieser Art versucht der Routingdienst, die Nachricht an den ersten Eintrag der Liste mit den Sicherungsendpunkten zu senden.</span><span class="sxs-lookup"><span data-stu-id="3a975-213">If such a failure occurs, the Routing Service attempts to transmit the message to the first entry in the backup endpoint list.</span></span> <span data-ttu-id="3a975-214">Falls bei diesem Sendeversuch ebenfalls ein Übertragungsfehler auftritt, wird der nächste Endpunkt in der Liste verwendet.</span><span class="sxs-lookup"><span data-stu-id="3a975-214">If this send attempt also encounters a transmission failure, the next endpoint in the backup list is tried.</span></span> <span data-ttu-id="3a975-215">Der Routingdienst sendet die Nachricht an jeden Endpunkt in der Liste, bis die Nachricht erfolgreich empfangen wurde, alle Endpunkte einen Übertragungsfehler zurückgeben oder ein Endpunkt einen anderen Fehler als einen Übertragungsfehler zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3a975-215">The Routing Service continues sending the message to each endpoint in the list until the message is successfully received, all endpoints return a transmission failure, or a non-transmission failure is returned by an endpoint.</span></span>

<span data-ttu-id="3a975-216">In den folgenden Beispielen wird der Routingdienst für die Verwendung einer Sicherungsliste konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="3a975-216">The following examples configure the Routing Service to use a backup list.</span></span>

```xml
<routing>
  <filters>
    <!-- Create a MatchAll filter that catches all messages -->
    <filter name="MatchAllFilter1" filterType="MatchAll" />
  </filters>
  <filterTables>
    <!-- Set up the Routing Service's Message Filter Table -->
    <filterTable name="filterTable1">
        <!-- Add an entry that maps the MatchAllMessageFilter to the dead destination -->
        <!-- If that endpoint is down, tell the Routing Service to try the endpoints -->
        <!-- Listed in the backupEndpointList -->
        <add filterName="MatchAllFilter1" endpointName="deadDestination" backupList="backupEndpointList"/>
    </filterTable>
  </filterTables>
  <!-- Create the backup endpoint list -->
  <backupLists>
    <!-- Add an endpoint list that contains the backup destinations -->
    <backupList name="backupEndpointList">
      <add endpointName="realDestination" />
      <add endpointName="backupDestination" />
    </backupList>
  </backupLists>
</routing>
```

```csharp
//create the endpoint list that contains the service endpoints we want to route to
List<ServiceEndpoint> backupList = new List<ServiceEndpoint>();
//add the endpoints in the order that the Routing Service should contact them
//first add the endpoint that we know is down
//clearly, normally you wouldn't know that this endpoint was down by default
backupList.Add(fakeDestination);
//then add the real Destination endpoint
//the Routing Service attempts to send to this endpoint only if it
//encounters a TimeOutException or CommunicationException when sending
//to the previous endpoint in the list.
backupList.Add(realDestination);
//add the backupDestination endpoint
//the Routing Service attempts to send to this endpoint only if it
//encounters a TimeOutException or CommunicationsException when sending
//to the previous endpoints in the list
backupList.Add(backupDestination);
//create the default RoutingConfiguration option
RoutingConfiguration rc = new RoutingConfiguration();
//add a MatchAll filter to the Routing Configuration's filter table
//map it to the list of endpoints defined above
//when a message matches this filter, it is sent to the endpoints in the list in order
//if an endpoint is down or does not respond (which the first endpoint won't
//since the client does not exist), the Routing Service automatically moves the message
//to the next endpoint in the list and try again.
rc.FilterTable.Add(new MatchAllMessageFilter(), backupList);
```

### <a name="supported-error-patterns"></a><span data-ttu-id="3a975-217">Unterstützte Fehlermuster</span><span class="sxs-lookup"><span data-stu-id="3a975-217">Supported Error Patterns</span></span>

<span data-ttu-id="3a975-218">In der folgenden Tabelle werden die Muster beschrieben, die mit der Verwendung von Sicherungsendpunktlisten kompatibel sind. Außerdem enthält die Tabelle Hinweise zu den Details der Fehlerbehandlung für bestimmte Muster.</span><span class="sxs-lookup"><span data-stu-id="3a975-218">The following table describes the patterns that are compatible with the use of backup endpoint lists, along with notes describing the details of error handling for specific patterns.</span></span>

|<span data-ttu-id="3a975-219">Muster</span><span class="sxs-lookup"><span data-stu-id="3a975-219">Pattern</span></span>|<span data-ttu-id="3a975-220">Sitzung</span><span class="sxs-lookup"><span data-stu-id="3a975-220">Session</span></span>|<span data-ttu-id="3a975-221">Transaktion</span><span class="sxs-lookup"><span data-stu-id="3a975-221">Transaction</span></span>|<span data-ttu-id="3a975-222">Empfangskontext</span><span class="sxs-lookup"><span data-stu-id="3a975-222">Receive Context</span></span>|<span data-ttu-id="3a975-223">Unterstützte Sicherungsliste</span><span class="sxs-lookup"><span data-stu-id="3a975-223">Backup List Supported</span></span>|<span data-ttu-id="3a975-224">Notizen</span><span class="sxs-lookup"><span data-stu-id="3a975-224">Notes</span></span>|
|-------------|-------------|-----------------|---------------------|---------------------------|-----------|
|<span data-ttu-id="3a975-225">Unidirektional</span><span class="sxs-lookup"><span data-stu-id="3a975-225">One-Way</span></span>||||<span data-ttu-id="3a975-226">Ja</span><span class="sxs-lookup"><span data-stu-id="3a975-226">Yes</span></span>|<span data-ttu-id="3a975-227">Versucht, die Nachricht erneut an einen Sicherungsendpunkt zu senden.</span><span class="sxs-lookup"><span data-stu-id="3a975-227">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="3a975-228">Falls für diese Nachricht ein Multicast ausgeführt wird, wird nur die Nachricht im Kanal mit dem Fehler an das entsprechende Sicherungsziel verschoben.</span><span class="sxs-lookup"><span data-stu-id="3a975-228">If this message is being multicast, only the message on the failed channel is moved to its backup destination.</span></span>|
|<span data-ttu-id="3a975-229">Unidirektional</span><span class="sxs-lookup"><span data-stu-id="3a975-229">One-Way</span></span>||<span data-ttu-id="3a975-230">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-230">✔️</span></span>||<span data-ttu-id="3a975-231">Nein</span><span class="sxs-lookup"><span data-stu-id="3a975-231">No</span></span>|<span data-ttu-id="3a975-232">Eine Ausnahme wird ausgelöst, und für die Transaktion wird ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a975-232">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="3a975-233">Unidirektional</span><span class="sxs-lookup"><span data-stu-id="3a975-233">One-Way</span></span>|||<span data-ttu-id="3a975-234">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-234">✔️</span></span>|<span data-ttu-id="3a975-235">Ja</span><span class="sxs-lookup"><span data-stu-id="3a975-235">Yes</span></span>|<span data-ttu-id="3a975-236">Versucht, die Nachricht erneut an einen Sicherungsendpunkt zu senden.</span><span class="sxs-lookup"><span data-stu-id="3a975-236">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="3a975-237">Nachdem die Nachricht erfolgreich empfangen wurde, werden alle Empfangskontexte abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3a975-237">After the message is successfully received, complete all receive contexts.</span></span> <span data-ttu-id="3a975-238">Falls die Nachricht von keinem Endpunkt erfolgreich empfangen wurde, wird der Empfangskontext nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3a975-238">If the message is not successfully received by any endpoint, do not complete the receive context.</span></span><br /><br /> <span data-ttu-id="3a975-239">Wenn für diese Nachricht ein Multicast ausgeführt wird, wird der Empfangskontext nur abgeschlossen, falls die Nachricht von mindestens einem Endpunkt (primär oder Sicherung) erfolgreich empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="3a975-239">When this message is being multicast, the receive context is only completed if the message is successfully received by at least one endpoint (primary or backup).</span></span> <span data-ttu-id="3a975-240">Schließen Sie den Empfangskontext nicht ab, falls der Empfang der Nachricht für keinen Endpunkt in den Multicastpfaden erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="3a975-240">If none of the endpoints in any of the multicast paths successfully receive the message, do not complete the receive context.</span></span>|
|<span data-ttu-id="3a975-241">Unidirektional</span><span class="sxs-lookup"><span data-stu-id="3a975-241">One-Way</span></span>||<span data-ttu-id="3a975-242">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-242">✔️</span></span>|<span data-ttu-id="3a975-243">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-243">✔️</span></span>|<span data-ttu-id="3a975-244">Ja</span><span class="sxs-lookup"><span data-stu-id="3a975-244">Yes</span></span>|<span data-ttu-id="3a975-245">Brechen Sie die vorherige Transaktion ab, erstellen Sie eine neue Transaktion, und senden Sie alle Nachrichten neu.</span><span class="sxs-lookup"><span data-stu-id="3a975-245">Abort the previous transaction, create a new transaction, and resend all messages.</span></span> <span data-ttu-id="3a975-246">Nachrichten, für die ein Fehler aufgetreten ist, werden an ein Sicherungsziel übertragen.</span><span class="sxs-lookup"><span data-stu-id="3a975-246">Messages that encountered an error are transmitted to a backup destination.</span></span><br /><br /> <span data-ttu-id="3a975-247">Nachdem eine Transaktion erstellt wurde, für die alle Übertragungen erfolgreich sind, schließen Sie die Empfangskontexte ab und führen für die Transaktion einen Commit aus.</span><span class="sxs-lookup"><span data-stu-id="3a975-247">After a transaction has been created in which all transmissions succeed, complete the receive contexts and commit the transaction.</span></span>|
|<span data-ttu-id="3a975-248">Unidirektional</span><span class="sxs-lookup"><span data-stu-id="3a975-248">One-Way</span></span>|<span data-ttu-id="3a975-249">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-249">✔️</span></span>|||<span data-ttu-id="3a975-250">Ja</span><span class="sxs-lookup"><span data-stu-id="3a975-250">Yes</span></span>|<span data-ttu-id="3a975-251">Versucht, die Nachricht erneut an einen Sicherungsendpunkt zu senden.</span><span class="sxs-lookup"><span data-stu-id="3a975-251">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="3a975-252">In einem Multicastszenario werden nur die Nachrichten einer Sitzung, für die ein Fehler aufgetreten ist oder bei der beim Schließen der Sitzung ein Fehler aufgetreten ist, zurück an die Sicherungsziele gesendet.</span><span class="sxs-lookup"><span data-stu-id="3a975-252">In a multicast scenario only the messages in a session that encountered an error or in a session whose session close failed are resent to backup destinations.</span></span>|
|<span data-ttu-id="3a975-253">Unidirektional</span><span class="sxs-lookup"><span data-stu-id="3a975-253">One-Way</span></span>|<span data-ttu-id="3a975-254">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-254">✔️</span></span>|<span data-ttu-id="3a975-255">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-255">✔️</span></span>||<span data-ttu-id="3a975-256">Nein</span><span class="sxs-lookup"><span data-stu-id="3a975-256">No</span></span>|<span data-ttu-id="3a975-257">Eine Ausnahme wird ausgelöst, und für die Transaktion wird ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a975-257">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="3a975-258">Unidirektional</span><span class="sxs-lookup"><span data-stu-id="3a975-258">One-Way</span></span>|<span data-ttu-id="3a975-259">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-259">✔️</span></span>||<span data-ttu-id="3a975-260">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-260">✔️</span></span>|<span data-ttu-id="3a975-261">Ja</span><span class="sxs-lookup"><span data-stu-id="3a975-261">Yes</span></span>|<span data-ttu-id="3a975-262">Versucht, die Nachricht erneut an einen Sicherungsendpunkt zu senden.</span><span class="sxs-lookup"><span data-stu-id="3a975-262">Attempts to resend the message on a backup endpoint.</span></span> <span data-ttu-id="3a975-263">Nachdem das Senden für alle Nachrichten erfolgreich abgeschlossen wurde, zeigt die Sitzung keine Nachrichten mehr an, und der Routingdienst schließt alle ausgehenden Sitzungskanäle. Außerdem werden alle Empfangskontexte abgeschlossen und der eingehende Sitzungskanal geschlossen.</span><span class="sxs-lookup"><span data-stu-id="3a975-263">After all message sends complete without error, the session indicates no more messages and the Routing Service successfully closes all outbound session channel(s), all receive contexts are completed, and the inbound session channel is closed.</span></span>|
|<span data-ttu-id="3a975-264">Unidirektional</span><span class="sxs-lookup"><span data-stu-id="3a975-264">One-Way</span></span>|<span data-ttu-id="3a975-265">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-265">✔️</span></span>|<span data-ttu-id="3a975-266">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-266">✔️</span></span>|<span data-ttu-id="3a975-267">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-267">✔️</span></span>|<span data-ttu-id="3a975-268">Ja</span><span class="sxs-lookup"><span data-stu-id="3a975-268">Yes</span></span>|<span data-ttu-id="3a975-269">Brechen Sie die aktuelle Transaktion ab, und erstellen Sie eine neue Transaktion.</span><span class="sxs-lookup"><span data-stu-id="3a975-269">Abort the current transaction and create a new one.</span></span> <span data-ttu-id="3a975-270">Senden Sie alle vorherigen Nachrichten der Sitzung neu.</span><span class="sxs-lookup"><span data-stu-id="3a975-270">Resend all previous messages in the session.</span></span> <span data-ttu-id="3a975-271">Nachdem eine Transaktion erstellt wurde, für die alle Nachrichten erfolgreich gesendet wurden, und die Sitzung keine Nachrichten mehr anzeigt, werden alle ausgehenden Sitzungskanäle geschlossen. Außerdem werden alle Empfangskontexte zusammen mit der Transaktion abgeschlossen, der eingehende Sitzungskanal wird geschlossen und für die Transaktion wird ein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a975-271">After a transaction has been created in which all messages have been successfully sent and the session indicates no more messages, all the outbound session channels are closed, receive contexts are all completed with the transaction, the inbound session channel is closed, and the transaction is committed.</span></span><br /><br /> <span data-ttu-id="3a975-272">Wenn für die Sitzungen ein Multicast durchgeführt wird, werden die Nachrichten, für die kein Fehler aufgetreten ist, wie vorher erneut zurück an das gleiche Ziel gesendet. Nachrichten, für die ein Fehler aufgetreten ist, werden an die Sicherungsziele gesendet.</span><span class="sxs-lookup"><span data-stu-id="3a975-272">When the sessions are being multicast the messages that had no error are resent to the same destination as before, and messages that encountered an error are sent to backup destinations.</span></span>|
|<span data-ttu-id="3a975-273">Bidirektional</span><span class="sxs-lookup"><span data-stu-id="3a975-273">Two-Way</span></span>||||<span data-ttu-id="3a975-274">Ja</span><span class="sxs-lookup"><span data-stu-id="3a975-274">Yes</span></span>|<span data-ttu-id="3a975-275">Das Senden erfolgt an ein Sicherungsziel.</span><span class="sxs-lookup"><span data-stu-id="3a975-275">Send to a backup destination.</span></span>  <span data-ttu-id="3a975-276">Nachdem ein Kanal eine Antwortnachricht zurückgegeben hat, wird die Antwort an den ursprünglichen Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3a975-276">After a channel returns a response message, return the response to the original client.</span></span>|
|<span data-ttu-id="3a975-277">Bidirektional</span><span class="sxs-lookup"><span data-stu-id="3a975-277">Two-Way</span></span>|<span data-ttu-id="3a975-278">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-278">✔️</span></span>|||<span data-ttu-id="3a975-279">Ja</span><span class="sxs-lookup"><span data-stu-id="3a975-279">Yes</span></span>|<span data-ttu-id="3a975-280">Alle Nachrichten im Kanal werden an ein Sicherungsziel gesendet.</span><span class="sxs-lookup"><span data-stu-id="3a975-280">Send all messages on the channel to a backup destination.</span></span>  <span data-ttu-id="3a975-281">Nachdem ein Kanal eine Antwortnachricht zurückgegeben hat, wird die Antwort an den ursprünglichen Client zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3a975-281">After a channel returns a response message, return the response to the original client.</span></span>|
|<span data-ttu-id="3a975-282">Bidirektional</span><span class="sxs-lookup"><span data-stu-id="3a975-282">Two-Way</span></span>||<span data-ttu-id="3a975-283">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-283">✔️</span></span>||<span data-ttu-id="3a975-284">Nein</span><span class="sxs-lookup"><span data-stu-id="3a975-284">No</span></span>|<span data-ttu-id="3a975-285">Eine Ausnahme wird ausgelöst, und für die Transaktion wird ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a975-285">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="3a975-286">Bidirektional</span><span class="sxs-lookup"><span data-stu-id="3a975-286">Two-Way</span></span>|<span data-ttu-id="3a975-287">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-287">✔️</span></span>|<span data-ttu-id="3a975-288">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-288">✔️</span></span>||<span data-ttu-id="3a975-289">Nein</span><span class="sxs-lookup"><span data-stu-id="3a975-289">No</span></span>|<span data-ttu-id="3a975-290">Eine Ausnahme wird ausgelöst, und für die Transaktion wird ein Rollback ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="3a975-290">An exception is thrown and the transaction is rolled back.</span></span>|
|<span data-ttu-id="3a975-291">Duplex</span><span class="sxs-lookup"><span data-stu-id="3a975-291">Duplex</span></span>||||<span data-ttu-id="3a975-292">Nein</span><span class="sxs-lookup"><span data-stu-id="3a975-292">No</span></span>|<span data-ttu-id="3a975-293">Die Duplexkommunikation außerhalb von Sitzungen wird momentan nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3a975-293">Non-session duplex communication is not currently supported.</span></span>|
|<span data-ttu-id="3a975-294">Duplex</span><span class="sxs-lookup"><span data-stu-id="3a975-294">Duplex</span></span>|<span data-ttu-id="3a975-295">✔️</span><span class="sxs-lookup"><span data-stu-id="3a975-295">✔️</span></span>|||<span data-ttu-id="3a975-296">Ja</span><span class="sxs-lookup"><span data-stu-id="3a975-296">Yes</span></span>|<span data-ttu-id="3a975-297">Das Senden erfolgt an ein Sicherungsziel.</span><span class="sxs-lookup"><span data-stu-id="3a975-297">Send to a backup destination.</span></span>|

## <a name="hosting"></a><span data-ttu-id="3a975-298">Hosting</span><span class="sxs-lookup"><span data-stu-id="3a975-298">Hosting</span></span>

<span data-ttu-id="3a975-299">Da der Routingdienst als WCF-Dienst implementiert wird, muss dieser entweder in einer Anwendung selbst oder von IIS oder WAS gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="3a975-299">Because the Routing Service is implemented as a WCF service, it must be either self-hosted within an application or hosted by IIS or WAS.</span></span> <span data-ttu-id="3a975-300">Es ist ratsam, den Routingdienst entweder unter IIS, WAS oder einer Windows-Dienstanwendung zu hosten. Sie können dann die Vorteile des automatischen Startens und die Funktionen zur Lebenszyklusverwaltung nutzen, die in diesen Hostumgebungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3a975-300">It is recommended that the Routing Service be hosted in either IIS, WAS, or a Windows Service application to take advantage of the automatic start and life-cycle management features available in these hosting environments.</span></span>

<span data-ttu-id="3a975-301">Im folgenden Beispiel wird das Hosten des Routingdiensts in einer Anwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3a975-301">The following example demonstrates hosting the Routing Service in an application.</span></span>

```csharp
using (ServiceHost serviceHost =
                new ServiceHost(typeof(RoutingService)))
```

<span data-ttu-id="3a975-302">Um den Routingdienst unter IIS oder WAS zu hosten, müssen Sie entweder eine Dienstdatei (.svc) erstellen oder eine Aktivierung des Diensts per Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a975-302">To host the Routing Service within IIS or WAS, you must either create a service file (.svc) or use configuration-based activation of the service.</span></span> <span data-ttu-id="3a975-303">Bei Verwendung einer Dienstdatei müssen Sie <xref:System.ServiceModel.Routing.RoutingService> angeben, indem Sie den Service-Parameter verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a975-303">When using a service file, you must specify the <xref:System.ServiceModel.Routing.RoutingService> using the Service parameter.</span></span> <span data-ttu-id="3a975-304">Das folgende Beispiel enthält eine Beispieldienstdatei, mit der der Routingdienst unter IIS oder WAS gehostet werden kann.</span><span class="sxs-lookup"><span data-stu-id="3a975-304">The following example contains a sample service file that can be used to host the Routing Service with IIS or WAS.</span></span>

```aspx-csharp
<%@ ServiceHost Language="C#" Debug="true" Service="System.ServiceModel.Routing.RoutingService,
     System.ServiceModel.Routing, version=4.0.0.0, Culture=neutral,
     PublicKeyToken=31bf3856ad364e35" %>
```

## <a name="routing-service-and-impersonation"></a><span data-ttu-id="3a975-305">Routingdienst und Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="3a975-305">Routing Service and Impersonation</span></span>

<span data-ttu-id="3a975-306">Der WCR-Routingdienst kann mit dem Identitätswechsel sowohl zum Senden als auch zum Empfangen von Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a975-306">The WCF Routing Service can be used with impersonation for both sending and receiving messages.</span></span> <span data-ttu-id="3a975-307">Alle üblichen Windows-Einschränkungen des Identitätswechsels sind gültig.</span><span class="sxs-lookup"><span data-stu-id="3a975-307">All of the usual Windows constraints of impersonation apply.</span></span> <span data-ttu-id="3a975-308">Wenn es beim Schreiben eines eigenen Diensts erforderlich ist, Dienst- oder Kontoberechtigungen für die Verwendung des Identitätswechsels einzurichten, müssen Sie dieselben Schritte ausführen, um den Identitätswechsel mit dem Routingdienst zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3a975-308">If you would have needed to set up service or account permissions to use impersonation when writing your own service, then you’ll have to do those same steps to use impersonation with the routing service.</span></span> <span data-ttu-id="3a975-309">Weitere Informationen finden Sie unter [Delegierung und](delegation-and-impersonation-with-wcf.md)Identitätswechsel.</span><span class="sxs-lookup"><span data-stu-id="3a975-309">For more information, see [Delegation and Impersonation](delegation-and-impersonation-with-wcf.md).</span></span>

<span data-ttu-id="3a975-310">Der Identitätswechsel mit dem Routingdienst erfordert entweder die Verwendung des ASP.NET-Identitätswechsels (im ASP.NET-Kompatibilitätsmodus) oder die Verwendung von Windows-Anmeldeinformationen, die konfiguriert wurden, um den Identitätswechsel zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3a975-310">Impersonation with the routing service requires either the use of ASP.NET impersonation while in ASP.NET compatibility mode or the use of Windows credentials that have been configured to allow impersonation.</span></span> <span data-ttu-id="3a975-311">Weitere Informationen zum ASP.NET-Kompatibilitätsmodus finden Sie unter [WCF-Dienste und ASP.net](wcf-services-and-aspnet.md).</span><span class="sxs-lookup"><span data-stu-id="3a975-311">For more information about ASP.NET compatibility mode, see [WCF Services and ASP.NET](wcf-services-and-aspnet.md).</span></span>

> [!WARNING]
> <span data-ttu-id="3a975-312">Der WCF-Routingdienst unterstützt keinen Identitätswechsel mit Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="3a975-312">The WCF Routing Service does not support impersonation with basic authentication.</span></span>

<span data-ttu-id="3a975-313">Um den ASP.NET-Identitätswechsel mit dem Routingdienst zu verwenden, aktivieren Sie den ASP.NET-Kompatibilitätsmodus für die Hostingumgebung des Diensts.</span><span class="sxs-lookup"><span data-stu-id="3a975-313">To use ASP.NET impersonation with the routing service, enable ASP.NET compatibility mode on the service hosting environment.</span></span> <span data-ttu-id="3a975-314">Der Routingdienst ist bereits für die Verwendung des ASP.NET-Kompatibilitätsmodus gekennzeichnet, und der Identitätswechsel wird automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3a975-314">The routing service has already been marked as allowing ASP.NET compatibility mode and impersonation will automatically be enabled.</span></span> <span data-ttu-id="3a975-315">Der Identitätswechsel ist die einzige unterstützte Verwendung der ASP.NET-Integration mit dem Routingdienst.</span><span class="sxs-lookup"><span data-stu-id="3a975-315">Impersonation is the only supported use of ASP.NET integration with the routing service.</span></span>

<span data-ttu-id="3a975-316">Um Windows-Anmeldeinformationen mit dem Routingdienst zu verwenden, müssen Sie sowohl die Anmeldeinformationen als auch den Dienst konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3a975-316">To use Windows credential impersonation with the routing service you need to configure both the credentials and the service.</span></span> <span data-ttu-id="3a975-317">Das Objekt für Clientanmeldeinformationen (<xref:System.ServiceModel.Security.WindowsClientCredential>, auf das von der <xref:System.ServiceModel.ChannelFactory> zugegriffen werden kann) definiert eine <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>-Eigenschaft, die festgelegt werden muss, um den Identitätswechsel zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="3a975-317">The client credentials object (<xref:System.ServiceModel.Security.WindowsClientCredential>, accessable from the <xref:System.ServiceModel.ChannelFactory>) defines an <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A> property that must be set to permit impersonation.</span></span> <span data-ttu-id="3a975-318">Schließlich müssen Sie für den Dienst das <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>-Verhalten konfigurieren, um `ImpersonateCallerForAllOperations` auf `true` festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3a975-318">Finally, on the service you need to configure the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> behavior to set `ImpersonateCallerForAllOperations` to `true`.</span></span> <span data-ttu-id="3a975-319">Der Routingdienst verwendet dieses Flag, um zu entscheiden, ob die Clients zum Weiterleiten von Nachrichten mit aktiviertem Identitätswechsel erstellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3a975-319">The routing service uses this flag to decide whether to create the clients for forwarding messages with impersonation enabled.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a975-320">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3a975-320">See also</span></span>

- [<span data-ttu-id="3a975-321">Nachrichtenfilter</span><span class="sxs-lookup"><span data-stu-id="3a975-321">Message Filters</span></span>](message-filters.md)
- [<span data-ttu-id="3a975-322">Routingverträge</span><span class="sxs-lookup"><span data-stu-id="3a975-322">Routing Contracts</span></span>](routing-contracts.md)
- [<span data-ttu-id="3a975-323">Auswählen eines Filters</span><span class="sxs-lookup"><span data-stu-id="3a975-323">Choosing a Filter</span></span>](choosing-a-filter.md)
