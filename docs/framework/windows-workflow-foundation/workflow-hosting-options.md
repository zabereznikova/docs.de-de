---
title: Optionen zum Hosten von Workflows
ms.date: 03/30/2017
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
ms.openlocfilehash: 2a03c7b5e15b76eabc714f44624f04d3385720d4
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713318"
---
# <a name="workflow-hosting-options"></a>Optionen zum Hosten von Workflows
Die meisten Windows Workflow Foundation (WF)-Beispiele verwenden die Workflows, die in einer Konsolenanwendung gehostet werden, aber dies ist ein realistisches Szenario für realer Workflows nicht. Workflows in realen Geschäftsanwendungen werden in persistenten Prozessen gehostet – entweder in einem vom Entwickler erstellten Webdienst oder in einer Serveranwendung wie [!INCLUDE[iisver](../../../includes/iisver-md.md)] oder AppFabric. Zwischen diesen Vorgehensweisen bestehen die folgenden Unterschiede.  
  
## <a name="hosting-workflows-in-iis-with-windows-appfabric"></a>Hosten von Workflows in IIS mit Windows AppFabric  
 Das Verwenden von IIS mit AppFabric ist die bevorzugte Hostmethode für Workflows. Die Hostanwendung für Workflows mit AppFabric ist Windows Activation Service (WAS). Durch diesen Dienst wird nur die Abhängigkeit von "HTTP over IIS" entfernt.  
  
## <a name="hosting-workflows-in-iis-alone"></a>Hosten von Workflows nur in IIS  
 Die alleinige Verwendung von [!INCLUDE[iisver](../../../includes/iisver-md.md)] wird nicht empfohlen, da Verwaltungs- und Überwachungstools mit AppFabric verfügbar sind, die die Wartung ausgeführter Anwendungen erleichtern. Workflows sollten nur alleine in [!INCLUDE[iisver](../../../includes/iisver-md.md)] gehostet werden, wenn der Wechsel zu AppFabric Infrastrukturprobleme mit sich bringen würde.  
  
> [!WARNING]
>  Von [!INCLUDE[iisver](../../../includes/iisver-md.md)] werden Anwendungspools regelmäßig aus verschiedenen Gründen wiederverwendet. Wenn ein Anwendungspool wiederverwendet wird, akzeptiert IIS keine an den alten Pool gerichteten Nachrichten und instanziiert einen neuen Anwendungspool, um neue Anforderungen zu akzeptieren. Wenn ein Workflow nach dem Senden einer Antwort weiter ausgeführt wird, hat [!INCLUDE[iisver](../../../includes/iisver-md.md)] davon keine Kenntnis, und der Hostanwendungspool wird möglicherweise wiederverwendet. Wenn dies geschieht, wird der Workflow abgebrochen und Überwachungsdienste zeichnen eine [1004 - WorkflowInstanceAborted](1004-workflowinstanceaborted.md) Nachricht mit einem leeren Feld "Grund".  
>   
>  Wenn Persistenz verwendet wird, müssen die seit dem letzten Persistenzpunkt abgebrochenen Instanzen explizit neu gestartet werden.  
>   
>  Bei Verwendung von AppFabric setzt der Workflowverwaltungsdienst die Ausführung des Workflows schließlich ab dem letzten erfolgreichen Persistenzpunkt fort, wenn Persistenz verwendet wird. Wenn keine Persistenz verwendet wird und der Workflow Vorgänge außerhalb eines Anforderungs-/Wartemusters ausführt, gehen die Daten beim Workflowabbruch verloren.  
  
## <a name="hosting-a-workflow-in-a-custom-windows-service"></a>Hosten eines Workflows in einem benutzerdefinierten Windows-Dienst  
 Wenn ein benutzerdefinierter Workflowdienst zum Hosten des Workflows erstellt wird, muss der Entwickler viele Funktionen, die von AppFabric standardmäßig bereitgestellt werden, duplizieren. Gleichzeitig erhöht dies jedoch auch die Flexibilität bei benutzerdefinierten Funktionen. Diese Möglichkeit sollte nur in Betracht gezogen werden, wenn AppFabric nicht verwendet werden kann.
