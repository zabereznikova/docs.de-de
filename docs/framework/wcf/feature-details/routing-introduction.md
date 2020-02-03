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
# <a name="routing-introduction"></a>Einführung in das Routing

Der Routingdienst stellt einen generischen austauschbaren SOAP-Vermittler bereit, der Nachrichten basierend auf dem Nachrichteninhalts weiterleiten kann. Mit dem Routingdienst können Sie eine komplexe Routinglogik erstellen, mit der Sie Szenarios wie Dienstaggregation, Dienstversionsverwaltung, Prioritätsrouting und Multicastrouting implementieren können. Außerdem stellt der Routingdienst eine Fehlerbehandlung bereit. Damit können Sie Listen von Sicherungsendpunkten einrichten, an die Nachrichten gesendet werden, falls beim Senden an den primären Zielendpunkt ein Fehler auftritt.

Dieses Thema richtet sich an Personen, die mit dem Routingdienst noch nicht vertraut sind, und behandelt die grundlegende Konfiguration und das Hosten des Routingdiensts.

## <a name="configuration"></a>Konfiguration

Der Routingdienst wird als WCF-Dienst implementiert, der einen oder mehrere Dienstendpunkte verfügbar macht, die Nachrichten von Clientanwendungen empfangen und die Nachrichten an einen oder mehrere Zielendpunkte weiterleiten. Der Dienst stellt ein <xref:System.ServiceModel.Routing.RoutingBehavior>-Objekt bereit, das auf die vom Dienst verfügbar gemachten Dienstendpunkte angewendet wird. Dieses Verhalten wird verwendet, um verschiedene Aspekte in Bezug auf die Funktionsweise des Diensts zu konfigurieren. Zur Erleichterung der Konfiguration bei Verwendung einer Konfigurationsdatei werden die Parameter für **Routing Behavior**angegeben. In Code basierten Szenarien werden diese Parameter als Teil eines <xref:System.ServiceModel.Routing.RoutingConfiguration> Objekts angegeben, das dann an ein **RoutingBehavior**-Objekt weitergeleitet werden kann.

Beim Starten fügt dieses Verhalten den Clientendpunkten das <xref:System.ServiceModel.Routing.SoapProcessingBehavior> hinzu. Dieses Verhalten wird für die SOAP-Verarbeitung von Nachrichten verwendet. Dadurch kann der Routing Dienst Nachrichten an Endpunkte übertragen, die eine andere **MessageVersion** benötigen als der Endpunkt, über den die Nachricht empfangen wurde. Das **RoutingBehavior** registriert auch eine Dienst Erweiterung, die <xref:System.ServiceModel.Routing.RoutingExtension>, die einen Barrierefreiheits Punkt zum Ändern der Routing Dienst Konfiguration zur Laufzeit bereitstellt.

Die **RoutingConfiguration** -Klasse bietet eine konsistente Möglichkeit, die Konfiguration des Routing Dienstanbieter zu konfigurieren und zu aktualisieren.  Sie enthält Parameter, die als Einstellungen für den Routing Dienst fungieren und zum Konfigurieren des **RoutingBehavior** verwendet werden, wenn der Dienst gestartet wird. Sie wird auch verwendet, um die Routing Konfiguration zur **Laufzeit zu ändern** .

Die Routinglogik, mit der das inhaltsbasierte Routing von Nachrichten durchgeführt wird, wird definiert, indem mehrere <xref:System.ServiceModel.Dispatcher.MessageFilter>-Objekte zu Filtertabellen (<xref:System.ServiceModel.Dispatcher.MessageFilterTable%601>-Objekten) gruppiert werden. Eingehende Nachrichten werden anhand der in der Filter Tabelle enthaltenen Nachrichtenfilter und für jeden **MessageFilter** , der mit der Nachricht übereinstimmt, an einen Ziel Endpunkt weitergeleitet. Die Filter Tabelle, die zum Weiterleiten von Nachrichten verwendet werden soll, wird entweder mithilfe des **RoutingBehavior** in der Konfiguration oder durch Code mithilfe des **RoutingConfiguration** -Objekts angegeben.

### <a name="defining-endpoints"></a>Definieren von Endpunkten

Es scheint so zu sein, als ob Sie die Konfiguration beginnen sollten, indem Sie die zu verwendende Routinglogik definieren. Stattdessen sollte der erste Schritt darin bestehen, die Form der Endpunkte zu ermitteln, an die Sie Nachrichten weiterleiten möchten. Der Routingdienst verwendet Verträge, die die Form der Kanäle definieren, die zum Empfangen und Senden von Nachrichten verwendet werden. Aus diesem Grund muss die Form des Eingabekanals mit der Form des Ausgabekanals übereinstimmen.  Wenn Sie die Weiterleitung z. B. an Endpunkte durchführen, die die Anforderung-Antwort-Kanalform verwenden, müssen Sie an den Eingangsendpunkten einen kompatiblen Vertrag verwenden, z. B. <xref:System.ServiceModel.Routing.IRequestReplyRouter>.

Wenn die Zielendpunkte Verträge mit mehreren Kommunikationsmustern verwenden (z. B. eine Mischung aus unidirektionalen und bidirektionalen Vorgängen), können Sie also keinen einzelnen Dienstendpunkt erstellen, der Nachrichten empfängt und an all diese Zielendpunkte weiterleitet. Sie müssen bestimmen, welche Endpunkte über kompatible Formen verfügen, und einen oder mehrere Dienstendpunkte definieren, an denen die Nachrichten empfangen werden, die an die Zielendpunkten weitergeleitet werden sollen.

> [!NOTE]
> Beim Arbeiten mit Verträgen, die mehrere Kommunikationsmuster angeben (z. B. eine Mischung aus unidirektionalen und bidirektionalen Vorgängen), besteht eine Problemumgehung in der Verwendung eines Duplexvertrags für den Routingdienst, z. B. <xref:System.ServiceModel.Routing.IDuplexSessionRouter>. Dies bedeutet jedoch, dass die Bindung für die Duplexkommunikation geeignet sein muss, was ggf. nicht für alle Szenarios der Fall ist. In Szenarios, in denen dies nicht möglich ist, kann das Verteilen der Kommunikation auf mehrere Endpunkte oder das Ändern der Anwendung erforderlich sein.

Weitere Informationen zu Routing Verträgen finden Sie unter [Routing Verträge](routing-contracts.md).

Nachdem der Dienst Endpunkt definiert wurde, können Sie das **Routing Behavior-Verhalten** verwenden, um dem Endpunkt eine bestimmte **RoutingConfiguration** zuzuordnen. Beim Konfigurieren des Routing Dienstanbieter mithilfe einer Konfigurationsdatei wird **RoutingBehavior** verwendet, um die Filter Tabelle anzugeben, die die Routing Logik zum Verarbeiten von Nachrichten enthält, die an diesem Endpunkt empfangen werden. Wenn Sie den Routing Dienstprogramm gesteuert konfigurieren, können Sie die Filter Tabelle mithilfe von **RoutingConfiguration**angeben.

Im folgenden Beispiel werden die Dienst- und Clientendpunkte, die vom Routingdienst verwendet werden, sowohl programmgesteuert als auch unter Verwendung einer Konfigurationsdatei definiert.

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

In diesem Beispiel wird der Routing Dienst so konfiguriert, dass ein einzelner Endpunkt mit der Adresse `http://localhost:8000/routingservice/router`verfügbar gemacht wird, der zum Empfangen von Nachrichten verwendet wird, die weitergeleitet werden sollen. Da die Nachrichten an die Anforderung-Antwort-Endpunkte weitergeleitet werden, verwendet der Dienstendpunkt den <xref:System.ServiceModel.Routing.IRequestReplyRouter>-Vertrag. Diese Konfiguration definiert auch einen einzelnen Client Endpunkt `http://localhost:8000/servicemodelsample/service`, an die Nachrichten weitergeleitet werden. Die Filter Tabelle (nicht angezeigt) mit dem Namen "routingTable1" enthält die Routing Logik, die zum Weiterleiten von Nachrichten verwendet wird, und ist mit dem Dienst Endpunkt verknüpft, indem Routing **Verhalten** (für eine Konfigurationsdatei) oder **RoutingConfiguration** (für die programmgesteuerte Konfiguration) verwendet wird.

### <a name="routing-logic"></a>Routinglogik

Um die Routinglogik zum Weiterleiten von Nachrichten zu definieren, müssen Sie ermitteln, welche in den eingehenden Nachrichten enthaltenen Daten eindeutig verarbeitet werden können. Wenn beispielsweise alle Zielendpunkte der Weiterleitung die gleichen SOAP-Aktionen verwenden, ist der Wert von "Action" innerhalb der Nachricht kein guter Indikator dafür, an welchen Endpunkt die Nachricht jeweils genau weitergeleitet werden soll. Falls Sie Nachrichten nur an einen bestimmten Endpunkt weiterleiten müssen, sollten Sie nach Daten filtern, die den Zielendpunkt eindeutig identifizieren, an den die Nachricht weitergeleitet wird.

Der Routing Dienst stellt mehrere **MessageFilter** -Implementierungen bereit, die bestimmte Werte innerhalb der Nachricht überprüfen, z. b. Adresse, Aktion, Endpunkt Name oder sogar eine XPath-Abfrage. Wenn keine dieser Implementierungen Ihren Anforderungen entspricht, können Sie eine benutzerdefinierte **MessageFilter** -Implementierung erstellen. Weitere Informationen zu Nachrichten filtern und einen Vergleich der vom Routing Dienst verwendeten Implementierungen finden Sie unter [Nachrichtenfilter](message-filters.md) und [Auswählen eines Filters](choosing-a-filter.md).

Mehrere Nachrichtenfilter sind in Filter Tabellen organisiert, die jeden **MessageFilter** einem Ziel Endpunkt zuordnen. Optional kann die Filtertabelle auch verwendet werden, um auch eine Liste mit Sicherungsendpunkten anzugeben. Der Routingdienst versucht dann, die Nachricht bei einem Übertragungsfehler an diese Endpunkte zu senden.

Standardmäßig werden alle Nachrichtenfilter einer Filtertabelle gleichzeitig ausgewertet. Sie können jedoch eine <xref:System.ServiceModel.Routing.Configuration.FilterTableEntryElement.Priority%2A>-Eigenschaft angeben, die bewirkt, dass die Nachrichtenfilter in einer bestimmten Reihenfolge ausgewertet werden. Alle Einträge mit der höchsten Priorität werden zuerst ausgewertet, und Nachrichtenfilter mit niedrigeren Prioritäten werden nicht ausgewertet, wenn eine Übereinstimmung mit einer höheren Prioritätsstufe gefunden wird. Weitere Informationen zu Filter Tabellen finden Sie unter [Nachrichtenfilter](message-filters.md).

In den folgenden Beispielen wird das <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter>-Objekt verwendet, das für alle Nachrichten `true` ergibt. Dieser **MessageFilter** wird der Filter Tabelle "routingTable1" hinzugefügt, die den **MessageFilter** dem Client Endpunkt mit dem Namen "CalculatorService" zuordnet. Das **RoutingBehavior** gibt dann an, dass diese Tabelle zum Weiterleiten von Nachrichten verwendet werden soll, die vom Dienst Endpunkt verarbeitet werden.

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
> Standardmäßig wertet der Routingdienst nur die Header der Nachricht aus. Um den Filtern den Zugriff auf den Text der Nachricht zu ermöglichen, müssen Sie <xref:System.ServiceModel.Routing.RoutingConfiguration.RouteOnHeadersOnly%2A> auf `false` festlegen.

**Multicast**

Viele Routingdienstkonfigurationen verwenden zwar eine exklusive Filterlogik, die Nachrichten an nur einen bestimmten Endpunkt weiterleitet, aber es kann erforderlich sein, dass Sie eine bestimmte Nachricht an mehrere Zielendpunkte weiterleiten müssen. Um für eine Nachricht per Multicast an mehrere Ziele zu senden, müssen die folgenden Bedingungen erfüllt sein:

- Die Kanalform darf nicht vom Typ "Anforderung-Antwort" sein (unidirektional oder duplex ist jedoch möglich), weil die Clientanwendung als Antwort auf die Anforderung nur eine Antwort empfangen kann.

- Mehrere Filter müssen beim Auswerten der Nachricht `true` zurückgeben.

Falls diese Bedingungen erfüllt sind, wird die Nachricht an alle Endpunkte aller Filter weitergeleitet, für die die Auswertung `true` ergibt. Im folgenden Beispiel wird eine Routing Konfiguration definiert, die dazu führt, dass Nachrichten an beide Endpunkte weitergeleitet werden, wenn die Endpunkt Adresse in der Nachricht `http://localhost:8000/routingservice/router/rounding`ist.

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

### <a name="soap-processing"></a>SOAP-Verarbeitung

Um das Routing von Nachrichten zwischen unterschiedlichen Protokollen zu unterstützen, fügt das **RoutingBehavior** standardmäßig den <xref:System.ServiceModel.Routing.SoapProcessingBehavior> allen Client Endpunkten hinzu, an die Nachrichten weitergeleitet werden. Dieses Verhalten erstellt automatisch eine neue **MessageVersion** , bevor die Nachricht an den Endpunkt weitergegeben wird, und erstellt eine kompatible **MessageVersion** für jedes Antwortdokument, bevor es an die anfordernde Client Anwendung zurückgegeben wird.

Die Schritte zum Erstellen einer neuen **MessageVersion** für die ausgehende Nachricht lauten wie folgt:

**Anforderungs Verarbeitung**

- Holen Sie sich die **MessageVersion** der ausgehenden Bindung/des Kanals.

- Rufen Sie den Textreader für die ursprüngliche Nachricht ab.

- Erstellen Sie eine neue Nachricht mit der gleichen Aktion, dem Text Reader und einer neuen **MessageVersion**.

- Wenn <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>! = **Adressierung. None**, kopieren Sie die Header in, from, FaultTo und RelatesTo in die neue Nachricht.

- Kopieren Sie alle Eigenschaften der Nachricht in die neue Nachricht.

- Speichern Sie die ursprüngliche Anforderungsnachricht, die zum Verarbeiten der Antwort verwendet werden soll.

- Geben Sie die neue Anforderungsnachricht zurück.

**Antwort Verarbeitung**

- Holen Sie sich die **MessageVersion** der ursprünglichen Anforderungs Nachricht.

- Rufen Sie den Textreader für die empfangene Antwortnachricht ab.

- Erstellen Sie eine neue Antwortnachricht mit der gleichen Aktion, dem Text Reader und der **MessageVersion** der ursprünglichen Anforderungs Nachricht.

- Wenn <xref:System.ServiceModel.Channels.MessageVersion.Addressing%2A>! = **Adressierung. None**, kopieren Sie die Header in, from, FaultTo und RelatesTo in die neue Nachricht.

- Kopieren Sie die Eigenschaften der Nachricht in die neue Nachricht.

- Geben Sie die neue Antwortnachricht zurück.

Standardmäßig wird das **soapprocessingbehavior** automatisch den Client Endpunkten von der <xref:System.ServiceModel.Routing.RoutingBehavior> hinzugefügt, wenn der Dienst gestartet wird. Sie können jedoch steuern, ob die SOAP-Verarbeitung allen Client Endpunkten mithilfe der <xref:System.ServiceModel.Routing.RoutingConfiguration.SoapProcessingEnabled%2A>-Eigenschaft hinzugefügt wird. Sie können das Verhalten auch direkt einem bestimmten Endpunkt hinzufügen und es auf Endpunktebene aktivieren oder deaktivieren, falls eine präzisere Steuerung der SOAP-Verarbeitung erforderlich ist.

> [!NOTE]
> Wenn die SOAP-Verarbeitung für einen Endpunkt deaktiviert ist, der eine andere MessageVersion als die der ursprünglichen Anforderungsnachricht erfordert, müssen Sie einen benutzerdefinierten Mechanismus zum Ausführen aller SOAP-Änderungen bereitstellen, die vor dem Senden der Nachricht an den Zielendpunkt erforderlich sind.

In den folgenden Beispielen wird die **soapprocessingenabled** -Eigenschaft verwendet, um zu verhindern, dass **soapprocessingbehavior** automatisch allen Client Endpunkten hinzugefügt wird.

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

### <a name="dynamic-configuration"></a>Dynamische Konfiguration

Wenn Sie zusätzliche Clientendpunkte hinzufügen oder die Filter zum Weiterleiten von Nachrichten ändern, müssen Sie eine Möglichkeit schaffen, die Konfiguration zur Laufzeit dynamisch zu aktualisieren. Auf diese Weise verhindern Sie die Unterbrechung des Diensts zu den Endpunkten, die momentan Nachrichten über den Routingdienst empfangen. Das Ändern einer Konfigurationsdatei oder des Codes der Hostanwendung ist nicht immer ausreichend, weil bei beiden Verfahren die Wiederverwendung der Anwendung erforderlich ist. Dies kann zum Verlust aller Nachrichten führen, die gerade übertragen werden, und es kann beim Warten auf den Neustart des Diensts zu einer Ausfallzeit kommen.

Sie können **RoutingConfiguration** nur Programm gesteuert ändern. Obwohl Sie den Dienst anfänglich mithilfe einer Konfigurationsdatei konfigurieren können, können Sie die Konfiguration nur zur Laufzeit ändern, indem Sie eine neue **RoutingConfiguration** erstellen und Sie als Parameter an die <xref:System.ServiceModel.Routing.RoutingExtension.ApplyConfiguration%2A> Methode übergeben, die von der <xref:System.ServiceModel.Routing.RoutingExtension> Dienst Erweiterung verfügbar gemacht wird. Alle Nachrichten, die zurzeit übertragen werden, werden weiterhin mithilfe der vorherigen Konfiguration weitergeleitet, während Nachrichten, die nach dem aufzurufen von **ApplyConfiguration** empfangen werden, die neue Konfiguration Im folgenden Beispiel wird das Erstellen einer Instanz des Routingdiensts und anschließend das Ändern der Konfiguration veranschaulicht.

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
> Beim Aktualisieren des Routingdiensts auf diese Weise ist es nur möglich, eine neue Konfiguration zu übergeben. Es ist nicht möglich, nur bestimmte Elemente der aktuellen Konfiguration zu ändern oder neue Einträge an die aktuelle Konfiguration anzufügen. Sie müssen eine neue Konfiguration erstellen und übergeben, die die vorhandene Konfiguration ersetzt.

> [!NOTE]
> Alle Sitzungen, die mit der vorherigen Konfiguration geöffnet wurden, verwenden weiterhin die vorherige Konfiguration. Die neue Konfiguration wird nur von neuen Sitzungen verwendet.

## <a name="error-handling"></a>Fehlerbehandlung

Wenn beim versuchten Senden einer Nachricht eine <xref:System.ServiceModel.CommunicationException> auftritt, wird die Fehlerbehandlung ausgeführt. Diese Ausnahmen weisen in der Regel darauf hin, dass beim Versuch der Kommunikation mit dem definierten Clientendpunkt ein Problem aufgetreten ist, z. B. <xref:System.ServiceModel.EndpointNotFoundException>, <xref:System.ServiceModel.ServerTooBusyException> oder <xref:System.ServiceModel.CommunicationObjectFaultedException>. Der Fehler Behandlungs Code fängt auch auf und versucht, den Sendevorgang zu wiederholen, wenn ein <xref:System.TimeoutException> auftritt. Dies ist eine andere häufige Ausnahme, die nicht von **CommunicationException**abgeleitet ist.

Wenn eine der vorangehenden Ausnahmen auftritt, führt der Routingdienst ein Failover zu einer Liste von Sicherungsendpunkten aus. Falls für alle Sicherungsendpunkte ein Kommunikationsfehler auftritt oder falls ein Endpunkt eine Ausnahme zurückgibt, die einen Fehler beim Zieldienst angibt, gibt der Routingdienst einen Fehler an die Clientanwendung zurück.

> [!NOTE]
> Die Fehlerbehandlungsfunktion erfasst und behandelt Ausnahmen, die beim versuchten Senden einer Nachricht oder Schließen eines Kanals auftreten. Der Fehler Behandlungs Code dient nicht zum erkennen oder behandeln von Ausnahmen, die von den Anwendungs Endpunkten erstellt werden, mit denen er kommuniziert. eine <xref:System.ServiceModel.FaultException>, die von einem Dienst ausgelöst wird, wird als **Fehlermeldung** am Routing Dienst angezeigt und an den Client zurückgegeben.
>
> Wenn beim Weiterleiten einer Nachricht durch den Routingdienst ein Fehler auftritt, erhalten Sie eventuell auf der Clientseite eine <xref:System.ServiceModel.FaultException> und keine <xref:System.ServiceModel.EndpointNotFoundException>, die Sie normalerweise bei nicht vorhandenem Routingdienst erhalten. Daher maskiert der Routingdienst möglicherweise Ausnahmen und bietet keine vollständige Transparenz, es sei denn, Sie überprüfen geschachtelte Ausnahmen.

### <a name="tracing-exceptions"></a>Nachverfolgen von Ausnahmen

Wenn beim Senden einer Nachricht an einen Endpunkt in einer Liste ein Fehler auftritt, verfolgt der Routing Dienst die resultierenden Ausnahme Daten und fügt die Ausnahme Details als Nachrichten Eigenschaft mit dem Namen " **Exceptions**" an. Dabei werden die Ausnahmedaten beibehalten, und Benutzern wird der programmgesteuerte Zugriff über einen Nachrichteninspektor ermöglicht.  Die Ausnahmedaten werden pro Nachricht in einem Wörterbuch gespeichert. Das Wörterbuch ordnet den Endpunktnamen den Ausnahmedetails zu, die beim versuchten Senden einer Nachricht an diesen Endpunkt auftreten.

### <a name="backup-endpoints"></a>Sicherungsendpunkte

Jeder Filtereintrag innerhalb der Filtertabelle kann optional eine Liste mit Sicherungsendpunkten angeben, die verwendet werden, wenn beim Senden an den primären Endpunkt ein Übertragungsfehler auftritt. Bei einem Fehler dieser Art versucht der Routingdienst, die Nachricht an den ersten Eintrag der Liste mit den Sicherungsendpunkten zu senden. Falls bei diesem Sendeversuch ebenfalls ein Übertragungsfehler auftritt, wird der nächste Endpunkt in der Liste verwendet. Der Routingdienst sendet die Nachricht an jeden Endpunkt in der Liste, bis die Nachricht erfolgreich empfangen wurde, alle Endpunkte einen Übertragungsfehler zurückgeben oder ein Endpunkt einen anderen Fehler als einen Übertragungsfehler zurückgibt.

In den folgenden Beispielen wird der Routingdienst für die Verwendung einer Sicherungsliste konfiguriert.

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

### <a name="supported-error-patterns"></a>Unterstützte Fehlermuster

In der folgenden Tabelle werden die Muster beschrieben, die mit der Verwendung von Sicherungsendpunktlisten kompatibel sind. Außerdem enthält die Tabelle Hinweise zu den Details der Fehlerbehandlung für bestimmte Muster.

|Muster|Sitzung|Transaktion|Empfangskontext|Unterstützte Sicherungsliste|Notizen|
|-------------|-------------|-----------------|---------------------|---------------------------|-----------|
|Unidirektional||||Ja|Versucht, die Nachricht erneut an einen Sicherungsendpunkt zu senden. Falls für diese Nachricht ein Multicast ausgeführt wird, wird nur die Nachricht im Kanal mit dem Fehler an das entsprechende Sicherungsziel verschoben.|
|Unidirektional||✔️||Nein|Eine Ausnahme wird ausgelöst, und für die Transaktion wird ein Rollback ausgeführt.|
|Unidirektional|||✔️|Ja|Versucht, die Nachricht erneut an einen Sicherungsendpunkt zu senden. Nachdem die Nachricht erfolgreich empfangen wurde, werden alle Empfangskontexte abgeschlossen. Falls die Nachricht von keinem Endpunkt erfolgreich empfangen wurde, wird der Empfangskontext nicht abgeschlossen.<br /><br /> Wenn für diese Nachricht ein Multicast ausgeführt wird, wird der Empfangskontext nur abgeschlossen, falls die Nachricht von mindestens einem Endpunkt (primär oder Sicherung) erfolgreich empfangen wird. Schließen Sie den Empfangskontext nicht ab, falls der Empfang der Nachricht für keinen Endpunkt in den Multicastpfaden erfolgreich ist.|
|Unidirektional||✔️|✔️|Ja|Brechen Sie die vorherige Transaktion ab, erstellen Sie eine neue Transaktion, und senden Sie alle Nachrichten neu. Nachrichten, für die ein Fehler aufgetreten ist, werden an ein Sicherungsziel übertragen.<br /><br /> Nachdem eine Transaktion erstellt wurde, für die alle Übertragungen erfolgreich sind, schließen Sie die Empfangskontexte ab und führen für die Transaktion einen Commit aus.|
|Unidirektional|✔️|||Ja|Versucht, die Nachricht erneut an einen Sicherungsendpunkt zu senden. In einem Multicastszenario werden nur die Nachrichten einer Sitzung, für die ein Fehler aufgetreten ist oder bei der beim Schließen der Sitzung ein Fehler aufgetreten ist, zurück an die Sicherungsziele gesendet.|
|Unidirektional|✔️|✔️||Nein|Eine Ausnahme wird ausgelöst, und für die Transaktion wird ein Rollback ausgeführt.|
|Unidirektional|✔️||✔️|Ja|Versucht, die Nachricht erneut an einen Sicherungsendpunkt zu senden. Nachdem das Senden für alle Nachrichten erfolgreich abgeschlossen wurde, zeigt die Sitzung keine Nachrichten mehr an, und der Routingdienst schließt alle ausgehenden Sitzungskanäle. Außerdem werden alle Empfangskontexte abgeschlossen und der eingehende Sitzungskanal geschlossen.|
|Unidirektional|✔️|✔️|✔️|Ja|Brechen Sie die aktuelle Transaktion ab, und erstellen Sie eine neue Transaktion. Senden Sie alle vorherigen Nachrichten der Sitzung neu. Nachdem eine Transaktion erstellt wurde, für die alle Nachrichten erfolgreich gesendet wurden, und die Sitzung keine Nachrichten mehr anzeigt, werden alle ausgehenden Sitzungskanäle geschlossen. Außerdem werden alle Empfangskontexte zusammen mit der Transaktion abgeschlossen, der eingehende Sitzungskanal wird geschlossen und für die Transaktion wird ein Commit ausgeführt.<br /><br /> Wenn für die Sitzungen ein Multicast durchgeführt wird, werden die Nachrichten, für die kein Fehler aufgetreten ist, wie vorher erneut zurück an das gleiche Ziel gesendet. Nachrichten, für die ein Fehler aufgetreten ist, werden an die Sicherungsziele gesendet.|
|Bidirektional||||Ja|Das Senden erfolgt an ein Sicherungsziel.  Nachdem ein Kanal eine Antwortnachricht zurückgegeben hat, wird die Antwort an den ursprünglichen Client zurückgegeben.|
|Bidirektional|✔️|||Ja|Alle Nachrichten im Kanal werden an ein Sicherungsziel gesendet.  Nachdem ein Kanal eine Antwortnachricht zurückgegeben hat, wird die Antwort an den ursprünglichen Client zurückgegeben.|
|Bidirektional||✔️||Nein|Eine Ausnahme wird ausgelöst, und für die Transaktion wird ein Rollback ausgeführt.|
|Bidirektional|✔️|✔️||Nein|Eine Ausnahme wird ausgelöst, und für die Transaktion wird ein Rollback ausgeführt.|
|Duplex||||Nein|Die Duplexkommunikation außerhalb von Sitzungen wird momentan nicht unterstützt.|
|Duplex|✔️|||Ja|Das Senden erfolgt an ein Sicherungsziel.|

## <a name="hosting"></a>Hosting

Da der Routingdienst als WCF-Dienst implementiert wird, muss dieser entweder in einer Anwendung selbst oder von IIS oder WAS gehostet werden. Es ist ratsam, den Routingdienst entweder unter IIS, WAS oder einer Windows-Dienstanwendung zu hosten. Sie können dann die Vorteile des automatischen Startens und die Funktionen zur Lebenszyklusverwaltung nutzen, die in diesen Hostumgebungen verfügbar sind.

Im folgenden Beispiel wird das Hosten des Routingdiensts in einer Anwendung veranschaulicht.

```csharp
using (ServiceHost serviceHost =
                new ServiceHost(typeof(RoutingService)))
```

Um den Routingdienst unter IIS oder WAS zu hosten, müssen Sie entweder eine Dienstdatei (.svc) erstellen oder eine Aktivierung des Diensts per Konfiguration verwenden. Bei Verwendung einer Dienstdatei müssen Sie <xref:System.ServiceModel.Routing.RoutingService> angeben, indem Sie den Service-Parameter verwenden. Das folgende Beispiel enthält eine Beispieldienstdatei, mit der der Routingdienst unter IIS oder WAS gehostet werden kann.

```aspx-csharp
<%@ ServiceHost Language="C#" Debug="true" Service="System.ServiceModel.Routing.RoutingService,
     System.ServiceModel.Routing, version=4.0.0.0, Culture=neutral,
     PublicKeyToken=31bf3856ad364e35" %>
```

## <a name="routing-service-and-impersonation"></a>Routingdienst und Identitätswechsel

Der WCR-Routingdienst kann mit dem Identitätswechsel sowohl zum Senden als auch zum Empfangen von Nachrichten verwendet werden. Alle üblichen Windows-Einschränkungen des Identitätswechsels sind gültig. Wenn es beim Schreiben eines eigenen Diensts erforderlich ist, Dienst- oder Kontoberechtigungen für die Verwendung des Identitätswechsels einzurichten, müssen Sie dieselben Schritte ausführen, um den Identitätswechsel mit dem Routingdienst zu verwenden. Weitere Informationen finden Sie unter [Delegierung und](delegation-and-impersonation-with-wcf.md)Identitätswechsel.

Der Identitätswechsel mit dem Routingdienst erfordert entweder die Verwendung des ASP.NET-Identitätswechsels (im ASP.NET-Kompatibilitätsmodus) oder die Verwendung von Windows-Anmeldeinformationen, die konfiguriert wurden, um den Identitätswechsel zu ermöglichen. Weitere Informationen zum ASP.NET-Kompatibilitätsmodus finden Sie unter [WCF-Dienste und ASP.net](wcf-services-and-aspnet.md).

> [!WARNING]
> Der WCF-Routingdienst unterstützt keinen Identitätswechsel mit Standardauthentifizierung.

Um den ASP.NET-Identitätswechsel mit dem Routingdienst zu verwenden, aktivieren Sie den ASP.NET-Kompatibilitätsmodus für die Hostingumgebung des Diensts. Der Routingdienst ist bereits für die Verwendung des ASP.NET-Kompatibilitätsmodus gekennzeichnet, und der Identitätswechsel wird automatisch aktiviert. Der Identitätswechsel ist die einzige unterstützte Verwendung der ASP.NET-Integration mit dem Routingdienst.

Um Windows-Anmeldeinformationen mit dem Routingdienst zu verwenden, müssen Sie sowohl die Anmeldeinformationen als auch den Dienst konfigurieren. Das Objekt für Clientanmeldeinformationen (<xref:System.ServiceModel.Security.WindowsClientCredential>, auf das von der <xref:System.ServiceModel.ChannelFactory> zugegriffen werden kann) definiert eine <xref:System.ServiceModel.Security.WindowsClientCredential.AllowedImpersonationLevel%2A>-Eigenschaft, die festgelegt werden muss, um den Identitätswechsel zu ermöglichen. Schließlich müssen Sie für den Dienst das <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>-Verhalten konfigurieren, um `ImpersonateCallerForAllOperations` auf `true` festzulegen. Der Routingdienst verwendet dieses Flag, um zu entscheiden, ob die Clients zum Weiterleiten von Nachrichten mit aktiviertem Identitätswechsel erstellt werden sollen.

## <a name="see-also"></a>Weitere Informationen

- [Nachrichtenfilter](message-filters.md)
- [Routingverträge](routing-contracts.md)
- [Auswählen eines Filters](choosing-a-filter.md)
