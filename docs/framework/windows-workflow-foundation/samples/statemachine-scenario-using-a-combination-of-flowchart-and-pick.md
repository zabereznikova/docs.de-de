---
title: "StateMachine-Szenario mit einer Kombination aus FlowChart und Pick | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# StateMachine-Szenario mit einer Kombination aus FlowChart und Pick
Dieses Beispiel veranschaulicht, wie ein einfaches Szenario mit einer Stoppuhr mithilfe einer Kombination der <xref:System.Activities.Statements.Flowchart>\-Aktivität und der <xref:System.Activities.Statements.Pick>\-Aktivität implementiert wird.Stoppuhrereignisse werden mithilfe von Empfangs\- und Sendeaktivitäten innerhalb der Pick\-Aktivität überwacht.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie \(Downloadseite\) auf, und laden Sie alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Beispiele und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunter.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## Beispieldetails  
 In der folgenden Tabelle sind die Projekte in diesem Beispiel aufgeführt.  
  
|||  
|-|-|  
|Projektname|Beschreibung|  
|StopWatchService|Dieses Projekt enthält die Implementierung eines Zustandsautomaten für das Stoppuhrbeispiel, in dem eine Kombination der <xref:System.Activities.Statements.Flowchart>\-Aktivität und der <xref:System.Activities.Statements.Pick>\-Aktivität verwendet wird.<br /><br /> Die <xref:System.Activities.Statements.Pick>\-Aktivität verfügt über 3 <xref:System.Activities.Statements.PickBranch>\-Anweisungen innerhalb der <xref:System.Activities.Statements.Pick.Branches%2A>\-Eigenschaft, die die Ereignisse `GetStart`, `GetStop` und `GetOff` überwacht.Auf Grundlage des eingehenden Ereignisses werden die Trigger für eine der Verzweigungen aktiviert, und die entsprechende <xref:System.Activities.Statements.PickBranch.Action%2A> wird ausgelöst.In der <xref:System.Activities.Statements.PickBranch.Action%2A>\-Eigenschaft gibt es eine <xref:System.Activities.Statements.Switch%601>\-Anweisung, die auswertet, ob der Übergang ein rechtmäßiger Übergang ist. Ist dies der Fall, wird die `currentState`\-Eigenschaft auf den Übergangszustand aktualisiert und an den Client gesendet.<br /><br /> Die <xref:System.Activities.Statements.FlowDecision>\-Aktivität am Ende von <xref:System.Activities.Statements.Flowchart> wertet die `currentState`\-Eigenschaft aus, um zu bestimmen, ob der Zustand ein Endstatus ist.Ist dies der Fall, endet der Workflow. Andernfalls springt die Steuerung zurück zum Start der <xref:System.Activities.Statements.Pick>\-Aktivität, wo der Workflow auf weitere Stoppuhrereignisse wartet.|  
|StopWatchClient|Dies ist eine einfache sequenzielle Workflowkonsolenanwendung, die verschiedene Stoppuhrereignisse mit einfachen Kombinationen der Send\- und Receive\-Aktivitäten sendet.|  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "StateMachineWithPick.sln".  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Starten Sie "StopWatchService.exe" in [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] als Administrator, indem Sie mit der rechten Maustaste auf die EXE\-Datei klicken und **Als Administrator ausführen** auswählen.  
  
    1.  Navigieren Sie zum Ordner "StateMachineWithPick\\CS\\StopWatchService\\bin\\Debug".  
  
    2.  Klicken Sie mit der rechten Maustaste auf die Datei "StopWatchService.exe", und wählen Sie **Als Administrator ausführen** aus.  
  
4.  Starten Sie die StopWatchClient\-Clientanwendung über [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    1.  Wählen Sie im **Projektmappen\-Explorer** das Projekt **StopWatchClient** aus, und klicken Sie mit der rechten Maustaste auf **Als Startprojekt festlegen**.  
  
    2.  Drücken Sie STRG\+F5, um die Projektmappe auszuführen.  
  
5.  Wechseln Sie zum Konsolenfenster für "StopWatchService.exe" zurück, um die Zustandsübergänge anzuzeigen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## Siehe auch