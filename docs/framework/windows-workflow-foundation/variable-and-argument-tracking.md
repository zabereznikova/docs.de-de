---
title: "Nachverfolgung von Variablen und Argumenten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f3d9d30-d899-49aa-b7ce-a8d0d32c4ff0
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Nachverfolgung von Variablen und Argumenten
Bei der Nachverfolgung der Workflowausführung kann sich das Extrahieren von Daten oft als nützlich erweisen.Sie stellt zusätzlichen Kontext bereit, wenn nach der Ausführung auf einen Überwachungsdatensatz zugegriffen wird.In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] können Sie alle sichtbaren Variablen oder Argumente innerhalb des Bereichs einer Aktivität in einem Workflow mithilfe der Nachverfolgung extrahieren.Überwachungsprofile vereinfachen das Extrahieren von Daten.  
  
## Variablen und Argumente  
 Variablen und Argumente werden extrahiert, wenn eine Aktivität einen ActivityStateRecord ausgibt.Eine Variable kann nur extrahiert werden, wenn sie innerhalb des Bereichs der Aktivität liegt.Eine Variable, die in einer Aktivität extrahiert werden soll, wird wie folgt angegeben:  
  
-   Wenn eine Variable über den Variablennamen angegeben wird, sucht die Nachverfolgung in der aktuellen Aktivität, die nachverfolgt wird, und in den übergeordneten Aktivitäten nach der Variable.Es wird im aktuellen Aktivitätsbereich und im übergeordneten Bereich nach der Variablen gesucht.  
  
-   Wenn Variablen, die extrahiert werden sollen, mit name\="\*" angegeben werden, werden alle Variablen innerhalb der aktuellen Aktivität extrahiert, die nachverfolgt wird.In diesem Fall werden keine Variablen extrahiert, die innerhalb des Bereichs liegen, jedoch in übergeordneten Aktivitäten definiert sind.  
  
 Beim Extrahieren von Argumenten sind die extrahierten Argumente vom Zustand der Aktivität abhängig.Wenn der Zustand einer Aktivität Executing ist, können nur `InArguments` extrahiert werden.Bei jedem anderen Aktivitätszustand \(Closed, Faulted, Canceled\) können alle Argumente, InArguments und OutArguments, extrahiert werden.  
  
 Das folgende Beispiel zeigt eine Abfrage des Aktivitätszustands, mit der Variablen und Argumente extrahiert werden, wenn der `Closed`\-Überwachungsdatensatz der Aktivität ausgegeben wird.Variablen und Argumente können nur mit einem <xref:System.Activities.Tracking.ActivityStateRecord>\-Objekt extrahiert und so innerhalb eines Überwachungsprofils mit <xref:System.Activities.Tracking.ActivityStateQuery> abonniert werden.  
  
```  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <variables>  
    <variable name="FromAddress"/>  
  </variables>  
  <arguments>  
    <argument name="Result"/>  
  </arguments>  
</activityStateQuery>  
  
```  
  
## Schützen von Informationen in Variablen und Argumenten  
 Eine nachverfolgte Variable oder ein nachverfolgtes Argument wird standardmäßig von der WF\-Laufzeit sichtbar gemacht.Workflowentwickler können mit folgenden Schritten einen Schutz vor Zugriffen erreichen:  
  
1.  Verschlüsseln Sie den Wert einer Variablen.  
  
2.  Steuern Sie die Erstellung eines Überwachungsprofils, um das Extrahieren von Variablen oder Argumenten zu verhindern.  
  
3.  Stellen Sie bei benutzerdefinierten Überwachungsteilnehmern sicher, dass im WF\-Code keine vertraulichen Informationen angegeben sind, die in Variablen oder Argumenten gespeichert werden.  
  
## Siehe auch  
 [Überwachung mit Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkId=201273)   
 [Überwachen von Anwendungen mit AppFabric](http://go.microsoft.com/fwlink/?LinkId=201275)