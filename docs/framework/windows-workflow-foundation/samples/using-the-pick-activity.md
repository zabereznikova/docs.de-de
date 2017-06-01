---
title: "Verwenden der Pick-Aktivit&#228;t | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b89be812-a247-4025-b0e3-ffb20db027a6
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Verwenden der Pick-Aktivit&#228;t
In diesem Beispiel wird veranschaulicht, wie die <xref:System.Activities.Statements.Pick>\-Aktivität verwendet wird.  
  
 Die <xref:System.Activities.Statements.Pick>\-Aktivität stellt eine ereignisbasierte Modellierung bereit.Sie weist ein ähnliches Verhalten wie die `switch`\-Anweisung in C\# auf, die nur eine der Verzweigungen in der `switch`\-Anweisung ausführt.Im Gegensatz zur `switch`\-Anweisung, in der eine Verzweigung basierend auf einem Wert ausgeführt wird, führt die <xref:System.Activities.Statements.Pick>\-Aktivität eine Verzweigung basierend darauf aus, wie eine Aktivität abgeschlossen wird.  
  
 In diesem Beispiel wird ein Benutzer aufgefordert, seinen Namen in der Konsole innerhalb eines bestimmten Zeitraums einzugeben.Die <xref:System.Activities.Statements.Pick>\-Aktivität im Beispiel verfügt über zwei Verzweigungen, die basierend darauf ausgeführt werden, ob der Benutzer seinen Namen innerhalb von 5 Sekunden eingibt oder nicht.Wenn der Benutzer seinen Namen innerhalb von 5 Sekunden eingibt, wird die erste Verzweigung ausgeführt, die eine benutzerdefinierte `ReadLine`\-Aktivität enthält; andernfalls wird die andere Verzweigung ausgeführt, die eine <xref:System.Activities.Statements.Delay>\-Aktivität enthält.Sobald der Name eines Benutzers in der Konsole eingegeben wird, wird der Name des Benutzers in der Konsole gedruckt.Wenn eine Eingabe nicht innerhalb von 5 Sekunden erfolgt, tritt ein Timeout für den Vorgang auf.  
  
## Veranschaulicht  
 <xref:System.Activities.Statements.Pick>\-Aktivität.  
  
## Diskussion  
 Das Beispiel umfasst einen Designerworkflow und einen codierten Workflow.  
  
 Designerworkflow  
 Die Designerversion des Beispiels veranschaulicht, wie ein Workflow im Designer erstellt wird.Die folgenden Dateien sind enthalten:  
  
-   Program.cs: schließt die `Main`\-Funktion ein, die den Beispielworkflow ausführt.  
  
-   ReadString.cs: eine benutzerdefinierte Aktivität, die Eingaben aus der Konsole liest.  
  
-   Sequence1.xaml: ein Workflow, der mit dem Designer erstellt wurde, der Pick verwendet.  
  
 Codierter Workflow  
 Die codierte Version des Beispiels veranschaulicht, wie ein Workflow im Designer erstellt wird.Die folgenden Dateien sind enthalten:  
  
-   Program.cs: schließt die `Main`\-Funktion ein, die den Beispielworkflow ausführt.  
  
-   ReadString.cs: eine benutzerdefinierte Aktivität, die Eingaben aus der Konsole liest.  
  
#### So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie mit [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei Pick.sln.  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Überprüfen Sie das folgende \(standardmäßige\) Verzeichnis, bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Pick`  
  
## Siehe auch