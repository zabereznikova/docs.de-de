---
title: StateMachine-Szenario mit einer Kombination aus FlowChart und Pick
ms.date: 03/30/2017
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
ms.openlocfilehash: b0f8e884a8a6c62c4e7edaf5cc9727bf7bfe8603
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "44032331"
---
# <a name="statemachine-scenario-using-a-combination-of-flowchart-and-pick"></a>StateMachine-Szenario mit einer Kombination aus FlowChart und Pick
Dieses Beispiel veranschaulicht, wie ein einfaches Szenario mit einer Stoppuhr mithilfe einer Kombination der <xref:System.Activities.Statements.Flowchart>-Aktivität und der <xref:System.Activities.Statements.Pick>-Aktivität implementiert wird. Stoppuhrereignisse werden mithilfe von Empfangs- und Sendeaktivitäten innerhalb der Pick-Aktivität überwacht.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie (Downloadseite) auf alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## <a name="sample-details"></a>Beispieldetails  
 In der folgenden Tabelle sind die Projekte in diesem Beispiel aufgeführt.  
  
|Projektname|Beschreibung|  
|-|-|  
|StopWatchService|Dieses Projekt enthält die Implementierung eines Zustandsautomaten für das Stoppuhrbeispiel, in dem eine Kombination der <xref:System.Activities.Statements.Flowchart>-Aktivität und der <xref:System.Activities.Statements.Pick>-Aktivität verwendet wird.<br /><br /> Die <xref:System.Activities.Statements.Pick>-Aktivität verfügt über 3 <xref:System.Activities.Statements.PickBranch>-Anweisungen innerhalb der <xref:System.Activities.Statements.Pick.Branches%2A>-Eigenschaft, die die Ereignisse `GetStart`, `GetStop` und `GetOff` überwacht. Auf Grundlage des eingehenden Ereignisses werden die Trigger für eine der Verzweigungen aktiviert, und die entsprechende <xref:System.Activities.Statements.PickBranch.Action%2A> wird ausgelöst. In der <xref:System.Activities.Statements.PickBranch.Action%2A>-Eigenschaft gibt es eine <xref:System.Activities.Statements.Switch%601>-Anweisung, die auswertet, ob der Übergang ein rechtmäßiger Übergang ist. Ist dies der Fall, wird die `currentState`-Eigenschaft auf den Übergangszustand aktualisiert und an den Client gesendet.<br /><br /> Die <xref:System.Activities.Statements.FlowDecision>-Aktivität am Ende von <xref:System.Activities.Statements.Flowchart> wertet die `currentState`-Eigenschaft aus, um zu bestimmen, ob der Zustand ein Endstatus ist. Ist dies der Fall, endet der Workflow. Andernfalls springt die Steuerung zurück zum Start der <xref:System.Activities.Statements.Pick>-Aktivität, wo der Workflow auf weitere Stoppuhrereignisse wartet.|  
|StopWatchClient|Dies ist eine einfache sequenzielle Workflowkonsolenanwendung, die verschiedene Stoppuhrereignisse mit einfachen Kombinationen der Send- und Receive-Aktivitäten sendet.|  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "StateMachineWithPick.sln".  
  
2.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
3.  Starten Sie den StopWatchService.exe aus [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] als Administrator aus, wenn Sie mit der rechten Maustaste auf die .exe-Datei und Auswählen von **als Administrator ausführen**.  
  
    1.  Navigieren Sie zum Ordner "StateMachineWithPick\CS\StopWatchService\bin\Debug".  
  
    2.  Mit der rechten Maustaste der StopWatchService.exe-Datei, und wählen Sie **als Administrator ausführen**.  
  
4.  Starten Sie die StopWatchClient-Clientanwendung über [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    1.  In **Projektmappen-Explorer**, wählen die **StopWatchClient** Projekt, und mit der rechten Maustaste **als Startprojekt festlegen**.  
  
    2.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.  
  
5.  Wechseln Sie zum Konsolenfenster für "StopWatchService.exe" zurück, um die Zustandsübergänge anzuzeigen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`