---
title: Optionen zum Hosten von Workflows
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be885a964ad7e8d63045febfa279b23d0d85ab1f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="workflow-hosting-options"></a>Optionen zum Hosten von Workflows
Für die meisten [!INCLUDE[wf](../../../includes/wf-md.md)]-Beispiele werden Workflows verwendet, die in einer Konsolenanwendung gehostet werden. In der Praxis ist dies jedoch kein realistisches Workflowszenario. Workflows in realen Geschäftsanwendungen werden in persistenten Prozessen gehostet – entweder in einem vom Entwickler erstellten Webdienst oder in einer Serveranwendung wie [!INCLUDE[iisver](../../../includes/iisver-md.md)] oder AppFabric. Zwischen diesen Vorgehensweisen bestehen die folgenden Unterschiede.  
  
## <a name="hosting-workflows-in-iis-with-windows-appfabric"></a>Hosten von Workflows in IIS mit Windows AppFabric  
 Das Verwenden von IIS mit AppFabric ist die bevorzugte Hostmethode für Workflows. Die Hostanwendung für Workflows mit AppFabric ist Windows Activation Service (WAS). Durch diesen Dienst wird nur die Abhängigkeit von "HTTP over IIS" entfernt.  
  
## <a name="hosting-workflows-in-iis-alone"></a>Hosten von Workflows nur in IIS  
 Die alleinige Verwendung von [!INCLUDE[iisver](../../../includes/iisver-md.md)] wird nicht empfohlen, da Verwaltungs- und Überwachungstools mit AppFabric verfügbar sind, die die Wartung ausgeführter Anwendungen erleichtern. Workflows sollten nur alleine in [!INCLUDE[iisver](../../../includes/iisver-md.md)] gehostet werden, wenn der Wechsel zu AppFabric Infrastrukturprobleme mit sich bringen würde.  
  
> [!WARNING]
>  Von [!INCLUDE[iisver](../../../includes/iisver-md.md)] werden Anwendungspools regelmäßig aus verschiedenen Gründen wiederverwendet. Wenn ein Anwendungspool wiederverwendet wird, akzeptiert IIS keine an den alten Pool gerichteten Nachrichten und instanziiert einen neuen Anwendungspool, um neue Anforderungen zu akzeptieren. Wenn ein Workflow nach dem Senden einer Antwort weiter ausgeführt wird, hat [!INCLUDE[iisver](../../../includes/iisver-md.md)] davon keine Kenntnis, und der Hostanwendungspool wird möglicherweise wiederverwendet. Wenn dies geschieht, der Workflow abgebrochen wird und Überwachungsdienste aufzeichnen wird eine [1004 - WorkflowInstanceAborted](../../../docs/framework/windows-workflow-foundation/1004-workflowinstanceaborted.md) Nachricht mit einem leeren Feld "Grund".  
>   
>  Wenn Persistenz verwendet wird, müssen die seit dem letzten Persistenzpunkt abgebrochenen Instanzen explizit neu gestartet werden.  
>   
>  Bei Verwendung von AppFabric setzt der Workflowverwaltungsdienst die Ausführung des Workflows schließlich ab dem letzten erfolgreichen Persistenzpunkt fort, wenn Persistenz verwendet wird. Wenn keine Persistenz verwendet wird und der Workflow Vorgänge außerhalb eines Anforderungs-/Wartemusters ausführt, gehen die Daten beim Workflowabbruch verloren.  
  
## <a name="hosting-a-workflow-in-a-custom-windows-service"></a>Hosten eines Workflows in einem benutzerdefinierten Windows-Dienst  
 Wenn ein benutzerdefinierter Workflowdienst zum Hosten des Workflows erstellt wird, muss der Entwickler viele Funktionen, die von AppFabric standardmäßig bereitgestellt werden, duplizieren. Gleichzeitig erhöht dies jedoch auch die Flexibilität bei benutzerdefinierten Funktionen. Diese Möglichkeit sollte nur in Betracht gezogen werden, wenn AppFabric nicht verwendet werden kann.
