---
title: "Windows Workflow Foundation-Funktionsdetails | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Windows Workflow Foundation-Funktionsdetails
Durch [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)] werden Windows Workflow Foundation eine Reihe von Funktionen hinzugefügt.In diesem Dokument wird eine Reihe neuer Funktionen beschrieben. Darüber hinaus enthält das Dokument detaillierte Informationen zu den Szenarien, in denen sie möglicherweise nützlich sind.  
  
## Messagingaktivitäten  
 Die Messagingaktivitäten \(<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.ReceiveReply>\) werden verwendet, um [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Nachrichten aus einem Workflow senden oder darin empfangen zu können. Die Aktivitäten <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> werden verwendet, um einen [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Dienstvorgang zu bilden, der über WSDL verfügbar gemacht wird, genauso wie standardmäßige [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Webdienste. <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.ReceiveReply> werden verwendet, um einen Webdienst zu nutzen, ähnlich wie eine WCF\-<xref:System.ServiceModel.ChannelFactory>. Darüber hinaus steht für Workflow Foundation auch die Option **Dienstverweis hinzufügen** zur Verfügung, um vorkonfigurierte Aktivitäten zu generieren.  
  
### Erste Schritte mit Messagingaktivitäten  
  
-   Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] ein Projekt für eine Dienstanwendung für WCF\-Workflows.Das Paar <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> wird auf dem Canvas platziert.  
  
-   Klicken Sie mit der rechten Maustaste auf das Projekt, und wählen Sie **Dienstverweis hinzufügen** aus. Zeigen Sie auf ein vorhandenes Webdienst\-WSDL, und klicken Sie auf **OK**. Erstellen Sie das Projekt, um die generierten Aktivitäten \(implementiert mit <xref:System.ServiceModel.Activities.Send> und <xref:System.ServiceModel.Activities.ReceiveReply>\) in der Toolbox anzuzeigen.  
  
-   Beispiele für diese Aktivitäten finden Sie in den folgenden Abschnitten:  
  
    -   Standard: [Dienste](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   Szenarien: [Dienste](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
-   [Dokumentation](http://go.microsoft.com/fwlink/?LinkId=204801)  
  
-   [Dokumentation für den Designer für Messagingaktivitäten](http://go.microsoft.com/fwlink/?LinkId=204802)  
  
### Beispielszenario für Messagingaktivitäten  
 Ein `BestPriceFinder`\-Dienst ruft von mehreren Fluggesellschaften Informationen ab, um den besten Ticketpreis für eine bestimmte Route zu suchen. Zum Implementieren dieses Szenarios müssen Nachrichtenaktivitäten verwendet werden, um die Preisanforderung zu empfangen, die Preise von den Back\-End\-Diensten abzurufen und auf die Preisanforderung mit dem besten Preis zu antworten. Zudem sind andere vordefinierte Aktivitäten erforderlich, um die Geschäftslogik zum Berechnen des besten Preises zu erstellen.  
  
## WorkflowServiceHost  
 Der <xref:System.ServiceModel.WorkflowServiceHost> ist der vordefinierte Workflowhost, der mehrere Instanzen sowie Konfiguration und [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Messaging unterstützt \(obwohl für das Hosten der Workflows kein Messaging erforderlich ist\). Der Workflowhost lässt sich durch einen Satz von Dienstverhaltensweisen auch in die Persistenz\-, Nachverfolgungs\- und Instanzsteuerung integrieren. Wie der <xref:System.ServiceModel.ServiceHost> von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] kann der <xref:System.ServiceModel.WorkflowServiceHost> von einer Konsolen\-, WinForms\- oder WPF\-Anwendung oder einem Windows\-Dienst selbst gehostet oder \(als XAMLX\-Datei\) in IIS oder WAS im Internet gehostet werden.  
  
### Erste Schritte mit dem Workflowdiensthost  
  
-   Erstellen Sie in Visual Studio 2010 ein Projekt für eine Dienstanwendung für [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Workflows: Dieses Projekt wird für die Verwendung von <xref:System.ServiceModel.WorkflowServiceHost> in einer Webhostumgebung eingerichtet.  
  
-   Zum Hosten eines Nicht\-Messaging\-Workflows fügen Sie einen benutzerdefinierten <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> hinzu, der die Instanz auf Grundlage einer Nachricht erstellt.  
  
-   Instanzen eines Workflows können gesteuert \(z. B.angehalten oder beendet\) werden, indem <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> zu <xref:System.ServiceModel.WorkflowServiceHost> hinzugefügt und anschließend <xref:System.ServiceModel.Activities.WorkflowControlClient> verwendet wird.  
  
-   Beispiele für <xref:System.ServiceModel.WorkflowServiceHost> finden Sie in den folgenden Abschnitten:  
  
    -   [Ausführung](../../../docs/framework/windows-workflow-foundation/samples/execution.md)  
  
    -   Standard: [Dienste](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   Szenarien: [Dienste](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   Anwendung: [Angehaltene Instanzverwaltung](../../../docs/framework/windows-workflow-foundation/samples/suspended-instance-management.md)  
  
-   [WorkflowServiceHost\-Dokumentation](http://go.microsoft.com/fwlink/?LinkId=204807)  
  
### WorkflowServiceHost\-Szenario  
 Ein BestPriceFinder\-Dienst ruft Informationen von mehreren Fluggesellschaften ab, um den besten Ticketpreis für eine bestimmte Route zu suchen. Zum Implementieren dieses Szenarios muss der Workflow in <xref:System.ServiceModel.WorkflowServiceHost> gehostet werden. Zudem werden Nachrichtenaktivitäten verwendet, um die Preisanforderung zu empfangen, die Preise von den Back\-End\-Diensten abzurufen und auf die Preisanforderung mit dem besten Preis zu antworten.  
  
## Korrelation  
 Eine Korrelation kann wie folgt definiert werden:  
  
-   Eine Möglichkeit zum Gruppieren von Nachrichten, d. h. die Beziehung zwischen einer Anforderungsnachricht und der dazugehörigen Antwort  
  
-   Eine Möglichkeit, ein Datenelement einer Dienstinstanz zuzuordnen  
  
### Erste Schritte  
  
-   Erstellen Sie in Visual Studio ein neues Projekt, um mit der Korrelation zu beginnen.Erstellen Sie eine Variable vom Typ <xref:System.ServiceModel.Activities.CorrelationHandle>.  
  
-   Ein Beispiel für die Verwendung einer Korrelation zum Gruppieren von Nachrichten ist eine Anforderung\/Antwort\-Korrelation, die Nachrichten zusammen gruppiert.  
  
    -   Klicken Sie für eine <xref:System.ServiceModel.Activities.Receive>\-Aktivität auf die <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A>\-Eigenschaft, und fügen Sie mithilfe der oben im ersten Schritt erstellten CorrelationHandle\-Variablen ein <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer>\-Element hinzu.  
  
    -   Erstellen Sie eine <xref:System.ServiceModel.Activities.SendReply>\-Aktivität, indem Sie mit der rechten Maustaste auf <xref:System.ServiceModel.Activities.Receive> klicken und dann auf "SendReply erstellen" klicken.Fügen Sie die Aktivität hinter der <xref:System.ServiceModel.Activities.Receive>\-Aktivität in den Workflow ein.  
  
-   Ein Beispiel für die Zuordnung eines Datenelements zu einer Dienstinstanz ist die inhaltsbasierte Korrelation, bei der ein Datenelement \(z. B. eine Auftrags\-ID\) einer bestimmten Workflowinstanz zugeordnet wird.  
  
    -   Klicken Sie auf die `CorrelationInitializers`\-Eigenschaft einer Messagingaktivität, und fügen Sie mit der oben erstellten <xref:System.ServiceModel.Activities.CorrelationHandle>\-Variable einen <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> hinzu.Doppelklicken Sie auf die gewünschte Eigenschaft der Nachricht \(z. B.OrderID\) im Dropdownmenü.Legen Sie die `CorrelatesWith`\-Eigenschaft auf die oben verwendete <xref:System.ServiceModel.Activities.CorrelationHandle>\-Variable fest.  
  
-   Beispiele:  
  
    -   Standard: [Dienste](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   Szenarien: [Dienste](../../../docs/framework/windows-workflow-foundation/samples/services.md)  
  
    -   [Korrelationsdokumentation](http://go.microsoft.com/fwlink/?LinkId=204939)  
  
### Korrelationsszenario  
 Zum Erstellen neuer Aufträge und zum Aktualisieren vorhandener Aufträge wird ein Bestellungsverarbeitungs\-Workflow verwendet. Dieses Szenario kann implementiert werden, indem der Workflow in <xref:System.ServiceModel.WorkflowServiceHost> gehostet wird und Messagingaktivitäten verwendet werden. Zudem ist eine Korrelation auf Grundlage von `orderId` erforderlich, um sicherzustellen, dass der richtige Workflow aktualisiert wird.  
  
## Vereinfachte Konfiguration  
 Das [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Konfigurationsschema ist komplex und stellt Benutzern viele schwer zu findende Funktionen bereit.In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] wurde insbesondere darauf geachtet, die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Benutzer beim Konfigurieren der Dienste mithilfe der folgenden Funktionen zu unterstützen:  
  
-   Es ist keine explizite Einzeldienstkonfiguration mehr notwendig.Wenn Sie keine \<service\>\-Elemente für den Dienst konfigurieren und der Dienst keine Endpunkte programmgesteuert definiert, wird dem Dienst automatisch ein Satz von Endpunkten hinzugefügt, und zwar ein Endpunkt für jede Dienstbasisadresse und für jeden vom Dienst implementierten Vertrag.  
  
-   Der Benutzer kann Standardwerte für WCF\-Bindungen und \-Verhalten definieren, die ohne explizite Konfiguration auf Dienste angewendet werden.  
  
-   Standardendpunkte definieren wiederverwendbare vorkonfigurierte Endpunkte, die feste Werte für mindestens eine Endpunkteigenschaft besitzen \(Adresse, Bindung und Vertrag\) und die die Definition benutzerdefinierter Eigenschaften erlauben.  
  
-   Mit <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> können Sie schließlich die [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Clientkonfiguration zentral verwalten. Dies kann auch in Szenarien nützlich sein, in denen die Konfiguration nach der Ladezeit der Anwendungsdomäne ausgewählt oder geändert wird.  
  
### Erste Schritte  
  
-   [Entwicklerhandbuch für WCF 4.0](http://go.microsoft.com/fwlink/?LinkId=204940)  
  
-   [Konfigurationskanalfactory](http://go.microsoft.com/fwlink/?LinkId=204941)  
  
-   [Standardendpunktelement](http://go.microsoft.com/fwlink/?LinkId=204942)  
  
-   [Dienstkonfigurationsverbesserungen in .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=204943)  
  
-   [Häufiger Benutzerfehler in .NET 4: Falsche Schreibweise des WF\/WCF\-Dienstkonfigurationsnamens](http://go.microsoft.com/fwlink/?LinkId=204944)  
  
### Vereinfachte Konfigurationsszenarien  
  
-   Ein erfahrener ASMX\-Entwickler möchte mit der Verwendung von [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] beginnen.[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] scheint ihm jedoch viel zu kompliziert zu sein.Er fragt sich, was das alles für Informationen sind, die in eine Konfigurationsdatei eingefügt werden müssen.In .NET 4 können Sie sich sogar entscheiden, überhaupt keine Konfigurationsdatei zu verwenden.  
  
-   Es ist sehr schwierig, einen vorhandenen Satz von WCF\-Diensten zu konfigurieren und zu verwalten.Die Konfigurationsdatei enthält Tausende von XML\-Codezeilen, und es kann sehr gefährlich sein, diese zu ändern.Es müsste eine Möglichkeit geben, diese vielen Codezeilen auf eine Menge zu reduzieren, die besser zu handhaben ist.  
  
## Datenvertragsresolver  
 In .NET 3.5 gab es einige Einschränkungen beim Entwurf bekannter Typen:  
  
-   Es war nicht möglich, während der Serialisierung oder Deserialisierung bekannte Typen dynamisch hinzuzufügen.  
  
-   Serialisierungsprogramme konnten keine unbekannten xsi:type\-Informationen behandeln.  
  
-   Benutzer konnten nicht angeben, welche xsi:type\-Informationen erscheinen sollten, um z. B. die Serialisierungsinstanz zu verkleinern.  
  
 Der [DataContractResolver](../../../docs/framework/wcf/samples/datacontractresolver.md) löst diese Probleme in .NET 4.5.  
  
### Erste Schritte  
  
-   [Dokumentation zur Datenvertragsresolver\-API](http://go.microsoft.com/fwlink/?LinkId=204946)  
  
-   [Einführung in den Datenvertragsresolver](http://go.microsoft.com/fwlink/?LinkId=204947)  
  
-   Beispiele:  
  
    -   [DataContractResolver](../../../docs/framework/wcf/samples/datacontractresolver.md)  
  
    -   [KnownAssemblyAttribute](../../../docs/framework/wcf/samples/knownassemblyattribute.md)  
  
### Datenvertragsresolver\-Szenarien  
  
-   Mit dem Datenvertragsresolver kann das Deklarieren von vielen <xref:System.Runtime.Serialization.KnownTypeAttribute>\-Objekten in einem Dienst vermieden werden.  
  
-   Zudem trägt ein Datenvertragsresolver zum Reduzieren des XML\-Blobs bei.  
  
## Flussdiagramm  
 Ein Flussdiagramm ist ein bekanntes Paradigma, um Domänenprobleme visuell darzustellen.Es ist ein neues Ablaufsteuerungsformat, das in .NET 4 eingeführt wird.Ein Kernmerkmal des Flussdiagrammes ist, dass zu einem beliebigen Zeitpunkt immer nur eine Aktivität ausgeführt wird.In Flussdiagrammen können Schleifen und alternative Ergebnisse ausgedrückt werden, aber nicht die gleichzeitige Ausführung mehrerer Knoten.  
  
### Erste Schritte  
  
-   Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] eine Konsolenanwendung für Workflows.Fügen Sie im Workflow\-Designer ein Flussdiagramm hinzu.  
  
-   Die Flussdiagrammfunktion verwendet die folgenden Klassen:  
  
    -   <xref:System.Activities.Statements.Flowchart>  
  
    -   <xref:System.Activities.Statements.FlowNode>  
  
    -   <xref:System.Activities.Statements.FlowDecision>  
  
    -   <xref:System.Activities.Statements.FlowStep>  
  
    -   <xref:System.Activities.Statements.FlowSwitch%601>  
  
-   Beispiele:  
  
    -   [Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch](../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
  
    -   [StateMachine\-Szenario mit einer Kombination aus FlowChart und Pick](../../../docs/framework/windows-workflow-foundation/samples/statemachine-scenario-using-a-combination-of-flowchart-and-pick.md)  
  
    -   [Einstellungsprozess](../../../docs/framework/windows-workflow-foundation/samples/hiring-process.md)  
  
-   Designerdokumentation:  
  
    -   [Flussdiagramm\-Aktivitätsdesigner](../Topic/Flowchart%20Activity%20Designers.md)  
  
### Flussdiagrammszenarien  
 Eine Flussdiagrammaktivität kann verwendet werden, um ein Ratespiel zu implementieren.Das Ratespiel ist sehr simpel: Der Computer wählt eine Zufallszahl aus, die der Spieler erraten muss.Wenn der Spieler einen Tipp abgibt, zeigt der Computer einen Hinweis an \(z. B."die Zahl war zu hoch"\).Wenn der Spieler die Zahl in weniger als 7 Versuchen errät, zeigt der Computer einen besonderen Glückwunsch an.Dieses Spiel kann mit einer Kombination der folgenden Verfahrensaktivitäten implementiert werden:  
  
-   <xref:System.Activities.Statements.Sequence>  
  
-   <xref:System.Activities.Statements.While>  
  
-   <xref:System.Activities.Statements.Switch%601>  
  
-   <xref:System.Activities.Statements.TryCatch>  
  
-   <xref:System.Activities.Statements.Assign%601>  
  
-   <xref:System.Activities.Statements.If>  
  
## Verfahrensaktivitäten \(Sequence, If, ForEach, Switch, Assign, DoWhile, While\)  
 Verfahrensaktivitäten stellen einen Mechanismus bereit, um sequenzielle Ablaufsteuerung mit Konzepten zu modellieren, die Programmierern vertraut sind.Diese Aktivitäten ermöglichen herkömmlich strukturierte Konstrukte der Programmiersprache und stellen ggf. Sprachparität mit allgemeinen Verfahrenssprachen wie C\#\/VB bereit.  
  
### Erste Schritte  
  
-   Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] eine Konsolenanwendung für Workflows.Fügen Sie im Workflow\-Designer Verfahrensaktivitäten hinzu.  
  
-   Beispiele:  
  
    -   [Einstellungsprozess](../../../docs/framework/windows-workflow-foundation/samples/hiring-process.md)  
  
    -   [Unternehmenseinkaufsprozess](../../../docs/framework/windows-workflow-foundation/samples/corporate-purchase-process.md)  
  
-   Designerdokumentation:  
  
    -   [Parallel\-Aktivitätsdesigner](../Topic/Parallel%20Activity%20Designer.md)  
  
    -   [ParallelForEach\<T\>\-Aktivitätsdesigner](../Topic/ParallelForEach%3CT%3E%20Activity%20Designer.md)  
  
### Verfahrensaktivitätsszenarien  
  
-   <xref:System.Activities.Statements.Parallel> Parallel: Ein Intranet\-Dokumentverwaltungssystem beinhaltet einen Dokumentgenehmigungsworkflow.Dokumente müssen von Personen in mehreren Abteilungen genehmigt werden, bevor sie im Intranet veröffentlicht werden können.Es gibt keine feste Reihenfolge für die Genehmigungen. Sie können jederzeit erteilt werden, während sich das Dokument in der Phase "Genehmigung ausstehend" befindet.Wenn ein Benutzer ein Dokument zwecks Überprüfung übermittelt, muss es vom direkten Vorgesetzten des Benutzers, dem Intranetadministrator und dem Leiter der internen Kommunikation genehmigt werden.  
  
-   <xref:System.Activities.Statements.ParallelForEach%601>: Eine WF\-Anwendung verwaltet Unternehmenseinkäufe innerhalb eines großen Unternehmens.Die Unternehmensregeln schreiben vor, dass vor einem Kauf die Angebote von drei verschiedenen Anbietern eingeholt werden müssen.Ein Mitarbeiter der Einkaufsabteilung wählt drei Anbieter aus der Anbieterliste des Unternehmens aus.Nachdem diese Anbieter ausgewählt und benachrichtigt wurden, wartet das Unternehmen auf die Unterbreitung ihrer Angebote.Die Angebote können in beliebiger Reihenfolge eingehen.Zum Implementieren dieses Szenarios in WF wird eine <xref:System.Activities.Statements.ParallelForEach%601>\-Aktivität verwendet, die die Auflistung von Anbietern durchläuft und Angebote anfordert.Nachdem alle Angebote eingegangen sind, wird das beste Angebot ausgewählt und angezeigt.  
  
## InvokeMethod  
 Die <xref:System.Activities.Statements.InvokeMethod>\-Aktivität erlaubt den Aufruf öffentlicher Methoden in Objekten oder Typen im Gültigkeitsbereich.Die Aktivität unterstützt den Aufruf von Instanz\- und statischen Methoden mit oder ohne Parameter \(einschließlich Parameterarrays\) und generischen Methoden.Zudem erlaubt sie eine synchrone und asynchrone Methodenausführung.  
  
### Erste Schritte  
  
-   Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] eine Konsolenanwendung für Workflows.Fügen Sie eine <xref:System.Activities.Statements.InvokeMethod>\-Aktivität im Workflow\-Designer hinzu, und konfigurieren Sie statische und Instanzmethoden für die Aktivität.  
  
-   Beispiele:  
  
    -   [InvokeMethod](../../../docs/framework/windows-workflow-foundation/samples/invokemethod.md)  
  
-   Designerdokumentation: [InvokeMethod\-Aktivitätsdesigner](../Topic/InvokeMethod%20Activity%20Designer.md)  
  
### InvokeMethod\-Szenarien  
  
-   Eine Methode in einem Objekt im Gültigkeitsbereich muss aufgerufen werden.Beispielsweise muss einem Wörterbuch ein Wert hinzugefügt werden.Die Add\-Methode der Instanz des Wörterbuchs wird aufgerufen, und der Schlüssel und der Wert werden bereitgestellt.  
  
-   Für ein Legacy\-CLR\-Objekt muss eine Methode aufgerufen werden.Anstatt eine benutzerdefinierte Aktivität zu erstellen, um den Aufruf dieser Legacyklasse zu umschließen, wenn es sich während der Workflowausführung im Gültigkeitsbereich befindet, kann <xref:System.Activities.Statements.InvokeMethod> verwendet werden.  
  
## Fehlerbehandlungsaktivitäten  
 Die <xref:System.Activities.Statements.TryCatch>\-Aktivität stellt einen Mechanismus zum Abfangen von Ausnahmen bereit, die während der Ausführung eines Satzes enthaltener Aktivitäten auftreten \(vergleichbar mit dem Try\/Catch\-Konstrukt in C\#\/VB\).<xref:System.Activities.Statements.TryCatch> stellt eine Ausnahmebehandlung auf Workflowebene bereit.Wenn ein Ausnahmefehler ausgelöst wird, wird der Workflow abgebrochen, und der Finally\-Block wird nicht ausgeführt.Dieses Verhalten ist mit C\# konsistent.  
  
### Erste Schritte  
  
-   Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] eine Konsolenanwendung für Workflows.Fügen Sie im Workflow\-Designer eine <xref:System.Activities.Statements.TryCatch>\-Aktivität hinzu.  
  
-   Beispiele:  
  
    1.  [Fehlerbehandlung in einer Flussdiagrammaktivität mit TryCatch](../../../docs/framework/windows-workflow-foundation/samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)  
  
    2.  [Verwenden von Verfahrensaktivitäten](../../../docs/framework/windows-workflow-foundation/samples/using-procedural-activities.md)  
  
-   Designerdokumentation: [Fehlerbehandlungsaktivitätsdesigner](../Topic/Error%20Handling%20Activity%20Designers.md)  
  
### Fehlerbehandlungsszenarien  
 Wenn ein Fehler auftritt, müssen ein Satz von Aktivitäten und eine bestimmte Logik ausgeführt werden.Wenn während dieser Fehlerbehandlung festgestellt wird, dass der Fehler nicht behoben werden kann, wird die Ausnahme erneut ausgelöst, und die übergeordnete Aktivität \(oder der Host\) befasst sich mit dem Problem.  
  
## Auswählen der Aktivität  
 Die <xref:System.Activities.Statements.Pick>\-Aktivität stellt eine ereignisbasierte Flusssteuerungsmodellierung in WF bereit.<xref:System.Activities.Statements.Pick> enthält zahlreiche Verzweigungen, wobei jede Verzweigung vor ihrer Ausführung auf ein bestimmtes Ereignis wartet.In diesem Setup verhält sich ein <xref:System.Activities.Statements.Pick> ähnlich wie ein <xref:System.Activities.Statements.Switch%601>, für den die Aktivität nur einen der überwachten Ereignissätze ausführt.Jede Verzweigung ist ereignisgesteuert, und das Ereignis, das zuerst auftritt, führt zuerst die entsprechende Verzweigung aus.Alle anderen Verzweigungen werden abgebrochen, und die Überwachung der Ereignisse wird beendet.  
  
### Erste Schritte  
  
-   Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] eine Konsolenanwendung für Workflows.Fügen Sie im Workflow\-Designer eine <xref:System.Activities.Statements.Pick>\-Aktivität hinzu.  
  
-   Beispiel: [Verwenden der Pick\-Aktivität](../../../docs/framework/windows-workflow-foundation/samples/using-the-pick-activity.md)  
  
-   Designerdokumentation: [Pick\-Aktivitätsdesigner](../Topic/Pick%20Activity%20Designer.md)  
  
### Auswahlszenario  
 Ein Benutzer muss zur Eingabe aufgefordert werden.Unter normalen Umständen würde der Entwickler einen Methodenaufruf wie <xref:System.Console.ReadLine%2A> verwenden, um einen Benutzer zur Eingabe aufzufordern.Das Problem bei diesem Setup ist, dass das Programm wartet, bis der Benutzer etwas eingibt.In diesem Szenario wird ein Timeout benötigt, um die Blockierung einer blockierenden Aktivität aufzuheben.Ein häufiges Szenario ist, dass eine Aufgabe innerhalb einer bestimmte Zeitspanne abgeschlossen werden muss.Das Umsetzen eines Timeouts für eine blockierende Aktivität ist ein Szenario, bei dem eine Auswahl sehr nützlich ist.  
  
## WCF\-Routingdienst  
 Der Routingdienst wurde als generischer Softwarerouter entworfen, mit dem Sie den [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Nachrichtenfluss zwischen den Clients und Diensten steuern können. Mit dem Routingdienst können Sie die Clients von den Diensten entkoppeln. Dies verleiht Ihnen mehr Freiheit in Bezug auf die Konfigurationen, die unterstützt werden können. Auch können Sie bei der Frage, wie die Dienste gehostet werden, flexibler agieren. In .NET 3.5 waren Clients und Dienste eng gekoppelt: Ein Client musste über alle Dienste und deren Ort informiert sein, mit denen er interagieren musste.Außerdem bestanden für WCF in .NET Framework 3.5 die folgenden Einschränkungen:  
  
-   Die Fehlerbehandlung war komplex, da diese Logik fest in den Client codiert werden musste.  
  
-   Clients und Dienste mussten immer die gleichen Bindungen verwenden.  
  
-   Dienste waren selten gut aufgeteilt: Es ist einfacher, eine Clientinteraktion mit nur einem Dienst umzusetzen, der alles implementiert, anstatt zwischen mehreren Diensten auswählen zu müssen.  
  
 Beim Entwurf des Routingdiensts in .NET 4 wurde dafür Sorge getragen, dass diese Probleme leichter gelöst werden können.Der neue Routingdienst hat die folgenden Funktionen:  
  
1.  Inhaltsbasiertes Routing \(<xref:System.ServiceModel.Dispatcher.MessageFilter>\-Objekte untersuchen eine Nachricht, um das Ziel der Nachricht zu ermitteln.  
  
2.  Protokollüberbrückung \(Transport und Nachricht\)  
  
3.  Fehlerbehandlung \(der Router fängt Kommunikationsausnahmen ab und führt ein Failover zu Sicherungsendpunkten aus\)  
  
4.  Dynamische Aktualisierung \(im Speicher\) von <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> und Routingkonfiguration.  
  
### Erste Schritte  
  
1.  Dokumentation: [Routing](../../../docs/framework/wcf/feature-details/routing.md)  
  
2.  Beispiele: [Routingdienste &#91;WCF\-Beispiele&#93;](../../../docs/framework/wcf/samples/routing-services.md)  
  
3.  Blog: [Routing Rules\!](http://go.microsoft.com/fwlink/?LinkId=204956) \(in englischer Sprache\)  
  
### Routingszenarien  
 Der Routingdienst ist in den folgenden Szenarien nützlich:  
  
-   Clients können mit mehreren Diensten interagieren, ohne alle diese Dienste direkt adressieren zu müssen.  
  
-   Clients können zusätzliche Logik für eine Clientanforderung ausführen, um das Routingziel zu bestimmen  
  
-   Die von einem Client durchgeführten Vorgänge können in mehrere Dienstimplementierungen zerlegt werden, ohne dass eine Umgestaltung des Clients erforderlich ist.  
  
-   Clients und Dienste können unterschiedliche Bindungen mit verschiedenen Sicherheitseinstellungen verwenden.  
  
-   Clients können so konfiguriert werden, dass sie stabiler gegenüber Fehlern oder der Nichtverfügbarkeit von Diensten sind.  
  
## WCF\-Suche  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]\-Suche ist eine Frameworktechnologie, mit der Sie einen Suchmechanismus in die Anwendungsinfrastruktur integrieren können.Mit WCF\-Suche können Sie sicherstellen, dass Ihr Dienst ermittelt werden kann, und Ihre Clients für die Suche nach Diensten konfigurieren.Clients müssen nicht mehr mit einem Endpunkt hartcodiert werden, sodass die Anwendung stabiler und fehlertolerant wird.WCF\-Suche ist die perfekte Plattform, um Funktionen für die automatische Konfiguration in die Anwendung zu integrieren.  
  
 Das Produkt basiert auf dem WS\-Discovery\-Standard.Das Produkt zeichnet sich dadurch aus, dass es interoperabel, erweiterbar und generisch ist.Es unterstützt zwei Betriebsmodi:  
  
1.  Verwaltet: Gibt es im Netzwerk eine Entität, die über die vorhandenen Dienste informiert ist, fordern Clients von dieser Entität direkt Informationen an.Dies ist analog zu Active Directory.  
  
2.  Ad\-hoc: Clients verwenden Multicastnachrichten, um Dienste zu suchen.  
  
 Darüber hinaus sind Ermittlungsnachrichten unabhängig vom Netzwerkprotokoll. Sie können für jedes Protokoll verwendet werden, das die Modusanforderungen unterstützt.So können Multicast\-Ermittlungsnachrichten beispielsweise über den UDP\-Kanal oder ein beliebiges anderes Netzwerk gesendet werden, das Multicastmessaging unterstützt. Diese Entwurfsaspekte in Verbindung mit der Funktionsflexibilität ermöglichen es Ihnen, die Suche speziell an Ihre Lösung anzupassen.  
  
### Erste Schritte  
  
-   Dokumentation: [WCF\-Suche](../../../docs/framework/wcf/feature-details/wcf-discovery.md)  
  
-   Beispiele: [Suche \(Beispiele\)](../../../docs/framework/wcf/samples/discovery-samples.md)  
  
### Suchszenarien  
 Ein Entwickler möchte Endpunkte nicht hartcodieren, da noch nicht feststeht, wann der Dienst verfügbar ist.Stattdessen möchte der Entwickler zur Laufzeit einen Dienst auswählen.Zwischen den Komponenten in der Anwendung ist ein höheres Maß an Entkopplung, Stabilität und automatischer Konfiguration erforderlich.  
  
## Nachverfolgung  
 Die Workflownachverfolgung bietet einen Einblick in die Ausführung einer Workflowinstanz. Die Nachverfolgungsereignisse werden von einem Workflow auf Workflowinstanzebene ausgegeben, wenn im Workflow Aktivitäten ausgeführt werden.Dem Workflowhost muss eine Workflownachverfolgungskomponente hinzugefügt werden, um Nachverfolgungsdatensätze zu abonnieren.Die Nachverfolgungsdatensätze werden mit einem Nachverfolgungsprofil gefiltert..NET Framework stellt eine ETW\-Nachverfolgungskomponente \(Event Tracing for Windows, Ereignisablaufverfolgung für Windows\) bereit, und in der Datei "machine.config" wird ein Basisprofil installiert.  
  
### Erste Schritte  
  
1.  Erstellen Sie in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] ein Projekt für eine Dienstanwendung für WCF\-Workflows.Um mit der Projekterstellung zu beginnen, werden <xref:System.ServiceModel.Activities.Receive> und <xref:System.ServiceModel.Activities.SendReply> auf dem Canvas platziert.  
  
2.  Öffnen Sie die Datei "web.config", und fügen Sie ein ETW\-Nachverfolgungsverhalten ohne Profil hinzu.  
  
    1.  Das Standardprofil wird verwendet.  
  
    2.  Öffnen Sie die Ereignisanzeige, und aktivieren Sie den Analysekanal im folgenden Knoten: **Ereignisanzeige**, **Anwendungs\- und Dienstprotokolle**, **Microsoft**, **Windows**, **Anwendungsserver\-Anwendungen**.Klicken Sie mit der rechten Maustaste auf **Analytisch**, und wählen Sie **Protokoll aktivieren** aus.  
  
    3.  Führen Sie den Workflowdienst aus.  
  
    4.  Beobachten Sie die Workflownachverfolgungsereignisse in der Ereignisanzeige.  
  
3.  Beispiele: [Nachverfolgung](../../../docs/framework/windows-workflow-foundation/samples/tracking.md)  
  
4.  Dokumentation: [Nachverfolgung und Ablaufverfolgung für Workflows](../../../docs/framework/windows-workflow-foundation//workflow-tracking-and-tracing.md)  
  
## SQL\-Workflowinstanzspeicher  
 Beim <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> handelt es sich um die SQL Server\-basierte Implementierung eines Instanzspeichers.Ein Instanzspeicher speichert den Zustand einer ausgeführten Instanz zusammen mit allen Daten, die zum Laden und Fortsetzen dieser Instanz erforderlich sind.Der Diensthost weist den Instanzspeicher an, den Instanzzustand zu speichern, wenn der Workflow beibehalten wird. Wenn für diese Instanz eine Nachricht eingeht oder eine Verzögerungsaktivität abläuft, weist der Diensthost den Instanzspeicher an, den Instanzzustand zu laden.  
  
### Erste Schritte  
  
1.  Erstellen Sie in [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] einen Workflow, der eine implizite oder explizite <xref:System.Activities.Statements.Persist>\-Aktivität enthält.Fügen Sie dem Workflowdiensthost das <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>\-Verhalten hinzu.Sie können die Aktivität dem Code oder der Anwendungskonfiguration hinzufügen.  
  
2.  Beispiele: [Persistenz](../../../docs/framework/windows-workflow-foundation/samples/persistence.md)  
  
3.  Dokumentation: [SQL\-Workflowinstanzspeicher](../../../docs/framework/windows-workflow-foundation//sql-workflow-instance-store.md)