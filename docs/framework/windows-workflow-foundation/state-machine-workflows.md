---
title: Zustandsautomatworkflows
ms.date: 03/30/2017
ms.assetid: 344caacd-bf3b-4716-bd5a-eca74fc5a61d
ms.openlocfilehash: a6dedffda6654cb0acb7ab507129cba9f0bdb7f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33519638"
---
# <a name="state-machine-workflows"></a>Zustandsautomatworkflows
Ein Zustandsautomat ist ein bekanntes Paradigma zum Entwickeln von Anwendungen. Die <xref:System.Activities.Statements.StateMachine>-Aktivität kann zusammen mit <xref:System.Activities.Statements.State>, <xref:System.Activities.Statements.Transition> und anderen Aktivitäten verwendet werden, um Zustandsautomatenworkflow-Programme zu erstellen. Dieses Thema bietet eine Übersicht über das Erstellen von Zustandsautomatenworkflows.  
  
## <a name="state-machine-workflow-overview"></a>Übersicht über Zustandsautomatenworkflows  
 Zustandsautomatenworkflows bieten eine Möglichkeit, Workflows in einer ereignisgesteuerten Weise zu modellieren. Eine <xref:System.Activities.Statements.StateMachine>-Aktivität enthält die Zustände und Übergänge, aus denen sich die Logik des Zustandsautomaten aufbaut, und kann überall dort verwendet werden, wo eine Aktivität verwendet werden kann. Es gibt mehrere Klassen in der Zustandsautomat-Laufzeit:  
  
-   <xref:System.Activities.Statements.StateMachine>  
  
-   <xref:System.Activities.Statements.State>  
  
-   <xref:System.Activities.Statements.Transition>  
  
 Um einen Zustandsautomatenworkflow erstellen, werden die Zustände einer <xref:System.Activities.Statements.StateMachine>-Aktivität hinzugefügt. Übergänge werden verwendet, um den Fluss zwischen den Zuständen zu steuern. Der folgende Screenshot aus der [Lernprogramm für erste Schritte](../../../docs/framework/windows-workflow-foundation/getting-started-tutorial.md) Schritt [Vorgehensweise: Erstellen Sie einen Zustandsautomatworkflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md), zeigt ein zustandsautomatenworkflow mit drei Zustände und Übergänge drei. **Ziel initialisieren** ist der Anfangszustand und stellt den ersten Zustand im Workflow dar. Dadurch wird festgelegt, durch die Linie, die führende aus der **starten** Knoten. Der Endzustand im Workflow wird mit dem Namen **FinalState**, und stellt den Punkt, an dem der Workflow abgeschlossen ist.  
  
 ![Abgeschlossener Zustandsautomatworkflow](../../../docs/framework/windows-workflow-foundation/media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
 Ein Zustandsautomatenworkflow muss über genau einen Anfangszustand und mindestens einen Endzustand verfügen. Jeder Zustand, der kein Endzustand ist, muss mindestens einen Übergang enthalten. In den folgenden Abschnitten wird das Erstellen und Konfigurieren von Zuständen und Übergängen erläutert.  
  
## <a name="creating-and-configuring-states"></a>Erstellen und Konfigurieren von Zuständen  
 <xref:System.Activities.Statements.State> stellt einen Zustand dar, in dem sich ein Zustandsautomat befinden kann. Hinzufügen einer <xref:System.Activities.Statements.State> für einen Workflow, ziehen Sie die **Status** Aktivitäts-Designer aus der **Zustandsautomat** im Abschnitt der **Toolbox** und legen ihn auf eine <xref:System.Activities.Statements.StateMachine> Aktivität auf die [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] Oberfläche.  
  
 ![WF4 State Machine Aktivitäten](../../../docs/framework/windows-workflow-foundation/media/netframework4platformupdate1statemachineactivities.jpg "NETFramework4PlatformUpdate1StateMachineActivities")  
  
 So konfigurieren Sie einen Zustand als das **Anfangszustand**mit der rechten Maustaste auf den Zustand, und wählen Sie **als Anfangszustand festlegen**. Darüber hinaus ist kein Anfangszustand, der anfängliche Zustand kann gekennzeichnet werden durch Ziehen eine Zeile aus der **starten** Knoten am oberen Rand des Workflows auf den gewünschten Zustand. Wenn eine <xref:System.Activities.Statements.StateMachine> Aktivität dem Workflow-Designer abgelegt wird, wird Sie vorkonfiguriert, dass mit einem Anfangszustand mit dem Namen **State1**. Ein Zustandsautomatenworkflow muss über genau einen Anfangszustand verfügen.  
  
 Ein Zustand, der einen beendenden Zustand in einem Zustandsautomaten darstellt, wird als Endzustand bezeichnet. Ein Endzustand ist ein Zustand, dessen <xref:System.Activities.Statements.State.IsFinal%2A>-Eigenschaft auf `true` festgelegt ist, der keine <xref:System.Activities.Statements.State.Exit%2A>-Aktivität aufweist und von dem keine Übergänge ausgehen. Um einem Workflow einen Endzustand hinzuzufügen, ziehen Sie eine **FinalState** Aktivitäts-Designer aus der **Zustandsautomat** Teil der **Toolbox** und legen ihn auf eine <xref:System.Activities.Statements.StateMachine> Aktivität auf die [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] Oberfläche. Ein Zustandsautomatenworkflow muss über mindestens einen Endzustand verfügen.  
  
### <a name="configuring-entry-and-exit-actions"></a>Konfigurieren von Eingangs- und Ausgangsaktionen  
 Ein Zustand kann über eine <xref:System.Activities.Statements.State.Entry%2A>-Aktion und eine <xref:System.Activities.Statements.State.Exit%2A>-Aktion verfügen. (Ein als Endzustand konfigurierter Zustand darf nur über eine Eingangsaktion verfügen.) Wenn eine Workflowinstanz in einen Zustand wechselt, werden alle Aktivitäten in der Eingangsaktion ausgeführt. Wenn die Eingangsaktion abgeschlossen ist, werden die Trigger für die Übergänge des Zustands geplant. Wenn ein Übergang zu einem anderen Status bestätigt wird, werden die Aktivitäten in der Ausgangsaktion auch dann ausgeführt, wenn der Zustand wieder in denselben Zustand übergeht. Nachdem die Ausgangsaktion abgeschlossen wurde, werden die Aktivitäten in der Aktion des Übergangs ausgeführt. Anschließend findet ein Übergang in den neuen Zustand statt, und dessen Eingangsaktionen werden geplant.  
  
> [!NOTE]
>  Wenn Sie einen Zustandsautomatenworkflow debuggen, können Haltepunkte für die Stammaktivität des Zustandsautomaten und für Zustände innerhalb des Zustandsautomatenworkflows festgelegt werden. Haltepunkte können nicht direkt in die Übergänge eingefügt werden, sie können jedoch für alle Aktivitäten festgelegt werden, die in den Zuständen und Übergängen enthalten sind.  
  
## <a name="creating-and-configuring-transitions"></a>Erstellen und Konfigurieren von Übergängen  
 Alle Zustände mit Ausnahme eines Endzustands, der keine Übergänge aufweisen darf, müssen über mindestens einen Übergang verfügen. Übergänge können hinzugefügt werden, nachdem ein Zustand einem Zustandsautomatenworkflow hinzugefügt wurde, oder sie können beim Ablegen des Zustands erstellt werden.  
  
 Hinzufügen einer <xref:System.Activities.Statements.State> und einen Übergang zu erstellen, in einem Schritt, ziehen Sie eine **Status** Aktivität aus der **Zustandsautomat** Teil der **Toolbox** und zeigen sie auf einen anderen Zustand im der Workflowdesigner. Sobald sich der gezogene <xref:System.Activities.Statements.State> über einem anderen <xref:System.Activities.Statements.State> befindet, werden vier Dreiecke um den anderen <xref:System.Activities.Statements.State> herum eingeblendet. Wenn <xref:System.Activities.Statements.State> auf einem der vier Dreiecke abgelegt wird, wird er dem Zustandsautomaten hinzugefügt, und es wird ein Übergang vom Quell-<xref:System.Activities.Statements.State> zum abgelegten Ziel-<xref:System.Activities.Statements.State> erstellt. Weitere Informationen finden Sie unter [Übergangsaktivitäts-Designer](/visualstudio/workflow-designer/transition-activity-designer).  
  
 Um einen Übergang zu erstellen, nachdem ein Zustand hinzugefügt wurde, gibt es zwei Möglichkeiten. Die erste Möglichkeit besteht darin, den Zustand aus der Workflow-Designeroberfläche auf einen vorhandenen Zustand zu ziehen und auf einem der Ablegepunkte abzulegen. Dies ist der Methode sehr ähnlich, die im vorherigen Abschnitt beschrieben wird. Sie können auch mit der Maus auf den gewünschten Quellzustand zeigen und eine Linie zum gewünschten Zielzustand ziehen.  
  
> [!NOTE]
>  Ein einzelner Zustand eines Zustandsautomaten kann bis zu 76 Übergänge aufweisen, die mithilfe des Workflow-Designers erstellt wurden. Die Anzahl der Zustandsübergänge für Workflows, die außerhalb des Designers erstellt werden, wird nur durch die verfügbaren Systemressourcen beschränkt.  
  
 Ein Übergang kann über <xref:System.Activities.Statements.Transition.Trigger%2A>, <xref:System.Activities.Statements.Transition.Condition%2A> und <xref:System.Activities.Statements.Transition.Action%2A> verfügen. Der <xref:System.Activities.Statements.Transition.Trigger%2A> eines Übergangs wird geplant, wenn die <xref:System.Activities.Statements.State.Entry%2A>-Aktion der Quelle des Übergangs abgeschlossen ist. In der Regel ist <xref:System.Activities.Statements.Transition.Trigger%2A> eine Aktivität, die darauf wartet, dass ein Ereignis eintritt. Er kann jedoch auch eine beliebige oder gar keine Aktivität darstellen. Sobald die <xref:System.Activities.Statements.Transition.Trigger%2A>-Aktivität abgeschlossen ist, wird <xref:System.Activities.Statements.Transition.Condition%2A> ausgewertet, falls vorhanden. Wenn keine <xref:System.Activities.Statements.Transition.Trigger%2A>-Aktivität vorhanden ist, wird <xref:System.Activities.Statements.Transition.Condition%2A> sofort ausgewertet. Wenn die Bedingung `false` ergibt, wird der Übergang abgebrochen und die <xref:System.Activities.Statements.Transition.Trigger%2A>-Aktivität für alle Übergänge aus dem Zustand neu geplant. Sind andere Übergänge vorhanden, die den gleichen Quellzustand wie der aktuelle Übergang aufweisen, werden diese <xref:System.Activities.Statements.Transition.Trigger%2A>-Aktionen ebenfalls abgebrochen und neu geplant. Wenn <xref:System.Activities.Statements.Transition.Condition%2A>`true` ergibt oder keine Bedingung vorhanden ist, wird die <xref:System.Activities.Statements.State.Exit%2A>-Aktion des Quellzustands ausgeführt, und dann wird <xref:System.Activities.Statements.Transition.Action%2A> des Übergangs ausgeführt. Wenn die <xref:System.Activities.Statements.Transition.Action%2A> abgeschlossen ist, die Steuerung an die **Ziel** Zustand  
  
 Übergänge, die einen gemeinsamen Trigger verwenden, werden als gemeinsamer Triggerübergang bezeichnet. Jeder Übergang in einer Gruppe von gemeinsamen Triggerübergängen verfügt über denselben Trigger, aber über eine eindeutige <xref:System.Activities.Statements.Transition.Condition%2A> und eine eindeutige Aktion. Um einem Übergang zusätzliche Aktionen hinzuzufügen und einen gemeinsamen Übergang zu erstellen, klicken Sie auf den Kreis, der den Anfang des gewünschten Übergangs angibt, und ziehen Sie ihn auf den gewünschten Zustand. Der neue Übergang verwendet denselben Trigger wie der Anfangsübergang, besitzt jedoch eine eindeutige Bedingung und Aktion. Gemeinsame Übergänge können auch aus erstellt werden innerhalb des Übergangs-Designers durch Klicken auf **gemeinsamen triggerübergang hinzufügen** am unteren Rand des Übergangs-Designers, und wählen Sie dann den gewünschten Zielzustand aus der  **Verfügbare Zustände für Verbindung** Dropdownliste aus.  
  
> [!NOTE]
>  Wenn die <xref:System.Activities.Statements.Transition.Condition%2A>-Aktivität eines Übergangs mit `False` ausgewertet wird (oder alle Bedingungen eines Übergangs mit freigegebenem Trigger mit `False` ausgewertet werden), erfolgt der Übergang nicht, und die Trigger aller Übergänge aus dem Zustand werden neu geplant.  
  
 Weitere Informationen zum Erstellen von Zustandsautomatworkflows, finden Sie unter [Vorgehensweise: Erstellen Sie einen Zustandsautomatworkflow](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md), [StateMachine-Aktivitäts-Designer](/visualstudio/workflow-designer/statemachine-activity-designer), [Zustand Aktivitäts-Designer](/visualstudio/workflow-designer/state-activity-designer), [FinalState-Aktivitäts-Designer](/visualstudio/workflow-designer/finalstate-activity-designer), und [Übergang Aktivitäts-Designer](/visualstudio/workflow-designer/transition-activity-designer).  
  
## <a name="state-machine-terminology"></a>Terminologie für Zustandsautomaten  
 In diesem Abschnitt werden die in diesem Thema verwendeten Begriffe im Hinblick auf Zustandsautomaten erläutert.  
  
 Zustand  
 Die Basiseinheit, aus der ein Zustandsautomat besteht. Ein Zustandsautomat kann zu einem bestimmten Zeitpunkt jeweils einen Zustand aufweisen.  
  
 Eingangsaktion  
 Eine Aktivität, die beim Eintritt in den Zustand ausgeführt wird.  
  
 Ausgangsaktion  
 Eine Aktivität, die beim Austritt aus dem Zustand ausgeführt wird.  
  
 Übergang  
 Eine spezielle Beziehung zwischen zwei Zuständen, die die vollständige Antwort eines Zustandsautomaten auf das Eintreten eines Ereignisses eines bestimmten Typs darstellt.  
  
 Gemeinsamer Übergang  
 Ein Übergang, der denselben Quellzustand und Trigger wie mindestens ein anderer Übergang verwendet, jedoch über eine eindeutige Bedingung und Aktion verfügt.  
  
 Trigger  
 Eine Triggeraktivität, die einen Übergang auslöst.  
  
 Bedingung  
 Eine Einschränkung, die nach dem Auftreten des Triggers `true` ergeben muss, damit der Übergang abgeschlossen wird.  
  
 Übergangsaktion  
 Eine Aktivität, die ausgeführt wird, wenn ein bestimmter Übergang ausgeführt wird.  
  
 Bedingter Übergang  
 Ein Übergang mit einer expliziten Bedingung.  
  
 Selbstübergang  
 Ein Übergang, der von einem Zustand in denselben Übergang übergeht.  
  
 Anfangszustand  
 Ein Zustand, der den Anfangspunkt des Zustandsautomaten darstellt.  
  
 Endzustand  
 Ein Zustand, der den Abschluss des Zustandsautomaten darstellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen eines Zustandsautomatenworkflows](../../../docs/framework/windows-workflow-foundation/how-to-create-a-state-machine-workflow.md)  
 [StateMachine-Aktivitätsdesigner](/visualstudio/workflow-designer/statemachine-activity-designer)  
 [Zustands-Aktivitätsdesigner](/visualstudio/workflow-designer/state-activity-designer)  
 [FinalState-Aktivitätsdesigner](/visualstudio/workflow-designer/finalstate-activity-designer)  
 [Übergangsaktivitäts-Designer](/visualstudio/workflow-designer/transition-activity-designer)
