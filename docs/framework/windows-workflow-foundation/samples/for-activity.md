---
title: "For-Aktivit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 2ea751b4-36f0-48aa-a115-70a2ab89f6d8
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# For-Aktivit&#228;t
Im For\-Beispiel wird veranschaulicht, wie eine benutzerdefinierte Aktivität erstellt wird, die von <xref:System.Activities.NativeActivity> erbt, und wie diese in einem Workflow verwendet wird, um ein Beispiel mit realen Bedingungen auszuführen.Die benutzerdefinierte Aktivität in diesem Beispiel funktioniert wie die `for`\-Anweisung in C\#.T  
  
 Die benutzerdefinierte `For`\-Aktivität weist die Eigenschaften `InitAction`, `IterationAction`, `Condition` und `Body` auf, die jeweils der Initialisierungsanweisung, der iterativen Anweisung, der Fortsetzungsbedingung und der Textanweisung in der standardmäßigen `For`\-Anweisung in C\# entsprechen.  
  
 In der folgenden Tabelle sind die im Beispiel verwendeten Schlüsseldateien beschrieben.  
  
|Datei|Beschreibung|  
|-----------|------------------|  
|For.cs|Klassendefinition für die benutzerdefinierte `For`\-Aktivität, die durch Erweiterung der <xref:System.Activities.NativeActivity>\-Klasse die Funktionalität der `For`\-Anweisung in C\# bereitstellt.|  
|Program.cs|Eine Clientanwendung, die unter Verwendung der benutzerdefinierten `For`\-Aktivität grundlegende iterative Verarbeitungsschritte für eine Auflistung ausführt.|  
  
> [!NOTE]
>  Stellen Sie bei Verwendung der benutzerdefinierten `For`\-Aktivität sicher, dass die `Condition`\-Eigenschaft festgelegt ist. Andernfalls kann eine Endlosschleife auftreten.  
  
## Veranschaulicht  
 Erstellen einer benutzerdefinierten Aktivität, die von <xref:System.Activities.NativeActivity> erbt.  
  
## Diskussion  
 In der folgenden Tabelle werden die Eigenschaften der Aktivität in diesem Beispiel beschrieben.  
  
 InitAction  
 Initialisierungsanweisung  
  
 IterationAction  
 Iterative Anweisung  
  
 Condition  
 Fortsetzungsanweisung  
  
 Body  
 Textanweisung  
  
 Die Aktivität erbt von <xref:System.Activities.NativeActivity>, um mittels einer der `ScheduleActivity`\-Methoden von <xref:System.Activities.NativeActivityContext> Zugriff auf Laufzeitfunktionen zu erhalten, z. B. zur Planung zusätzlicher auszuführender Aktivitäten.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "For.sln".  
  
2.  Erstellen Sie die Projektmappe, indem Sie STRG\+UMSCHALT\+B drücken.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\For`  
  
## Siehe auch