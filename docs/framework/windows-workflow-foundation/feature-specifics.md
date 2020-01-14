---
title: Windows Workflow Foundation-Funktionsdetails
ms.date: 03/30/2017
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
ms.openlocfilehash: 197b2e0d6586e001a4970cf8cb3f8e6b2a372af2
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75936795"
---
# <a name="windows-workflow-foundation-feature-specifics"></a>Windows Workflow Foundation-Funktionsdetails

.NET Framework 4 fügt Windows Workflow Foundation eine Reihe von Features hinzu. In diesem Dokument wird eine Reihe neuer Funktionen beschrieben. Darüber hinaus enthält das Dokument detaillierte Informationen zu den Szenarien, in denen sie möglicherweise nützlich sind.

## <a name="messaging-activities"></a>Messagingaktivitäten

Die Messaging Aktivitäten (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.ReceiveReply>) werden verwendet, um WCF-Nachrichten aus dem Workflow zu senden und zu empfangen. <xref:System.ServiceModel.Activities.Receive>-und <xref:System.ServiceModel.Activities.SendReply> Aktivitäten werden verwendet, um einen Windows Communication Foundation (WCF)-Dienst Vorgang zu bilden, der wie Standard-WCF-Webdienste über WSDL verfügbar gemacht wird. <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.ReceiveReply> werden verwendet, um einen Webdienst zu nutzen, der einem WCF-<xref:System.ServiceModel.ChannelFactory>ähnelt; eine **Dienstverweis hinzufügen** -Darstellung ist auch für Workflow Foundation vorhanden, die vorkonfigurierte Aktivitäten generiert.

### <a name="getting-started-with-messaging-activities"></a>Erste Schritte mit Messagingaktivitäten

- Erstellen Sie in Visual Studio 2012 ein WCF-Workflow Dienst-Anwendungsprojekt. Das Paar <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> wird auf dem Canvas platziert.

- Klicken Sie mit der rechten Maustaste auf das Projekt, und wählen Sie **Dienstverweis hinzufügen**. Zeigen Sie auf eine vorhandene WSDL-Webdienst, und klicken Sie auf **OK**. Erstellen Sie das Projekt, um die generierten Aktivitäten (implementiert mithilfe von <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.ReceiveReply>) in der Toolbox anzuzeigen.

- [Dokumentation zu Workflow Diensten](../wcf/feature-details/workflow-services.md)

### <a name="messaging-activities-example-scenario"></a>Beispielszenario für Messagingaktivitäten

Ein `BestPriceFinder`-Dienst ruft bei mehreren Fluggesellschaften Dienste auf, um den besten Ticketpreis für eine bestimmte Route zu ermitteln. Das Implementieren dieses Szenarios erfordert, dass Sie die Nachrichten Aktivitäten verwenden, um die Preis Anforderung zu empfangen, die Preise von den Back-End-Diensten abzurufen und auf die Preis Anforderung mit dem besten Preis zu antworten. Außerdem müssen Sie andere Out-of-Box-Aktivitäten verwenden, um die Geschäftslogik zum Berechnen des besten Preises zu erstellen.

## <a name="workflowservicehost"></a>WorkflowServiceHost

Der <xref:System.ServiceModel.WorkflowServiceHost> ist der Out-of-Box-Workflow Host, der mehrere Instanzen, Konfigurationen und WCF-Messaging unterstützt (obwohl die Workflows nicht für die Verwendung von Messaging erforderlich sind, um gehostet zu werden). Außerdem wird durch einen Satz von Dienstverhalten die Integration von Persistenz, Nachverfolgung und Instanzsteuerung bereitgestellt. Ebenso wie der <xref:System.ServiceModel.ServiceHost>von WCF können die <xref:System.ServiceModel.WorkflowServiceHost> in einer Konsolen-/WinForms-/WPF-Anwendung oder einem Windows-Dienst oder im Internet gehostet (als xamlx-Datei) in IIS oder was selbst gehostet werden.

### <a name="getting-started-with-workflow-service-host"></a>Erste Schritte mit dem Workflowdiensthost

- Erstellen Sie in Visual Studio 2010 ein WCF-Workflow Dienst-Anwendungsprojekt: dieses Projekt wird für die Verwendung von <xref:System.ServiceModel.WorkflowServiceHost> in einer Webhost Umgebung eingerichtet.

- Zum Hosten eines Nicht-Messaging-Workflows fügen Sie einen benutzerdefinierten <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> hinzu, der die Instanz auf Grundlage einer Nachricht erstellt.

- Workflowinstanzen können gesteuert (z. B.angehalten oder beendet) werden, indem <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> ein <xref:System.ServiceModel.WorkflowServiceHost> hinzugefügt und anschließend ein <xref:System.ServiceModel.Activities.WorkflowControlClient> verwendet wird.

- Beispiele für <xref:System.ServiceModel.WorkflowServiceHost> finden Sie in den folgenden Abschnitten:

  - [Ausführung](./samples/execution.md)

  - Anwendung: angehaltene [Instanzverwaltung](./samples/suspended-instance-management.md)

- [Übersicht über das Hosting von Workflow Diensten](../wcf/feature-details/hosting-workflow-services-overview.md)

### <a name="workflowservicehost-scenario"></a>WorkflowServiceHost-Szenario

Ein Best Price Finder-Dienst ruft bei mehreren Fluggesellschaften Dienste auf, um den besten Ticketpreis für eine bestimmte Route zu ermitteln. Das Implementieren dieses Szenarios erfordert, dass Sie den Workflow in <xref:System.ServiceModel.WorkflowServiceHost>hosten. Außerdem werden die Nachrichten Aktivitäten verwendet, um die Preis Anforderung zu empfangen, die Preise von den Back-End-Diensten abzurufen und auf die Preis Anforderung mit dem besten Preis zu antworten.

## <a name="correlation"></a>Korrelation

Eine Korrelation kann wie folgt definiert werden:

- Eine Möglichkeit zum Gruppieren von Nachrichten, d. h. die Beziehung zwischen einer Anforderungsnachricht und der dazugehörigen Antwort

- Eine Möglichkeit, ein Datenelement einer Dienstinstanz zuzuordnen

### <a name="getting-started"></a>Erste Schritte

- Erstellen Sie in Visual Studio ein neues Projekt, um mit der Korrelation zu beginnen. Erstellen Sie eine Variable vom Typ <xref:System.ServiceModel.Activities.CorrelationHandle>.

- Ein Beispiel für die Verwendung einer Korrelation zum Gruppieren von Nachrichten ist eine Anforderung/Antwort-Korrelation, die Nachrichten zusammen gruppiert.

  - Klicken Sie bei einer <xref:System.ServiceModel.Activities.Receive> Aktivität auf die Eigenschaft <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>, und fügen Sie mithilfe des correlationhandle, das Sie im ersten Schritt oben erstellt haben, eine <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> hinzu.

  - Erstellen Sie eine <xref:System.ServiceModel.Activities.SendReply> Aktivität, indem Sie mit der rechten Maustaste auf die <xref:System.ServiceModel.Activities.Receive> klicken und dann auf "SendReply erstellen" klicken. Fügen Sie die Aktivität hinter der <xref:System.ServiceModel.Activities.Receive>-Aktivität in den Workflow ein.

- Ein Beispiel für die Zuordnung eines Datenelements zu einer Dienstinstanz ist die inhaltsbasierte Korrelation, bei der ein Datenelement (z. B. eine Auftrags-ID) einer bestimmten Workflowinstanz zugeordnet wird.

  - Klicken Sie auf die `CorrelationInitializers`-Eigenschaft einer Messagingaktivität, und fügen Sie mit der oben erstellten <xref:System.ServiceModel.Activities.QueryCorrelationInitializer>-Variable einen <xref:System.ServiceModel.Activities.CorrelationHandle> hinzu. Doppelklicken Sie im Dropdownmenü auf die gewünschte Eigenschaft der Nachricht (z. B. "OrderID"). Legen Sie die `CorrelatesWith`-Eigenschaft auf die oben verwendete <xref:System.ServiceModel.Activities.CorrelationHandle>-Variable fest.

- [Dokumentation zu Korrelations Konzepten](../wcf/feature-details/correlation.md)

### <a name="correlation-scenario"></a>Korrelationsszenario

Ein Auftrags Verarbeitungs Workflow wird verwendet, um die Erstellung neuer Aufträge zu verarbeiten und vorhandene Aufträge zu aktualisieren, die gerade verarbeitet werden. Das Implementieren dieses Szenarios erfordert, dass Sie den Workflow in <xref:System.ServiceModel.WorkflowServiceHost> hosten und die Messaging Aktivitäten verwenden. Außerdem ist eine Korrelation auf Grundlage der `orderId` erforderlich, um sicherzustellen, dass Aktualisierungen am richtigen Workflow vorgenommen werden.

## <a name="simplified-configuration"></a>Vereinfachte Konfiguration

Das WCF-Konfigurations Schema ist komplex und bietet Benutzern viele schwer zu suchende Features. In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)]haben wir uns auf die Unterstützung von WCF-Benutzern bei der Konfiguration Ihrer Dienste mit den folgenden Features konzentriert:

- Es ist keine explizite Einzeldienstkonfiguration mehr notwendig. Wenn Sie keine \<Dienst > Elemente für den Dienst konfigurieren und der Dienst keinen Endpunkt Programm gesteuert definiert, wird dem Dienst automatisch ein Satz von Endpunkten hinzugefügt, einer pro Dienst Basisadresse und pro Vertrag, der vom Dienst implementiert wird.

- Der Benutzer kann Standardwerte für WCF-Bindungen und -Verhalten definieren, die ohne explizite Konfiguration auf Dienste angewendet werden.

- Standardendpunkte definieren wiederverwendbare vorkonfigurierte Endpunkte, die feste Werte für mindestens eine Endpunkteigenschaft besitzen (Adresse, Bindung und Vertrag) und die die Definition benutzerdefinierter Eigenschaften erlauben.

- Schließlich können Sie mit dem <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> die zentrale Verwaltung der WCF-Client Konfiguration durchführen. Dies ist nützlich in Szenarien, in denen die Konfiguration nach der Ladezeit der Anwendungsdomäne ausgewählt oder geändert wird.

### <a name="getting-started"></a>Erste Schritte

- [Entwicklerhandbuch zu WCF 4,0](https://docs.microsoft.com/previous-versions/dotnet/articles/ee354381(v=msdn.10))

- [Konfigurationskanalfactory](xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601)

- [Standard Endpunkt Element](xref:System.ServiceModel.Configuration.StandardEndpointElement)

- [Verbesserungen der Dienst Konfiguration in .NET Framework 4](https://docs.microsoft.com/archive/blogs/endpoint/service-configuration-improvements-in-net-4)

- [Häufige Benutzerfehler in .NET 4: falsch formatiping des WF/WCF-Dienst Konfigurations namens](https://docs.microsoft.com/archive/blogs/endpoint/common-user-mistake-in-net-4-mistyping-the-wfwcf-service-configuration-name)

### <a name="simplified-configuration-scenarios"></a>Vereinfachte Konfigurationsszenarien

- Ein erfahrener ASMX-Entwickler möchte zunächst WCF verwenden. WCF scheint jedoch zu kompliziert zu werden! Er fragt sich, was das alles für Informationen sind, die in eine Konfigurationsdatei eingefügt werden müssen. In .NET 4 können Sie sich sogar entscheiden, überhaupt keine Konfigurationsdatei zu verwenden.

- Es ist sehr schwierig, einen vorhandenen Satz von WCF-Diensten zu konfigurieren und zu verwalten. Die Konfigurationsdatei enthält Tausende von XML-Codezeilen, und es kann sehr gefährlich sein, diese zu ändern. Es müsste eine Möglichkeit geben, diese vielen Codezeilen auf eine Menge zu reduzieren, die besser zu handhaben ist.

## <a name="data-contract-resolver"></a>Datenvertragsresolver

In .NET 3.5 gab es einige Einschränkungen beim Entwurf bekannter Typen:

- Es war nicht möglich, während der Serialisierung oder Deserialisierung bekannte Typen dynamisch hinzuzufügen.

- Serialisierungsprogramme konnten keine unbekannten xsi:type-Informationen behandeln.

- Benutzer konnten nicht angeben, welche xsi:type-Informationen erscheinen sollten, um z. B. die Serialisierungsinstanz zu verkleinern.

Der [DataContractResolver](../wcf/samples/datacontractresolver.md) löst diese Probleme in .NET 4,5.

### <a name="getting-started"></a>Erste Schritte

- [Dokumentation zur datenvertragsresolver-API](xref:System.Runtime.Serialization.DataContractResolver)

- [Einführung in den datenvertragsresolver](https://docs.microsoft.com/archive/blogs/youssefm/configuring-known-types-dynamically-introducing-the-datacontractresolver)

- Beispiele:

  - [DataContractResolver](../wcf/samples/datacontractresolver.md)

  - [KnownAssemblyAttribute](../wcf/samples/knownassemblyattribute.md)

### <a name="data-contract-resolver-scenarios"></a>Datenvertragsresolver-Szenarien

- Mit dem Datenvertragsresolver kann das Deklarieren von vielen <xref:System.Runtime.Serialization.KnownTypeAttribute>-Objekten in einem Dienst vermieden werden.

- Zudem trägt ein Datenvertragsresolver zum Reduzieren des XML-Blobs bei.

## <a name="flowchart"></a>Flussdiagramm

Ein Flussdiagramm ist ein bekanntes Paradigma, um Domänenprobleme visuell darzustellen. Es ist ein neues Ablaufsteuerungsformat, das in .NET 4 eingeführt wird. Ein Kernmerkmal des Flussdiagrammes ist, dass zu einem beliebigen Zeitpunkt immer nur eine Aktivität ausgeführt wird. In Flussdiagrammen können Schleifen und alternative Ergebnisse ausgedrückt werden, aber nicht die gleichzeitige Ausführung mehrerer Knoten.

### <a name="getting-started"></a>Erste Schritte

- Erstellen Sie in Visual Studio 2012 eine Workflow Konsolenanwendung. Fügen Sie im Workflow-Designer ein Flussdiagramm hinzu.

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

  - [Flussdiagramm-Aktivitätsdesigner](/visualstudio/workflow-designer/flowchart-activity-designers)

### <a name="flowchart-scenarios"></a>Flussdiagrammszenarien

Eine Flussdiagrammaktivität kann verwendet werden, um ein Ratespiel zu implementieren. Das Ratespiel ist sehr simpel: Der Computer wählt eine Zufallszahl aus, die der Spieler erraten muss. Wenn der Spieler die einzelnen Raten übermittelt, zeigt der Computer einen Hinweis an (d. h. "try a Lower Number"). Wenn der Spieler die Zahl in weniger als 7 Versuchen errät, zeigt der Computer einen besonderen Glückwunsch an. Dieses Spiel kann mit einer Kombination der folgenden Verfahrensaktivitäten implementiert werden:

- <xref:System.Activities.Statements.Sequence>

- <xref:System.Activities.Statements.While>

- <xref:System.Activities.Statements.Switch%601>

- <xref:System.Activities.Statements.TryCatch>

- <xref:System.Activities.Statements.Assign%601>

- <xref:System.Activities.Statements.If>

## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a>Verfahrensaktivitäten (Sequence, If, ForEach, Switch, Assign, DoWhile, While)

Verfahrensaktivitäten stellen einen Mechanismus bereit, um sequenzielle Ablaufsteuerung mit Konzepten zu modellieren, die Programmierern vertraut sind. Mit diesen Aktivitäten werden traditionell strukturierte programmierungssprachkonstrukte ermöglicht und, falls zutreffend, die sprach Parität mit gängigen C# prozeduralen Sprachen wie und Visual Basic bereitgestellt.

### <a name="getting-started"></a>Erste Schritte

- Erstellen Sie in Visual Studio 2012 eine Workflow Konsolenanwendung. Fügen Sie im Workflow-Designer Verfahrensaktivitäten hinzu.

- Beispiele:

  - [Einstellungsprozess](./samples/hiring-process.md)

  - [Unternehmenseinkaufsprozess](./samples/corporate-purchase-process.md)

- Designerdokumentation:

  - [Parallel-Aktivitätsdesigner](/visualstudio/workflow-designer/parallel-activity-designer)

  - [ParallelForEach-\<t > Aktivitäts Designer](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)

### <a name="procedural-activity-scenarios"></a>Verfahrensaktivitätsszenarien

- <xref:System.Activities.Statements.Parallel>: ein intranetdokumentverwaltungs-System verfügt über einen Workflow für die Dokument Genehmigung. Dokumente müssen von Personen in mehreren Abteilungen genehmigt werden, bevor sie im Intranet veröffentlicht werden können. Es gibt keine festgelegte Reihenfolge für die Genehmigungen. Sie können jederzeit auftreten, während sich das Dokument in der Phase "Genehmigung Ausstehend" befindet. Wenn ein Benutzer ein Dokument zwecks Überprüfung übermittelt, muss es vom direkten Vorgesetzten des Benutzers, dem Intranetadministrator und dem Leiter der internen Kommunikation genehmigt werden.

- <xref:System.Activities.Statements.ParallelForEach%601>: Eine WF-Anwendung verwaltet Unternehmenseinkäufe innerhalb eines großen Unternehmens. Die Unternehmensregeln schreiben vor, dass vor einem Kauf die Angebote von drei verschiedenen Anbietern eingeholt werden müssen. Ein Mitarbeiter der Einkaufsabteilung wählt drei Anbieter aus der Anbieterliste des Unternehmens aus. Nachdem diese Anbieter ausgewählt und benachrichtigt wurden, wartet das Unternehmen auf die Unterbreitung ihrer Angebote. Die Angebote können in beliebiger Reihenfolge eingehen. Zum Implementieren dieses Szenarios in WF wird eine <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität verwendet, die die Auflistung von Anbietern durchläuft und Angebote anfordert. Nachdem alle Angebote eingegangen sind, wird das beste Angebot ausgewählt und angezeigt.

## <a name="invokemethod"></a>InvokeMethod

Die <xref:System.Activities.Statements.InvokeMethod>-Aktivität erlaubt den Aufruf öffentlicher Methoden in Objekten oder Typen im Gültigkeitsbereich. Die Aktivität unterstützt den Aufruf von Instanz- und statischen Methoden mit oder ohne Parameter (einschließlich Parameterarrays) und generischen Methoden. Zudem erlaubt sie eine synchrone und asynchrone Methodenausführung.

### <a name="getting-started"></a>Erste Schritte

- Erstellen Sie in Visual Studio 2012 eine Workflow Konsolenanwendung. Fügen Sie eine <xref:System.Activities.Statements.InvokeMethod>-Aktivität im Workflow-Designer hinzu, und konfigurieren Sie statische und Instanzmethoden für die Aktivität.

- Designer-Dokumentation: [InvokeMethod-Aktivitäts Designer](/visualstudio/workflow-designer/invokemethod-activity-designer)

### <a name="invokemethod-scenarios"></a>InvokeMethod-Szenarien

- Eine Methode in einem Objekt im Gültigkeitsbereich muss aufgerufen werden. Beispielsweise muss einem Wörterbuch ein Wert hinzugefügt werden. Die Add-Methode der Instanz des Wörterbuchs wird aufgerufen, und der Schlüssel und der Wert werden bereitgestellt.

- Für ein Legacy-CLR-Objekt muss eine Methode aufgerufen werden. Anstatt eine benutzerdefinierte Aktivität zu erstellen, um den Aufruf dieser Legacyklasse zu umschließen, wenn es sich während der Workflowausführung im Gültigkeitsbereich befindet, kann <xref:System.Activities.Statements.InvokeMethod> verwendet werden.

## <a name="error-handling-activities"></a>Fehlerbehandlungsaktivitäten

Die <xref:System.Activities.Statements.TryCatch>-Aktivität stellt einen Mechanismus zum Abfangen von Ausnahmen bereit, die während der Ausführung eines Satzes enthaltener Aktivitäten auftreten (vergleichbar mit dem Try C# /Catch-Konstrukt in und Visual Basic). <xref:System.Activities.Statements.TryCatch> stellt eine Ausnahmebehandlung auf Workflowebene bereit. Wenn eine nicht behandelte Ausnahme ausgelöst wird, wird der Workflow abgebrochen, und der Finally-Block wird nicht ausgeführt. Dieses Verhalten ist mit C# konsistent.

### <a name="getting-started"></a>Erste Schritte

- Erstellen Sie in Visual Studio 2012 eine Workflow Konsolenanwendung. Fügen Sie im Workflow-Designer eine <xref:System.Activities.Statements.TryCatch>-Aktivität hinzu.

- Beispiel: [Fehlerbehandlung in einer Flussdiagramm Aktivität mit trycatch](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

- Designer-Dokumentation: [Aktivitäts Designer für die Fehlerbehandlung](/visualstudio/workflow-designer/error-handling-activity-designers)

### <a name="error-handling-scenarios"></a>Fehlerbehandlungsszenarien

Wenn ein Fehler auftritt, müssen ein Satz von Aktivitäten und eine bestimmte Logik ausgeführt werden. Wenn während dieser Fehlerbehandlung festgestellt wird, dass der Fehler nicht behoben werden kann, wird die Ausnahme erneut ausgelöst, und die übergeordnete Aktivität (oder der Host) befasst sich mit dem Problem.

## <a name="pick-activity"></a>Auswählen der Aktivität

Die <xref:System.Activities.Statements.Pick>-Aktivität stellt eine ereignisbasierte Flusssteuerungsmodellierung in WF bereit. <xref:System.Activities.Statements.Pick> enthält zahlreiche Verzweigungen, wobei jede Verzweigung vor ihrer Ausführung auf ein bestimmtes Ereignis wartet. In diesem Setup verhält sich ein <xref:System.Activities.Statements.Pick> ähnlich wie ein <xref:System.Activities.Statements.Switch%601>, für den die Aktivität nur einen der überwachten Ereignissätze ausführt. Jeder Branch ist ereignisgesteuert, und das Ereignis, das zuerst auftritt, führt zuerst den entsprechende Branch aus. Alle anderen Verzweigungen werden abgebrochen, und die Überwachung der Ereignisse wird beendet.

### <a name="getting-started"></a>Erste Schritte

- Erstellen Sie in Visual Studio 2012 eine Workflow Konsolenanwendung. Fügen Sie im Workflow-Designer eine <xref:System.Activities.Statements.Pick>-Aktivität hinzu.

- Beispiel: [Verwenden der Pick-Aktivität](./samples/using-the-pick-activity.md)

- Designer-Dokumentation: [Pick-Aktivitäts Designer](/visualstudio/workflow-designer/pick-activity-designer)

### <a name="pick-scenario"></a>Auswahlszenario

Ein Benutzer muss zur Eingabe aufgefordert werden. Unter normalen Umständen würde der Entwickler einen Methodenaufruf wie <xref:System.Console.ReadLine%2A> verwenden, um einen Benutzer zur Eingabe aufzufordern. Das Problem bei diesem Setup ist, dass das Programm wartet, bis der Benutzer etwas eingibt. In diesem Szenario wird ein Timeout benötigt, um die Blockierung einer blockierenden Aktivität aufzuheben. Ein häufiges Szenario ist, dass eine Aufgabe innerhalb einer bestimmte Zeitspanne abgeschlossen werden muss. Das Umsetzen eines Timeouts für eine blockierende Aktivität ist ein Szenario, bei dem eine Auswahl sehr nützlich ist.

## <a name="wcf-routing-service"></a>WCF-Routingdienst

Der Routing Dienst ist als generischer Software Router konzipiert, mit dem Sie steuern können, wie WCF-Nachrichten zwischen Clients und Diensten fließen. Der Routing Dienst ermöglicht es Ihnen, Ihre Clients von Ihren Diensten zu entkoppeln, was Ihnen viel mehr Freiheit in Bezug auf die von Ihnen unterstützten Konfigurationen und die Flexibilität bietet, die Sie bei der Planung ihrer Dienste erreichen können. In .NET 3,5 waren Clients und Dienste eng gekoppelt. ein Client musste sich über alle Dienste informieren, mit denen er kommunizieren musste und wo Sie sich befinden. Außerdem wies WCF in .NET Framework 3,5 die folgenden Einschränkungen auf:

- Die Fehlerbehandlung war komplex, da diese Logik fest in den Client codiert werden musste.

- Clients und Dienste mussten immer die gleichen Bindungen verwenden.

- Dienste waren selten gut aufgeteilt: Es ist einfacher, eine Clientinteraktion mit nur einem Dienst umzusetzen, der alles implementiert, anstatt zwischen mehreren Diensten auswählen zu müssen.

Der Routing Dienst in .NET 4 ist so konzipiert, dass diese Probleme leichter gelöst werden können. Der neue Routingdienst hat die folgenden Funktionen:

1. Inhaltsbasiertes Routing (<xref:System.ServiceModel.Dispatcher.MessageFilter>-Objekte untersuchen eine Nachricht, um das Ziel der Nachricht zu ermitteln.

2. Protokoll Überbrückung (Transport & Nachricht)

3. Fehlerbehandlung (der Router fängt Kommunikationsausnahmen ab und führt ein Failover zu Sicherungsendpunkten aus)

4. Dynamische Aktualisierung (im Speicher) von <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> und Routingkonfiguration.

### <a name="getting-started"></a>Erste Schritte

1. Dokumentation: [Routing](../wcf/feature-details/routing.md)

2. Beispiele: [WCF- &#91;&#93; Beispiele für Routing Dienste](../wcf/samples/routing-services.md)

3. Blog: [Routing Regeln!](https://docs.microsoft.com/archive/blogs/RoutingRules/)

### <a name="routing-scenarios"></a>Routingszenarien

Der Routingdienst ist in den folgenden Szenarien nützlich:

- Clients können mit mehreren Diensten interagieren, ohne alle diese Dienste direkt adressieren zu müssen.

- Clients können zusätzliche Logik für eine Clientanforderung ausführen, um das Routingziel zu bestimmen

- Die von einem Client durchgeführten Vorgänge können in mehrere Dienstimplementierungen zerlegt werden, ohne dass ein Refactoring des Clients erforderlich ist.

- Clients und Dienste können unterschiedliche Bindungen mit verschiedenen Sicherheitseinstellungen verwenden.

- Clients können so konfiguriert werden, dass sie stabiler gegenüber Fehlern oder der Nichtverfügbarkeit von Diensten sind.

## <a name="wcf-discovery"></a>WCF-Suche

WCF Discovery ist eine Framework-Technologie, mit der Sie einen Ermittlungs Mechanismus in Ihre Anwendungs Infrastruktur integrieren können. Mit WCF-Suche können Sie sicherstellen, dass Ihr Dienst ermittelt werden kann, und Ihre Clients für die Suche nach Diensten konfigurieren. Clients müssen nicht mehr mit einem Endpunkt hartcodiert werden, sodass die Anwendung stabiler und fehlertolerant wird. WCF-Suche ist die perfekte Plattform, um Funktionen für die automatische Konfiguration in die Anwendung zu integrieren.

Das Produkt basiert auf dem WS-Discovery-Standard. Das Produkt zeichnet sich dadurch aus, dass es interoperabel, erweiterbar und generisch ist. Es unterstützt zwei Betriebsmodi:

1. Verwaltet: Gibt es im Netzwerk eine Entität, die über die vorhandenen Dienste informiert ist, fordern Clients von dieser Entität direkt Informationen an. Dies ist analog zu Active Directory.

2. Ad-hoc: Clients verwenden Multicastnachrichten, um Dienste zu suchen.

Darüber hinaus sind Ermittlungsnachrichten unabhängig vom Netzwerkprotokoll. Sie können für jedes Protokoll verwendet werden, das die Modusanforderungen unterstützt. Beispielsweise können Discovery-Multicast Nachrichten über den UDP-Kanal oder ein beliebiges anderes Netzwerk gesendet werden, das Multicast Nachrichten unterstützt. Diese Entwurfs Punkte ermöglichen Ihnen in Kombination mit der Funktions Flexibilität, die Ermittlung speziell an Ihre Lösung anzupassen.

### <a name="getting-started"></a>Erste Schritte

- Dokumentation: [WCF Discovery](../wcf/feature-details/wcf-discovery.md)

- Beispiele: Ermittlung [(Beispiele)](../wcf/samples/discovery-samples.md)

### <a name="discovery-scenarios"></a>Suchszenarien

Ein Entwickler möchte Endpunkte nicht hartcodieren, da noch nicht feststeht, wann der Dienst verfügbar ist. Stattdessen möchte der Entwickler zur Laufzeit einen Dienst auswählen. Zwischen den Komponenten in der Anwendung ist ein höheres Maß an Entkopplung, Stabilität und automatischer Konfiguration erforderlich.

## <a name="tracking"></a>Nachverfolgung

Die Workflow Nachverfolgung bietet Einblicke in die Ausführung einer Workflow Instanz. Die nach Verfolgungs Ereignisse werden von einem Workflow auf der Workflowinstanzebene ausgegeben, und wenn Aktivitäten innerhalb des Workflows ausgeführt werden. Dem Workflowhost muss eine Workflownachverfolgungskomponente hinzugefügt werden, um Nachverfolgungsdatensätze zu abonnieren. Die Nachverfolgungsdatensätze werden mit einem Nachverfolgungsprofil gefiltert. Der .NET Framework stellt einen etw-nach Verfolgungs Teilnehmer (Ereignis Ablauf Verfolgung für Windows) bereit, und in der Datei Machine. config ist ein einfaches Profil installiert.

### <a name="getting-started"></a>Erste Schritte

1. Erstellen Sie in Visual Studio 2010 ein Projekt für eine Dienstanwendung für WCF-Workflows. Um mit der Projekterstellung zu beginnen, werden <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> auf dem Canvas platziert.

2. Öffnen Sie die Datei "web.config", und fügen Sie ein ETW-Nachverfolgungsverhalten ohne Profil hinzu.

    1. Das Standardprofil wird verwendet.

    2. Öffnen Sie die Ereignisanzeige, und aktivieren Sie den analytischen Kanal im folgenden Knoten: **Ereignisanzeige**, Anwendungs **-und Dienst Protokolle**, **Microsoft**, **Windows**, **Anwendungs Server-Anwendungen**. Klicken Sie mit der rechten Maustaste auf **Analyse** , und wählen Sie **Protokoll aktivieren**

    3. Führen Sie den Workflowdienst aus.

    4. Beobachten Sie die Workflownachverfolgungsereignisse in der Ereignisanzeige.

3. Beispiele: nach [Verfolgung](./samples/tracking.md)

4. Konzeptionelle Dokumentation: [Workflow Nachverfolgung und Ablauf Verfolgung](workflow-tracking-and-tracing.md)

## <a name="sql-workflow-instance-store"></a>SQL-Workflowinstanzspeicher

Beim <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> handelt es sich um die SQL Server-basierte Implementierung eines Instanzspeichers. Ein Instanzspeicher speichert den Zustand einer ausgeführten Instanz zusammen mit allen Daten, die zum Laden und Fortsetzen dieser Instanz erforderlich sind. Der Diensthost weist den Instanzspeicher an, den Instanzzustand zu speichern, wenn der Workflow beibehalten wird. Wenn für diese Instanz eine Nachricht eingeht oder eine Verzögerungsaktivität abläuft, weist der Diensthost den Instanzspeicher an, den Instanzzustand zu laden.

### <a name="getting-started"></a>Erste Schritte

1. Erstellen Sie in Visual Studio 2012 einen Workflow, der eine implizite oder explizite <xref:System.Activities.Statements.Persist> Aktivität enthält. Fügen Sie dem Workflowdiensthost das <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Verhalten hinzu. Sie können die Aktivität dem Code oder der Anwendungskonfiguration hinzufügen.

2. Beispiele: [Persistenz](/previous-versions/dotnet/netframework-4.0/dd699769(v%3dvs.100))

3. Konzeptionelle Dokumentation: [SQL-workflowinstanzspeicher](sql-workflow-instance-store.md).
