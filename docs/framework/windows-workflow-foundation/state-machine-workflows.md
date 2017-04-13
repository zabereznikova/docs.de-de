---
title: "Zustandsautomatworkflows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 344caacd-bf3b-4716-bd5a-eca74fc5a61d
caps.latest.revision: 16
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# Zustandsautomatworkflows
Ein Zustandsautomat ist ein bekanntes Paradigma zum Entwickeln von Anwendungen.Die <xref:System.Activities.Statements.StateMachine>\-Aktivität kann zusammen mit <xref:System.Activities.Statements.State>, <xref:System.Activities.Statements.Transition> und anderen Aktivitäten verwendet werden, um Zustandsautomatworkflowprogramme zu erstellen.Dieses Thema bietet eine Übersicht über das Erstellen von Zustandsautomatworkflows.  
  
## Übersicht über Zustandsautomatworkflows  
 Zustandsautomatworkflows bieten eine Möglichkeit, Workflows in einer ereignisgesteuerten Weise zu modellieren.Eine <xref:System.Activities.Statements.StateMachine>\-Aktivität enthält die Zustände und Übergänge, aus denen sich die Logik des Zustandsautomaten aufbaut, und können überall dort eingesetzt werden, wo eine Aktivität verwendet werden kann.Es gibt mehrere Klassen in der Zustandsautomat\-Laufzeit:  
  
-   <xref:System.Activities.Statements.StateMachine>  
  
-   <xref:System.Activities.Statements.State>  
  
-   <xref:System.Activities.Statements.Transition>  
  
 Um einen Zustandsautomatworkflow erstellen, werden die Zustände in eine <xref:System.Activities.Statements.StateMachine>\-Aktivität hinzugefügt. Übergänge werden verwendet, um den Fluss zwischen Zuständen zu steuern.Die folgende Bildschirmabbildung aus dem [Lernprogramm 'Erste Schritte'](../../../docs/framework/windows-workflow-foundation//getting-started-tutorial.md), Schritt [Gewusst wie: Erstellen eines Zustandsautomatenworkflows](../../../docs/framework/windows-workflow-foundation//how-to-create-a-state-machine-workflow.md), zeigt einen Zustandsautomatworkflow mit drei Zuständen und drei Übergängen.**Ziel initialisieren** ist der Ausgangszustand und stellt den ersten Zustand im Workflow dar.Er ist an der Linie erkennbar, die vom Knoten **Start** zum Zustand führt.Der Endzustand im Workflow wird **FinalState** genannt und stellt den Punkt dar, an dem der Workflow abgeschlossen ist.  
  
 ![Abgeschlossener Zustandsautomatworkflow](../../../docs/framework/windows-workflow-foundation//media/wfstatemachinegettingstartedtutorialcomplete.JPG "WFStateMachineGettingStartedTutorialComplete")  
  
 Ein Zustandsautomatworkflow muss über genau einen Ausgangszustand und mindestens einen Endzustand verfügen.Jeder Zustand, der kein Endzustand ist, muss mindestens einen Übergang enthalten.In den folgenden Abschnitte wird das Erstellen und Konfigurieren von Zuständen und Übergängen erläutert.  
  
## Erstellen und Konfigurieren von Zuständen  
 <xref:System.Activities.Statements.State> stellt einen Zustand dar, in dem sich ein Zustandsautomat befinden kann.Um einem Workflow <xref:System.Activities.Statements.State> hinzuzufügen, ziehen Sie den **State**\-Aktivitätsdesigner aus dem Abschnitt **Zustandsautomat** der **Toolbox** und legen ihn auf einer <xref:System.Activities.Statements.StateMachine>\-Aktivität auf der [!INCLUDE[wfd1](../../../includes/wfd1-md.md)]\-Oberfläche ab.  
  
 ![WF4&#45;Zustandsautomataktivitäten](../../../docs/framework/windows-workflow-foundation//media/netframework4platformupdate1statemachineactivities.jpg "NETFramework4PlatformUpdate1StateMachineActivities")  
  
 Um einen Zustand als **Anfangszustand** zu konfigurieren, klicken Sie mit der rechten Maustaste auf den Zustand und wählen **Als Ausgangszustand festlegen** aus.Wenn derzeit kein Ausgangszustand vorhanden sind, kann der Ausgangszustand auch festgelegt werden, indem eine Linie vom Knoten **Start** am oberen Rand des Workflows zum gewünschten Zustand gezogen wird.Wenn eine <xref:System.Activities.Statements.StateMachine>\-Aktivität im Workflow\-Designer abgelegt wird, wird sie mit einem Anfangszustand namens **State1** vorkonfiguriert.Ein Zustandsautomatworkflow muss über genau einen Ausgangszustand verfügen.  
  
 Ein Zustand, der einen endenden Zustand in einen Zustandsautomat darstellt, wird als Endzustand bezeichnet.Ein Endzustand ist ein Zustand, dessen `true`\-Eigenschaft auf <xref:System.Activities.Statements.State.IsFinal%2A> festgelegt ist, der keine <xref:System.Activities.Statements.State.Exit%2A>\-Aktivität aufweist und von dem keine Übergänge ausgehen.Um einem Workflow einen Endzustand hinzuzufügen, ziehen Sie eine **FinalState**\-Aktivität aus dem Abschnitt **Zustandsautomat** der **Toolbox** und legen sie auf einer <xref:System.Activities.Statements.StateMachine>\-Aktivität auf der [!INCLUDE[wfd1](../../../includes/wfd1-md.md)]\-Oberfläche ab.Ein Zustandsautomatworkflow muss über mindestens einen Endzustand verfügen.  
  
### Konfigurieren von Entry\- und Exit\-Aktionen  
 Ein Zustand kann über eine <xref:System.Activities.Statements.State.Entry%2A>\- und eine <xref:System.Activities.Statements.State.Exit%2A>\-Aktion verfügen.\(Ein als Endzustand konfigurierter Zustand darf nur über eine Entry\-Aktion verfügen.\)Wenn eine Workflowinstanz in einen Zustand eintritt, werden alle Aktivitäten in der Entry\-Aktion ausgeführt.Wenn die Entry\-Aktion abgeschlossen ist, werden die Trigger für die Übergänge des Zustands geplant.Wenn ein Übergang zu einem anderen Status bestätigt wird, werden die Aktivitäten in der Exit\-Aktion ausgeführt, auch wenn der Zustand wieder zum selben Zustand übergeht.Nachdem die Exit\-Aktion abgeschlossen wurde, werden die Aktivitäten in der Aktion des Übergangs ausgeführt. Anschließend findet ein Übergang in den neuen Zustand statt, und dessen Entry\-Aktionen werden geplant.  
  
> [!NOTE]
>  Wenn Sie einen Zustandsautomatworkflow debuggen, können Haltepunkte für die Stammaktivität des Zustandsautomaten und für Zustände innerhalb des Zustandsautomatworkflows festgelegt werden.Haltepunkte nicht direkt in die Übergänge eingefügt werden, sie können jedoch für alle Aktivitäten festgelegt werden, die in den Zuständen und Übergängen enthalten sind.  
  
## Erstellen und Konfigurieren von Übergängen  
 Alle Zustände außer einem Endzustand, der gar keine Übergänge aufweisen darf, müssen über mindestens einen Übergang verfügen.Übergänge können hinzugefügt werden, nachdem ein Zustand einem Zustandsautomatworkflow hinzugefügt wurde, oder sie können beim Ablegen des Zustands erstellt wurden.  
  
 Um in einem Schritt <xref:System.Activities.Statements.State> hinzuzufügen und einen Übergang zu erstellen, ziehen Sie eine **State**\-Aktivität aus dem Abschnitt **Zustandsautomat** der **Toolbox** auf einen anderen Zustand im Workflow\-Designer.Sobald sich der gezogene <xref:System.Activities.Statements.State> über einem anderen <xref:System.Activities.Statements.State> befindet, werden vier Dreiecke um den anderen <xref:System.Activities.Statements.State> herum eingeblendet.Wenn <xref:System.Activities.Statements.State> auf einem der vier Dreiecke abgelegt wird, wird er dem Zustandsautomat hinzugefügt, und es wird ein Übergang vom Quell\-<xref:System.Activities.Statements.State> zum abgelegten Ziel\-<xref:System.Activities.Statements.State> erstellt.Weitere Informationen finden Sie unter [Übergangsaktivitäts\-Designer](../Topic/Transition%20Activity%20Designer.md).  
  
 Um einen Übergang zu erstellen, nachdem ein Zustand hinzugefügt wurde, gibt es zwei Möglichkeiten.Die erste Möglichkeit besteht darin, den Zustand aus der Workflow\-Designeroberfläche auf einen vorhandenen Zustand zu ziehen und auf einem der Ablegepunkte abzulegen.Dies ist der Methode sehr ähnlich, die im vorherigen Abschnitt beschrieben wird.Sie können auch mit der Maus auf den gewünschten Quellzustand zeigen und eine Linie zum gewünschten Zielzustand ziehen.  
  
> [!NOTE]
>  Ein einzelner Zustand eines Zustandsautomaten kann bis zu 76 Übergänge aufweisen, die mithilfe des Workflow\-Designers erstellt wurden.Die Anzahl der Zustandsübergänge für Workflows, die außerhalb des Designers erstellt werden, wird nur durch die verfügbaren Systemressourcen beschränkt.  
  
 Ein Übergang kann über <xref:System.Activities.Statements.Transition.Trigger%2A>, <xref:System.Activities.Statements.Transition.Condition%2A> und <xref:System.Activities.Statements.Transition.Action%2A> verfügen.Der <xref:System.Activities.Statements.Transition.Trigger%2A> eines Übergangs wird geplant, wenn die <xref:System.Activities.Statements.State.Entry%2A>\-Aktion der Quellzustände des Übergangs abgeschlossen ist.In der Regel ist <xref:System.Activities.Statements.Transition.Trigger%2A> eine Aktivität, die darauf wartet, dass ein Ereignis eintritt. Er kann jedoch auch eine beliebige oder gar keine Aktivität darstellen.Sobald die <xref:System.Activities.Statements.Transition.Trigger%2A>\-Aktivität abgeschlossen ist, wird <xref:System.Activities.Statements.Transition.Condition%2A>, falls vorhanden, ausgewertet.Wenn keine <xref:System.Activities.Statements.Transition.Trigger%2A>\-Aktivität vorhanden ist, wird <xref:System.Activities.Statements.Transition.Condition%2A> sofort ausgewertet.Wenn die Bedingung `false` ergibt, wird der Übergang abgebrochen und die <xref:System.Activities.Statements.Transition.Trigger%2A>\-Aktivität für alle Übergänge aus dem Zustand neu geplant.Sind andere Übergänge vorhanden, die den gleichen Quellzustand wie der aktuelle Übergang aufweisen, werden diese <xref:System.Activities.Statements.Transition.Trigger%2A>\-Aktionen ebenfalls abgebrochen und neu geplant.Wenn <xref:System.Activities.Statements.Transition.Condition%2A>`true` ergibt oder keine Bedingung vorhanden ist, wird die <xref:System.Activities.Statements.State.Exit%2A>\-Aktion des Quellzustands ausgeführt, und dann wird <xref:System.Activities.Statements.Transition.Action%2A> des Übergangs ausgeführt.Wenn <xref:System.Activities.Statements.Transition.Action%2A> abgeschlossen wird, wird die Steuerung an den **Zielzustand** übergeben.  
  
 Übergänge, die einen gemeinsamen Trigger verwenden, werden als Übergänge mit gemeinsamem Trigger bezeichnet.Jeder Übergang in einer Gruppe von Übergängen mit gemeinsamem Trigger verfügt über denselben Trigger, aber über eine eindeutige <xref:System.Activities.Statements.Transition.Condition%2A> und eine eindeutige Aktion.Um einem Übergang zusätzliche Aktionen hinzuzufügen und einen gemeinsamen Übergang zu erstellen, klicken Sie auf den Kreis, der den Anfang des gewünschten Übergangs angibt, und ziehen Sie ihn auf den gewünschten Zustand.Der neue Übergang verwendet denselben Trigger wie der Anfangsübergang, besitzt jedoch eine eindeutige Bedingung und Aktion.Gemeinsame Übergänge können auch innerhalb des Übergangs\-Designers erstellt werden, indem Sie am unteren Rand des Übergangs\-Designers auf **Übergang mit gemeinsamem Trigger hinzufügen** klicken und dann den gewünschten Zielzustand aus der Dropdownliste **Für Verbindung verfügbare Zustände** auswählen.  
  
> [!NOTE]
>  Wenn die <xref:System.Activities.Statements.Transition.Condition%2A>\-Aktivität eines Übergangs mit `False` ausgewertet wird \(oder alle Bedingungen eines Übergangs mit freigegebenem Trigger mit `False` ausgewertet werden\), erfolgt der Übergang nicht, und die Trigger aller Übergänge aus dem Zustand werden neu geplant.  
  
 Weitere Informationen zum Erstellen von Zustandsautomatworkflows finden Sie unter [Gewusst wie: Erstellen eines Zustandsautomatenworkflows](../../../docs/framework/windows-workflow-foundation//how-to-create-a-state-machine-workflow.md), [StateMachine\-Aktivitäts\-Designer](../Topic/StateMachine%20Activity%20Designer.md), [Zustandsaktivitäts\-Designer](../Topic/State%20Activity%20Designer.md), [FinalState\-Aktivitäts\-Designer](../Topic/FinalState%20Activity%20Designer.md) und [Übergangsaktivitäts\-Designer](../Topic/Transition%20Activity%20Designer.md).  
  
## Zustandsautomat\-Terminologie  
 In diesem Abschnitt werden die in diesem Thema verwendeten Begriffe im Hinblick auf Zustandsautomaten erläutert.  
  
 Zustand  
 Die Basiseinheit, aus der ein Zustandsautomat besteht.Ein Zustandsautomat kann zu einem bestimmten Zeitpunkt jeweils einen Zustand aufweisen.  
  
 Entry\-Aktion  
 Eine Aktivität, die beim Eintritt in den Zustand ausgeführt wird.  
  
 Exit\-Aktion  
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
  
 Ausgangszustand  
 Ein Zustand, der den Anfangspunkt des Zustandsautomaten darstellt.  
  
 Endzustand  
 Ein Zustand, der den Abschluss des Zustandsautomaten darstellt.  
  
## Siehe auch  
 [Gewusst wie: Erstellen eines Zustandsautomatenworkflows](../../../docs/framework/windows-workflow-foundation//how-to-create-a-state-machine-workflow.md)   
 [StateMachine\-Aktivitäts\-Designer](../Topic/StateMachine%20Activity%20Designer.md)   
 [Zustandsaktivitäts\-Designer](../Topic/State%20Activity%20Designer.md)   
 [FinalState\-Aktivitäts\-Designer](../Topic/FinalState%20Activity%20Designer.md)   
 [Übergangsaktivitäts\-Designer](../Topic/Transition%20Activity%20Designer.md)