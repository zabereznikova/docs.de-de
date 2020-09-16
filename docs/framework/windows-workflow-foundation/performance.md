---
title: Windows Workflow Foundation 4 – Leistung
description: In diesem Artikel werden die Leistungsmerkmale der Haupt Revision von Windows Workflow Foundation erläutert, die Teil von .NET Framework 4 ist.
ms.date: 03/30/2017
ms.assetid: 67d2b3e8-3777-49f8-9084-abbb33b5a766
ms.openlocfilehash: 1ad12d9fd69205bde726fe650a2ec28ba6c750ef
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558341"
---
# <a name="windows-workflow-foundation-4-performance"></a>Windows Workflow Foundation 4 – Leistung

 .NET Framework 4 enthält eine wesentliche Revision des Windows Workflow Foundation (WF) mit hohen Investitionen in die Leistung. Diese neue Revision führt bedeutende Entwurfs Änderungen aus den früheren Versionen von ein [!INCLUDE[wf1](../../../includes/wf1-md.md)] , die als Teil von .NET Framework 3,0 und .NET Framework 3,5 ausgeliefert wurden. Die Architektur wurde auf Grundlage von Programmiermodell, Laufzeit und Tools neu gestaltet, um Leistung und Benutzerfreundlichkeit erheblich zu verbessern. In diesem Thema werden die wichtigen Leistungsmerkmale dieser Revisionen gezeigt und mit denen der vorherigen Version verglichen.

 Die Leistung der einzelnen Workflowkomponenten wurde von WF3 zu WF4 um ein Vielfaches gesteigert.  Dadurch bleibt die Lücke zwischen dem Hand codierten Windows Communication Foundation (WCF)-Diensten und den WCF-Workflow Diensten sehr gering.  Die Workflowlatenzzeit wurde in WF4 bedeutend verringert.  Die Persistenzleistung wurde um den Faktor 2,5 bis 3,0 gesteigert.  Der Mehraufwand für die Systemüberwachung mittels Workflownachverfolgung wurde bedeutend verringert.  Dies sind überzeugende Gründe für die Migration zu WF4 oder zur Verwendung dieser Technologie in Ihren Anwendungen.

## <a name="terminology"></a>Begriff

 Die Version von [!INCLUDE[wf1](../../../includes/wf1-md.md)] , die in .NET Framework 4 eingeführt wurde, wird im weiteren Verlauf dieses Themas als WF4 bezeichnet. [!INCLUDE[wf1](../../../includes/wf1-md.md)] wurde in .NET Framework 3,0 eingeführt und enthielt einige geringfügige Revisionen durch .NET Framework 3,5 SP1. Die .NET Framework 3,5-Version von Workflow Foundation wird im weiteren Verlauf dieses Themas als WF3 bezeichnet. WF3 wird in .NET Framework 4 nebeneinander mit WF4 ausgeliefert. Weitere Informationen zum Migrieren von WF3-Artefakten zu WF4 finden Sie im [Migrations Handbuch zu Windows Workflow Foundation 4](migration-guidance.md).

 Windows Communication Foundation (WCF) ist das vereinheitlichte Programmiermodell von Microsoft zum entwickeln Dienst orientierter Anwendungen. Sie wurde zuerst als Teil von .NET 3,0 zusammen mit WF3 eingeführt und ist jetzt eine der Hauptkomponenten des .NET Framework.

 Windows Server AppFabric ist eine Reihe integrierter Technologien, mit denen das Erstellen, Skalieren und Verwalten von Webanwendungen und zusammengesetzten Anwendungen, die unter IIS ausgeführt werden, vereinfacht wird. Es stellt Tools zum Überwachen und Verwalten von Diensten und Workflows bereit. Weitere Informationen finden Sie unter [Windows Server AppFabric 1,0](/previous-versions/appfabric/ff384253(v=azure.10)).

## <a name="goals"></a>Ziele
 In diesem Thema werden die Leistungsmerkmale von WF4 anhand von Daten gezeigt, die für unterschiedliche Szenarien gemessen wurden. Außerdem werden ausführliche Vergleiche zwischen WF4 und WF3 bereitgestellt und so die Verbesserungen in dieser neuen Revision veranschaulicht. Die Szenarien und Daten in diesem Artikel quantifizieren die zugrunde liegenden Kosten für verschiedene Aspekte von WF4 und WF3. Diese Daten sind nützlich, um die Leistungsmerkmale von WF4 zu verstehen, und können bei der Planung von Migrationen von WF3 zu WF4 oder beim Einsatz von WF4 in der Anwendungsentwicklung hilfreich sein. Sie sollten jedoch vorsichtig sein, aus den in diesem Artikel präsentierten Daten Schlüsse zu ziehen. Die Leistung einer zusammengesetzten Workflowanwendung hängt stark von der Art der Workflowimplementierung und der Integration der verschiedenen Komponenten ab. Jede Anwendung muss gemessen werden, um die Leistungsmerkmale dieser Anwendung zu bestimmen.

## <a name="overview-of-wf4-performance-enhancements"></a>Übersicht über die Leistungsverbesserungen in WF4
 Bei der Entwicklung und Implementierung von WF4 wurde sorgfältig auf die hohe Leistungsfähigkeit und Skalierbarkeit geachtet, die in den folgenden Abschnitten beschrieben werden.

### <a name="wf-runtime"></a>WF-Laufzeit
 Die zentrale Komponente der [!INCLUDE[wf1](../../../includes/wf1-md.md)]-Laufzeit ist ein asynchroner Planer, der die Ausführung der Aktivitäten in einem Workflow steuert. Er stellt eine leistungsstarke, vorhersagbare Ausführungsumgebung für Aktivitäten zur Verfügung. Die Umgebung weist einen gut definierten Vertrag für Ausführung, Fortsetzung, Abschluss, Abbruch, Ausnahmen und ein vorhersagbares Threadingmodell auf.

 Im Vergleich zu WF3 ist der Planer der WF4-Laufzeit effizienter. Er nutzt den gleichen e/a-Thread Pool, der für WCF verwendet wird. Dies ist bei der Ausführung von Arbeitsaufgaben im Batch Umfang sehr effizient. Die interne Warteschlange des Arbeitselementplaners ist für die gängigsten Verwendungsmuster optimiert. Die WF4-Laufzeit verwaltet die Ausführungs Zustände ebenfalls sehr einfach mit minimaler Synchronisierungs-und Ereignis Behandlungs Logik, während WF3 von einer umfangreichen Ereignis Registrierung und einem Aufruf abhängig ist, um eine komplexe Synchronisierung für Zustandsübergänge auszuführen.

### <a name="data-storage-and-flow"></a>Datenspeicherung und -fluss
 In WF3 werden einer Aktivität zugeordnete Daten durch Abhängigkeitseigenschaften modelliert, die vom Typ <xref:System.Windows.DependencyProperty> implementiert werden. Das Muster für die Abhängigkeits Eigenschaft wurde in Windows Presentation Foundation (WPF) eingeführt. Im Allgemeinen ist dieses Muster sehr flexibel, sodass eine einfache Datenbindung und andere Benutzeroberflächenfunktionen unterstützt werden. Für das Muster müssen jedoch die Eigenschaften als statische Felder in der Workflowdefinition definiert sein. Jedes Mal, wenn die [!INCLUDE[wf1](../../../includes/wf1-md.md)]-Laufzeit die Eigenschaftswerte festlegt oder abruft, wird eine komplexe Suchlogik angewendet.

 WF4 verwendet eine Bewertungslogik mit Klartextdaten, um die Verarbeitung von Daten in einem Workflow erheblich zu verbessern. Die in einer Aktivität gespeicherten Daten werden durch zwei verschiedene Konzepte (Variablen und Argumente) von den Daten getrennt, die über die Aktivitätsgrenzen fließen. Wenn ein eindeutiger hierarchischer Bereich für Variablen und "in/out-/INOUT"-Argumente verwendet wird, wird die Daten Verwendungs Komplexität für Aktivitäten drastisch reduziert, und die Lebensdauer der Daten wird ebenfalls automatisch festgelegt. Aktivitäten verfügen über eine gut definierte Signatur, die von ihren Argumenten beschrieben wird. Durch die einfache Überprüfung einer Aktivität können Sie bestimmen, welche Daten erwartet und welche Daten als Ausführungsergebnis erzeugt werden.

 In WF3 wurden Aktivitäten bei der Erstellung eines Workflows initialisiert. In WF4 werden Aktivitäten nur dann initialisiert, wenn die entsprechenden Aktivitäten ausgeführt werden. Dies ermöglicht einen einfacheren Aktivitätslebenszyklus ohne Vorgänge zum Initialisieren und zum Aufheben der Initialisierung, wenn eine neue Workflowinstanz erstellt wird. Somit wurde die Effizienz gesteigert.

### <a name="control-flow"></a>Ablaufsteuerung
 Wie andere Programmiersprachen auch unterstützt [!INCLUDE[wf1](../../../includes/wf1-md.md)] Ablaufsteuerungen für Workflowdefinitionen. Hierzu wurde ein Satz von Ablaufsteuerungsaktivitäten für die Sequenzierung, die Ausführung als Schleife, das Verzweigen und andere Muster eingeführt. Wenn in WF3 dieselbe Aktivität erneut ausgeführt werden muss, wird ein neuer <xref:System.Workflow.ComponentModel.ActivityExecutionContext> erstellt und die Aktivität durch eine komplexe Serialisierungs- und eine Deserialisierungslogik auf Grundlage von <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> geklont. Normalerweise ist die Leistung bei iterativen Ablaufsteuerungen viel geringer als beim Ausführen einer Sequenz von Aktivitäten.

 WF4 behandelt diesen Vorgang anders. Es nimmt die Aktivitätsvorlage, erstellt ein neues ActivityInstance-Objekt und fügt es der Planerwarteschlange hinzu. Dieser gesamte Prozess umfasst nur explizite Objekt Erstellung und ist sehr einfach.

### <a name="asynchronous-programming"></a>Asynchrone Programmierung
 Anwendungen weisen in der Regel bessere Leistung und Skalierbarkeit mit asynchroner Programmierung für lang ausgeführte blockierende Vorgänge auf, wie z. B. E/A oder verteilte Computervorgänge. WF4 stellt asynchrone Unterstützung durch die Basisaktivitätstypen <xref:System.Activities.AsyncCodeActivity> und <xref:System.Activities.AsyncCodeActivity%601> bereit. Die Laufzeit versteht asynchrone Aktivitäten systemintern und kann daher die Instanz automatisch in eine Zone ohne Persistenz verschieben, während die asynchrone Arbeit aussteht. Benutzerdefinierte Aktivitäten können von diesen Typen abgeleitet werden, um asynchrone Aufgaben auszuführen, ohne dass der Workflowplanerthread angehalten und Aktivitäten, die möglicherweise parallel ausgeführt werden, blockiert werden.

### <a name="messaging"></a>Nachrichten
 Anfänglich hatte WF3 sehr beschränkte Messagingunterstützung über externe Ereignisse oder Webdienstaufrufe. In .NET 3,5 können Workflows als WCF-Clients implementiert oder über und als WCF-Dienste verfügbar gemacht werden <xref:System.Workflow.Activities.SendActivity> <xref:System.Workflow.Activities.ReceiveActivity> . In WF4 wurde das Konzept der Workflow basierten Messaging Programmierung durch die enge Integration von WCF-Messaging Logik in WF weiter gestärkt.

 Die vereinheitlichte Pipeline zur Nachrichtenverarbeitung in WCF in .NET 4 unterstützt WF4-Dienste bei einer deutlich besseren Leistung und Skalierbarkeit als bei WF3. WF4 stellt außerdem eine umfangreichere Messagingprogrammierungsunterstützung bereit, die komplexe Nachrichtenaustauschmuster (MEPs) modellieren kann. Entwickler verwenden entweder typisierte Dienstverträge, um eine einfache Programmierung zu erreichen, oder nicht typisierte Dienstverträge, um bessere Leistung ohne Bezahlung von Serialisierungskosten zu erzielen. Die clientseitige Channelzwischenspeicherunterstützung über die <xref:System.ServiceModel.Activities.SendMessageChannelCache>-Klasse in WF4 hilft Entwicklern beim Erstellen schneller Anwendungen mit minimalem Aufwand. Weitere Informationen finden Sie unter [Ändern der Cache Freigabe Ebenen für Sendeaktivitäten](../wcf/feature-details/changing-the-cache-sharing-levels-for-send-activities.md).

### <a name="declarative-programming"></a>Deklarative Programmierung
 WF4 stellt ein reines und einfaches, deklaratives Programmierframework bereit, um Geschäftsprozesse und -dienste zu modellieren. Das Programmiermodell unterstützt die vollständig deklarative Komposition von Aktivitäten ohne Code-Beside, was die Workflowerstellung sehr vereinfacht. In .NET Framework 4 wurde das XAML-basierte deklarative Programmier Framework in der einzelnen Assembly vereinheitlicht System.Xaml.dll, um sowohl WPF als auch WF zu unterstützen.

 In WF4 stellt XAML eine wirklich deklarative Erfahrung bereit und lässt die vollständige Definition des Workflows in XML-Markup zu, wobei auf Aktivitäten und Typen verwiesen wird, die mithilfe von .NET erstellt wurden. Ohne Einbeziehen benutzerdefinierter Code-Behind-Logik war dies in WF3 mit dem XOML-Format schwierig. Der neue XAML-Stapel in .NET 4 bietet eine viel bessere Leistung beim Serialisieren/Deserialisieren von Workflow Artefakten und macht die deklarative Programmierung ansprechender und stabiler.

### <a name="workflow-designer"></a>Workflow-Designer
 Eine vollständig deklarative Programmierungsunterstützung für WF4 stellt der Entwurfszeitleistung für große Workflows explizit höhere Anforderungen. Der Workflow-Designer in WF4 weist eine viel bessere Skalierbarkeit für große Workflows als in WF3 auf. Dank der Unterstützung der Benutzeroberflächenvirtualisierung kann der Designer einen großen Workflow von 1000 Aktivitäten einfach in wenigen Sekunden laden, obwohl es beinahe unmöglich ist, einen Workflow von einigen hundert Aktivitäten mit dem WF3-Designer zu laden.

## <a name="component-level-performance-comparisons"></a>Leistungsvergleiche auf Komponentenebene
 Dieser Abschnitt enthält Daten zu direkten Vergleichen zwischen einzelnen Aktivitäten in WF3-und WF4-Workflows.  Hauptbereiche wie Persistenz haben tiefgründigere Auswirkungen auf die Leistung als die einzelnen Aktivitätskomponenten.  Die Leistungsverbesserungen an einzelnen Komponenten in WF4 sind dennoch wichtig, da die Komponenten jetzt schnell genug sind, um mit der handcodierten Orchestrierungslogik verglichen zu werden.  Ein Beispiel hierfür finden Sie im nächsten Abschnitt: "Dienst Kompositions Szenario".

### <a name="environment-setup"></a>Einrichten der Umgebung
 ![Umgebungs Einrichtung für Workflow-Leistungsmessung](./media/performance/performance-test-environment.gif)

 Die oben erwähnte Abbildung zeigt die zur Leistungsmessung auf Komponentenebene verwendete Computerkonfiguration. Ein einzelner Server und fünf Clients sind über eine 1-GBit/s-Ethernet-Netzwerkschnittstelle verbunden. Zur einfacheren Messung ist der Server so konfiguriert, dass ein einzelner Kern eines Dual-Proc/Quad-Core-Servers verwendet wird, der unter Windows Server 2008 x86 ausgeführt wird. Die CPU-Auslastung des Systems wird bei annähernd 100&#160;% gehalten.

### <a name="test-details"></a>Testdetails
 Die WF3-<xref:System.Workflow.Activities.CodeActivity> ist wahrscheinlich die einfachste Aktivität, die in einem WF3-Workflow verwendet werden kann.  Die Aktivität ruft eine Methode im Code-Behind auf, in die der Workflowprogrammierer benutzerdefinierten Code einfügen kann.  In WF4 gibt es kein direktes Pendant zur WF3-<xref:System.Workflow.Activities.CodeActivity>, die dieselbe Funktionalität bietet.  Beachten Sie, dass es eine <xref:System.Activities.CodeActivity>-Basisklasse in WF4 gibt, die nicht mit der WF3-<xref:System.Workflow.Activities.CodeActivity> im Zusammenhang steht.  Workflowautoren werden ermutigt, benutzerdefinierte Aktivitäten und Nur-XAML-Workflows zu erstellen.  Unten in den Tests wird eine Aktivität mit der Bezeichnung `Comment` anstelle einer leeren <xref:System.Workflow.Activities.CodeActivity> in WF4-Workflows verwendet.  Der Code in der `Comment`-Aktivität lautet folgendermaßen:

```csharp
[ContentProperty("Body")]
    public sealed class Comment : CodeActivity
    {
        public Comment()
            : base()
        {
        }

        [DefaultValue(null)]
        public Activity Body
        {
            get;
            set;
        }

        protected override void Execute(CodeActivityContext context)
        {
        }
    }
```

### <a name="empty-workflow"></a>Leerer Workflow
 Dieser Test verwendet einen Sequenzworkflow ohne untergeordnete Aktivitäten.

### <a name="single-activity"></a>Einfache Aktivität
 Der Workflow ist ein Sequenzworkflow, der eine untergeordnete Aktivität enthält.  Bei der Aktivität handelt es sich um eine <xref:System.Workflow.Activities.CodeActivity> ohne Code in WF3 und um eine `Comment`-Aktivität in WF4.

### <a name="while-with-1000-iterations"></a>Bei 1000 Iterationen
 Der Sequenzworkflow enthält eine <xref:System.Activities.Statements.While>-Aktivität mit einer untergeordneten Aktivität in der Schleife, die keine Arbeit ausführt.

### <a name="replicator-compared-to-parallelforeach"></a>Replikationsdienst im Vergleich zu ParallelForEach
 <xref:System.Workflow.Activities.ReplicatorActivity> in WF3 weist sequenzielle und parallele Ausführungsmodi auf.  Im sequenziellen Modus entspricht die Leistung der Aktivität in etwa der der <xref:System.Workflow.Activities.WhileActivity>.  Die <xref:System.Workflow.Activities.ReplicatorActivity> ist für die parallele Ausführung äußerst nützlich.  Das Pendant dafür in WF4 ist die <xref:System.Activities.Statements.ParallelForEach%601>-Aktivität.

 Das folgende Diagramm zeigt die für diesen Test verwendeten Workflows. Der WF3-Workflow befindet sich links, der WF4-Workflow rechts.

 ![WF3-ReplicatorActivity und WF4-ParallelForEach](./media/performance/replicator-parallel-wf3-wf4.gif)

### <a name="sequential-workflow-with-five-activities"></a>Sequenzieller Workflow mit fünf Aktivitäten
 Dieser Test ist dafür vorgesehen, den Effekt des Ausführens mehrerer Aktivitäten nacheinander zu zeigen.  Die Sequenz enthält fünf Aktivitäten.

### <a name="transaction-scope"></a>Transaktionsbereich
 Der Transaktionsbereichstest unterscheidet sich insofern minimal von den anderen Tests, da nicht für jede Iteration eine neue Workflowinstanz erstellt wird.  Stattdessen wird der Workflow mit einer while-Schleife strukturiert, die eine <xref:System.Activities.Statements.TransactionScope>-Aktivität enthält, die eine einzelne Aktivität enthält, die keine Arbeit ausführt.  Jede einzelne Ausführung eines Batches von 50 Iterationen über die while-Schleife wird als einzelner Vorgang betrachtet.

### <a name="compensation"></a>Kompensierung
 Der WF3-Workflow verfügt über eine einzelne kompensierbare Aktivität mit der Bezeichnung `WorkScope`.  Die Aktivität implementiert einfach die <xref:System.Workflow.ComponentModel.ICompensatableActivity>-Schnittstelle:

```csharp
class WorkScope :
        CompositeActivity, ICompensatableActivity
    {
        public WorkScope() : base() { }

        public WorkScope(string name)
        {
            this.Name = name;
        }

        public ActivityExecutionStatus Compensate(
            ActivityExecutionContext executionContext)
        {
            return ActivityExecutionStatus.Closed;
        }
    }
```

 Der Fehlerhandler hat die-Aktivität als Ziel `WorkScope` . Der WF4-Workflow ist gleichermaßen einfach.  Eine <xref:System.Activities.Statements.CompensableActivity> verfügt über einen Textkörper und einen Kompensierungshandler.  Als Nächstes folgt eine explizite Kompensierung in der Sequenz.  Die Textkörperaktivität und die Kompensationshandleraktivität sind jeweils leere Implementierungen:

```csharp
public sealed class CompensableActivityEmptyCompensation : CodeActivity
    {
        public CompensableActivityEmptyCompensation()
            : base() { }

        public Activity Body { get; set; }

        protected override void Execute(CodeActivityContext context) { }
    }
    public sealed class CompensableActivityEmptyBody : CodeActivity
    {
        public CompensableActivityEmptyBody()
            : base() { }

        public Activity Body { get; set; }

        protected override void Execute(CodeActivityContext context) { }
    }
```

Im folgenden Diagramm wird der grundlegende Kompensations Workflow gezeigt. Der WF3-Workflow befindet sich links, der WF4-Workflow rechts.

![Grundlegende Kompensations Workflows für WF3 und WF4](./media/performance/basic-compensation-workflows-wf3-wf4.gif)

### <a name="performance-test-results"></a>Ergebnisse des Leistungstests

 ![Tabelle mit Leistungstest-Ergebnisdaten](./media/performance/performance-test-data.gif)

 ![Säulendiagramm Vergleichen von WF3-und WF4-Leistungstest Daten](./media/performance/performance-test-chart.gif)

 Alle Tests werden mit Ausnahme des Transaktionsbereichstests in Workflows pro Sekunde gemessen.  Wie oben angezeigt, wurde die Leistung der [!INCLUDE[wf1](../../../includes/wf1-md.md)]-Laufzeit im gesamten System verbessert, insbesondere in Bereichen, die mehrere Ausführungen derselben Aktivität erfordern wie etwa die while-Schleife.

## <a name="service-composition-scenario"></a>Dienstkompositionsszenario
 Wie im vorherigen Abschnitt "Leistungsvergleiche auf Komponentenebene" gezeigt, wurde der Aufwand zwischen WF3 und WF4 erheblich reduziert.  WCF-Workflow Dienste können jetzt fast mit der Leistung von Hand codierten WCF-Diensten verglichen werden, haben jedoch weiterhin alle Vorteile der [!INCLUDE[wf1](../../../includes/wf1-md.md)] Laufzeit.  Dieses Testszenario vergleicht einen WCF-Dienst mit einem WCF-Workflow Dienst in WF4.

### <a name="online-store-service"></a>Onlineshopdienst
 Eine der Stärken von Windows Workflow Foundation ist die Möglichkeit, Prozesse mithilfe mehrerer Dienste zu verfassen.  Für dieses Beispiel gibt es einen Onlineshopdienst, der zwei Dienstaufrufe orchestriert, um eine Bestellung abzuwickeln.  Der erste Schritt besteht darin, die Bestellung mithilfe eines Bestellungsvalidierungsdiensts zu validieren.  Der zweite Schritt besteht darin, die Bestellung mithilfe eines Warehouse-Diensts auszufüllen.

 Die zwei Back-End-Dienste, Bestellungsvalidierungsdienst und Warehouse-Dienst, bleiben für beide Tests gleich.  Der Teil, der sich ändert, ist der Onlineshopdienst, von dem die Orchestrierung ausgeführt wird.  In einem Fall ist der Dienst handcodiert als WCF-Dienst.  Im anderen Fall wird der Dienst als WCF-Workflow Dienst in WF4 geschrieben. [!INCLUDE[wf1](../../../includes/wf1-md.md)]-spezifische Funktionen wie Nachverfolgen und Persistenz sind für diesen Test deaktiviert.

### <a name="environment"></a>Umgebung
![Einrichten der Umgebung für die Leistungsmessung](./media/performance/performance-test-environment.gif)

 Clientanforderungen werden dem Onlineshopdienst über HTTP von mehreren Computern gestellt.  Ein einzelner Computer hostet alle drei Dienste.  Die Transportebene zwischen dem Onlineshopdienst und den Back-End-Diensten ist TCP oder HTTP.  Die Messung der Vorgänge pro Sekunde basiert auf der Anzahl der beim Onlineshopdienst eingegangenen `PurchaseOrder`-Aufrufe.  Channelpooling ist eine neue, in WF4 verfügbare Funktion.  Im WCF-Teil dieses Test Kanal-Pooling wird nicht standardmäßig bereitgestellt, sodass eine Hand codierte Implementierung einer einfachen Pooling-Technik im Online Store-Dienst verwendet wurde.

### <a name="performance"></a>Leistung
![Säulendiagramm mit der Leistung des Online Store-Dienstanbieter](./media/performance/online-store-performance-graph.gif)

 Beim Herstellen einer Verbindung zu Back-End-TCP-Diensten ohne Channelpooling weist der [!INCLUDE[wf1](../../../includes/wf1-md.md)]-Dienst Auswirkungen von 17,2 % auf den Durchsatz auf.  Mit Channelpooling beträgt der Abzug etwa 23,8 %.  Bei HTTP sind die Auswirkungen viel weniger: 4,3 % ohne Pooling und 8,1 % mit Pooling.  Zudem muss beachtet werden, dass bei Verwendung von HTTP das Channelpooling sehr wenig Vorteile bietet.

 Obwohl der Aufwand von der WF4-Laufzeit im Vergleich zu einem Hand codierten WCF-Dienst in diesem Test erfolgt, könnte dies als ungünstigste Szenario angesehen werden.  Die zwei Back-End-Dienste in diesem Test erledigen sehr wenig Arbeit.  In einem echten End-to-End-Szenario würden diese Dienste aufwendigere Vorgänge wie Datenbankaufrufe ausführen und so die Auswirkungen auf die Leistung der Transportebene reduzieren.  Dieses Argument sowie die Vorteile der in WF4 verfügbaren Funktionen machen Workflow Foundation zu einer brauchbaren Lösung beim Erstellen von Orchestrierungsdiensten.

## <a name="key-performance-considerations"></a>Wichtige Überlegungen zur Leistung
 Die Funktionsbereiche in diesem Abschnitt haben sich mit Ausnahme von Interop zwischen WF3 und WF4 dramatisch verändert.  Dies wirkt sich auf das Design von Workflowanwendungen sowie die Leistung aus.

#### <a name="workflow-activation-latency"></a>Workflowaktivierungslatenzzeit
 In einer WCF-Workflow Dienst Anwendung ist die Latenzzeit für das Starten eines neuen Workflows oder das Laden eines vorhandenen Workflows wichtig, da er blockiert werden kann.  Dieser Testfall misst einen WF3-XOML-Host in einem typischen Szenario im Vergleich zu einem WF4-XAMLX-Host.

##### <a name="environment-setup"></a>Einrichten der Umgebung
 ![Umgebungseinrichtung für Latenz- und Durchsatztests](./media/performance/latency-throughput-environment-setup.gif)

##### <a name="test-setup"></a>Testsetup
 In diesem Szenario kontaktiert ein Client Computer mithilfe einer kontextbasierten Korrelation einen WCF-Workflow Dienst.  Kontextkorrelation erfordert eine besondere Kontextbindung und verwendet einen Kontextheader oder ein Cookie, um Meldungen mit der richtigen Workflowinstanz zu verknüpfen.  Ein Leistungsvorteil besteht darin, dass sich die Korrelations-ID im Nachrichtenheader befindet, damit der Nachrichtentext nicht analysiert werden muss.

 Der Dienst erstellt einen neuen Workflow mit der Anforderung und sendet eine sofortige Antwort, damit bei der Messung der Latenzzeit die Zeit für die Ausführung des Workflows nicht einbezogen wird.  Der WF3-Workflow basiert auf XOML mit Code-Behind, und der WF4-Workflow basiert vollständig auf XAML.  Der WF4-Workflow sieht folgendermaßen aus:

 ![WF4-Korrelations Bereich-Workflow](./media/performance/wf4-correlationscope-workflow.gif)

 Die <xref:System.ServiceModel.Activities.Receive>-Aktivität erstellt die Workflowinstanz.  Ein in der empfangenen Meldung übergebener Wert wird in der Antwortnachricht wiederholt.  Eine Sequenz, die der Antwort folgt, enthält den Rest des Workflows.  Im oben erwähnten Fall wird nur eine Kommentaraktivität angezeigt.  Die Anzahl der Kommentaraktivitäten wird geändert, um Workflowkomplexität zu simulieren.  Eine Kommentaraktivität entspricht einer WF3-<xref:System.Workflow.Activities.CodeActivity>, die keine Arbeit erledigt. Weitere Informationen zur Kommentar Aktivität finden Sie im Abschnitt "Leistungsvergleiche auf Komponentenebene" weiter oben in diesem Artikel.

##### <a name="test-results"></a>Testergebnisse

 Kalte und warme Latenz für WCF-Workflow Dienste:

 ![Säulendiagramm mit kalter und warmer Latenz für WCF-Workflow Dienste mit WF3 und WF4](./media/performance/latency-results-graph.gif)

 Im vorherigen Diagramm bezieht sich "kalt" auf den Fall, <xref:System.ServiceModel.WorkflowServiceHost> dass für den angegebenen Workflow kein vorhandener vorhanden ist.  Anders ausgedrückt bedeutet kalte Latenzzeit, dass der Workflow erstmals verwendet wird und XOML oder XAML kompiliert werden muss.  Warme Latenzzeit ist die Zeit zum Erstellen einer neuen Workflowinstanz, wenn der Workflowtyp bereits kompiliert wurde.  Die Komplexität des Workflows macht im Fall von WF4 nur einen geringen Unterschied, weist allerdings in WF3 linearen Fortschritt auf.

#### <a name="correlation-throughput"></a>Korrelationsdurchsatz
 WF4 führt eine neue inhaltsbasierte Korrelationsfunktion ein.  WF3 bot nur kontextbasierte Korrelation.  Die kontextbasierte Korrelation konnte nur über bestimmte WCF-Kanal Bindungen durchgeführt werden.  Beim Verwenden dieser Bindungen wird die Workflow-ID in den Nachrichtenheader eingefügt.  Die WF3-Laufzeit konnte einen Workflow nur anhand seiner ID identifizieren.  Mit Inhalts basierter Korrelation kann der Workflow Autor aus einem relevanten Datenelement wie einer Kontonummer oder einer Kunden-ID einen Korrelations Schlüssel erstellen.

 Kontextbasierte Korrelation weist einen Leistungsvorteil auf, da sich der Korrelationsschlüssel im Nachrichtenheader befindet.  Der Schlüssel kann ohne Deserialisierung/Kopieren der Meldung von der Meldung gelesen werden.  Bei der inhaltsbasierten Korrelation wird der Korrelationsschlüssel im Nachrichtentext gespeichert.  Ein XPath-Ausdruck wird verwendet, um den Schlüssel zu suchen.  Die Kosten für diese zusätzliche Verarbeitung hängen von der Größe der Meldung, Tiefe des Schlüssels im Text und der Anzahl der Schlüssel ab.  Dieser Test vergleicht die kontext - und inhaltsbasierte Korrelation und zeigt zudem den Leistungsabfall beim Verwenden mehrerer Schlüssel.

#### <a name="environment-setup"></a>Einrichten der Umgebung
![Umgebungs Einrichtung für Workflow Leistungstest](./media/performance/performance-test-environment.gif)

#### <a name="test-setup"></a>Testsetup
![Workflowtest für Korrelationsdurchsatz](./media/performance/correlation-throughput-workflow.gif "Workflow Test-Setup für Korrelations Durchsatz")

 Der vorherige Workflow ist derselbe Workflow, der im [persistenzabschnitt](#persistence) verwendet wird. Bei Korrelationstests ohne Persistenz ist kein Persistenzanbieter in der Laufzeit installiert. Korrelation tritt an zwei Stellen auf: CreateOrder und CompleteOrder.

#### <a name="test-results"></a>Testergebnisse
![Korrelationsdurchsatz](./media/performance/correlation-throughput-graph.gif "Korrelations Durchsatz Diagramm")

 Dieses Diagramm zeigt eine Leistungsabnahme als Anzahl der in inhaltsbasierten Korrelationszunahmen verwendeten Schlüssel an.  Die Ähnlichkeit der Kurven zwischen TCP und HTTP gibt den Aufwand an, der diesen Protokollen zugeordnet wurde.

#### <a name="correlation-with-persistence"></a>Korrelation mit Persistenz
 Bei einem persistenten Workflow wird der CPU-Druck von der inhaltsbasierten Korrelation von der Workflowlaufzeit auf die SQL-Datenbank umgestellt.  Die gespeicherten Prozeduren im SQL-Persistenzanbieter passen die Schlüssel an, um den entsprechenden Workflow zu finden.

 ![Liniendiagramm mit Korrelations-und persistenzergebnissen](./media/performance/correlation-persistence-graph.gif)

 Die kontextbasierte Korrelation ist immer noch schneller als die inhaltsbasierte Korrelation.  Der Unterschied ist jedoch weniger deutlich, da die Persistenz mehr Auswirkungen auf die Leistung als die Korrelation hat.

### <a name="complex-workflow-throughput"></a>Komplexer Workflowdurchsatz
 Die Komplexität eines Workflows wird nicht nur an der Anzahl der Aktivitäten gemessen.  Zusammengesetzte Aktivitäten können viele untergeordnete Elemente enthalten, und bei diesen untergeordneten Elementen kann es sich auch um zusammengesetzte Aktivitäten handeln.  Mit der Anzahl der Schachtelungsebenen steigt auch die Anzahl der Aktivitäten, die derzeit den Status "Wird ausgeführt" aufweisen, sowie die Anzahl der Variablen, die diesen Status besitzen können.  Dieser Test vergleicht den Durchsatz von WF3 und WF4 beim Ausführen von komplexen Workflows.

### <a name="test-setup"></a>Testsetup
 Diese Tests wurden auf einem Intel Xeon X5355 mit 2,66 GHz (4-Prozessoren) sowie 4 GB RAM unter Windows Server 2008 x64 durchgeführt.  Der Testcode wird in einem einzelnen Prozess mit einem Thread pro Kern ausgeführt, um 100% CPU-Auslastung zu erreichen.

 Die für diesen Test generierten Workflows verfügen über zwei Hauptvariablen: Tiefe und Anzahl der Aktivitäten in jeder Sequenz.  Jede Tiefenebene enthält eine parallele Aktivität, while-Schleife, Entscheidungen, Zuweisungen und Sequenzen.  Der unten abgebildeten WF4-Designer zeigt das Flussdiagramm der obersten Ebene.  Jede Flussdiagrammaktivität ähnelt dem Hauptflussdiagramm.  Bei der Abbildung dieses Workflows, in dem die Tiefe auf die Parameter des Tests beschränkt ist, hilft es möglicherweise, an ein Fraktal zu denken.

 Die Anzahl der Aktivitäten in einem bestimmten Test wird anhand der Tiefe und der Anzahl der Aktivitäten pro Sequenz bestimmt.  Die folgende Formel berechnet die Anzahl der Aktivitäten im WF4-Test:

 ![Gleichung zur Berechnung der Anzahl von Aktivitäten](./media/performance/number-activities-equation.gif)

 Die Anzahl der Aktivitäten im WF3-Test kann aufgrund einer zusätzlichen Sequenz mit einer etwas anderen Formel berechnet werden:

 ![Gleichung zur Berechnung der Anzahl von WF3-Aktivitäten](./media/performance/wf3-number-activities-equation.gif)

 d entspricht der Tiefe, a der Anzahl der Aktivitäten pro Sequenz.  Die Logik hinter diesen Formeln: Das Produkt aus der ersten Konstante und a entspricht der Anzahl der Sequenzen, die zweite Konstante entspricht der statischen Anzahl der Aktivitäten in der aktuellen Ebene.  In jedem Flussdiagramm sind drei untergeordnete Flussdiagrammaktivitäten vorhanden.  Auf der untersten Ebene sind diese Flussdiagramme leer, aber auf den anderen Ebenen sind sie Kopien des Hauptflussdiagramms.  Die Anzahl der Aktivitäten in der Workflowdefinition der jeweiligen Testvariation ist in der folgenden Tabelle angegeben:

 ![Eine Tabelle, die die Anzahl der in jedem Test verwendeten Aktivitäten anzeigt.](./media/performance/workflow-variation-compare-table.gif)

 Die Anzahl der Aktivitäten in der Workflowdefinition nimmt scharf mit jeder Tiefenebene zu.  In einer angegebenen Workflowinstanz wird jedoch nur ein Pfad pro Entscheidungspunkt ausgeführt, sodass nur eine kleine Teilmenge der tatsächlichen Aktivitäten ausgeführt wird.

 ![Flussdiagramm des Workflows für den komplexen Durchsatz](./media/performance/complex-workflow-throughput-workflow.gif)

 Ein entsprechender Workflow wurde für WF3 erstellt. Der WF3-Designer zeigt den ganzen Workflow im Entwurfsbereich anstelle der Schachtelung an. Er ist daher für eine Anzeige in diesem Thema zu groß. Ein Ausschnitt des Workflows wird unten dargestellt.

 ![Flussdiagramm Ausschnitt des WF3-Workflows](./media/performance/wf3-workflow-snippet.gif)

 Ein anderer Workflow, der Teil dieses Tests ist, verwendet 100 geschachtelte Sequenzen, um die Schachtelung im Extremfall zu üben.  In der innersten Sequenz befindet sich ein einzelner `Comment` oder eine einzelne <xref:System.Workflow.Activities.CodeActivity>.

 ![Flussdiagramm einer in einem Netz stehenden Reihenfolge](./media/performance/nested-sequence-workflow.gif)

 Nachverfolgung und Persistenz werden nicht als Teil dieses Tests verwendet.

### <a name="test-results"></a>Testergebnisse
 ![Säulendiagramm mit Leistungsergebnissen für den Durchsatz](./media/performance/throughput-performance-results.gif)

 Sogar mit komplexen Workflows mit viel Tiefe und einer hohen Anzahl Aktivitäten sind die Leistungsergebnisse mit anderen, weiter oben in diesem Artikel angezeigten Durchsatzzahlen konsistent.  Der Durchsatz von WF4 ist größer und muss auf einer logarithmischen Skala verglichen werden.

### <a name="memory"></a>Arbeitsspeicher
 Der Arbeitsspeicheraufwand von Windows Workflow Foundation wird in zwei Hauptbereichen gemessen: Workflowkomplexität und Anzahl von Workflowdefinitionen.  Arbeitsspeichermessungen wurden auf einem Windows 7-64-Bit-PC vorgenommen.  Es gibt viele Möglichkeiten, die Größe der Workingsetgröße zu ermitteln, wie z. b. das Überwachen von Leistungsindikatoren, der Abruf Umgebung. WorkingSet oder die Verwendung eines Tools wie VMMap, das in [VMMap](/sysinternals/downloads/vmmap)verfügbar ist Eine Kombination von Methoden wurde verwendet, um die Ergebnisse aller Tests abzurufen und zu überprüfen.

### <a name="workflow-complexity-test"></a>Workflowkomplexitätstest
 Der Workflowkomplexitätstest misst den Workingsetunterschied auf Grundlage der Komplexität des Workflows.  Zusätzlich zu den komplexen, im vorherigen Abschnitt verwendeten Workflows werden neue Variationen hinzugefügt, die zwei grundlegende Fälle abdecken: ein einzelner Aktivitätsworkflow und eine Sequenz mit 1000 Aktivitäten.  Für diese Tests werden die Workflows initialisiert und zum Abschluss eine Minute lang in einer einzelnen seriellen Schleife ausgeführt.  Jede Testvariation wird dreimal ausgeführt, und die aufgezeichneten Daten sind der Durchschnitt dieser drei Ausführungen.

 Die zwei neuen grundlegenden Tests weisen Workflows auf, die wie die im Folgenden angezeigten aussehen:

 ![Komplexer Workflow für WF3 und WF4](./media/performance/complex-workflow-wf3-wf4.gif)

 Im oben angezeigten WF3-Workflow werden leere <xref:System.Workflow.Activities.CodeActivity>-Aktivitäten verwendet.  Der WF4-Workflow oben verwendet `Comment`-Aktivitäten.  Die `Comment`-Aktivität wurde weiter oben in diesem Artikel im Abschnitt "Leistungsvergleiche auf Komponentenebene" beschrieben.

 ![Säulendiagramm, das eine komplexe Workflow Speicherauslastung für WF3-und WF4-Workflows anzeigt](./media/performance/complex-memory-usage-wf3-wf4.gif)

 Einer der klaren Trends in diesem Diagramm ist, dass die Schachtelung relativ geringe Auswirkungen auf die Speicherauslastung in WF3 und WF4 hat.  Die bedeutendsten Arbeitsspeicherauswirkungen in einem bestimmten Workflow resultieren aus der Anzahl der Aktivitäten.  Gegeben sind die Daten aus folgenden Variationen: Sequenz 1000, komplexe Tiefe 5 Sequenz 5 und komplexe Tiefe 7 Sequenz 1. Wenn die Anzahl der Aktivitäten 1000 überschreitet, ist es daher klar, dass die Zunahme der Speicherauslastung beträchtlicher wird.  Im Extremfall (Tiefe 7 Sequenz 1) mit ~ 29.000 Aktivitäten verwendet WF4 fast 79 % weniger Arbeitsspeicher als WF3.

### <a name="multiple-workflow-definitions-test"></a>Test mehrerer Workflowdefinitionen
 Das Messen des Arbeitsspeichers pro Workflowdefinition ist wegen der verfügbaren Optionen zum Hosten von Workflows in WF3 und WF4 in zwei verschiedene Tests unterteilt.  Die Tests werden auf eine andere Weise als der Workflowkomplexitätstest ausgeführt, da ein angegebener Workflow als Beispiel angeführt und pro Definition nur einmal ausgeführt wird.  Das liegt daran, dass die Workflowdefinition und ihr Host die gesamte Lebensdauer der AppDomain lang im Arbeitsspeicher bleiben.  Der Arbeitsspeicher, der für die Ausführung einer angegebenen Workflowinstanz verwendet wurde, sollte während der automatischen Speicherbereinigung bereinigt werden.  Die Migrationsanleitung für WF4 enthält detaillierte Informationen zu den Hostingoptionen. Weitere Informationen finden Sie unter [Cookbook zur WF-Migration: Workflow Hosting](migration-guidance.md).

 Das Erstellen vieler Workflowdefinitionen für einen Workflowdefinitionstest kann auf mehrere Arten erfolgen.  Sie können beispielsweise die Codegenerierung verwenden, um einen Satz von 1000 Workflows zu erstellen, die mit Ausnahme des Namens identisch sind, und jeden einzelnen dieser Workflows davon in separaten Dateien speichern.  Dieser Ansatz wurde für den konsolengehosteten Test gewählt.  In WF3 wurde die <xref:System.Workflow.Runtime.WorkflowRuntime>-Klasse verwendet, um die Workflowdefinitionen auszuführen.  WF4 kann entweder <xref:System.Activities.WorkflowApplication> zum Erstellen einer einzelnen Workflowinstanz oder, ähnlich einem Methodenaufruf, <xref:System.Activities.WorkflowInvoker> zum direkten Ausführen der Aktivität verwenden.  <xref:System.Activities.WorkflowApplication> ist ein Host einer einzelnen Workflowinstanz, weist engere Funktionsparität zu <xref:System.Workflow.Runtime.WorkflowRuntime> auf und wurde daher in diesem Test verwendet.

 Beim Hosten von Workflows in IIS kann ein <xref:System.Web.Hosting.VirtualPathProvider> zum Erstellen eines neuen <xref:System.ServiceModel.WorkflowServiceHost> verwendet werden, statt alle XAMLX- oder XOML-Dateien zu generieren.  Der <xref:System.Web.Hosting.VirtualPathProvider> verarbeitet die eingehende Anforderung und antwortet mit einer "virtuellen Datei", die aus einer Datenbank geladen oder in diesem Fall dynamisch generiert werden kann.  Daher ist es nicht erforderlich, 1000 physische Dateien zu erstellen.

 Die im Konsolentest verwendeten Workflowdefinitionen waren einfache sequenzielle Workflows mit einer einzelnen Aktivität.  Die einzelne Aktivität war eine leere <xref:System.Workflow.Activities.CodeActivity> für WF3 und eine `Comment`-Aktivität für WF4.  Im von IIS gehosteten Fall wurden Workflows verwendet, die mit dem Empfang einer Meldung beginnen und mit dem Senden einer Antwort enden:

Die folgende Abbildung zeigt einen WF3-Workflow mit ReceiveActivity und einen WF4-Workflow mit Anforderungs-/Antwort-Muster:

 ![Workflowdienste in WF3 und WF4](./media/performance/workflow-receive-activity.gif)

 In der folgenden Tabelle wird das Delta des Workingsets zwischen einer einzelnen Workflow Definition und 1001 Definitionen angezeigt:

|Hostingoptionen|WF3-Workingset-Differenz|WF4-Workingset-Differenz|
|---------------------|---------------------------|---------------------------|
|Von der Konsolenanwendung gehostete Workflows|18 MB|9 MB|
|Von IIS gehostete Workflowdienste|446 MB|364 MB|

 Das Hosten von Workflow Definitionen in IIS beansprucht aufgrund der <xref:System.ServiceModel.WorkflowServiceHost> detaillierten WCF-Dienst Artefakte und der Nachrichten Verarbeitungslogik, die dem Host zugeordnet ist, viel mehr Arbeitsspeicher.

 Beim Konsolenhosting in WF3 wurden die Workflows in Code anstelle von XOML implementiert.  In WF4 wird standardmäßig XAML verwendet.  Das XAML wird als eingebettete Ressource in der Assembly gespeichert und während der Laufzeit kompiliert, um die Implementierung des Workflows bereitzustellen.  Dieser Prozess erfordert etwas zusätzlichen Aufwand.  Um einen fairen Vergleich zwischen WF3 und WF4 zu erhalten, wurden anstelle von XAML codierte Workflows verwendet.  Unten wird ein Beispiel für einen der WF4-Workflows aufgeführt:

```csharp
public class Workflow1 : Activity
{
    protected override Func<Activity> Implementation
    {
        get
        {
            return new Func<Activity>(() =>
            {
                return new Sequence
                {
                    Activities = {
                        new Comment()
                    }
                };
            });
        }
        set
        {
            base.Implementation = value;
        }
    }
}
```

 Es gibt viele andere Faktoren, die sich auf den Speicherverbrauch auswirken können. Derselbe Rat für alle verwalteten Programme trifft auch hier zu.  In von IIS gehosteten Umgebungen bleibt das für eine Workflowdefinition erstellte <xref:System.ServiceModel.WorkflowServiceHost>-Objekt im Arbeitsspeicher, bis der Anwendungspool wiederverwendet wird.  Dies sollte beim Schreiben von Erweiterungen bedacht werden.  Außerdem empfiehlt es sich, globale Variablen (Variablen, die für den gesamten Workflow gelten) zu vermeiden und den Bereich von Variablen nach Möglichkeit einzuschränken.

## <a name="workflow-runtime-services"></a>Workflowlaufzeitdienste

### <a name="persistence"></a>Persistenz
 WF3 und WF4 werden jeweils mit einem SQL-Persistenzanbieter bereitgestellt.  Der WF3-SQL-Persistenzanbieter ist eine einfache Implementierung, die die Workflowinstanz serialisiert und in einem BLOB speichert.  Daher hängt die Leistung dieses Anbieters stark von der Größe der Workflowinstanz ab.  In WF3 konnte die Instanzgröße aus vielen Gründen zunehmen, wie bereits weiter oben in diesem Artikel erläutert.  Viele Kunden verwenden den Standard-SQL-Persistenzanbieter nicht, da das Speichern einer serialisierten Instanz in einer Datenbank keinen Einblick in den Status des Workflows erlaubt.  Zur Suche nach einem bestimmten Workflow ohne Kenntnis der Workflow-ID müssten Sie jede beibehaltene Instanz deserialisieren und ihren Inhalt untersuchen.  Viele Entwickler bevorzugen das Verfassen eigener Persistenzanbieter, um dieses Hindernis zu umgehen.

 Im WF4-SQL-Persistenzanbieter wird versucht, einige dieser Probleme zu behandeln.  In den Persistenztabellen stehen bestimmte Informationen, wie z. B. die aktiven Lesezeichen und heraufstufbare Eigenschaften, zur Verfügung.  Die Ausführung der neuen, inhaltsbasierten Korrelationsfunktion in WF4 funktionierte nicht gut mit dem WF3-SQL-Persistenzansatz, was zu einer Änderung in der Organisation der persistenten Workflowinstanz führte.  Dadurch wird der Auftrag des Persistenzanbieters komplexer, was zu einer zusätzlichen Belastung der Datenbank führt.

### <a name="environment-setup"></a>Einrichten der Umgebung
![Umgebungs Einrichtung für Workflow Leistungstest](./media/performance/performance-test-environment.gif)

### <a name="test-setup"></a>Testsetup
 Trotz verbesserten Funktionsumfangs und besserer Parallelitätsbehandlung ist der SQL-Persistenzanbieter in WF4 schneller als der Anbieter in WF3.  Zur Veranschaulichung werden nachfolgend zwei Workflows verglichen, die prinzipiell dieselben Vorgänge in WF3 und WF4 ausführen.

 ![Persistenzworkflow in WF3 on left und WF4 on right](./media/performance/persist-workflow-wf3-wf4.gif)

 Die beiden Workflows wurden anhand einer empfangenen Meldung erstellt.  Der Workflow wird beibehalten, nachdem eine erste Antwort gesendet wurde.  In WF3 wird eine leere <xref:System.Workflow.ComponentModel.TransactionScopeActivity> verwendet, um die Persistenz zu initiieren.  Dasselbe kann in WF3 erreicht werden, indem eine Aktivität als "beim Schließen beibehalten" markiert wird.  Eine zweite, korrelierte Meldung schließt den Workflow ab.  Die Workflows werden beibehalten, aber nicht entladen.

### <a name="test-results"></a>Testergebnisse
 ![Säulendiagramm mit Durchsatz Persistenz](./media/performance/throughput-persistence-graph.gif)

 Wenn der Transport zwischen Client und mittlerer Ebene über HTTP erfolgt, steigt die Persistenz in WF4 um das 2,6-Fache.  Beim TCP-Transport wird dieser Faktor um das 3-Fache erhöht.  In allen Fällen beträgt die CPU-Auslastung auf der mittleren Ebene mindestens 98 %.  Der Grund für den höheren WF4-Durchsatz ist die schnellere Workflowlaufzeit.  Die Größe der serialisierten Instanz ist in beiden Fällen gering und in dieser Situation nicht entscheidend.

 Die Workflows in WF3 und WF4 verwenden in diesem Test eine Aktivität, um den Zeitpunkt der Persistenz explizit anzugeben.  Dies hat den Vorteil, dass der Workflow ohne Entladen beibehalten wird.  In WF3 ist Persistenz auch mithilfe der <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A>-Funktion möglich. Dabei wird allerdings die Workflowinstanz über den Arbeitsspeicher entladen.  Wenn ein Entwickler, der WF3 verwendet, Persistenz eines Workflows an bestimmten Punkten sicherstellen möchte, muss er entweder die Workflowdefinition ändern oder die Kosten für das Entladen und erneute Laden der Workflowinstanz zahlen.  Eine neue Funktion in WF4 ermöglicht Persistenz ohne Entladung: <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToPersist%2A>.  Diese Funktion erlaubt das Beibehalten der Workflowinstanz im Leerlauf. Diese bleibt jedoch im Arbeitsspeicher, bis der <xref:System.ServiceModel.Activities.Description.WorkflowIdleBehavior.TimeToUnload%2A>-Schwellenwert übertroffen oder die Ausführung fortgesetzt wird.

 Beachten Sie, dass der WF4-SQL-Persistenzanbieter weitere Aufgaben in der Datenbankebene ausführt.  Die SQL-Datenbank kann zu einem Engpass führen. Daher ist die Überwachung der CPU und Datenträgerverwendung in diesem Fall von Bedeutung.  Nehmen Sie die folgenden Leistungsindikatoren aus der SQL-Datenbank bei den Leistungstests von Workflowanwendungen auf:

- PhysicalDisk \ \\ Lese Zeit (%)

- PhysicalDisk \datenträger- \\ Zeit

- PhysicalDisk \\ % Schreibzeit (%)

- PhysicalDisk \\ % Durchschnittl. Warteschlangen Länge des Datenträgers

- Physikalischer Datenträger \ Durchschnittl. Warteschlangen Länge des Datenträgers

- Physischer Datenträger\Durchschnittl. Warteschlangenlänge der Datenträger-Schreibvorgänge

- Physischer Datenträger\Aktuelle Warteschlangenlänge

- Prozessor Informationen \\ % Prozessorzeit

- SQLServer:Latches\Durchschnittliche Latchwartezeit (ms)

- SQLServer:Latches\Latchwartezeiten/s

### <a name="tracking"></a>Nachverfolgung
 Die Workflownachverfolgung kann verwendet werden, um den Status eines Workflows nachzuverfolgen.  Die Informationen, die in den Nachverfolgungsereignissen enthalten sind, werden von einem Nachverfolgungsprofil bestimmt.  Mit der Komplexität des Nachverfolgungsprofils steigt der Aufwand für die Nachverfolgung.

 WF3 wurde mit einem auf SQL-basierenden Nachverfolgungsdienst geliefert.  Dieser Dienst funktionierte im Batchmodus und in Nicht-Batch-Modi.  Im Nicht-Batch-Modus werden Nachverfolgungsereignisse direkt in die Datenbank geschrieben.  Im Batchmodus werden Nachverfolgungsereignisse im selben Batch wie der Workflowinstanzzustand gesammelt.  Der Batchmodus weist für den größten Bereich von Workflowentwürfen die beste Leistung auf.  Die Batchverarbeitung kann jedoch negative Auswirkungen auf die Leistung haben, wenn der Workflow viele Aktivitäten ohne Persistenz ausführt und diese Aktivitäten nachverfolgt werden.  Dies trat am häufigsten in Schleifen auf. Dieses Szenario wird am besten vermieden, indem große Schleifen entworfen werden, die einen Persistenzpunkt enthalten.  Das Einfügen eines Persistenzpunkts in eine Schleife kann negative Auswirkungen auf die Leistung haben. Daher müssen sich die jeweiligen Kosten gegeneinander aufwiegen.

 WF4 wird nicht mit einem SQL-Nachverfolgungsdienst bereitgestellt.  Das Aufzeichnen von Überwachungsinformationen in einer SQL-Datenbank kann besser von einem Anwendungsserver verarbeitet werden, anstatt in den .NET Framework integriert zu werden. Daher wird die SQL-Nachverfolgung jetzt von AppFabric abgewickelt.  Der Standardnachverfolgungsanbieter in WF4 basiert auf der Ereignisablaufverfolgung für Windows (ETW).

 ETW ist ein in Windows integriertes Ereignissystem mit niedriger Latenzzeit auf Kernelebene.  Es verwendet ein Anbieter-/Consumermodell, das ermöglicht, dass die Strafe für die Ereignisablaufverfolgung nur übernommen wird, wenn tatsächlich ein Consumer vorhanden ist.  Zusätzlich zu Kernel-Ereignissen, wie z. B. Prozessor, Datenträger, Arbeitsspeicher und Netzwerkverwendung, nutzen auch viele Anwendungen ETW.  ETW-Ereignisse sind insofern leistungsstärker als Leistungsindikatoren, da Ereignisse an die Anwendung angepasst werden können.  Ein Ereignis kann Text enthalten, wie z. B. eine Workflow-ID oder eine Informationsmeldung.  Zudem werden Ereignisse mit Bitmasken kategorisiert, da die Verarbeitung einer bestimmten Teilmenge von Ereignissen geringere Auswirkungen auf die Leistung als das Erfassen sämtlicher Ereignisse hat.

 Vorteile des Ansatzes der Verwendung von ETW zur Nachverfolgung anstelle von SQL:

- Eine Auflistung von Nachverfolgungsereignissen kann in einem anderen Prozess abgetrennt werden.  Dies ermöglicht höhere Flexibilität beim Aufzeichnen der Ereignisse.

- Etw-nach Verfolgungs Ereignisse können problemlos mit den WCF ETW-Ereignissen oder anderen etw-Anbietern kombiniert werden, wie z. b. ein SQL Server oder ein Kernel Anbieter

- Workflowautoren müssen keinen Workflow ändern, damit er besser mit einer bestimmten Nachverfolgungsimplementierung funktioniert, wie z. B. dem Batchmodus des WF3-SQL-Überwachungsdiensts.

- Ein Administrator kann die Nachverfolgung aktivieren oder deaktivieren, ohne den Hostprozess wiederzuverwenden.

 Die Leistungsvorteile der ETW-Nachverfolgung haben auch einen Nachteil.  ETW-Ereignisse können unter intensivem Ressourcendruck auf das System verloren gehen.  Die Verarbeitung von Ereignissen soll die normale Programmausführung nicht blockieren. Daher wird nicht garantiert, dass alle ETW-Ereignisse an ihre Abonnenten übertragen werden.  Daher eignet sich die ETW-Nachverfolgung hervorragend zum Systemmonitoring, ist aber nicht für das Auditing geeignet.

 WF4 verfügt über keinen SQL-Nachverfolgungsanbieter, AppFabric jedoch schon.  Der SQL-Nachverfolgungsansatz von AppFabric ist, ETW-Ereignisse mit einem Windows-Dienst zu abonnieren, der die Ereignisse stapelweise verarbeitet und sie in eine SQL-Tabelle schreibt, die für schnelle Einfügungen entworfen wurde.  Ein separater Auftrag entnimmt die Daten aus dieser Tabelle und ordnet sie in Berichtstabellen neu an, die auf dem AppFabric-Dashboard angezeigt werden können.  Dies bedeutet, dass ein Batch von Nachverfolgungsereignissen unabhängig vom Workflow behandelt wird, von dem er stammt, und daher vor dem Aufzeichnen nicht auf einen Persistenzpunkt warten muss.

 ETW-Ereignisse können mit Tools, wie z. B. logman oder xperf, aufgezeichnet werden.  Die kompakte ETL-Datei kann mit einem Tool wie xperfview angezeigt oder mit tracerpt in ein besser lesbares Format, wie z. B. XML, konvertiert werden.  In WF3 ist die einzige Option zum Abrufen von Nachverfolgungsereignissen ohne SQL-Datenbank das Erstellen eines benutzerdefinierten Überwachungsdiensts. Weitere Informationen zu etw finden Sie unter [WCF-Dienste und Ereignis Ablauf Verfolgung für Windows](../wcf/samples/wcf-services-and-event-tracing-for-windows.md) und [Ereignis Ablauf Verfolgung-Windows-Anwendungen](/windows/desktop/etw/event-tracing-portal).

 Die Aktivierung der Workflownachverfolgung wirkt sich unterschiedlich auf die Leistung aus.  Der folgende Vergleichstest verwendet das logman-Tool, um die ETW-Nachverfolgungsereignisse zu verarbeiten und sie in einer ETL-Datei aufzuzeichnen.  Die Kosten für die SQL-Nachverfolgung in AppFabric liegen außerhalb des Rahmens dieses Artikels.  Das grundlegende Nachverfolgungsprofil, das auch in AppFabric verwendet wurde, wird in diesem Vergleichstest angezeigt.  Ebenfalls enthalten sind die Kosten für die Nachverfolgung von Systemüberwachungsereignissen.  Diese Ereignisse sind für das Beheben von Problemen und Bestimmen des durchschnittlichen Durchsatzes des Systems hilfreich.

### <a name="environment-setup"></a>Einrichten der Umgebung
 ![Umgebungs Einrichtung für Workflow Leistungstest](./media/performance/performance-test-environment.gif)

### <a name="test-results"></a>Testergebnisse

 ![Säulendiagramm mit den Kosten für die Workflow Nachverfolgung](./media/performance/workflow-tracking-costs.gif)

 Die Systemüberwachung wirkt sich in etwa zu 3 % auf den Durchsatz aus.  Die Kosten des grundlegenden Profils liegen bei etwa 8 %.

## <a name="interop"></a>Interop
 WF4 ist eine fast vollständig neue Version von [!INCLUDE[wf1](../../../includes/wf1-md.md)]. Daher sind WF3-Workflows und Aktivitäten nicht direkt mit WF4 kompatibel.  Viele Kunden, die Windows Workflow Foundation früh übernommen haben, verfügen über interne Workflow Definitionen oder Workflow Definitionen von Drittanbietern und benutzerdefinierte Aktivitäten für WF3.  Eine Möglichkeit, den Übergang zu WF4 zu vereinfachen, ist die Verwendung der Interop-Aktivität, mit der WF3-Aktivitäten in WF4-Workflows ausgeführt werden können.  Es wird empfohlen, die <xref:System.Activities.Statements.Interop>-Aktivität nur bei Bedarf zu verwenden. Weitere Informationen zum Migrieren zu WF4 finden Sie in der [WF4-Migrations Anleitung](migration-guidance.md).

### <a name="environment-setup"></a>Einrichten der Umgebung
 ![Umgebungs Einrichtung für Workflow Leistungstest](./media/performance/performance-test-environment.gif)

### <a name="test-results"></a>Testergebnisse

Die folgende Tabelle zeigt die Ergebnisse der Ausführung eines Workflows, der fünf Aktivitäten in einer Sequenz in verschiedenen Konfigurationen enthält.

|Test|Durchsatz (Workflows/Sek)|
|----------|-----------------------------------|
|WF3-Sequenz in WF3-Laufzeit|1,576|
|WF3-Sequenz in WF4-Laufzeit mit Interop|2,745|
|WF4-Sequenz|153,582|

 Bei der Verwendung von Interop ist eine enorme Leistungszunahme im Vergleich zur alleinigen Verwendung von WF3 zu verzeichnen.  Beim Vergleich mit WF4-Aktivitäten ist die Zunahme jedoch vernachlässigbar.

## <a name="summary"></a>Zusammenfassung
 Hohe Investitionen in die Leistung von WF4 haben sich in vielen entscheidenden Bereichen ausgezahlt.  Die Leistung einzelner Workflowkomponenten ist in einigen Fällen aufgrund einer schlankeren [!INCLUDE[wf1](../../../includes/wf1-md.md)]-Laufzeit in WF4 Hunderte Male besser als in WF3.  Die Latenzzeiten sind ebenfalls bedeutend besser.  Dies bedeutet, dass die Leistungseinbußen bei der Verwendung [!INCLUDE[wf1](../../../includes/wf1-md.md)] von im Gegensatz zum Hand Codieren der WCF-Orchestrierungs Dienste sehr klein sind, wenn Sie die zusätzlichen Vorteile von verwenden [!INCLUDE[wf1](../../../includes/wf1-md.md)] .  Die Persistenzleistung wurde um den Faktor 2,5 bis 3,0 gesteigert.  Die Systemüberwachung mittels der Workflownachverfolgung erfordert nun äußerst wenig Aufwand.  Ein umfassender Satz Migrationshandbücher ist für Benutzer verfügbar, die einen Wechsel von WF3 zu WF4 erwägen.  All diese Vorteile machen WF4 zu einer attraktiven Option für das Erstellen komplexer Anwendungen.
