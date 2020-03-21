---
title: Windows Workflow Foundation-Funktionsdetails
ms.date: 03/30/2017
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
ms.openlocfilehash: 11bde5edea44f09ef1a5658cdf0e20ec1349c84b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182924"
---
# <a name="windows-workflow-foundation-feature-specifics"></a>Windows Workflow Foundation-Funktionsdetails

.NET Framework 4 fügt Windows Workflow Foundation eine Reihe von Features hinzu. In diesem Dokument wird eine Reihe neuer Funktionen beschrieben. Darüber hinaus enthält das Dokument detaillierte Informationen zu den Szenarien, in denen sie möglicherweise nützlich sind.

## <a name="messaging-activities"></a>Messagingaktivitäten

Die Messagingaktivitäten<xref:System.ServiceModel.Activities.Receive> <xref:System.ServiceModel.Activities.SendReply>( <xref:System.ServiceModel.Activities.Send> <xref:System.ServiceModel.Activities.ReceiveReply>, , , ) werden zum Senden und Empfangen von WCF-Nachrichten aus Ihrem Workflow verwendet. <xref:System.ServiceModel.Activities.Receive>und <xref:System.ServiceModel.Activities.SendReply> Aktivitäten werden verwendet, um einen Windows Communication Foundation (WCF)-Dienstvorgang zu bilden, der wie Standard-WCF-Webdienste über WSDL verfügbar gemacht wird. <xref:System.ServiceModel.Activities.Send>und <xref:System.ServiceModel.Activities.ReceiveReply> werden verwendet, um einen Webdienst <xref:System.ServiceModel.ChannelFactory>ähnlich einem WCF zu nutzen; Eine **Erfahrung zum Hinzufügen von Dienstreferenz** ist auch für Workflow Foundation vorhanden, die vorkonfigurierte Aktivitäten generiert.

### <a name="getting-started-with-messaging-activities"></a>Erste Schritte mit Messagingaktivitäten

- Erstellen Sie in Visual Studio 2012 ein WCF-Workflowdienstanwendungsprojekt. Das Paar <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> wird auf dem Canvas platziert.

- Klicken Sie mit der rechten Maustaste auf das Projekt, und wählen Sie **Servicereferenz hinzufügen**aus. Zeigen Sie auf einen vorhandenen Webdienst WSDL, und klicken Sie auf **OK**. Erstellen Sie Ihr Projekt, um <xref:System.ServiceModel.Activities.Send> die <xref:System.ServiceModel.Activities.ReceiveReply>generierten Aktivitäten (implementiert mit und ) in Ihrer Toolbox anzuzeigen.

- [Dokumentation zu Workflow-Services](../wcf/feature-details/workflow-services.md)

### <a name="messaging-activities-example-scenario"></a>Beispielszenario für Messagingaktivitäten

Ein `BestPriceFinder` Service ruft mehrere Fluggesellschaften an, um den besten Ticketpreis für eine bestimmte Strecke zu finden. Um dieses Szenario zu implementieren, müssen Sie die Nachrichtenaktivitäten verwenden, um die Preisanforderung zu empfangen, die Preise von den Back-End-Diensten abzurufen und auf die Preisanfrage mit dem besten Preis zu antworten. Außerdem müssen Sie andere Sofortmaßnahmen verwenden, um die Geschäftslogik für die Berechnung des besten Preises zu erstellen.

## <a name="workflowservicehost"></a>WorkflowServiceHost

Der <xref:System.ServiceModel.WorkflowServiceHost> ist der sofort einsatzbereite Workflowhost, der mehrere Instanzen, Konfiguration und WCF-Messaging unterstützt (obwohl die Workflows nicht für die Verwendung von Messaging erforderlich sind, um gehostet zu werden). Außerdem wird durch einen Satz von Dienstverhalten die Integration von Persistenz, Nachverfolgung und Instanzsteuerung bereitgestellt. Genau wie WCF <xref:System.ServiceModel.ServiceHost>kann <xref:System.ServiceModel.WorkflowServiceHost> der in einer Konsole/WinForms/WPF-Anwendung oder einem Windows-Dienst selbst gehostet oder in IIS oder WAS webgehostet (als .xamlx-Datei) sein.

### <a name="getting-started-with-workflow-service-host"></a>Erste Schritte mit dem Workflowdiensthost

- Erstellen Sie in Visual Studio 2010 ein WCF-Workflowdienstanwendungsprojekt: <xref:System.ServiceModel.WorkflowServiceHost> Dieses Projekt wird für die Verwendung in einer Webhostumgebung eingerichtet.

- Zum Hosten eines Nicht-Messaging-Workflows fügen Sie einen benutzerdefinierten <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> hinzu, der die Instanz auf Grundlage einer Nachricht erstellt.

- Workflowinstanzen können gesteuert (z. B.angehalten oder beendet) werden, indem <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> ein <xref:System.ServiceModel.WorkflowServiceHost> hinzugefügt und anschließend ein <xref:System.ServiceModel.Activities.WorkflowControlClient> verwendet wird.

- Beispiele für <xref:System.ServiceModel.WorkflowServiceHost> finden Sie in den folgenden Abschnitten:

  - [Ausführung](./samples/execution.md)

  - Anwendung: [Suspended Instance Management](./samples/suspended-instance-management.md)

- [Übersicht über Hosting-Workflow-Services](../wcf/feature-details/hosting-workflow-services-overview.md)

### <a name="workflowservicehost-scenario"></a>WorkflowServiceHost-Szenario

Ein BestPriceFinder-Service ruft mehrere Fluggesellschaften an, um den besten Ticketpreis für eine bestimmte Strecke zu finden. Für das Implementieren dieses Szenarios <xref:System.ServiceModel.WorkflowServiceHost>müssen Sie den Workflow in hosten. Es würde auch die Nachrichtenaktivitäten verwenden, um die Preisanfrage zu erhalten, die Preise von den Back-End-Diensten abzurufen und auf die Preisanfrage mit dem besten Preis zu antworten.

## <a name="correlation"></a>Correlation

Eine Korrelation kann wie folgt definiert werden:

- Eine Möglichkeit zum Gruppieren von Nachrichten, d. h. die Beziehung zwischen einer Anforderungsnachricht und der dazugehörigen Antwort

- Eine Möglichkeit, ein Datenelement einer Dienstinstanz zuzuordnen

### <a name="getting-started"></a>Erste Schritte

- Erstellen Sie in Visual Studio ein neues Projekt, um mit der Korrelation zu beginnen. Erstellen Sie eine Variable vom Typ <xref:System.ServiceModel.Activities.CorrelationHandle>.

- Ein Beispiel für die Verwendung einer Korrelation zum Gruppieren von Nachrichten ist eine Anforderung/Antwort-Korrelation, die Nachrichten zusammen gruppiert.

  - Klicken <xref:System.ServiceModel.Activities.Receive> Sie bei einer <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> Aktivität auf <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> die Eigenschaft, und fügen Sie eine mit dem CorrelationHandle hinzu, das im ersten Schritt oben erstellt wurde.

  - Erstellen <xref:System.ServiceModel.Activities.SendReply> Sie eine Aktivität, indem <xref:System.ServiceModel.Activities.Receive> Sie mit der rechten Maustaste auf die klicken und auf "SendReply erstellen" klicken. Fügen Sie die Aktivität hinter der <xref:System.ServiceModel.Activities.Receive>-Aktivität in den Workflow ein.

- Ein Beispiel für die Zuordnung eines Datenelements zu einer Dienstinstanz ist die inhaltsbasierte Korrelation, bei der ein Datenelement (z. B. eine Auftrags-ID) einer bestimmten Workflowinstanz zugeordnet wird.

  - Klicken Sie auf die `CorrelationInitializers`-Eigenschaft einer Messagingaktivität, und fügen Sie mit der oben erstellten <xref:System.ServiceModel.Activities.QueryCorrelationInitializer>-Variable einen <xref:System.ServiceModel.Activities.CorrelationHandle> hinzu. Doppelklicken Sie im Dropdownmenü auf die gewünschte Eigenschaft der Nachricht (z. B. "OrderID"). Legen Sie die `CorrelatesWith`-Eigenschaft auf die oben verwendete <xref:System.ServiceModel.Activities.CorrelationHandle>-Variable fest.

- [Korrelationsdokumentation](../wcf/feature-details/correlation.md)

### <a name="correlation-scenario"></a>Korrelationsszenario

Ein Auftragsverarbeitungsworkflow wird verwendet, um neue Auftragserstellungen zu verarbeiten und vorhandene Aufträge zu aktualisieren, die gerade in Bearbeitung sind. Für das Implementieren dieses Szenarios <xref:System.ServiceModel.WorkflowServiceHost> müssen Sie den Workflow in den Messagingaktivitäten hosten und verwenden. Außerdem wäre eine Korrelation `orderId` erforderlich, die auf der basiert, um sicherzustellen, dass Aktualisierungen am richtigen Workflow vorgenommen werden.

## <a name="simplified-configuration"></a>Vereinfachte Konfiguration

Das WCF-Konfigurationsschema ist komplex und bietet Benutzern viele schwer zu findende Features. In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]haben wir uns darauf konzentriert, WCF-Benutzern bei der Konfiguration ihrer Dienste mit den folgenden Funktionen zu helfen:

- Es ist keine explizite Einzeldienstkonfiguration mehr notwendig. Wenn Sie keine \<Dienstelemente> Für Ihren Dienst konfigurieren und Ihr Dienst keinen programmgesteuerten Endpunkt definiert, wird automatisch ein Satz von Endpunkten zu Ihrem Dienst hinzugefügt, einer pro Servicebasisadresse und pro Vertrag, der von Ihrem Dienst implementiert wird.

- Der Benutzer kann Standardwerte für WCF-Bindungen und -Verhalten definieren, die ohne explizite Konfiguration auf Dienste angewendet werden.

- Standardendpunkte definieren wiederverwendbare vorkonfigurierte Endpunkte, die feste Werte für mindestens eine Endpunkteigenschaft besitzen (Adresse, Bindung und Vertrag) und die die Definition benutzerdefinierter Eigenschaften erlauben.

- Schließlich können <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> Sie mit der zentrale Verwaltung der WCF-Clientkonfiguration vornehmen, die in Szenarien nützlich ist, in denen die Konfiguration nach der Ladezeit der Anwendungsdomäne ausgewählt oder geändert wird.

### <a name="getting-started"></a>Erste Schritte

- [Entwicklerhandbuch für WCF 4.0](https://docs.microsoft.com/previous-versions/dotnet/articles/ee354381(v=msdn.10))

- [Konfigurationskanalfactory](xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601)

- [Standardendpunktelement](xref:System.ServiceModel.Configuration.StandardEndpointElement)

- [Verbesserungen der Dienstkonfiguration in .NET Framework 4](https://docs.microsoft.com/archive/blogs/endpoint/service-configuration-improvements-in-net-4)

- [Häufiger Benutzerfehler in .NET 4: Falsche Schreibweise des WF/WCF-Dienstkonfigurationsnamens](https://docs.microsoft.com/archive/blogs/endpoint/common-user-mistake-in-net-4-mistyping-the-wfwcf-service-configuration-name)

### <a name="simplified-configuration-scenarios"></a>Vereinfachte Konfigurationsszenarien

- Ein erfahrener ASMX-Entwickler möchte WCF verwenden. WCF scheint jedoch viel zu kompliziert! Er fragt sich, was das alles für Informationen sind, die in eine Konfigurationsdatei eingefügt werden müssen. In .NET 4 können Sie sich sogar entscheiden, überhaupt keine Konfigurationsdatei zu verwenden.

- Es ist sehr schwierig, einen vorhandenen Satz von WCF-Diensten zu konfigurieren und zu verwalten. Die Konfigurationsdatei enthält Tausende von XML-Codezeilen, und es kann sehr gefährlich sein, diese zu ändern. Es müsste eine Möglichkeit geben, diese vielen Codezeilen auf eine Menge zu reduzieren, die besser zu handhaben ist.

## <a name="data-contract-resolver"></a>Datenvertragsresolver

In .NET 3.5 gab es einige Einschränkungen beim Entwurf bekannter Typen:

- Es war nicht möglich, während der Serialisierung oder Deserialisierung bekannte Typen dynamisch hinzuzufügen.

- Serialisierungsprogramme konnten keine unbekannten xsi:type-Informationen behandeln.

- Benutzer konnten nicht angeben, welche xsi:type-Informationen erscheinen sollten, um z. B. die Serialisierungsinstanz zu verkleinern.

[DataContractResolver](../wcf/samples/datacontractresolver.md) löst diese Probleme in .NET 4.5.

### <a name="getting-started"></a>Erste Schritte

- [Dokumentation zur Datenvertragsresolver-API](xref:System.Runtime.Serialization.DataContractResolver)

- [Einführung in den Datenvertragsresolver](https://docs.microsoft.com/archive/blogs/youssefm/configuring-known-types-dynamically-introducing-the-datacontractresolver)

- Beispiele:

  - [DataContractResolver](../wcf/samples/datacontractresolver.md)

  - [KnownAssemblyAttribute](../wcf/samples/knownassemblyattribute.md)

### <a name="data-contract-resolver-scenarios"></a>Datenvertragsresolver-Szenarien

- Mit dem Datenvertragsresolver kann das Deklarieren von vielen <xref:System.Runtime.Serialization.KnownTypeAttribute>-Objekten in einem Dienst vermieden werden.

- Zudem trägt ein Datenvertragsresolver zum Reduzieren des XML-Blobs bei.

## <a name="flowchart"></a>Flussdiagramm

Ein Flussdiagramm ist ein bekanntes Paradigma, um Domänenprobleme visuell darzustellen. Es ist ein neuer Steuerungsflussstil, den wir in .NET 4 einführen. Ein Kernmerkmal des Flussdiagrammes ist, dass zu einem beliebigen Zeitpunkt immer nur eine Aktivität ausgeführt wird. In Flussdiagrammen können Schleifen und alternative Ergebnisse ausgedrückt werden, aber nicht die gleichzeitige Ausführung mehrerer Knoten.

### <a name="getting-started"></a>Erste Schritte

- Erstellen Sie in Visual Studio 2012 eine Workflowkonsolenanwendung. Fügen Sie im Workflow-Designer ein Flussdiagramm hinzu.

- Die Flussdiagrammfunktion verwendet die folgenden Klassen:

  - <xref:System.Activities.Statements.Flowchart>

  - <xref:System.Activities.Statements.FlowNode>

  - <xref:System.Activities.Statements.FlowDecision>

  - <xref:System.Activities.Statements.FlowStep>

  - <xref:System.Activities.Statements.FlowSwitch%601>

- Beispiele:

  - [Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

  - [Einstellungsprozess](./samples/hiring-process.md)

- Designerdokumentation:

  - [Flowchart-Aktivitätsdesigner](/visualstudio/workflow-designer/flowchart-activity-designers)

### <a name="flowchart-scenarios"></a>Flussdiagrammszenarien

Eine Flussdiagrammaktivität kann verwendet werden, um ein Ratespiel zu implementieren. Das Ratespiel ist sehr simpel: Der Computer wählt eine Zufallszahl aus, die der Spieler erraten muss. Wenn der Spieler jede Vermutung einreicht, zeigt ihnen der Computer einen Hinweis (d. h. "versuchen Sie eine niedrigere Zahl"). Wenn der Spieler die Zahl in weniger als 7 Versuchen findet, erhält er eine besondere Gratulation vom Computer. Dieses Spiel kann mit einer Kombination der folgenden Verfahrensaktivitäten implementiert werden:

- <xref:System.Activities.Statements.Sequence>

- <xref:System.Activities.Statements.While>

- <xref:System.Activities.Statements.Switch%601>

- <xref:System.Activities.Statements.TryCatch>

- <xref:System.Activities.Statements.Assign%601>

- <xref:System.Activities.Statements.If>

## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a>Verfahrensaktivitäten (Sequence, If, ForEach, Switch, Assign, DoWhile, While)

Verfahrensaktivitäten stellen einen Mechanismus bereit, um sequenzielle Ablaufsteuerung mit Konzepten zu modellieren, die Programmierern vertraut sind. Diese Aktivitäten ermöglichen traditionell strukturierte Programmiersprachenkonstrukte und bieten gegebenenfalls Die Sprachparität mit gängigen Verfahrenssprachen wie Z. C und Visual Basic.

### <a name="getting-started"></a>Erste Schritte

- Erstellen Sie in Visual Studio 2012 eine Workflowkonsolenanwendung. Fügen Sie im Workflow-Designer Verfahrensaktivitäten hinzu.

- Beispiele:

  - [Einstellungsprozess](./samples/hiring-process.md)

  - [Unternehmenseinkaufsprozess](./samples/corporate-purchase-process.md)

- Designerdokumentation:

  - [Parallel-Aktivitätsdesigner](/visualstudio/workflow-designer/parallel-activity-designer)

  - [ParallelForEach\<T> Aktivitäts-Designer](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)

### <a name="procedural-activity-scenarios"></a>Verfahrensaktivitätsszenarien

- <xref:System.Activities.Statements.Parallel>: Ein Intranetdokumentenverwaltungssystem verfügt über einen Dokumentgenehmigungsworkflow. Dokumente müssen von Personen in mehreren Abteilungen genehmigt werden, bevor sie im Intranet veröffentlicht werden können. Es gibt keine feste Reihenfolge für die Genehmigungen; Sie können jederzeit auftreten, während sich das Dokument in der Phase "Genehmigung ausstehend" befindet. Wenn ein Benutzer ein Dokument zur Überprüfung sendet, muss es von seinem direkten Manager, dem Intranetadministrator und dem internen Kommunikationsmanager genehmigt werden.

- <xref:System.Activities.Statements.ParallelForEach%601>: Eine WF-Anwendung verwaltet Unternehmenseinkäufe innerhalb eines großen Unternehmens. Die Unternehmensregeln schreiben vor, dass vor einem Kauf die Angebote von drei verschiedenen Anbietern eingeholt werden müssen. Ein Mitarbeiter der Einkaufsabteilung wählt drei Kreditoren aus der Kreditorenliste des Unternehmens aus. Nachdem diese Anbieter ausgewählt und benachrichtigt wurden, wartet das Unternehmen auf die Unterbreitung ihrer Angebote. Die Angebote können in beliebiger Reihenfolge eingehen. Zum Implementieren dieses Szenarios in WF wird eine <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität verwendet, die die Auflistung von Anbietern durchläuft und Angebote anfordert. Nachdem alle Angebote eingegangen sind, wird das beste Angebot ausgewählt und angezeigt.

## <a name="invokemethod"></a>InvokeMethod

Die <xref:System.Activities.Statements.InvokeMethod>-Aktivität erlaubt den Aufruf öffentlicher Methoden in Objekten oder Typen im Gültigkeitsbereich. Die Aktivität unterstützt den Aufruf von Instanz- und statischen Methoden mit oder ohne Parameter (einschließlich Parameterarrays) und generischen Methoden. Zudem erlaubt sie eine synchrone und asynchrone Methodenausführung.

### <a name="getting-started"></a>Erste Schritte

- Erstellen Sie in Visual Studio 2012 eine Workflowkonsolenanwendung. Fügen Sie eine <xref:System.Activities.Statements.InvokeMethod>-Aktivität im Workflow-Designer hinzu, und konfigurieren Sie statische und Instanzmethoden für die Aktivität.

- Designerdokumentation: [InvokeMethod-Aktivitäts-Designer](/visualstudio/workflow-designer/invokemethod-activity-designer)

### <a name="invokemethod-scenarios"></a>InvokeMethod-Szenarien

- Eine Methode in einem Objekt im Gültigkeitsbereich muss aufgerufen werden. Beispielsweise muss einem Wörterbuch ein Wert hinzugefügt werden. Die Add-Methode der Instanz des Wörterbuchs wird aufgerufen, und der Schlüssel und der Wert werden bereitgestellt.

- Für ein Legacy-CLR-Objekt muss eine Methode aufgerufen werden. Anstatt eine benutzerdefinierte Aktivität zu erstellen, um den Aufruf dieser Legacyklasse zu umschließen, wenn es sich während der Workflowausführung im Gültigkeitsbereich befindet, kann <xref:System.Activities.Statements.InvokeMethod> verwendet werden.

## <a name="error-handling-activities"></a>Fehlerbehandlungsaktivitäten

Die <xref:System.Activities.Statements.TryCatch> Aktivität stellt einen Mechanismus zum Abfangen von Ausnahmen bereit, die während der Ausführung einer Reihe enthaltener Aktivitäten auftreten (ähnlich dem Try/Catch-Konstrukt in C- und Visual Basic). <xref:System.Activities.Statements.TryCatch> stellt eine Ausnahmebehandlung auf Workflowebene bereit. Wenn eine nicht behandelte Ausnahme ausgelöst wird, wird der Workflow abgebrochen, und der Finally-Block wird nicht ausgeführt. Dieses Verhalten ist mit C# konsistent.

### <a name="getting-started"></a>Erste Schritte

- Erstellen Sie in Visual Studio 2012 eine Workflowkonsolenanwendung. Fügen Sie im Workflow-Designer eine <xref:System.Activities.Statements.TryCatch>-Aktivität hinzu.

- Beispiel: [Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

- Designerdokumentation: [Fehlerbehandlungsaktivitätsdesigner](/visualstudio/workflow-designer/error-handling-activity-designers)

### <a name="error-handling-scenarios"></a>Fehlerbehandlungsszenarien

Wenn ein Fehler auftritt, müssen ein Satz von Aktivitäten und eine bestimmte Logik ausgeführt werden. Wenn während dieser Fehlerbehandlung festgestellt wird, dass der Fehler nicht behoben werden kann, wird die Ausnahme erneut ausgelöst, und die übergeordnete Aktivität (oder der Host) befasst sich mit dem Problem.

## <a name="pick-activity"></a>Auswählen der Aktivität

Die <xref:System.Activities.Statements.Pick>-Aktivität stellt eine ereignisbasierte Flusssteuerungsmodellierung in WF bereit. <xref:System.Activities.Statements.Pick> enthält zahlreiche Verzweigungen, wobei jede Verzweigung vor ihrer Ausführung auf ein bestimmtes Ereignis wartet. In diesem Setup verhält sich ein <xref:System.Activities.Statements.Pick> ähnlich wie ein <xref:System.Activities.Statements.Switch%601>, für den die Aktivität nur einen der überwachten Ereignissätze ausführt. Jeder Branch ist ereignisgesteuert, und das Ereignis, das zuerst auftritt, führt zuerst den entsprechende Branch aus. Alle anderen Verzweigungen werden abgebrochen, und die Überwachung der Ereignisse wird beendet.

### <a name="getting-started"></a>Erste Schritte

- Erstellen Sie in Visual Studio 2012 eine Workflowkonsolenanwendung. Fügen Sie im Workflow-Designer eine <xref:System.Activities.Statements.Pick>-Aktivität hinzu.

- Beispiel: [Verwenden der Pick-Aktivität](./samples/using-the-pick-activity.md)

- Designerdokumentation: [Aktivitäts-Designer auswählen](/visualstudio/workflow-designer/pick-activity-designer)

### <a name="pick-scenario"></a>Auswahlszenario

Ein Benutzer muss zur Eingabe aufgefordert werden. Unter normalen Umständen verwendet der Entwickler <xref:System.Console.ReadLine%2A> einen Methodenaufruf, der z. B. zur Eingabe eines Benutzers auffordert. Das Problem bei diesem Setup ist, dass das Programm wartet, bis der Benutzer etwas eingibt. In diesem Szenario wird ein Timeout benötigt, um die Blockierung einer blockierenden Aktivität aufzuheben. Ein häufiges Szenario ist, dass eine Aufgabe innerhalb einer bestimmte Zeitspanne abgeschlossen werden muss. Das Umsetzen eines Timeouts für eine blockierende Aktivität ist ein Szenario, bei dem eine Auswahl sehr nützlich ist.

## <a name="wcf-routing-service"></a>WCF-Routingdienst

Der Routingdienst ist als generischer Softwarerouter konzipiert, mit dem Sie steuern können, wie WCF-Nachrichten zwischen Ihren Clients und Diensten fließen. Mit dem Routing-Service können Sie Ihre Clients von Ihren Diensten entkoppeln, was Ihnen viel mehr Freiheit in Bezug auf die Konfigurationen gibt, die Sie unterstützen können, und die Flexibilität, die Sie haben, wenn Sie überlegen, wie Sie Ihre Dienste hosten sollen. In .NET 3.5 waren Clients und Dienste eng miteinander verknüpft. ein Kunde musste über alle Dienstleistungen, mit denen er sprechen musste, und wissen, wo sie sich befanden. Darüber hinaus hatte WCF in .NET Framework 3.5 die folgenden Einschränkungen:

- Die Fehlerbehandlung war komplex, da diese Logik fest in den Client codiert werden musste.

- Clients und Dienste mussten immer die gleichen Bindungen verwenden.

- Dienste waren selten gut aufgeteilt: Es ist einfacher, eine Clientinteraktion mit nur einem Dienst umzusetzen, der alles implementiert, anstatt zwischen mehreren Diensten auswählen zu müssen.

Der Routingdienst in .NET 4 wurde entwickelt, um die Lösung dieser Probleme zu vereinfachen. Der neue Routingdienst hat die folgenden Funktionen:

1. Inhaltsbasiertes Routing (<xref:System.ServiceModel.Dispatcher.MessageFilter>-Objekte untersuchen eine Nachricht, um das Ziel der Nachricht zu ermitteln.

2. Protokollüberbrückung (Transport & Nachricht)

3. Fehlerbehandlung (der Router fängt Kommunikationsausnahmen ab und führt ein Failover zu Sicherungsendpunkten aus)

4. Dynamische Aktualisierung (im Speicher) von <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> und Routingkonfiguration.

### <a name="getting-started"></a>Erste Schritte

1. Dokumentation: [Routing](../wcf/feature-details/routing.md)

2. Beispiele: [Routingdienste &#91;&#93;von WCF-Beispielen](../wcf/samples/routing-services.md)

3. Blog: [Routing-Regeln!](https://docs.microsoft.com/archive/blogs/RoutingRules/)

### <a name="routing-scenarios"></a>Routingszenarien

Der Routingdienst ist in den folgenden Szenarien nützlich:

- Clients können mit mehreren Diensten interagieren, ohne alle diese Dienste direkt adressieren zu müssen.

- Clients können zusätzliche Logik für eine Clientanforderung ausführen, um das Routingziel zu bestimmen

- Die von einem Client durchgeführten Vorgänge können in mehrere Dienstimplementierungen zerlegt werden, ohne dass ein Refactoring des Clients erforderlich ist.

- Clients und Dienste können unterschiedliche Bindungen mit verschiedenen Sicherheitseinstellungen verwenden.

- Clients können so konfiguriert werden, dass sie stabiler gegenüber Fehlern oder der Nichtverfügbarkeit von Diensten sind.

## <a name="wcf-discovery"></a>WCF-Suche

WCF Discovery ist eine Frameworktechnologie, mit der Sie einen Erkennungsmechanismus in Ihre Anwendungsinfrastruktur integrieren können. Mit WCF-Suche können Sie sicherstellen, dass Ihr Dienst ermittelt werden kann, und Ihre Clients für die Suche nach Diensten konfigurieren. Clients müssen nicht mehr mit einem Endpunkt hartcodiert werden, sodass die Anwendung stabiler und fehlertolerant wird. WCF-Suche ist die perfekte Plattform, um Funktionen für die automatische Konfiguration in die Anwendung zu integrieren.

Das Produkt basiert auf dem WS-Discovery-Standard. Es ist so konzipiert, dass es interoperabel, erweiterbar und allgemein ist. Es unterstützt zwei Betriebsmodi:

1. Verwaltet: Gibt es im Netzwerk eine Entität, die über die vorhandenen Dienste informiert ist, fordern Clients von dieser Entität direkt Informationen an. Dies ist analog zu Active Directory.

2. Ad-hoc: Clients verwenden Multicastnachrichten, um Dienste zu suchen.

Darüber hinaus sind Ermittlungsnachrichten unabhängig vom Netzwerkprotokoll. Sie können für jedes Protokoll verwendet werden, das die Modusanforderungen unterstützt. Beispielsweise können Erkennungsmulticastnachrichten über den UDP-Kanal oder ein anderes Netzwerk gesendet werden, das Multicastnachrichten unterstützt. Diese Designpunkte in Kombination mit Der Funktionsflexibilität ermöglichen es Ihnen, die Entdeckung speziell an Ihre Lösung anzupassen.

### <a name="getting-started"></a>Erste Schritte

- Dokumentation: [WCF Discovery](../wcf/feature-details/wcf-discovery.md)

- Beispiele: [Ermittlung (Beispiele)](../wcf/samples/discovery-samples.md)

### <a name="discovery-scenarios"></a>Suchszenarien

Ein Entwickler möchte Endpunkte nicht hartcodieren, da noch nicht feststeht, wann der Dienst verfügbar ist. Stattdessen möchte der Entwickler zur Laufzeit einen Dienst auswählen. Zwischen den Komponenten in der Anwendung ist ein höheres Maß an Entkopplung, Stabilität und automatischer Konfiguration erforderlich.

## <a name="tracking"></a>Tracking

Die Workflow-Nachverfolgung bietet Einblicke in die Ausführung einer Workflowinstanz. Die Nachverfolgungsereignisse werden von einem Workflow auf Workflowinstanzebene und bei der Ausführung von Aktivitäten innerhalb des Workflows emittiert. Dem Workflowhost muss eine Workflownachverfolgungskomponente hinzugefügt werden, um Nachverfolgungsdatensätze zu abonnieren. Die Nachverfolgungsdatensätze werden mit einem Nachverfolgungsprofil gefiltert. .NET Framework stellt einen ETW-Tracking-Teilnehmer (Event Tracing for Windows) bereit, und in der Datei machine.config ist ein Basisprofil installiert.

### <a name="getting-started"></a>Erste Schritte

1. Erstellen Sie in Visual Studio 2010 ein Projekt für eine Dienstanwendung für WCF-Workflows. Um mit der Projekterstellung zu beginnen, werden <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> auf dem Canvas platziert.

2. Öffnen Sie die Datei "web.config", und fügen Sie ein ETW-Nachverfolgungsverhalten ohne Profil hinzu.

    1. Das Standardprofil wird verwendet.

    2. Öffnen Sie die Ereignisanzeige, und aktivieren Sie den Analysekanal im folgenden Knoten: **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows**, **Application Server-Applications**. Klicken Sie mit der rechten Maustaste auf **Analytic,** und wählen Sie **Protokoll aktivieren**aus.

    3. Führen Sie den Workflowdienst aus.

    4. Beobachten Sie die Workflownachverfolgungsereignisse in der Ereignisanzeige.

3. Beispiele: [Tracking](./samples/tracking.md)

4. Konzeptionelle Dokumentation: [Workflow-Tracking und -Ablaufverfolgung](workflow-tracking-and-tracing.md)

## <a name="sql-workflow-instance-store"></a>SQL-Workflowinstanzspeicher

Beim <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> handelt es sich um die SQL Server-basierte Implementierung eines Instanzspeichers. Ein Instanzspeicher speichert den Zustand einer ausgeführten Instanz zusammen mit allen Daten, die zum Laden und Fortsetzen dieser Instanz erforderlich sind. Der Diensthost weist den Instanzspeicher an, den Instanzzustand zu speichern, wenn der Workflow beibehalten wird. Wenn für diese Instanz eine Nachricht eingeht oder eine Verzögerungsaktivität abläuft, weist der Diensthost den Instanzspeicher an, den Instanzzustand zu laden.

### <a name="getting-started"></a>Erste Schritte

1. Erstellen Sie in Visual Studio 2012 einen <xref:System.Activities.Statements.Persist> Workflow, der eine implizite oder explizite Aktivität enthält. Fügen Sie dem Workflowdiensthost das <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Verhalten hinzu. Sie können die Aktivität dem Code oder der Anwendungskonfiguration hinzufügen.

2. Beispiele: [Persistenz](/previous-versions/dotnet/netframework-4.0/dd699769(v%3dvs.100))

3. Konzeptionelle Dokumentation: [SQL Workflow Instance Store](sql-workflow-instance-store.md).
