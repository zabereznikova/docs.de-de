---
title: "Optionen zum Hosten von Workflows | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Optionen zum Hosten von Workflows
Für die meisten [!INCLUDE[wf](../../../includes/wf-md.md)]\-Beispiele werden Workflows verwendet, die in einer Konsolenanwendung gehostet werden. In der Praxis ist dies jedoch kein realistisches Workflowszenario.Workflows in realen Geschäftsanwendungen werden in persistenten Prozessen gehostet – entweder in einem vom Entwickler erstellten Webdienst oder in einer Serveranwendung wie [!INCLUDE[iisver](../../../includes/iisver-md.md)] oder AppFabric.Zwischen diesen Vorgehensweisen bestehen die folgenden Unterschiede.  
  
## Hosten von Workflows in IIS mit Windows AppFabric  
 Das Verwenden von IIS mit AppFabric ist die bevorzugte Hostmethode für Workflows.Die Hostanwendung für Workflows mit AppFabric ist Windows Activation Service \(WAS\). Durch diesen Dienst wird nur die Abhängigkeit von "HTTP over IIS" entfernt.  
  
## Hosten von Workflows nur in IIS  
 Die alleinige Verwendung von [!INCLUDE[iisver](../../../includes/iisver-md.md)] wird nicht empfohlen, da Verwaltungs\- und Überwachungstools mit AppFabric verfügbar sind, die die Wartung ausgeführter Anwendungen erleichtern.Workflows sollten nur alleine in [!INCLUDE[iisver](../../../includes/iisver-md.md)] gehostet werden, wenn der Wechsel zu AppFabric Infrastrukturprobleme mit sich bringen würde.  
  
> [!WARNING]
>  Von [!INCLUDE[iisver](../../../includes/iisver-md.md)] werden Anwendungspools regelmäßig aus verschiedenen Gründen wiederverwendet.Wenn ein Anwendungspool wiederverwendet wird, akzeptiert IIS keine an den alten Pool gerichteten Nachrichten und instanziiert einen neuen Anwendungspool, um neue Anforderungen zu akzeptieren.Wenn ein Workflow nach dem Senden einer Antwort weiter ausgeführt wird, hat [!INCLUDE[iisver](../../../includes/iisver-md.md)] davon keine Kenntnis, und der Hostanwendungspool wird möglicherweise wiederverwendet.In diesem Fall wird der Workflow abgebrochen, und die Überwachungsdienste zeichnen eine [1004 \- WorkflowInstanceAborted](../../../docs/framework/windows-workflow-foundation//1004-workflowinstanceaborted.md)\-Meldung auf, in der kein Grund angegeben ist.  
>   
>  Wenn Persistenz verwendet wird, müssen die seit dem letzten Persistenzpunkt abgebrochenen Instanzen explizit neu gestartet werden.  
>   
>  Bei Verwendung von AppFabric setzt der Workflowverwaltungsdienst die Ausführung des Workflows schließlich ab dem letzten erfolgreichen Persistenzpunkt fort, wenn Persistenz verwendet wird.Wenn keine Persistenz verwendet wird und der Workflow Vorgänge außerhalb eines Anforderungs\-\/Wartemusters ausführt, gehen die Daten beim Workflowabbruch verloren.  
  
## Hosten eines Workflows in einem benutzerdefinierten Windows\-Dienst  
 Wenn ein benutzerdefinierter Workflowdienst zum Hosten des Workflows erstellt wird, muss der Entwickler viele Funktionen, die von AppFabric standardmäßig bereitgestellt werden, duplizieren. Gleichzeitig erhöht dies jedoch auch die Flexibilität bei benutzerdefinierten Funktionen.Diese Möglichkeit sollte nur in Betracht gezogen werden, wenn AppFabric nicht verwendet werden kann.