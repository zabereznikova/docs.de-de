---
title: Windows Workflow Foundation-Funktionsdetails
ms.date: 03/30/2017
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
ms.openlocfilehash: b18c6dd76762f4495ac475cd3dfa4e1995733b59
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43884483"
---
# <a name="windows-workflow-foundation-feature-specifics"></a>Windows Workflow Foundation-Funktionsdetails
Durch [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] werden Windows Workflow Foundation eine Reihe von Funktionen hinzugefügt. In diesem Dokument wird eine Reihe neuer Funktionen beschrieben. Darüber hinaus enthält das Dokument detaillierte Informationen zu den Szenarien, in denen sie möglicherweise nützlich sind.  
  
## <a name="messaging-activities"></a>Messagingaktivitäten  
 Die messagingaktivitäten (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.ReceiveReply>) zum Senden und Empfangen von WCF-Nachrichten vom Workflow verwendet werden.  <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> Aktivitäten werden verwendet, um einen Windows Communication Foundation (WCF)-Dienstvorgang zu bilden, der über WSDL wie standard-WCF-Webdienste verfügbar gemacht wird.  <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.ReceiveReply> werden verwendet, um eine ähnliche für einen WCF-Webdiensts <xref:System.ServiceModel.ChannelFactory>; eine **Hinzufügen eines Dienstverweises** Erfahrung, die auch für Workflow Foundation, die vorkonfiguriert, dass Aktivitäten generiert vorhanden ist.  
  
### <a name="getting-started-with-messaging-activities"></a>Erste Schritte mit Messagingaktivitäten  
  
-   Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] ein Projekt für eine Dienstanwendung für WCF-Workflows. Das Paar <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> wird auf dem Canvas platziert.  
  
-   Mit der rechten Maustaste auf das Projekt, und wählen Sie **Hinzufügen eines Dienstverweises**.  Zeigen Sie auf einen vorhandenen Webdienst-WSDL, und klicken Sie auf **OK**.  Erstellen Sie das Projekt aus, um die generierten Aktivitäten anzuzeigen (implementiert mit <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.ReceiveReply>) in der Toolbox.  
  
-   Beispiele für diese Aktivitäten finden Sie in den folgenden Abschnitten:  
  
    -   Basic: [Dienste](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   In folgenden Szenarien: [Dienste](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
-   [Konzeptionelle Dokumentation](https://go.microsoft.com/fwlink/?LinkId=204801)  
  
-   [Dokumentation für den Designer Messaging](https://go.microsoft.com/fwlink/?LinkId=204802)  
  
### <a name="messaging-activities-example-scenario"></a>Beispielszenario für Messagingaktivitäten  
 Ein `BestPriceFinder` Dienst Ruft Informationen zu mehrere Airline-Services, um den besten TicketPreis für eine bestimmte Route zu suchen.  Implementieren dieses Szenario müssten Sie Nachrichtenaktivitäten verwendet, um die preisanforderung zu empfangen, die Preise von den Back-End-Diensten abzurufen und auf die preisanforderung mit dem besten Preis zu antworten.  Es wäre auch müssen Sie andere Aktivitäten des Out-of-Box zu verwenden, um die Geschäftslogik für die Berechnung von des besten Preis zu erstellen.  
  
## <a name="workflowservicehost"></a>WorkflowServiceHost  
 Die <xref:System.ServiceModel.WorkflowServiceHost> ist die Out-of-Box-Workflowhost, der mehrere Instanzen, Konfiguration und WCF-messaging unterstützt (obwohl die Workflows nicht erforderlich, um die Verwendung von messaging zum gehostet werden, sind).  Außerdem wird durch einen Satz von Dienstverhalten die Integration von Persistenz, Nachverfolgung und Instanzsteuerung bereitgestellt.  Ebenso wie von WCF <xref:System.ServiceModel.ServiceHost>, <xref:System.ServiceModel.WorkflowServiceHost> können in einer Konsole/WinForms-/WPF-Anwendung oder ein Windows-Dienst selbst gehostet sein webgehostete (als xamlx-Datei) in IIS oder WAS.  
  
### <a name="getting-started-with-workflow-service-host"></a>Erste Schritte mit dem Workflowdiensthost  
  
-   Erstellen Sie in Visual Studio 2010 ein Projekt für die Dienstanwendung für WCF-Workflows: dieses Projekt eingerichtet mit <xref:System.ServiceModel.WorkflowServiceHost> in einer Web-Host-Umgebung.  
  
-   Zum Hosten eines Nicht-Messaging-Workflows fügen Sie einen benutzerdefinierten <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> hinzu, der die Instanz auf Grundlage einer Nachricht erstellt.  
  
-   Workflowinstanzen können gesteuert (z. B.angehalten oder beendet) werden, indem <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> ein <xref:System.ServiceModel.WorkflowServiceHost> hinzugefügt und anschließend ein <xref:System.ServiceModel.Activities.WorkflowControlClient> verwendet wird.  
  
-   Beispiele für <xref:System.ServiceModel.WorkflowServiceHost> finden Sie in den folgenden Abschnitten:  
  
    -   [Ausführung](../../../docs/framework/windows-workflow-foundation/samples/execution.md)  
  
    -   Basic: [Dienste](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   In folgenden Szenarien: [Dienste](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   Anwendung: [angehaltene Instanzverwaltung](../../../docs/framework/windows-workflow-foundation/samples/suspended-instance-management.md)  
  
-   [WorkflowServiceHost-Dokumentation](https://go.microsoft.com/fwlink/?LinkId=204807)  
  
### <a name="workflowservicehost-scenario"></a>WorkflowServiceHost-Szenario  
 Ein BestPriceFinder-Dienst ruft mehrere Airline-Dienste, um den besten TicketPreis für eine bestimmte Route zu suchen.  Dieses Szenario implementieren, müssten Sie der Workflow in <xref:System.ServiceModel.WorkflowServiceHost>.  Er würde Nachrichtenaktivitäten auch verwenden, um die preisanforderung zu empfangen, die Preise von den Back-End-Diensten abzurufen und auf die preisanforderung mit dem besten Preis zu antworten.  
  
## <a name="correlation"></a>Korrelation  
 Eine Korrelation kann wie folgt definiert werden:  
  
-   Eine Möglichkeit zum Gruppieren von Nachrichten, d. h. die Beziehung zwischen einer Anforderungsnachricht und der dazugehörigen Antwort  
  
-   Eine Möglichkeit, ein Datenelement einer Dienstinstanz zuzuordnen  
  
### <a name="getting-started"></a>Erste Schritte  
  
-   Erstellen Sie in Visual Studio ein neues Projekt, um mit der Korrelation zu beginnen. Erstellen Sie eine Variable vom Typ <xref:System.ServiceModel.Activities.CorrelationHandle>.  
  
-   Ein Beispiel für die Verwendung einer Korrelation zum Gruppieren von Nachrichten ist eine Anforderung/Antwort-Korrelation, die Nachrichten zusammen gruppiert.  
  
    -   Auf einem <xref:System.ServiceModel.Activities.Receive> -Aktivität, klicken Sie auf die <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> Eigenschaft und fügen eine <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> mithilfe der CorrelationHandle im ersten Schritt oben erstellt.  
  
    -   Erstellen einer <xref:System.ServiceModel.Activities.SendReply> -Aktivität mit der rechten Maustaste auf die <xref:System.ServiceModel.Activities.Receive> und klicken Sie auf "SendReply erstellen". Fügen Sie die Aktivität hinter der <xref:System.ServiceModel.Activities.Receive>-Aktivität in den Workflow ein.  
  
-   Ein Beispiel für die Zuordnung eines Datenelements zu einer Dienstinstanz ist die inhaltsbasierte Korrelation, bei der ein Datenelement (z. B. eine Auftrags-ID) einer bestimmten Workflowinstanz zugeordnet wird.  
  
    -   Klicken Sie auf die `CorrelationInitializers`-Eigenschaft einer Messagingaktivität, und fügen Sie mit der oben erstellten <xref:System.ServiceModel.Activities.QueryCorrelationInitializer>-Variable einen <xref:System.ServiceModel.Activities.CorrelationHandle> hinzu. Doppelklicken Sie im Dropdownmenü auf die gewünschte Eigenschaft der Nachricht (z. B. "OrderID"). Legen Sie die `CorrelatesWith`-Eigenschaft auf die oben verwendete <xref:System.ServiceModel.Activities.CorrelationHandle>-Variable fest.  
  
-   Beispiele:  
  
    -   Basic: [Dienste](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   In folgenden Szenarien: [Dienste](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   [Korrelationsdokumentation](https://go.microsoft.com/fwlink/?LinkId=204939)  
  
### <a name="correlation-scenario"></a>Korrelationsszenario  
 Erstellen neuer und Aktualisieren vorhandener Aufträge, die verarbeitet werden, wird ein bestellungsverarbeitungs Workflow verwendet.  Dieses Szenario implementieren, müssten Sie der Workflow in <xref:System.ServiceModel.WorkflowServiceHost> und messagingaktivitäten verwenden.  Es müsste auch die Korrelation auf Grundlage der `orderId` um sicherzustellen, dass der richtige Workflow Updates vorgenommen werden.  
  
## <a name="simplified-configuration"></a>Vereinfachte Konfiguration  
 Das WCF-Konfigurationsschema ist komplex und bietet Benutzern viele schwer zu findende Funktionen. In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], haben wir den Schwerpunkt auf die Unterstützung von WCF-Benutzern, die ihre Dienste mit den folgenden Features zu konfigurieren:  
  
-   Es ist keine explizite Einzeldienstkonfiguration mehr notwendig. Wenn Sie keine konfigurieren \<Service > Elemente für den Dienst, und der Dienst nicht programmgesteuert auf einen beliebigen Endpunkt definiert, und klicken Sie dann eine Reihe von Endpunkten wird automatisch hinzugefügt werden, zu dem Dienst dienstbasisadresse und für jeden Vertrag vom Dienst implementiert wird.  
  
-   Der Benutzer kann Standardwerte für WCF-Bindungen und -Verhalten definieren, die ohne explizite Konfiguration auf Dienste angewendet werden.  
  
-   Standardendpunkte definieren wiederverwendbare vorkonfigurierte Endpunkte, die feste Werte für mindestens eine Endpunkteigenschaft besitzen (Adresse, Bindung und Vertrag) und die die Definition benutzerdefinierter Eigenschaften erlauben.  
  
-   Zum Schluss die <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> können Sie zentrale Verwaltung von WCF-Clientkonfiguration, nützlich in Szenarien, in der Konfiguration ausgewählt oder geändert, nachdem die Ladezeit der Anwendungsdomäne.  
  
### <a name="getting-started"></a>Erste Schritte  
  
-   [Entwicklerhandbuch für WCF 4.0](https://go.microsoft.com/fwlink/?LinkId=204940)  
  
-   [Konfigurationskanalfactory](https://go.microsoft.com/fwlink/?LinkId=204941)  
  
-   [Standardendpunktelement](https://go.microsoft.com/fwlink/?LinkId=204942)  
  
-   [Dienstkonfigurationsverbesserungen in .net Framework 4](https://go.microsoft.com/fwlink/?LinkId=204943)  
  
-   [Häufiger Benutzerfehler in .NET 4: falsche Schreibweise den Konfigurationsnamen des WF-/WCF-Dienst](https://go.microsoft.com/fwlink/?LinkId=204944)  
  
### <a name="simplified-configuration-scenarios"></a>Vereinfachte Konfigurationsszenarien  
  
-   Einstieg in WCF ist ein erfahrener ASMX-Entwickler möchte. WCF scheint jedoch zu kompliziert! Er fragt sich, was das alles für Informationen sind, die in eine Konfigurationsdatei eingefügt werden müssen. In .NET 4 können Sie sich sogar entscheiden, überhaupt keine Konfigurationsdatei zu verwenden.  
  
-   Es ist sehr schwierig, einen vorhandenen Satz von WCF-Diensten zu konfigurieren und zu verwalten. Die Konfigurationsdatei enthält Tausende von XML-Codezeilen, und es kann sehr gefährlich sein, diese zu ändern. Es müsste eine Möglichkeit geben, diese vielen Codezeilen auf eine Menge zu reduzieren, die besser zu handhaben ist.  
  
## <a name="data-contract-resolver"></a>Datenvertragsresolver  
 In .NET 3.5 gab es einige Einschränkungen beim Entwurf bekannter Typen:  
  
-   Es war nicht möglich, während der Serialisierung oder Deserialisierung bekannte Typen dynamisch hinzuzufügen.  
  
-   Serialisierungsprogramme konnten keine unbekannten xsi:type-Informationen behandeln.  
  
-   Benutzer konnten nicht angeben, welche xsi:type-Informationen erscheinen sollten, um z. B. die Serialisierungsinstanz zu verkleinern.  
  
 Die [DataContractResolver](../../../docs/framework/wcf/samples/datacontractresolver.md) löst diese Probleme in .NET 4.5.  
  
### <a name="getting-started"></a>Erste Schritte  
  
-   [Data Datenvertragsresolver-API-Dokumentation](https://go.microsoft.com/fwlink/?LinkId=204946)  
  
-   [Einführung in den Datenvertragsresolver](https://go.microsoft.com/fwlink/?LinkId=204947)  
  
-   Beispiele:  
  
    -   [DataContractResolver](../../../docs/framework/wcf/samples/datacontractresolver.md)  
  
    -   [KnownAssemblyAttribute](../../../docs/framework/wcf/samples/knownassemblyattribute.md)  
  
### <a name="data-contract-resolver-scenarios"></a>Datenvertragsresolver-Szenarien  
  
-   Mit dem Datenvertragsresolver kann das Deklarieren von vielen <xref:System.Runtime.Serialization.KnownTypeAttribute>-Objekten in einem Dienst vermieden werden.  
  
-   Zudem trägt ein Datenvertragsresolver zum Reduzieren des XML-Blobs bei.  
  
## <a name="flowchart"></a>Flussdiagramm  
 Ein Flussdiagramm ist ein bekanntes Paradigma, um Domänenprobleme visuell darzustellen. Es ist ein neues Ablaufsteuerungsformat, das in .NET 4 eingeführt wird. Ein Kernmerkmal des Flussdiagrammes ist, dass zu einem beliebigen Zeitpunkt immer nur eine Aktivität ausgeführt wird. In Flussdiagrammen können Schleifen und alternative Ergebnisse ausgedrückt werden, aber nicht die gleichzeitige Ausführung mehrerer Knoten.  
  
### <a name="getting-started"></a>Erste Schritte  
  
-   Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] eine Konsolenanwendung für Workflows. Fügen Sie im Workflow-Designer ein Flussdiagramm hinzu.  
  
-   Die Flussdiagrammfunktion verwendet die folgenden Klassen:  
  
    -   <xref:System.Activities.Statements.Flowchart>  
  
    -   <xref:System.Activities.Statements.FlowNode>  
  
    -   <xref:System.Activities.Statements.FlowDecision>  
  
    -   <xref:System.Activities.Statements.FlowStep>  
  
    -   <xref:System.Activities.Statements.FlowSwitch%601>  
  
-   Beispiele:  
  
    -   [Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch](../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
  
    -   [StateMachine-Szenario mit einer Kombination aus FlowChart und Pick](../../../docs/framework/windows-workflow-foundation/samples/statemachine-scenario-using-a-combination-of-flowchart-and-pick.md)  
  
    -   [Einstellungsprozess](../../../docs/framework/windows-workflow-foundation/samples/hiring-process.md)  
  
-   Designerdokumentation:  
  
    -   [Flussdiagramm-Aktivitätsdesigner](/visualstudio/workflow-designer/flowchart-activity-designers)  
  
### <a name="flowchart-scenarios"></a>Flussdiagrammszenarien  
 Eine Flussdiagrammaktivität kann verwendet werden, um ein Ratespiel zu implementieren. Das Ratespiel ist sehr simpel: Der Computer wählt eine Zufallszahl aus, die der Spieler erraten muss. Wenn der Spieler abgibt, zeigt der Computer einen Hinweis (d. h. "versuchen Sie eine geringere Anzahl"). Wenn der Spieler die Zahl in weniger als 7 Versuchen errät, zeigt der Computer einen besonderen Glückwunsch an. Dieses Spiel kann mit einer Kombination der folgenden Verfahrensaktivitäten implementiert werden:  
  
-   <xref:System.Activities.Statements.Sequence>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.TryCatch>  
  
-   <xref:System.Activities.Statements.Assign%601>  
  
-   <xref:System.Activities.Statements.If>  
  
## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a>Verfahrensaktivitäten (Sequence, If, ForEach, Switch, Assign, DoWhile, While)  
 Verfahrensaktivitäten stellen einen Mechanismus bereit, um sequenzielle Ablaufsteuerung mit Konzepten zu modellieren, die Programmierern vertraut sind. Diese Aktivitäten ermöglichen herkömmlich strukturierte Konstrukte der Programmiersprache und stellen ggf. Sprachparität mit allgemeinen Verfahrenssprachen wie C#/VB bereit.  
  
### <a name="getting-started"></a>Erste Schritte  
  
-   Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] eine Konsolenanwendung für Workflows. Fügen Sie im Workflow-Designer Verfahrensaktivitäten hinzu.  
  
-   Beispiele:  
  
    -   [Einstellungsprozess](../../../docs/framework/windows-workflow-foundation/samples/hiring-process.md)  
  
    -   [Unternehmenseinkaufsprozess](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md)  
  
-   Designerdokumentation:  
  
    -   [Parallel-Aktivitätsdesigner](/visualstudio/workflow-designer/parallel-activity-designer)  
  
    -   [ParallelForEach\<T >-Aktivitätsdesigner](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)  
  
### <a name="procedural-activity-scenarios"></a>Verfahrensaktivitätsszenarien  
  
-   <xref:System.Activities.Statements.Parallel>: Ein Intranet-Dokumentverwaltungssystem verfügt über einen Dokumentgenehmigungsworkflow. Dokumente müssen von Personen in mehreren Abteilungen genehmigt werden, bevor sie im Intranet veröffentlicht werden können. Gibt es keine feste Reihenfolge für die Genehmigungen. Sie können jederzeit auftreten, während das Dokument in der Phase "Genehmigung ausstehend" ist. Wenn ein Benutzer ein Dokument zwecks Review übermittelt, muss es vom direkten Vorgesetzten des Benutzers, dem Intranetadministrator und dem Leiter der internen Kommunikation genehmigt werden.  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>: Eine WF-Anwendung verwaltet Unternehmenseinkäufe innerhalb eines großen Unternehmens. Die Unternehmensregeln schreiben vor, dass vor einem Kauf die Angebote von drei verschiedenen Anbietern eingeholt werden müssen. Ein Mitarbeiter der Einkaufsabteilung wählt drei Anbieter aus der Anbieterliste des Unternehmens aus. Nachdem diese Anbieter ausgewählt und benachrichtigt wurden, wartet das Unternehmen auf die Unterbreitung ihrer Angebote. Die Angebote können in beliebiger Reihenfolge eingehen. Zum Implementieren dieses Szenarios in WF wird eine <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität verwendet, die die Auflistung von Anbietern durchläuft und Angebote anfordert. Nachdem alle Angebote eingegangen sind, wird das beste Angebot ausgewählt und angezeigt.  
  
## <a name="invokemethod"></a>InvokeMethod  
 Die <xref:System.Activities.Statements.InvokeMethod>-Aktivität erlaubt den Aufruf öffentlicher Methoden in Objekten oder Typen im Gültigkeitsbereich. Die Aktivität unterstützt den Aufruf von Instanz- und statischen Methoden mit oder ohne Parameter (einschließlich Parameterarrays) und generischen Methoden. Zudem erlaubt sie eine synchrone und asynchrone Methodenausführung.  
  
### <a name="getting-started"></a>Erste Schritte  
  
-   Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] eine Konsolenanwendung für Workflows. Fügen Sie eine <xref:System.Activities.Statements.InvokeMethod>-Aktivität im Workflow-Designer hinzu, und konfigurieren Sie statische und Instanzmethoden für die Aktivität.  
  
-   Beispiele:  
  
    -   [InvokeMethod](../../../docs/framework/windows-workflow-foundation/samples/invokemethod.md)  
  
-   Designerdokumentation: [InvokeMethod-Aktivitätsdesigner](/visualstudio/workflow-designer/invokemethod-activity-designer)  
  
### <a name="invokemethod-scenarios"></a>InvokeMethod-Szenarien  
  
-   Eine Methode in einem Objekt im Gültigkeitsbereich muss aufgerufen werden. Beispielsweise muss einem Wörterbuch ein Wert hinzugefügt werden. Die Add-Methode der Instanz des Wörterbuchs wird aufgerufen, und der Schlüssel und der Wert werden bereitgestellt.  
  
-   Für ein Legacy-CLR-Objekt muss eine Methode aufgerufen werden. Anstatt eine benutzerdefinierte Aktivität zu erstellen, um den Aufruf dieser Legacyklasse zu umschließen, wenn es sich während der Workflowausführung im Gültigkeitsbereich befindet, kann <xref:System.Activities.Statements.InvokeMethod> verwendet werden.  
  
## <a name="error-handling-activities"></a>Fehlerbehandlungsaktivitäten  
 Die <xref:System.Activities.Statements.TryCatch>-Aktivität stellt einen Mechanismus zum Abfangen von Ausnahmen bereit, die während der Ausführung eines Satzes enthaltener Aktivitäten auftreten (vergleichbar mit dem Try/Catch-Konstrukt in C#/VB). <xref:System.Activities.Statements.TryCatch> stellt eine Ausnahmebehandlung auf Workflowebene bereit. Wenn eine nicht behandelte Ausnahme ausgelöst wird, wird der Workflow abgebrochen, und der Finally-Block wird nicht ausgeführt. Dieses Verhalten ist mit C# konsistent.  
  
### <a name="getting-started"></a>Erste Schritte  
  
-   Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] eine Konsolenanwendung für Workflows. Fügen Sie im Workflow-Designer eine <xref:System.Activities.Statements.TryCatch>-Aktivität hinzu.  
  
-   Beispiele:  
  
    1.  [Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch](../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
  
    2.  [Verwenden von Verfahrensaktivitäten](../../../docs/framework/windows-workflow-foundation/samples/using-procedural-activities.md)  
  
-   Designerdokumentation: [Fehlerbehandlungs-Aktivitätsdesigner](/visualstudio/workflow-designer/error-handling-activity-designers)  
  
### <a name="error-handling-scenarios"></a>Fehlerbehandlungsszenarien  
 Wenn ein Fehler auftritt, müssen ein Satz von Aktivitäten und eine bestimmte Logik ausgeführt werden. Wenn während dieser Fehlerbehandlung festgestellt wird, dass der Fehler nicht behoben werden kann, wird die Ausnahme erneut ausgelöst, und die übergeordnete Aktivität (oder der Host) befasst sich mit dem Problem.  
  
## <a name="pick-activity"></a>Auswählen der Aktivität  
 Die <xref:System.Activities.Statements.Pick>-Aktivität stellt eine ereignisbasierte Flusssteuerungsmodellierung in WF bereit. <xref:System.Activities.Statements.Pick> enthält zahlreiche Verzweigungen, wobei jede Verzweigung vor ihrer Ausführung auf ein bestimmtes Ereignis wartet. In diesem Setup verhält sich ein <xref:System.Activities.Statements.Pick> ähnlich wie ein <xref:System.Activities.Statements.Switch%601>, für den die Aktivität nur einen der überwachten Ereignissätze ausführt. Jede Verzweigung ist ereignisgesteuert, und das Ereignis, das zuerst auftritt, führt zuerst die entsprechende Verzweigung aus. Alle anderen Verzweigungen werden abgebrochen, und die Überwachung der Ereignisse wird beendet.  
  
### <a name="getting-started"></a>Erste Schritte  
  
-   Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] eine Konsolenanwendung für Workflows. Fügen Sie im Workflow-Designer eine <xref:System.Activities.Statements.Pick>-Aktivität hinzu.  
  
-   Beispiel: [verwenden der Pick-Aktivität](../../../docs/framework/windows-workflow-foundation/samples/using-the-pick-activity.md)  
  
-   Designerdokumentation: [Pick-Aktivitätsdesigner](/visualstudio/workflow-designer/pick-activity-designer)  
  
### <a name="pick-scenario"></a>Auswahlszenario  
 Ein Benutzer muss zur Eingabe aufgefordert werden. Unter normalen Umständen würde der Entwickler einen Methodenaufruf wie <xref:System.Console.ReadLine%2A> verwenden, um einen Benutzer zur Eingabe aufzufordern. Das Problem bei diesem Setup ist, dass das Programm wartet, bis der Benutzer etwas eingibt. In diesem Szenario wird ein Timeout benötigt, um die Blockierung einer blockierenden Aktivität aufzuheben. Ein häufiges Szenario ist, dass eine Aufgabe innerhalb einer bestimmte Zeitspanne abgeschlossen werden muss. Das Umsetzen eines Timeouts für eine blockierende Aktivität ist ein Szenario, bei dem eine Auswahl sehr nützlich ist.  
  
## <a name="wcf-routing-service"></a>WCF-Routingdienst  
 Der Routingdienst soll ein generischer Software Router zu sein, der können Sie steuern, wie WCFmessages zwischen den Clients und Diensten zu übertragen.  Der Routingdienst können Sie entkoppeln Ihre Clients Ihrer Dienste, die Ihnen mehr Freiheit in Bezug auf die Konfigurationen bietet, können Sie unterstützen, und die Flexibilität bei der Verwendung zum Hosten Ihrer Dienste in Betracht ziehen.  In .NET 3.5 waren Clients und Dienste eng gekoppelt; ein Client musste es musste es, sprechen und, wo sie gespeichert wurden alle Dienste kennen. Außerdem bestanden für WCF in .NET Framework 3.5 die folgenden Einschränkungen:  
  
-   Die Fehlerbehandlung war komplex, da diese Logik fest in den Client codiert werden musste.  
  
-   Clients und Dienste mussten immer die gleichen Bindungen verwenden.  
  
-   Dienste waren selten gut aufgeteilt: Es ist einfacher, eine Clientinteraktion mit nur einem Dienst umzusetzen, der alles implementiert, anstatt zwischen mehreren Diensten auswählen zu müssen.  
  
 Beim Entwurf des Routingdiensts in .NET 4 wurde dafür Sorge getragen, dass diese Probleme leichter gelöst werden können. Der neue Routingdienst hat die folgenden Funktionen:  
  
1.  Inhaltsbasiertes Routing (<xref:System.ServiceModel.Dispatcher.MessageFilter>-Objekte untersuchen eine Nachricht, um das Ziel der Nachricht zu ermitteln.  
  
2.  Protokollüberbrückung (Transport und Nachricht)  
  
3.  Fehlerbehandlung (der Router fängt Kommunikationsausnahmen ab und führt ein Failover zu Sicherungsendpunkten aus)  
  
4.  Dynamische Aktualisierung (im Speicher) von <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> und Routingkonfiguration.  
  
### <a name="getting-started"></a>Erste Schritte  
  
1.  Dokumentation: [Routing](../../../docs/framework/wcf/feature-details/routing.md)  
  
2.  Beispiele: [Routingdienste &#91;WCF-Beispiele&#93;](../../../docs/framework/wcf/samples/routing-services.md)  
  
3.  Blog: [Routingregeln!](https://go.microsoft.com/fwlink/?LinkId=204956)  
  
### <a name="routing-scenarios"></a>Routingszenarien  
 Der Routingdienst ist in den folgenden Szenarien nützlich:  
  
-   Clients können mit mehreren Diensten interagieren, ohne alle diese Dienste direkt adressieren zu müssen.  
  
-   Clients können zusätzliche Logik für eine Clientanforderung ausführen, um das Routingziel zu bestimmen  
  
-   Die von einem Client durchgeführten Vorgänge können in mehrere Dienstimplementierungen zerlegt werden, ohne dass eine Umgestaltung des Clients erforderlich ist.  
  
-   Clients und Dienste können unterschiedliche Bindungen mit verschiedenen Sicherheitseinstellungen verwenden.  
  
-   Clients können so konfiguriert werden, dass sie stabiler gegenüber Fehlern oder der Nichtverfügbarkeit von Diensten sind.  
  
## <a name="wcf-discovery"></a>WCF-Suche  
 WCF-Suche ist eine frameworktechnologie, mit der Sie einen Suchmechanismus in die Anwendungsinfrastruktur integrieren kann. Mit WCF-Suche können Sie sicherstellen, dass Ihr Dienst ermittelt werden kann, und Ihre Clients für die Suche nach Diensten konfigurieren. Clients müssen nicht mehr mit einem Endpunkt hartcodiert werden, sodass die Anwendung stabiler und fehlertolerant wird. WCF-Suche ist die perfekte Plattform, um Funktionen für die automatische Konfiguration in die Anwendung zu integrieren.  
  
 Das Produkt basiert auf dem WS-Discovery-Standard. Das Produkt zeichnet sich dadurch aus, dass es interoperabel, erweiterbar und generisch ist. Es unterstützt zwei Betriebsmodi:  
  
1.  Verwaltet: Gibt es im Netzwerk eine Entität, die über die vorhandenen Dienste informiert ist, fordern Clients von dieser Entität direkt Informationen an. Dies ist analog zu Active Directory.  
  
2.  Ad-hoc: Clients verwenden Multicastnachrichten, um Dienste zu suchen.  
  
 Darüber hinaus sind Ermittlungsnachrichten unabhängig vom Netzwerkprotokoll. Sie können für jedes Protokoll verwendet werden, das die Modusanforderungen unterstützt. Beispielsweise können multicast-Nachrichten gesendet werden, über den UDP-Kanal oder einem anderen Netzwerk, das multicastmessaging unterstützt.  Diese Entwurfsaspekte in Verbindung mit der funktionsflexibilität ermöglichen es Ihnen, die Suche speziell an Ihre Lösung anzupassen.  
  
### <a name="getting-started"></a>Erste Schritte  
  
-   Dokumentation: [WCF-Suche](../../../docs/framework/wcf/feature-details/wcf-discovery.md)  
  
-   Beispiele: [Suche (Beispiele)](../../../docs/framework/wcf/samples/discovery-samples.md)  
  
### <a name="discovery-scenarios"></a>Suchszenarien  
 Ein Entwickler möchte Endpunkte nicht hartcodieren, da noch nicht feststeht, wann der Dienst verfügbar ist. Stattdessen möchte der Entwickler zur Laufzeit einen Dienst auswählen. Zwischen den Komponenten in der Anwendung ist ein höheres Maß an Entkopplung, Stabilität und automatischer Konfiguration erforderlich.  
  
## <a name="tracking"></a>Nachverfolgung  
 Die workflownachverfolgung bietet einen Einblick in die Ausführung einer Workflowinstanz.  Die Nachverfolgungsereignisse werden von einem Workflow auf workflowinstanzebene und beim Ausführen von Aktivitäten innerhalb des Workflows ausgegeben. Dem Workflowhost muss eine Workflownachverfolgungskomponente hinzugefügt werden, um Nachverfolgungsdatensätze zu abonnieren. Die Nachverfolgungsdatensätze werden mit einem Nachverfolgungsprofil gefiltert. .NET Framework stellt eine ETW-Nachverfolgungskomponente (Event Tracing for Windows, Ereignisablaufverfolgung für Windows) bereit, und in der Datei "machine.config" wird ein Basisprofil installiert.  
  
### <a name="getting-started"></a>Erste Schritte  
  
1.  Erstellen Sie in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] ein Projekt für eine Dienstanwendung für WCF-Workflows. Um mit der Projekterstellung zu beginnen, werden <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> auf dem Canvas platziert.  
  
2.  Öffnen Sie die Datei "web.config", und fügen Sie ein ETW-Nachverfolgungsverhalten ohne Profil hinzu.  
  
    1.  Das Standardprofil wird verwendet.  
  
    2.  Öffnen Sie die Ereignisanzeige, und aktivieren Sie den analysekanal im folgenden Knoten: **Ereignisanzeige**, **Anwendungs- und Dienstprotokolle**, **Microsoft**, **Windows** , **Anwendungsserver-Anwendungen**. Mit der rechten Maustaste **analytisch** , und wählen Sie **Protokoll aktivieren**.  
  
    3.  Führen Sie den Workflowdienst aus.  
  
    4.  Beobachten Sie die Workflownachverfolgungsereignisse in der Ereignisanzeige.  
  
3.  Beispiele: [nachverfolgen](../../../docs/framework/windows-workflow-foundation/samples/tracking.md)  
  
4.  Dokumentation: [nachverfolgung und Ablaufverfolgung für Workflows](../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
  
## <a name="sql-workflow-instance-store"></a>SQL-Workflowinstanzspeicher  
 Beim <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> handelt es sich um die SQL Server-basierte Implementierung eines Instanzspeichers. Ein Instanzspeicher speichert den Zustand einer ausgeführten Instanz zusammen mit allen Daten, die zum Laden und Fortsetzen dieser Instanz erforderlich sind. Der Diensthost weist den Instanzspeicher an, den Instanzzustand zu speichern, wenn der Workflow beibehalten wird. Wenn für diese Instanz eine Nachricht eingeht oder eine Verzögerungsaktivität abläuft, weist der Diensthost den Instanzspeicher an, den Instanzzustand zu laden.  
  
### <a name="getting-started"></a>Erste Schritte  
  
1.  Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] einen Workflow, der eine implizite oder explizite <xref:System.Activities.Statements.Persist>-Aktivität enthält. Fügen Sie dem Workflowdiensthost das <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>-Verhalten hinzu. Sie können die Aktivität dem Code oder der Anwendungskonfiguration hinzufügen.  
  
2.  Beispiele: [Persistenz](../../../docs/framework/windows-workflow-foundation/samples/persistence.md)  
  
3.  Dokumentation: [SQL Workflow-Instanz Store](../../../docs/framework/windows-workflow-foundation/sql-workflow-instance-store.md).
