---
title: Zustandsautomatworkflows
description: Dieser Artikel bietet eine Übersicht über das Erstellen von Zustands Automaten Workflows mithilfe der StateMachine-Aktivität.
ms.date: 03/30/2017
ms.assetid: 344caacd-bf3b-4716-bd5a-eca74fc5a61d
ms.openlocfilehash: 2b259f315e0186c13ca44c5eed50d861bce3668a
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421331"
---
# <a name="state-machine-workflows"></a>Zustandsautomatworkflows
Ein Zustandsautomat ist ein bekanntes Paradigma zum Entwickeln von Anwendungen. Die <xref:System.Activities.Statements.StateMachine>-Aktivität kann zusammen mit <xref:System.Activities.Statements.State>, <xref:System.Activities.Statements.Transition> und anderen Aktivitäten verwendet werden, um Zustandsautomatenworkflow-Programme zu erstellen. Dieses Thema bietet eine Übersicht über das Erstellen von Zustandsautomatenworkflows.  
  
## <a name="state-machine-workflow-overview"></a>Übersicht über Zustandsautomatenworkflows  
 Zustandsautomatenworkflows bieten eine Möglichkeit, Workflows in einer ereignisgesteuerten Weise zu modellieren. Eine <xref:System.Activities.Statements.StateMachine>-Aktivität enthält die Zustände und Übergänge, aus denen sich die Logik des Zustandsautomaten aufbaut, und kann überall dort verwendet werden, wo eine Aktivität verwendet werden kann. Es gibt mehrere Klassen in der Zustandsautomat-Laufzeit:  
  
- <xref:System.Activities.Statements.StateMachine>  
  
- <xref:System.Activities.Statements.State>  
  
- <xref:System.Activities.Statements.Transition>  
  
 Zum Erstellen eines Zustandsautomatworkflows werden Zustände zu einer <xref:System.Activities.Statements.StateMachine> -Aktivität hinzugefügt, und Übergänge werden verwendet, um den Fluss zwischen Zuständen zu steuern. Der folgende Screenshot zeigt im Schritt " [Getting Started Tutorial](getting-started-tutorial.md) [How to: Create a State Machine Workflow](how-to-create-a-state-machine-workflow.md)" einen Zustands Automaten Workflow mit drei Zuständen und drei Übergängen. **Initialisieren des Ziels** ist der Anfangszustand und stellt den ersten Zustand im Workflow dar. Dies wird durch die Zeile festgelegt, die vom **Start** Knoten zu dieser führt. Der endgültige Zustand im Workflow heißt **FinalState**und stellt den Punkt dar, an dem der Workflow abgeschlossen ist.  
  
 ![Die Abbildung zeigt den abgeschlossenen Zustandsautomatworkflow.](./media/state-machine-workflows/complete-state-machine-workflow.jpg)  
  
 Ein Zustandsautomatenworkflow muss über genau einen Anfangszustand und mindestens einen Endzustand verfügen. Jeder Zustand, der kein Endzustand ist, muss mindestens einen Übergang enthalten. In den folgenden Abschnitten wird das Erstellen und Konfigurieren von Zuständen und Übergängen erläutert.  
  
## <a name="creating-and-configuring-states"></a>Erstellen und Konfigurieren von Zuständen  
 <xref:System.Activities.Statements.State> stellt einen Zustand dar, in dem sich ein Zustandsautomat befinden kann. Wenn Sie einen einem Workflow hinzufügen möchten <xref:System.Activities.Statements.State> , ziehen Sie den **Zustands** Aktivitäts Designer aus dem Abschnitt **Zustands Automat** der **Toolbox** , und legen Sie ihn auf einer- <xref:System.Activities.Statements.StateMachine> Aktivität auf der Windows-Workflow-Designer Oberfläche ab.  
  
 ![Screenshot des Abschnitts "Zustands Automat" der Toolbox.](./media/state-machine-workflows/state-machine-section-toolbox.jpg)  
  
 Um einen Zustand als **Ausgangszustand**zu konfigurieren, klicken Sie mit der rechten Maustaste auf den Status, und wählen Sie **als Anfangszustand festlegen**aus. Wenn kein aktueller Anfangszustand vorhanden ist, kann der Anfangszustand festgelegt werden, indem eine Linie vom **Start** Knoten am oberen Rand des Workflows in den gewünschten Zustand gezogen wird. Wenn eine- <xref:System.Activities.Statements.StateMachine> Aktivität auf dem Workflow-Designer abgelegt wird, wird Sie mit einem Anfangszustand namens **state1**vorkonfiguriert. Ein Zustandsautomatenworkflow muss über genau einen Anfangszustand verfügen.  
  
 Ein Zustand, der einen beendenden Zustand in einem Zustandsautomaten darstellt, wird als Endzustand bezeichnet. Ein Endzustand ist ein Zustand, dessen <xref:System.Activities.Statements.State.IsFinal%2A>-Eigenschaft auf `true` festgelegt ist, der keine <xref:System.Activities.Statements.State.Exit%2A>-Aktivität aufweist und von dem keine Übergänge ausgehen. Um einem Workflow einen Endzustand hinzuzufügen, ziehen Sie einen **FinalState** -Aktivitäts Designer aus dem Abschnitt **Zustands Automat** der **Toolbox** , und legen Sie ihn auf einer- <xref:System.Activities.Statements.StateMachine> Aktivität auf der Windows-Workflow-Designer Oberfläche ab. Ein Zustandsautomatenworkflow muss über mindestens einen Endzustand verfügen.  
  
### <a name="configuring-entry-and-exit-actions"></a>Konfigurieren von Eingangs- und Ausgangsaktionen  
 Ein Zustand kann über eine <xref:System.Activities.Statements.State.Entry%2A>-Aktion und eine <xref:System.Activities.Statements.State.Exit%2A>-Aktion verfügen. (Ein als Endzustand konfigurierter Zustand darf nur über eine Eingangsaktion verfügen.) Wenn eine Workflowinstanz in einen Zustand wechselt, werden alle Aktivitäten in der Eingangsaktion ausgeführt. Wenn die Eintrags Aktion beendet ist, werden die Trigger für die Übergänge des Zustands geplant. Wenn ein Übergang zu einem anderen Status bestätigt wird, werden die Aktivitäten in der Ausgangsaktion auch dann ausgeführt, wenn der Zustand wieder in denselben Zustand übergeht. Nachdem die Beendigungs Aktion abgeschlossen ist, werden die Aktivitäten in der Aktion des Übergangs ausgeführt, und der neue Zustand wird in gewechselt, und die zugehörigen Eintrags Aktionen werden geplant.  
  
> [!NOTE]
> Wenn Sie einen Zustandsautomatenworkflow debuggen, können Haltepunkte für die Stammaktivität des Zustandsautomaten und für Zustände innerhalb des Zustandsautomatenworkflows festgelegt werden. Haltepunkte können nicht direkt in die Übergänge eingefügt werden, sie können jedoch für alle Aktivitäten festgelegt werden, die in den Zuständen und Übergängen enthalten sind.  
  
## <a name="creating-and-configuring-transitions"></a>Erstellen und Konfigurieren von Übergängen  
 Alle Zustände müssen über mindestens einen Übergang verfügen, mit Ausnahme eines Endzustands, bei dem möglicherweise keine Übergänge vorhanden sind. Übergänge können hinzugefügt werden, nachdem ein Zustand einem Zustandsautomatenworkflow hinzugefügt wurde, oder sie können beim Ablegen des Zustands erstellt werden.  
  
 Wenn Sie ein hinzufügen <xref:System.Activities.Statements.State> und einen Übergang in einem Schritt erstellen möchten, ziehen Sie eine **State** -Aktivität aus dem Abschnitt **Zustands Automat** der **Toolbox** , und bewegen Sie den Mauszeiger über einen anderen Zustand im Workflow-Designer. Sobald sich der gezogene <xref:System.Activities.Statements.State> über einem anderen <xref:System.Activities.Statements.State> befindet, werden vier Dreiecke um den anderen <xref:System.Activities.Statements.State> herum eingeblendet. Wenn <xref:System.Activities.Statements.State> auf einem der vier Dreiecke abgelegt wird, wird er dem Zustandsautomaten hinzugefügt, und es wird ein Übergang vom Quell-<xref:System.Activities.Statements.State> zum abgelegten Ziel-<xref:System.Activities.Statements.State> erstellt. Weitere Informationen finden Sie unter [Transition Activity Designer](/visualstudio/workflow-designer/transition-activity-designer).  
  
 Um einen Übergang zu erstellen, nachdem ein Zustand hinzugefügt wurde, gibt es zwei Möglichkeiten. Die erste Möglichkeit besteht darin, den Zustand aus der Workflow-Designeroberfläche auf einen vorhandenen Zustand zu ziehen und auf einem der Ablegepunkte abzulegen. Dies ähnelt der im vorherigen Abschnitt beschriebenen Methode. Sie können auch mit der Maus auf den gewünschten Quellzustand zeigen und eine Linie zum gewünschten Zielzustand ziehen.  
  
> [!NOTE]
> Ein einzelner Zustand eines Zustandsautomaten kann bis zu 76 Übergänge aufweisen, die mithilfe des Workflow-Designers erstellt wurden. Die Anzahl der Zustandsübergänge für Workflows, die außerhalb des Designers erstellt werden, wird nur durch die verfügbaren Systemressourcen beschränkt.  
  
 Ein Übergang kann über <xref:System.Activities.Statements.Transition.Trigger%2A>, <xref:System.Activities.Statements.Transition.Condition%2A> und <xref:System.Activities.Statements.Transition.Action%2A> verfügen. Der Übergang eines Übergangs <xref:System.Activities.Statements.Transition.Trigger%2A> wird geplant, wenn die Aktion des Quell Zustands des Übergangs <xref:System.Activities.Statements.State.Entry%2A> beendet ist. In der Regel ist <xref:System.Activities.Statements.Transition.Trigger%2A> eine Aktivität, die darauf wartet, dass ein Ereignis eintritt. Er kann jedoch auch eine beliebige oder gar keine Aktivität darstellen. Sobald die <xref:System.Activities.Statements.Transition.Trigger%2A>-Aktivität abgeschlossen ist, wird <xref:System.Activities.Statements.Transition.Condition%2A> ausgewertet, falls vorhanden. Wenn keine Aktivität vorhanden ist <xref:System.Activities.Statements.Transition.Trigger%2A> , <xref:System.Activities.Statements.Transition.Condition%2A> wird sofort ausgewertet. Wenn die Bedingung ergibt `false` , wird der Übergang abgebrochen, und die <xref:System.Activities.Statements.Transition.Trigger%2A> Aktivität für alle Übergänge aus dem Zustand wird neu geplant. Wenn andere Übergänge denselben Quell Zustand wie der aktuelle Übergang aufweisen, <xref:System.Activities.Statements.Transition.Trigger%2A> werden diese Aktionen ebenfalls abgebrochen und neu geplant. Wenn <xref:System.Activities.Statements.Transition.Condition%2A>`true` ergibt oder keine Bedingung vorhanden ist, wird die <xref:System.Activities.Statements.State.Exit%2A>-Aktion des Quellzustands ausgeführt, und dann wird <xref:System.Activities.Statements.Transition.Action%2A> des Übergangs ausgeführt. Wenn <xref:System.Activities.Statements.Transition.Action%2A> abgeschlossen ist, wird die Steuerung an den **Ziel** Zustand weitergeleitet.  
  
 Übergänge, die einen gemeinsamen Trigger verwenden, werden als gemeinsamer Triggerübergang bezeichnet. Jeder Übergang in einer Gruppe von gemeinsamen Triggerübergängen verfügt über denselben Trigger, aber über eine eindeutige <xref:System.Activities.Statements.Transition.Condition%2A> und eine eindeutige Aktion. Um einem Übergang zusätzliche Aktionen hinzuzufügen und einen gemeinsamen Übergang zu erstellen, klicken Sie auf den Kreis, der den Anfang des gewünschten Übergangs angibt, und ziehen Sie ihn auf den gewünschten Zustand. Der neue Übergang verwendet denselben Trigger wie der Anfangsübergang, besitzt jedoch eine eindeutige Bedingung und Aktion. Freigegebene Übergänge können auch aus dem Übergangs-Designer erstellt werden, indem Sie im unteren Bereich des Übergangs-Designers auf frei **gegebenen triggerübergang hinzufügen** klicken und dann den gewünschten Ziel Status aus der Dropdown Liste **Verfügbare Zustände zum Verbinden** auswählen.  
  
> [!NOTE]
> Wenn die <xref:System.Activities.Statements.Transition.Condition%2A>-Aktivität eines Übergangs mit `False` ausgewertet wird (oder alle Bedingungen eines Übergangs mit freigegebenem Trigger mit `False` ausgewertet werden), erfolgt der Übergang nicht, und die Trigger aller Übergänge aus dem Zustand werden neu geplant.  
  
 Weitere Informationen zum Erstellen von Zustandsautomatworkflows finden Sie unter Vorgehens [Weise: Erstellen eines](how-to-create-a-state-machine-workflow.md)Zustandsautomatworkflows, [StateMachine-Aktivitäts Designers](/visualstudio/workflow-designer/statemachine-activity-designer), [Zustands Aktivitäts](/visualstudio/workflow-designer/state-activity-designer)Designers, [FinalState-Aktivitäts Designer](/visualstudio/workflow-designer/finalstate-activity-designer)und [Übergangs Aktivitäts Designer](/visualstudio/workflow-designer/transition-activity-designer).  
  
## <a name="state-machine-terminology"></a>Terminologie für Zustandsautomaten  
 In diesem Abschnitt werden die in diesem Thema verwendeten Begriffe im Hinblick auf Zustandsautomaten erläutert.  
  
 Staat  
 Die Basiseinheit, aus der ein Zustandsautomat besteht. Ein Zustandsautomat kann zu einem bestimmten Zeitpunkt jeweils einen Zustand aufweisen.  
  
 Eingangsaktion  
 Eine Aktivität, die beim Eintritt in den Zustand ausgeführt wird.  
  
 Ausgangsaktion  
 Eine Aktivität, die beim Austritt aus dem Zustand ausgeführt wird.  
  
 Umstellung  
 Eine gesteuerte Beziehung zwischen zwei Zuständen, die die komplette Antwort eines Zustands Automaten auf das Vorkommen eines Ereignisses eines bestimmten Typs darstellt.  
  
 Gemeinsamer Übergang  
 Ein Übergang, der denselben Quellzustand und Trigger wie mindestens ein anderer Übergang verwendet, jedoch über eine eindeutige Bedingung und Aktion verfügt.  
  
 Trigger  
 Eine Triggeraktivität, die einen Übergang auslöst.  
  
 Bedingung  
 Eine Einschränkung, die `true` nach dem Auftreten des Auslösers ausgewertet werden muss, damit der Übergang beendet wird.  
  
 Übergangsaktion  
 Eine Aktivität, die ausgeführt wird, wenn ein bestimmter Übergang ausgeführt wird.  
  
 Bedingter Übergang  
 Ein Übergang mit einer expliziten Bedingung.  
  
 Selbstübergang  
 Ein Übergang, der von einem Zustand in sich selbst übergeht.  
  
 Anfangszustand  
 Ein Zustand, der den Anfangspunkt des Zustands Automaten darstellt.  
  
 Endzustand  
 Ein Zustand, der den Abschluss des Zustands Automaten darstellt.  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen eines Zustandsautomatworkflows](how-to-create-a-state-machine-workflow.md)
- [StateMachine-Aktivitätsdesigner](/visualstudio/workflow-designer/statemachine-activity-designer)
- [Zustands-Aktivitätsdesigner](/visualstudio/workflow-designer/state-activity-designer)
- [FinalState-Aktivitätsdesigner](/visualstudio/workflow-designer/finalstate-activity-designer)
- [Übergangsaktivitäts-Designer](/visualstudio/workflow-designer/transition-activity-designer)
