---
title: "IfElse mit Regeln | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# IfElse mit Regeln
Dieses Beispiel veranschaulicht die Verwendung einer Regelbedingung mit einer <xref:System.Workflow.Activities.IfElseActivity>\-Aktivität.  
  
 Das Beispiel übergibt einen `OrderValue`\-Parameter vom Host.Der Wert des Parameters wird in einer Regelbedingung für die erste Verzweigung der <xref:System.Workflow.Activities.IfElseActivity>\-Aktivität verwendet.Wenn der Wert niedriger als 10.000 ist, wird die erste Verzweigung ausgeführt, und die <xref:System.Workflow.Activities.CodeActivity>\-Aktivität in der ersten Verzweigung gibt **Get Manager Approval** in der Konsole aus.Wenn der Wert höher als 10.000 ist, wird die <xref:System.Workflow.Activities.CodeActivity>\-Aktivität in der zweiten Verzweigung ausgeführt, und in der Konsole wird **Get VP Approval** ausgegeben.  
  
### So erstellen Sie das Beispiel  
  
1.  Öffnen Sie die Projektmappe in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Erstellen Sie die Projektmappe, indem Sie STRG\+UMSCHALT\+B drücken.  
  
3.  Führen Sie die Projektmappe ohne Debuggen aus, indem Sie STRG\+F5 drücken.  
  
### So führen Sie das Beispiel aus  
  
-   Führen Sie im Eingabeaufforderungsfenster des SDKs die EXE\-Datei im Ordner "IfElseWithRules\\bin\\debug" aus \(bzw. im Ordner "IfElseWithRules\\bin" für die Visual Basic\-Version des Beispiels\), der sich unter dem Hauptordner des Beispiels befindet.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren:  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## Siehe auch  
 <xref:System.Workflow.Activities.Rules>   
 <xref:System.Workflow.Activities.IfElseActivity>   
 <xref:System.Workflow.Activities.CodeActivity>   
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>