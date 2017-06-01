---
title: "Verwenden von CancellationScope | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 39c5c338-b316-43d6-b7fe-a543281dd1ec
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Verwenden von CancellationScope
Mit diesem Beispiel wird veranschaulicht, wie die <xref:System.Activities.Statements.CancellationScope>\-Aktivität verwendet wird, um die Arbeit in einer Anwendung abzubrechen.  
  
 Viele Komponenten und Dienste der mittleren Ebene nutzen das bekannte Programmiermodell der Transaktionen zur Durchführung von Abbruchvorgängen.  Es gibt jedoch viele Situationen, in denen Transaktionen nicht verwendet werden können und die Arbeit manuell abgebrochen werden muss.  Ein Abbruch ist schwieriger als das Verwenden von Transaktionen, da die abzubrechende Arbeit zunächst nachverfolgt werden muss.  [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)] unterstützt Sie dabei durch Bereitstellen einer <xref:System.Activities.Statements.CancellationScope>\-Aktivität.  
  
 Der Abbruch kann innerhalb einer Aktivität oder über das übergeordnete Element einer Aktivität ausgelöst werden.  Untergeordnete Aktivitäten werden von der zugehörigen übergeordneten Aktivität \(z. B. <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Parallel>, <xref:System.Activities.Statements.Flowchart> oder eine benutzerdefinierte zusammengesetzte Aktivität\) geplant.  Die übergeordnete Aktivität kann untergeordnete Aktivitäten aus jedem beliebigen Grund abbrechen.  Beispiel: Eine <xref:System.Activities.Statements.Parallel>\-Aktivität mit drei untergeordneten Aktivitäten \(Verzweigungen\) bricht die verbleibenden Verzweigungen ab, wenn eine Verzweigung abgeschlossen wird und die Auswertung des <xref:System.Activities.Statements.Parallel.CompletionCondition%2A>\-Ausdrucks `true` ergibt.  Der Workflow kann auch extern von der Hostanwendung durch Aufrufen von <xref:System.Activities.WorkflowApplication.Cancel%2A> abgebrochen werden.  
  
 Zur Verwendung der <xref:System.Activities.Statements.CancellationScope>\-Aktivität fügen Sie die abzubrechende Arbeit in eine <xref:System.Activities.Statements.CancellationScope.Body%2A>\-Eigenschaft und die nach dem Abbruchvorgang auszuführende Arbeit in eine <xref:System.Activities.Statements.CancellationScope.CancellationHandler%2A>\-Eigenschaft ein.  
  
 In diesem Beispiel wird das Abbrechen einer Aktivität innerhalb der Aktivität selbst veranschaulicht.  
  
 Das im Beispiel zur Veranschaulichung der <xref:System.Activities.Statements.CancellationScope>\-Aktivität verwendete Szenario ist ein Kunde, der so schnell wie möglich ein Ticket nach Miami kaufen möchte.  Es gibt zwei Reiseagenturen, die das Geschäft abschließen möchten.  Für diese Geschäftslogik werden im Beispiel zwei <xref:System.Activities.Statements.CancellationScope>\-Elemente innerhalb einer <xref:System.Activities.Statements.Parallel>\-Aktivität verwendet.  Die <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> der <xref:System.Activities.Statements.Parallel>\-Aktivität wird auf `true` festgelegt. Da die <xref:System.Activities.Statements.Parallel.CompletionCondition%2A> nach Abschluss jeder der Verzweigungen geprüft wird, wird nach Abschluss einer Verzweigung die verbleibende Verzweigung abgebrochen.  Die Clientanwendung fordert beide Agenturen auf, das Ticket zu kaufen. Sobald eine Agentur den Kauf des Tickets bestätigt, bricht die Anwendung den Auftrag bei der anderen Agentur ab.  
  
## So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] die Projektmappendatei "CancelationScopeXAML.sln".  
  
2.  Drücken Sie STRG\+UMSCHALT\+B, um die Projektmappe zu erstellen.  
  
3.  Drücken Sie STRG\+F5, um die Projektmappe auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert.  Suchen Sie nach dem folgenden Verzeichnis \(Standardverzeichnis\), bevor Sie fortfahren.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\- und [!INCLUDE[wf1](../../../../includes/wf1-md.md)]\-Beispiele herunterzuladen.  Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<Installationslaufwerk>:\WF_WCF_Samples\WF\Basic\Built-InActivities\CancellationScope`  
  
## Siehe auch