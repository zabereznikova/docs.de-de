---
title: Unterstützung für neue Workflow Foundation 4.5-Funktionen im neu gehosteten Workflow-Designer
ms.date: 03/30/2017
ms.assetid: 1a4a4038-d8e6-41dd-99ea-93bd76286772
ms.openlocfilehash: 2b893fede30606789c82a64a19fa368e3fd74c4d
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74142070"
---
# <a name="support-for-new-workflow-foundation-45-features-in-the-rehosted-workflow-designer"></a>Unterstützung für neue Workflow Foundation 4.5-Funktionen im neu gehosteten Workflow-Designer
Mit Windows Workflow Foundation (WF) in .NET Framework 4,5 wurden viele neue Features eingeführt, einschließlich verschiedener Erweiterungen der Workflow-Designer-Darstellung. In diesem Thema wird erörtert, welche dieser Funktionen im neu gehosteten Designer bzw. derzeit überhaupt nicht unterstützt werden.

> [!NOTE]
> Eine Liste aller in .NET Framework 4,5 eingeführten neuen Features der neuen Windows Workflow Foundation (WF), einschließlich derjenigen, die nicht im Zusammenhang mit dem Designer-neuhosting stehen, finden Sie unter [What es New in Windows Workflow Foundation in .NET 4,5](whats-new-in-wf-in-dotnet.md).

## <a name="activities"></a>Aktivitäten
 Die integrierte Aktivitätsbibliothek enthält neue Aktivitäten und neue Funktionen für vorhandene Aktivitäten. Alle diese neuen Aktivitäten werden im neu gehosteten Designer unterstützt. Weitere Informationen zu diesen neuen Aktivitäten finden Sie im Abschnitt " [Aktivitäten](whats-new-in-wf-in-dotnet.md#BKMK_NewActivities) " unter [Neues in Windows Workflow Foundation in .NET 4,5](whats-new-in-wf-in-dotnet.md).

## <a name="c-expressions"></a>C#-Ausdrücke
 Vor .NET Framework 4,5 konnten alle Ausdrücke in Workflows nur in Visual Basic geschrieben werden. In .NET Framework 4,5 werden Visual Basic Ausdrücke nur für Projekte verwendet, die mit Visual Basic erstellt werden. Visual C#-Projekte verwenden jetzt die Programmiersprache C# für Ausdrücke. Beim Erstellen von Workflows in Visual Studio 2012 wird ein voll C# funktionsfähiger Ausdrucks-Editor bereitgestellt, der Funktionen wie Grammatik Hervorhebung und IntelliSense bietet. Die in früheren Versionen erstellten C#-Workflowprojekte, die Visual Basic-Ausdrücke verwenden, sind weiterhin funktionsfähig.

> [!WARNING]
> C#-Ausdrücke werden im neu gehosteten Designer nicht unterstützt.

## <a name="new-designer-capabilities"></a>Neue Designer-Funktionen

### <a name="designer-search"></a>Designer-Suche
 Die in .NET Framework 4,5 eingeführten Features " [Schnellsuche](whats-new-in-wf-in-dotnet.md#BKMK_QuickFind) " und " [in Dateien](whats-new-in-wf-in-dotnet.md#BKMK_FindInFiles) suchen" werden im neu gehosteten Designer nicht unterstützt. Die `Toolbox`-Suche wird im neu gehosteten Designer unterstützt. Weitere Informationen zu diesen Features finden Sie unter [Designer Search](whats-new-in-wf-in-dotnet.md#BKMK_DesignerSearch).

> [!WARNING]
> Die [Schnellsuche](whats-new-in-wf-in-dotnet.md#BKMK_QuickFind) und die [Suche in Dateien](whats-new-in-wf-in-dotnet.md#BKMK_FindInFiles) werden im neu gehosteten Designer nicht unterstützt.

### <a name="delete-context-menu-item-in-variable-and-argument-designer"></a>Löschen von Kontextmenüelementen im Variablen- und Argument-Designer
 In .NET Framework 4 konnten Variablen und Argumente nur im Designer mit der Tastatur gelöscht werden. Ab .NET Framework 4,5 können Variablen und Argumente über das Kontextmenü gelöscht werden. Diese Funktion wird im neu gehosteten Designer unterstützt.

 Das folgende Bildschirmfoto zeigt das Kontextmenü des Variablen- und Argument-Designers.

 ![Kontextmenü des Variablen- und Argument-Designers](./media/wf-features-in-the-rehosted-workflow-designer/designer-context-menu.png)

### <a name="auto-surround-with-sequence"></a>Automatisches Umschließen mit Sequenz
 Da ein Workflow oder bestimmte Containeraktivitäten (z. B. <xref:System.Activities.Statements.NoPersistScope>) nur eine einzelne Textkörperaktivität enthalten können, musste der Entwickler zum Hinzufügen einer zweiten Aktivität die erste Aktivität löschen, eine <xref:System.Activities.Statements.Sequence>-Aktivität hinzufügen und der Sequenzaktivität dann beide Aktivitäten hinzufügen. Ab .NET Framework 4,5 wird automatisch eine `Sequence` Aktivität erstellt, um beide Aktivitäten zu umschließen, wenn der Designer Oberfläche eine zweite Aktivität hinzugefügt wird. Diese Funktion wird im neu gehosteten Designer unterstützt.

 Die folgende Bildschirmaufnahme zeigt eine `WriteLine`-Aktivität in `Body` von `NoPersistScope`.

 ![Eine "Write teline"-Aktivität im Text einer nopersistscope-Aktivität.](./media/wf-features-in-the-rehosted-workflow-designer/auto-surround-write-line-activity.png)

 Die folgende Bildschirmaufnahme zeigt die automatisch erstellte `Sequence`-Aktivität in `Body`, wenn eine zweite `WriteLine`-Komponente unterhalb der ersten abgelegt wird.

 ![Eine automatisch erstellte Sequenz im Text eines nopersistscope.](./media/wf-features-in-the-rehosted-workflow-designer/auto-surround-sequence-activity.png)

### <a name="pan-mode"></a>Schwenkmodus
 Um in einem umfangreichen Workflow einfacher im Designer zu navigieren, kann der Schwenkmodus aktiviert werden, der es dem Entwickler ermöglicht, den sichtbaren Teil des Workflows durch Klicken und Ziehen zu verschieben, anstatt die Bildlaufleisten zu verwenden. Die Schaltfläche zum Aktivieren des Schwenkmodus befindet sich in der rechten unteren Ecke des Designers. Diese Funktion wird im neu gehosteten Designer unterstützt.

 Das folgende Bildschirmfoto zeigt die Schaltfläche zum Schwenken, die sich in der unteren rechten Ecke des Workflow-Designers befindet.

 ![Die Schaltfläche schwenken, die im Workflow-Designer hervorgehoben ist.](./media/wf-features-in-the-rehosted-workflow-designer/pan-button-workflow-designer.png)

 Die mittlere Maustaste oder die LEERTASTE kann ebenfalls verwendet werden, um den Workflow-Designer zu schwenken.

### <a name="multi-select"></a>Mehrfachauswahl
 Mehrere Aktivitäten können gleichzeitig ausgewählt werden, indem Sie entweder ein Rechteck darum ziehen (wenn der Schwenkmodus nicht aktiviert ist), oder indem Sie die STRG-TASTE gedrückt halten und nacheinander auf die gewünschten Aktivitäten klicken. Diese Funktion wird im neu gehosteten Designer unterstützt.

 Mehrere ausgewählte Aktivitäten können auch im Designer gezogen und abgelegt und über das Kontextmenü bearbeitet werden.

### <a name="outline-view-of-workflow-items"></a>Gliederungsansicht der Workflowelemente
 Um das Navigieren in hierarchischen Workflows zu erleichtern, werden die Komponenten eines Workflows in einer strukturähnlichen Gliederungsansicht angezeigt. Die Gliederungs Ansicht wird in der Ansicht **Dokument** Gliederung angezeigt. Um diese Ansicht in Visual Studio zu öffnen, wählen Sie im oberen Menü **Ansicht**, **Weitere Fenster**, **Dokument**Gliederung aus, oder drücken Sie STRG W, U. Wenn Sie auf einen Knoten in der Gliederungsansicht klicken, wechseln Sie automatisch zur entsprechenden Aktivität im Workflow-Designer, und die Gliederungsansicht wird aktualisiert, um die im Designer ausgewählten Aktivitäten anzuzeigen. Diese Funktion wird im neu gehosteten Designer unterstützt.

 Der folgende Screenshot des abgeschlossenen Workflows aus dem [Tutorial "Getting Started](getting-started-tutorial.md) " zeigt die Gliederungs Ansicht mit einem sequenziellen Workflow.

 ![Screenshot der Gliederungs Ansicht mit einem sequenziellen Workflow in Visual Studio](./media/wf-features-in-the-rehosted-workflow-designer/outline-view-in-workflow-designer.jpg)

### <a name="more-control-of-visibility-of-shell-bar-and-header-items"></a>Bessere Kontrolle über die Sichtbarkeit der Shellleiste und Headerelemente
 In einem neu gehosteten Designer sind einige standardmäßigen Benutzeroberflächen-Steuerelemente für einen bestimmten Workflow möglicherweise bedeutungslos und deaktiviert. In .NET Framework 4 wird diese Anpassung nur von der shellleiste am unteren Rand des Designers unterstützt. In .NET Framework 4,5 kann die Sichtbarkeit von shellheadern am oberen Rand des Designers angepasst werden, indem <xref:System.Activities.Presentation.View.DesignerView.WorkflowShellHeaderItemsVisibility%2A> mit dem entsprechenden <xref:System.Activities.Presentation.View.ShellHeaderItemsVisibility> Wert festgelegt wird.

### <a name="auto-connect-and-auto-insert-in-flowchart-and-state-machine-workflows"></a>Automatisches Verbinden und Einfügen in Flussdiagramm- und Zustandsautomatworkflows
 In .NET Framework 4 mussten Verbindungen zwischen Knoten in einem Flussdiagramm-Workflow manuell hinzugefügt werden. In .NET Framework 4,5 verfügen Flussdiagramm-und Zustands Automaten Knoten über automatische Verbindungspunkte, die sichtbar werden, wenn eine Aktivität aus der Toolbox auf die Designer Oberfläche gezogen wird. Durch Ablegen einer Aktivität auf einem dieser Punkte wird die Aktivität automatisch zusammen mit der erforderlichen Verbindung hinzugefügt.

 Das folgende Bildschirmfoto zeigt die Anfügepunkte, die sichtbar werden, wenn eine Aktivität aus der Toolbox gezogen wird.

 ![Flussdiagramm-Startknoten mit automatischen Verbindungs Punkten](./media/wf-features-in-the-rehosted-workflow-designer/auto-connect-points-start-node.png)

 Aktivitäten können auch auf Verbindungen zwischen Flussdiagrammknoten und -zuständen gezogen werden, um den Knoten automatisch zwischen zwei anderen Knoten einzufügen. Das folgende Bildschirmfoto zeigt die hervorgehobene Verbindungslinie, auf die Aktivitäten aus der Toolbox gezogen und abgelegt werden können.

 ![AutoEinfügen-Handle zum Ablegen von Aktivitäten](./media/wf-features-in-the-rehosted-workflow-designer/auto-insert-connecting-line.png)

 Automatisches Verbinden und automatisches Einfügen werden im neu gehosteten Designer unterstützt.

### <a name="designer-annotations"></a>Designer-Anmerkungen
 Zur einfacheren Entwicklung größerer Workflows unterstützt der Designer jetzt das Hinzufügen von Anmerkungen, um den Entwurfsprozess nachzuverfolgen. Aktivitäten, Zustände, Flussdiagrammknoten, Variablen und Argumente können mit Anmerkungen versehen werden. Das folgende Bildschirmfoto zeigt das Kontextmenü, das verwendet wird, um dem Designer Anmerkungen hinzuzufügen.

 ![Screenshot, der das Menü zum Hinzufügen von Notationen anzeigt.](./media/wf-features-in-the-rehosted-workflow-designer/designer-annotations-context-menu.png)

 Designer-Anmerkungen werden im neu gehosteten Designer unterstützt.

### <a name="define-and-consume-activitydelegate-objects-in-the-designer"></a>Definieren und Nutzen von ActivityDelegate-Objekten im Designer
 Die Aktivitäten in .NET Framework 4 wurden <xref:System.Activities.ActivityDelegate> Objekten verwendet, um Ausführungs Punkte verfügbar zu machen, an denen andere Teile des Workflows mit der Ausführung eines Workflows interagieren konnten, aber die Verwendung dieser Ausführungs Punkte erforderte normalerweise eine ziemlich große Menge an Code. In diesem Release können Entwickler die Aktivitätsdelegaten mit dem Workflow-Designer definieren und nutzen. Weitere Informationen finden Sie unter [Vorgehensweise: Definieren und Verarbeiten von Aktivitäts Delegaten im Workflow-Designer](/visualstudio/workflow-designer/how-to-define-and-consume-activity-delegates-in-the-workflow-designer).

 Aktivitätsdelegaten werden im neu gehosteten Designer unterstützt.

### <a name="build-time-validation"></a>Validierung zur Buildzeit
 In .NET Framework 4 wurden Workflow Validierungs Fehler während der Erstellung eines Workflow Projekts nicht als Buildfehler gezählt. Das bedeutete, dass das Erstellen eines Workflowprojekts erfolgreich gewesen sein konnte, obwohl Workflowvalidierungsfehler auftraten. In .NET Framework 4,5 bewirken Workflow Validierungs Fehler, dass der Build fehlschlägt.

> [!WARNING]
> Die Validierung zur Buildzeit wird im neu gehosteten Designer nicht unterstützt.  
  
### <a name="design-time-background-validation"></a>Hintergrundvalidierung zur Entwurfszeit  
 In .NET Framework 4 wurden Workflows als Vordergrund Prozess überprüft, der die Benutzeroberfläche bei komplexen oder zeitaufwändigen Validierungs Prozessen potenziell blockieren kann. Da die Workflowvalidierung nun in einem Hintergrundthread stattfindet, wird die Benutzeroberfläche nicht blockiert.  
  
 Die Hintergrundvalidierung zur Entwurfszeit wird im neu gehosteten Designer unterstützt.  
  
### <a name="view-state-located-in-a-separate-location-in-xaml-files"></a>Der Ansichtszustand wird an einem separaten Ort in XAML-Dateien gespeichert  
 In .NET Framework 4 werden die Ansichts Zustandsinformationen für einen Workflow in der XAML-Datei an vielen verschiedenen Speicherorten gespeichert. Dies ist für Entwickler, die XAML direkt lesen oder Code zum Entfernen von Ansichtszustandsinformationen schreiben möchten, ungünstig. In .NET Framework 4,5 werden die Ansichts Zustandsinformationen in der XAML-Datei als separates Element in der XAML-Datei serialisiert.  Entwickler können die Ansichts Zustandsinformationen einer Aktivität leicht finden und bearbeiten oder den Ansichts Zustand vollständig entfernen.  
  
 Diese Funktion wird im neu gehosteten Workflow-Designer unterstützt.  
  
### <a name="opt-in-for-workflow-45-features-in-rehosted-designer"></a>Opt-In für Workflow 4.5-Funktionen im neu gehosteten Designer  
 Um die Abwärtskompatibilität aufrechtzuerhalten, sind einige neue Features, die in .NET Framework 4,5 enthalten sind, im neu gehosteten Designer standardmäßig nicht aktiviert. Dadurch wird sichergestellt, dass vorhandene Anwendungen, die den neu gehosteten Designer verwenden, nicht beeinträchtigt werden, indem ein Update auf die neueste Version ausgeführt wird. Um neue Funktionen im neu gehosteten Designer zu aktivieren, legen Sie entweder <xref:System.Activities.Presentation.DesignerConfigurationService.TargetFrameworkName%2A> auf „.NET Framework 4.5“ oder einzelne Member von <xref:System.Activities.Presentation.DesignerConfigurationService> so fest, dass sie einzelne Funktionen aktivieren.  
  
## <a name="new-workflow-development-models"></a>Neue Modelle für die Workflowentwicklung  
 Zusätzlich zu den Entwicklungsmodellen für sequenzielle oder Flussdiagramm-Workflows umfasst dieses Release Zustandsautomatworkflows und Vertrag zuerst-Workflowdienste.  
  
### <a name="state-machine-workflows"></a>Zustandsautomatworkflows  
 Zustandsautomatworkflows wurden als Teil der .NET Framework 4.0.1 im [Microsoft .NET Framework 4 Platform Update 1](https://go.microsoft.com/fwlink/?LinkID=215092)eingeführt. Dieses Update umfasste verschiedene neue Klassen und Aktivitäten, die es den Entwicklern ermöglichten, Zustandsautomatworkflows zu erstellen. Diese Klassen und Aktivitäten wurden für .NET Framework 4,5 aktualisiert. Updates umfassen:  
  
1. Festlegen von Haltepunkten für Zustände  
  
2. Kopieren und Einfügen von Übergängen im Workflow-Designer  
  
3. Designerunterstützung für das Erstellen von freigegebenen Triggerübergängen  
  
4. Aktivitäten, die zum Erstellen von Zustandsautomatworkflows verwendet werden, darunter: <xref:System.Activities.Statements.StateMachine>, <xref:System.Activities.Statements.State> und <xref:System.Activities.Statements.Transition>  
  
 Der folgende Screenshot zeigt den abgeschlossenen Zustandsautomatworkflow aus dem Schritt " [Getting Started Tutorial](getting-started-tutorial.md) " [Vorgehensweise: Erstellen Sie einen Zustands Automaten Workflow](how-to-create-a-state-machine-workflow.md).  
  
 ![Die Abbildung zeigt den abgeschlossenen Zustandsautomatworkflow.](./media/wf-features-in-the-rehosted-workflow-designer/complete-state-machine-workflow.jpg)  
  
 Weitere Informationen zum Erstellen von Zustandsautomatworkflows finden Sie unter [Zustandsautomatworkflows](state-machine-workflows.md). Zustandsautomatworkflows werden im neu gehosteten Designer unterstützt.  
  
### <a name="contract-first-workflow-development"></a>Vertrag zuerst-Workflowentwicklung  
 Mit dem Contract-First-Workflow-Entwicklungs Tool können Entwickler zunächst einen Vertrag im Code entwerfen und dann mit wenigen Klicks in Visual Studio automatisch eine Aktivitäts Vorlage in der Toolbox generieren, die die einzelnen Vorgänge darstellt. Diese Aktivitäten werden dann verwendet, um einen Workflow zu erstellen, der die vom Vertrag definierten Vorgänge implementiert. Der Workflow-Designer überprüft den Workflowdienst, um sicherzustellen, dass diese Vorgänge implementiert wurden und dass die Signatur des Workflows mit der Vertragssignatur übereinstimmt. Der Entwickler kann einen Workflowdienst auch einer Auflistung implementierter Verträge zuordnen. Weitere Informationen zur Entwicklung von Vertrag zuerst-Workflow Diensten finden Sie unter [Vorgehensweise: Erstellen Sie einen Workflow Dienst, der einen vorhandenen Dienstvertrags](how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)verwendet.  
  
> [!WARNING]
> Die Vertrag zuerst-Workflowentwicklung wird im Workflow-Designer nicht unterstützt.
