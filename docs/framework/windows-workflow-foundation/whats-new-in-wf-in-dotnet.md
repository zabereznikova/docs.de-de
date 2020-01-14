---
title: Neues in Windows Workflow Foundation in .NET 4.5
ms.date: 03/30/2017
ms.assetid: 195c43a8-e0a8-43d9-aead-d65a9e6751ec
ms.openlocfilehash: b14f18dce64bc5738f3d3c6af11d6d6224764486
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937892"
---
# <a name="whats-new-in-windows-workflow-foundation-in-net-45"></a>Neues in Windows Workflow Foundation in .NET 4.5

Windows Workflow Foundation (WF) in .NET Framework 4,5 führt viele neue Features ein, z. b. neue Aktivitäten, Designer Funktionen und Workflow Entwicklungsmodelle. Viele, aber nicht alle neuen Workflow Features, die in .NET Framework 4,5 eingeführt wurden, werden im neu gehosteten Workflow-Designer unterstützt. Weitere Informationen zu den neuen Funktionen, die unterstützt werden, finden Sie [unter Unterstützung für neue Workflow Foundation 4,5-Features in der neu gehosteten Workflow-Designer](wf-features-in-the-rehosted-workflow-designer.md). Weitere Informationen zum Migrieren von .NET 3,0-und .NET 3,5-Workflow Anwendungen, um die neueste Version zu verwenden, finden Sie in der [Migrations Anleitung](migration-guidance.md). Dieses Thema enthält eine Übersicht über die neuen Workflow Features, die in .NET Framework 4,5 eingeführt wurden.

> [!WARNING]
> Die neuen Windows Workflow Foundation Features, die in .NET Framework 4,5 eingeführt wurden, sind für Projekte, die auf frühere Versionen des Frameworks ausgerichtet sind, nicht verfügbar. Wenn ein Projekt, das .NET Framework 4,5, auf eine frühere Version des Frameworks ausgerichtet ist, können mehrere Probleme auftreten.
>
> - C#Ausdrücke werden im Designer ersetzt, wobei der Nachrichten **Wert in XAML festgelegt wurde**.
> - Viele Erstellungsfehler einschließlich des folgenden Fehlers treten auf.
>
> **Das Dateiformat ist mit dem aktuellen Ziel Ziel Framework nicht kompatibel. Speichern Sie die Datei explizit, um das Dateiformat zu konvertieren. Diese Fehlermeldung wird entfernt, nachdem Sie die Datei gespeichert und den Designer erneut geöffnet haben.**

## <a name="BKMK_Versioning"></a>Workflow Versionsverwaltung

In .NET Framework 4,5 wurden mehrere neue Versions Verwaltungsfunktionen eingeführt, die auf der neuen <xref:System.Activities.WorkflowIdentity> Klasse basieren. <xref:System.Activities.WorkflowIdentity> bietet Anwendern von Workflowanwendungen einen Mechanismus, um ihrer Definition eine persistente Workflowinstanz zuzuordnen.

- Entwickler, die das <xref:System.Activities.WorkflowApplication>-Hosting verwenden, können mit <xref:System.Activities.WorkflowIdentity> das parallele Hosten mehrerer Versionen eines Workflows aktivieren. Persistente Workflowinstanzen können mit der neuen <xref:System.Activities.WorkflowApplicationInstance>-Klasse geladen werden, und anschließend kann <xref:System.Activities.WorkflowApplicationInstance.DefinitionIdentity%2A> vom Host verwendet werden, um beim Instanziieren von <xref:System.Activities.WorkflowApplication> die richtige Version der Workflowdefinition bereitzustellen. Weitere Informationen finden Sie unter [Verwenden von workflowidentity und Versions](using-workflowidentity-and-versioning.md) Verwaltung und Gewusst [wie: Hosten mehrerer Versionen eines Workflows nebeneinander](how-to-host-multiple-versions-of-a-workflow-side-by-side.md).

- <xref:System.ServiceModel.WorkflowServiceHost> ist jetzt ein versionsübergreifender Host. Wenn eine neue Version eines Workflowdiensts bereitgestellt wird, werden neue Instanzen mithilfe des neuen Diensts erstellt, während vorhandene Instanzen mit der vorherigen Version abgeschlossen werden. Weitere Informationen finden Sie unter parallele [Versionsverwaltung in Workflow Service Host](../wcf/feature-details/side-by-side-versioning-in-workflowservicehost.md).

- Dynamische Updates werden eingeführt, die einen Mechanismus zum Aktualisieren der Definition einer persistenten Workflowinstanz bereitstellen. Weitere Informationen finden Sie unter [dynamisches Update](dynamic-update.md) und Gewusst [wie: Aktualisieren der Definition einer laufenden Workflow Instanz](how-to-update-the-definition-of-a-running-workflow-instance.md).

- Ein sqlworkflowinstancestoreschemaupgrade. SQL-Datenbankskript wird zur Aktualisierung von Persistenzdatenbanken bereitgestellt, die mit den .NET Framework 4-Daten Bank Skripts erstellt Dieses Skript aktualisiert .NET Framework 4-Persistenzdatenbanken zur Unterstützung der neuen Versions Verwaltungsfunktionen in .NET Framework 4,5. Den persistenten Workflowinstanzen in der Datenbank werden Standardversionswerte zugeordnet, und sie können an einer parallelen Ausführung und an dynamischen Updates beteiligt sein. Weitere Informationen finden [Sie unter Aktualisieren von .NET Framework 4-Persistenzdatenbanken zur Unterstützung der Workflow Versions](using-workflowidentity-and-versioning.md#UpdatingWF4PersistenceDatabases)Verwaltung.

## <a name="BKMK_NewActivities"></a>Aktivitäts

Die integrierte Aktivitätsbibliothek enthält neue Aktivitäten und neue Funktionen für vorhandene Aktivitäten.

### <a name="BKMK_NoPersistScope"></a>Nopersist-Bereich

<xref:System.Activities.Statements.NoPersistScope> ist eine neue Containeraktivität, die verhindert, dass ein Workflow persistent gespeichert wird, wenn die untergeordneten Aktivitäten von NoPersistScopes ausgeführt werden. Dies ist in Szenarien hilfreich, in denen die persistente Speicherung des Workflows nicht angebracht ist, beispielsweise, wenn der Workflow computerspezifische Ressourcen wie Dateihandles verwendet, oder im Verlauf von Datenbanktransaktionen. Um zu vermeiden, dass die Persistenz während der Ausführung einer Aktivität auftritt, war früher eine benutzerdefinierte <xref:System.Activities.NativeActivity> erforderlich, die einen <xref:System.Activities.NoPersistHandle> verwendete.

### <a name="BKMK_NewFlowchartCapabilities"></a>Neue Flussdiagramm Funktionen

Flussdiagramme werden für .NET Framework 4,5 aktualisiert und haben die folgenden neuen Funktionen:

- Die `DisplayName`-Eigenschaft einer <xref:System.Activities.Statements.FlowSwitch%601>-Aktivität oder <xref:System.Activities.Statements.FlowDecision>-Aktivität ist bearbeitbar. Auf diese Weise kann der Aktivitäts-Designer mehr Informationen über den Zweck der Aktivität anzeigen.

- Flussdiagramme weisen eine neue Eigenschaft auf, die <xref:System.Activities.Statements.Flowchart.ValidateUnconnectedNodes%2A> genannt wird. Der Standardwert für diese Eigenschaft ist `False`. Wenn diese Eigenschaft auf `True` festgelegt ist, führen nicht verbundene Flussdiagrammknoten zu Validierungsfehlern.

## <a name="support-for-partial-trust"></a>Unterstützung für teilweise Vertrauenswürdigkeit

Workflows in .NET Framework 4 erfordern eine voll vertrauenswürdige Anwendungsdomäne. In .NET Framework 4,5 können Workflows in einer teilweise vertrauenswürdigen Umgebung ausgeführt werden. In einer teilweise vertrauenswürdigen Umgebung können Komponenten von Drittanbietern eingesetzt werden, ohne ihnen vollen Zugriff auf die Ressourcen des Hosts zu gewähren. Mögliche Bedenken zum Ausführen von Workflows unter teilweiser Vertrauenswürdigkeit:

1. Das Verwenden älterer, in der <xref:System.Activities.Statements.Interop>-Aktivität enthaltener Komponenten (einschließlich Regeln) wird unter teilweiser Vertrauenswürdigkeit nicht unterstützt.

2. Das Ausführen von Workflows unter teilweiser Vertrauenswürdigkeit in <xref:System.ServiceModel.WorkflowServiceHost> wird nicht unterstützt.

3. Persistente Ausnahmen in einem teilweise vertrauenswürdigen Szenario stellen ein Sicherheitsrisiko dar. Um die Persistenz von Ausnahmen zu deaktivieren, muss dem Projekt eine Erweiterung des Typs <xref:System.Activities.ExceptionPersistenceExtension> hinzugefügt werden. Im folgenden Codebeispiel wird die Implementierung dieses Typs veranschaulicht.

    ```csharp
    public class ExceptionPersistenceExtension
    {
        public ExceptionPersistenceExtension()
        {
            this.PersistExceptions = false;
        }
        public bool PersistExceptions { get; set; }
    }
    ```

     Wenn Ausnahmen nicht serialisiert werden müssen, stellen Sie sicher, dass Ausnahmen in <xref:System.Activities.Statements.NoPersistScope> verwendet werden.

4. Aktivitätsautoren sollten <xref:System.Activities.Activity.CacheMetadata%2A> überschreiben, damit während der Workflowlaufzeit nicht automatisch eine Reflektion für den Typ ausgeführt wird. Argumente und untergeordnete Aktivitäten dürfen nicht NULL sein, und <xref:System.Activities.ActivityMetadata.Bind%2A> muss explizit aufgerufen werden. Weitere Informationen zum Überschreiben von <xref:System.Activities.Activity.CacheMetadata%2A>finden Sie unter verfügbar machen von [Daten mit CacheMetadata](exposing-data-with-cachemetadata.md). Außerdem müssen Instanzen von Argumenten, die von einem Typ sind, der `internal` oder **Privat** ist, explizit in <xref:System.Activities.Activity.CacheMetadata%2A> erstellt werden, um zu vermeiden, dass Sie durch Reflektion erstellt werden.

5. Die Typen verwenden nicht <xref:System.Runtime.Serialization.ISerializable> oder <xref:System.SerializableAttribute> für die Serialisierung. Die zu serialisierenden Typen müssen <xref:System.Runtime.Serialization.DataContractSerializer> unterstützen.

6. Ausdrücke, die <xref:System.Activities.Expressions.LambdaValue%601> verwenden, setzen <xref:System.Security.Permissions.ReflectionPermissionAttribute.RestrictedMemberAccess%2A> voraus und funktionieren deshalb nicht unter teilweiser Vertrauenswürdigkeit. Bei Workflows, die <xref:System.Activities.Expressions.LambdaValue%601> verwenden, sollten diese Ausdrücke durch Aktivitäten ersetzt werden, die von <xref:System.Activities.CodeActivity%601> abgeleitet sind. .

7. Ausdrücke können nicht mit <xref:System.Activities.XamlIntegration.TextExpressionCompiler> oder dem von Visual Basic gehosteten Compiler für teilweise Vertrauenswürdigkeit kompiliert werden, zuvor kompilierte Ausdrücke können jedoch ausgeführt werden.

8. Eine einzelne Assembly, die [Transparenz der Ebene 2](https://aka.ms/Level2Transparency) verwendet, kann in .NET Framework 4, [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] mit vollständiger Vertrauenswürdigkeit und [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] bei teilweiser Vertrauenswürdigkeit nicht verwendet werden.

## <a name="BKMK_NewDesignerCapabilites"></a>Neue Designer-Funktionen

### <a name="BKMK_DesignerSearch"></a>Designer Suche

Um größere Workflows überschaubarer zu halten, können sie jetzt nach Schlüsselwort durchsucht werden. Diese Funktion ist nur in Visual Studio verfügbar. Diese Funktion ist in einem neu gehosteten Designer nicht verfügbar. Es gibt zwei Arten von Suchen:

- Schnellsuche, initiiert mit **STRG + F** oder **Bearbeiten**, **Suchen und ersetzen**, **Schnellsuche**.

- In Dateien suchen, initiiert mit **STRG + UMSCHALT + F** oder **Bearbeiten**, **Suchen und ersetzen**, **in Dateien suchen**.

Beachten Sie, dass der Ersetzungsvorgang nicht unterstützt wird.

#### <a name="BKMK_QuickFind"></a>Schnellsuche

Schlüsselwörter, die in den Workflows gesucht werden, entsprechen den folgenden Designerelementen:

- Eigenschaften von <xref:System.Activities.Activity>-Objekten, <xref:System.Activities.Statements.FlowNode>-Objekten, <xref:System.Activities.Statements.State>-Objekten, <xref:System.Activities.Statements.Transition>-Objekten und anderen benutzerdefinierten Flusssteuerungselementen.

- Variablen

- Argumente

- Ausdrücke

Die Schnellsuche wird in der <xref:System.Activities.Presentation.Model.ModelItem>-Struktur des Designers ausgeführt. Die Schnellsuche findet keine Namespaces, die in die Workflowdefinition importiert wurden.

#### <a name="BKMK_FindInFiles"></a>In Dateien suchen

Schlüsselwörter, die in den Workflows gesucht werden, stimmen mit dem tatsächlichen Inhalt der Workflowdateien überein. Die Suchergebnisse werden im Visual Studio-Ansichtsbereich Suchergebnisse angezeigt. Durch Doppelklicken auf das Ergebniselement navigieren Sie im Workflow-Designer zur Aktivität, in der die Übereinstimmung enthalten ist.

### <a name="BKMK_VariableDeleteContextMenu"></a>Kontextmenü Element im Variablen-und Argument-Designer löschen

In .NET Framework 4 konnten Variablen und Argumente nur im Designer mit der Tastatur gelöscht werden. Ab .NET Framework 4,5 können Variablen und Argumente über das Kontextmenü gelöscht werden.

Das folgende Bildschirmfoto zeigt das Kontextmenü des Variablen- und Argument-Designers.

![Kontextmenü des Variablen- und Argument-Designers](./media/whats-new-in-wf-in-dotnet/designer-context-menu.png)

### <a name="BKMK_AutoSurround"></a>Automatisches umschließen mit Sequenz

Da ein Workflow oder bestimmte Containeraktivitäten (z. B. <xref:System.Activities.Statements.NoPersistScope>) nur eine einzelne Textkörperaktivität enthalten können, musste der Entwickler zum Hinzufügen einer zweiten Aktivität die erste Aktivität löschen, eine <xref:System.Activities.Statements.Sequence>-Aktivität hinzufügen und der Sequenzaktivität dann beide Aktivitäten hinzufügen. Ab .NET Framework 4,5 wird automatisch eine `Sequence` Aktivität erstellt, um beide Aktivitäten zu umschließen, wenn der Designer Oberfläche eine zweite Aktivität hinzugefügt wird.

Die folgende Bildschirmaufnahme zeigt eine `WriteLine`-Aktivität in `Body` von `NoPersistScope`.

![Eine "Write teline"-Aktivität im Text einer nopersistscope-Aktivität.](./media/whats-new-in-wf-in-dotnet/auto-surround-write-line-activity.png)

Die folgende Bildschirmaufnahme zeigt die automatisch erstellte `Sequence`-Aktivität in `Body`, wenn eine zweite `WriteLine`-Komponente unterhalb der ersten abgelegt wird.

![Eine automatisch erstellte Sequenz im Text eines nopersistscope.](./media/whats-new-in-wf-in-dotnet/auto-surround-sequence-activity.png)

### <a name="BKMK_PanMode"></a>Schwenk Modus

Um in einem umfangreichen Workflow einfacher im Designer zu navigieren, kann der Schwenkmodus aktiviert werden, der es dem Entwickler ermöglicht, den sichtbaren Teil des Workflows durch Klicken und Ziehen zu verschieben, anstatt die Bildlaufleisten zu verwenden. Die Schaltfläche zum Aktivieren des Schwenkmodus befindet sich in der rechten unteren Ecke des Designers.

Das folgende Bildschirmfoto zeigt die Schaltfläche zum Schwenken, die sich in der unteren rechten Ecke des Workflow-Designers befindet.

![Die Schaltfläche schwenken, die im Workflow-Designer hervorgehoben ist.](./media/whats-new-in-wf-in-dotnet/pan-button-workflow-designer.png)

Die mittlere Maustaste oder die LEERTASTE kann ebenfalls verwendet werden, um den Workflow-Designer zu schwenken.

### <a name="BKMK_MultiSelect"></a>Mehrfachauswahl

Mehrere Aktivitäten können gleichzeitig ausgewählt werden, indem Sie entweder ein Rechteck darum ziehen (wenn der Schwenkmodus nicht aktiviert ist), oder indem Sie die STRG-TASTE gedrückt halten und nacheinander auf die gewünschten Aktivitäten klicken.

Mehrere ausgewählte Aktivitäten können auch im Designer gezogen und abgelegt und über das Kontextmenü bearbeitet werden.

### <a name="BKMK_DocumentOutline"></a>Gliederungsansicht von Workflow Elementen

Um das Navigieren in hierarchischen Workflows zu erleichtern, werden die Komponenten eines Workflows in einer strukturähnlichen Gliederungsansicht angezeigt. Die Gliederungs Ansicht wird in der Ansicht **Dokument** Gliederung angezeigt. Um diese Ansicht zu öffnen, wählen Sie im oberen Menü **Ansicht**, **Weitere Fenster**, **Dokument**Gliederung aus, oder drücken Sie STRG W, U. Wenn Sie auf einen Knoten in der Gliederungsansicht klicken, wechseln Sie automatisch zur entsprechenden Aktivität im Workflow-Designer, und die Gliederungsansicht wird aktualisiert, um die im Designer ausgewählten Aktivitäten anzuzeigen.

Der folgende Screenshot des abgeschlossenen Workflows aus dem [Tutorial "Getting Started](getting-started-tutorial.md) " zeigt die Gliederungs Ansicht mit einem sequenziellen Workflow.

![Screenshot der Gliederungs Ansicht mit einem sequenziellen Workflow in Visual Studio.](./media/whats-new-in-wf-in-dotnet/outline-view-in-workflow-designer.jpg)

### <a name="BKMK_CSharpExpressions"></a>C# Ausdrücke

Vor .NET Framework 4,5 konnten alle Ausdrücke in Workflows nur in Visual Basic geschrieben werden. In .NET Framework 4,5 werden Visual Basic Ausdrücke nur für Projekte verwendet, die mit Visual Basic erstellt werden. Visual C#-Projekte verwenden jetzt die Programmiersprache C# für Ausdrücke. Ein voll funktionaler C#-Ausdrucks-Editor wird mit Funktionen wie IntelliSense und der Hervorhebung grammatikalischer Fehler bereitgestellt. Die in früheren Versionen erstellten C#-Workflowprojekte, die Visual Basic-Ausdrücke verwenden, sind weiterhin funktionsfähig.

C#-Ausdrücke werden zur Entwurfszeit validiert. Fehler in C#-Ausdrücken werden mit einer roten wellenförmigen Unterstreichung gekennzeichnet.

Weitere Informationen zu C# Ausdrücken finden [ C# ](csharp-expressions.md)Sie unter Ausdrücke.

### <a name="BKMK_Visibility"></a>Mehr Kontrolle über die Sichtbarkeit der shellleiste und der Header Elemente

In einem neu gehosteten Designer sind einige standardmäßigen Benutzeroberflächen-Steuerelemente für einen bestimmten Workflow möglicherweise bedeutungslos und deaktiviert. In .NET Framework 4 wird diese Anpassung nur von der shellleiste am unteren Rand des Designers unterstützt. In .NET Framework 4,5 kann die Sichtbarkeit von shellheadern am oberen Rand des Designers angepasst werden, indem <xref:System.Activities.Presentation.View.DesignerView.WorkflowShellHeaderItemsVisibility%2A> mit dem entsprechenden <xref:System.Activities.Presentation.View.ShellHeaderItemsVisibility> Wert festgelegt wird.

### <a name="BKMK_AutoConnect"></a>Automatisches Verbinden und automatisches Einfügen in Flussdiagramm-und Zustandsautomatworkflows

In .NET Framework 4 mussten Verbindungen zwischen Knoten in einem Flussdiagramm-Workflow manuell hinzugefügt werden. In .NET Framework 4,5 verfügen Flussdiagramm-und Zustands Automaten Knoten über automatische Verbindungspunkte, die sichtbar werden, wenn eine Aktivität aus der Toolbox auf die Designer Oberfläche gezogen wird. Durch Ablegen einer Aktivität auf einem dieser Punkte wird die Aktivität automatisch zusammen mit der erforderlichen Verbindung hinzugefügt.

Das folgende Bildschirmfoto zeigt die Anfügepunkte, die sichtbar werden, wenn eine Aktivität aus der Toolbox gezogen wird.

![Flussdiagramm-Startknoten mit automatischen Verbindungs Punkten](./media/whats-new-in-wf-in-dotnet/auto-connect-points-start-node.png)

Aktivitäten können auch auf Verbindungen zwischen Flussdiagrammknoten und -zuständen gezogen werden, um den Knoten automatisch zwischen zwei anderen Knoten einzufügen. Das folgende Bildschirmfoto zeigt die hervorgehobene Verbindungslinie, auf die Aktivitäten aus der Toolbox gezogen und abgelegt werden können.

![AutoEinfügen-Handle zum Ablegen von Aktivitäten](./media/whats-new-in-wf-in-dotnet/auto-insert-connecting-line.png)

### <a name="BKMK_Annotations"></a>Designer-Anmerkungen

Zur einfacheren Entwicklung größerer Workflows unterstützt der Designer jetzt das Hinzufügen von Anmerkungen, um den Entwurfsprozess nachzuverfolgen. Aktivitäten, Zustände, Flussdiagrammknoten, Variablen und Argumente können mit Anmerkungen versehen werden. Das folgende Bildschirmfoto zeigt das Kontextmenü, das verwendet wird, um dem Designer Anmerkungen hinzuzufügen.

![Screenshot, der ein Menü zum Hinzufügen von Anmerkungen anzeigt.](./media/whats-new-in-wf-in-dotnet/designer-annotations-context-menu.png)

### <a name="debugging-states"></a>Debugzustände

In .NET Framework 4 konnten nicht aktivitätenelemente debugbreakpunkte nicht unterstützen, da Sie keine Ausführungs Einheiten sind. Dieses Release stellt einen Mechanismus bereit, um <xref:System.Activities.Statements.State>-Objekten Haltepunkte hinzuzufügen. Wenn ein Haltepunkt für <xref:System.Activities.Statements.State> festgelegt wird, wird die Ausführung unterbrochen, wenn vor der Planung der Eintragsaktivitäten oder Trigger ein Zustandsübergang stattfindet.

### <a name="BKMK_ActivityDelegates"></a>Definieren und Verarbeiten von activitydelegatobjekten im Designer

Die Aktivitäten in .NET Framework 4 wurden <xref:System.Activities.ActivityDelegate> Objekten verwendet, um Ausführungs Punkte verfügbar zu machen, an denen andere Teile des Workflows mit der Ausführung eines Workflows interagieren konnten, aber die Verwendung dieser Ausführungs Punkte erforderte normalerweise eine ziemlich große Menge an Code. In diesem Release können Entwickler die Aktivitätsdelegaten mit dem Workflow-Designer definieren und nutzen. Weitere Informationen finden Sie unter Gewusst [wie: definieren und](/visualstudio/workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer)verarbeiten von Aktivitäts Delegaten im Workflow-Designer.

### <a name="BKMK_BuildTimeValidation"></a>Überprüfung der Build-Zeit

In .NET Framework 4 wurden Workflow Validierungs Fehler während der Erstellung eines Workflow Projekts nicht als Buildfehler gezählt. Das bedeutete, dass das Erstellen eines Workflowprojekts erfolgreich gewesen sein konnte, obwohl Workflowvalidierungsfehler auftraten. In .NET Framework 4,5 bewirken Workflow Validierungs Fehler, dass der Build fehlschlägt.

### <a name="BKMK_DesignTimeValidation"></a>Hintergrund Validierung zur Entwurfszeit

In .NET Framework 4 wurden Workflows als Vordergrund Prozess überprüft, der die Benutzeroberfläche bei komplexen oder zeitaufwändigen Validierungs Prozessen potenziell blockieren kann. Da die Workflowvalidierung nun in einem Hintergrundthread stattfindet, wird die Benutzeroberfläche nicht blockiert.

### <a name="BKMK_ViewState"></a>Ansichts Zustand an einem anderen Speicherort in XAML-Dateien

In .NET Framework 4 werden die Ansichts Zustandsinformationen für einen Workflow in der XAML-Datei an vielen verschiedenen Speicherorten gespeichert. Dies ist für Entwickler, die XAML direkt lesen oder Code zum Entfernen von Ansichtszustandsinformationen schreiben möchten, ungünstig. In .NET Framework 4,5 werden die Ansichts Zustandsinformationen in der XAML-Datei als separates Element in der XAML-Datei serialisiert. Entwickler können die Ansichts Zustandsinformationen einer Aktivität leicht finden und bearbeiten oder den Ansichts Zustand vollständig entfernen.

### <a name="BKMK_ExpressionExtensibility"></a>Ausdrucks Erweiterbarkeit

In .NET Framework 4,5 bieten wir Entwicklern die Möglichkeit, eigene Ausdrucks-und Ausdrucks Erstellungs Funktionen zu erstellen, die an den Workflow-Designer angeschlossen werden können.

### <a name="BKMK_BackwardCompatRehostedDesigner"></a>Aktivieren von Workflow 4,5-Funktionen im neu gehosteten Designer

Um die Abwärtskompatibilität aufrechtzuerhalten, sind einige neue Features, die in .NET Framework 4,5 enthalten sind, im neu gehosteten Designer standardmäßig nicht aktiviert. Dadurch wird sichergestellt, dass vorhandene Anwendungen, die den neu gehosteten Designer verwenden, nicht beeinträchtigt werden, indem ein Update auf die neueste Version ausgeführt wird. Um neue Funktionen im neu gehosteten Designer zu aktivieren, legen Sie entweder <xref:System.Activities.Presentation.DesignerConfigurationService.TargetFrameworkName%2A> auf „.NET Framework 4.5“ oder einzelne Member von <xref:System.Activities.Presentation.DesignerConfigurationService> fest, um einzelne Funktionen zu aktivieren.

## <a name="BKMK_NewWFModels"></a>Neue Workflow Entwicklungsmodelle

Zusätzlich zu den Entwicklungsmodellen für sequenzielle oder Flussdiagramm-Workflows umfasst dieses Release Zustandsautomatworkflows und Vertrag zuerst-Workflowdienste.

### <a name="BKMK_StateMachine"></a>Zustandsautomatworkflows

Zustandsautomatworkflows wurden als Teil der .NET Framework 4, Version 4.0.1, im [Microsoft .NET Framework 4 Platform Update 1](https://docs.microsoft.com/archive/blogs/endpoint/microsoft-net-framework-4-platform-update-1)eingeführt. Dieses Update umfasste verschiedene neue Klassen und Aktivitäten, die es den Entwicklern ermöglichten, Zustandsautomatworkflows zu erstellen. Diese Klassen und Aktivitäten wurden für .NET Framework 4,5 aktualisiert. Updates umfassen:

1. Festlegen von Haltepunkten für Zustände

2. Kopieren und Einfügen von Übergängen im Workflow-Designer

3. Designerunterstützung für das Erstellen von freigegebenen Triggerübergängen

4. Aktivitäten, die zum Erstellen von Zustandsautomatworkflows verwendet werden, darunter: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> und <xref:System.Activities.Statements.Transition>

Der folgende Screenshot zeigt den abgeschlossenen Zustandsautomatworkflow aus dem Schritt " [Getting Started Tutorial](getting-started-tutorial.md) " Gewusst [wie: Erstellen eines Zustands Automaten Workflows](how-to-create-a-state-machine-workflow.md).

![Die Abbildung zeigt den abgeschlossenen Zustandsautomatworkflow.](./media/whats-new-in-wf-in-dotnet/complete-state-machine-workflow.jpg)

Weitere Informationen zum Erstellen von Zustandsautomatworkflows finden Sie unter [Zustandsautomatworkflows](state-machine-workflows.md).

### <a name="BKMK_ContractFirst"></a>Vertrag zuerst-Workflow Entwicklung

Mit dem Contract-First-Workflow-Entwicklungs Tool können Entwickler zunächst einen Vertrag im Code entwerfen und dann mit wenigen Klicks in Visual Studio automatisch eine Aktivitäts Vorlage in der Toolbox generieren, die die einzelnen Vorgänge darstellt. Diese Aktivitäten werden dann verwendet, um einen Workflow zu erstellen, der die vom Vertrag definierten Vorgänge implementiert. Der Workflow-Designer überprüft den Workflowdienst, um sicherzustellen, dass diese Vorgänge implementiert wurden und dass die Signatur des Workflows mit der Vertragssignatur übereinstimmt. Der Entwickler kann einen Workflowdienst auch einer Auflistung implementierter Verträge zuordnen. Weitere Informationen zur Entwicklung von Vertrag zuerst-Workflow Diensten finden Sie unter Gewusst [wie: Erstellen eines Workflow Dienstanbieter, der einen vorhandenen Dienstvertrag](how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)verwendet.
