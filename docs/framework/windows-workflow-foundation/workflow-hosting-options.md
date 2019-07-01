---
title: Optionen zum Hosten von Workflows
ms.date: 03/30/2017
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
ms.openlocfilehash: b0cd9748c28cd6206e1fedffc5772b2849462dba
ms.sourcegitcommit: 2d42b7ae4252cfe1232777f501ea9ac97df31b63
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2019
ms.locfileid: "67487363"
---
# <a name="workflow-hosting-options"></a>Optionen zum Hosten von Workflows
Die meisten Windows Workflow Foundation (WF)-Beispiele verwenden die Workflows, die in einer Konsolenanwendung gehostet werden, aber dies ist ein realistisches Szenario für realer Workflows nicht. Workflows in realen Geschäftsanwendungen werden in persistenten Prozessen – entweder ein Windows-Dienst erstellt vom Entwickler oder in einer Serveranwendung, z. B. IIS 7.0 oder AppFabric gehostet werden. Zwischen diesen Vorgehensweisen bestehen die folgenden Unterschiede.  
  
## <a name="hosting-workflows-in-iis-with-windows-appfabric"></a>Hosten von Workflows in IIS mit Windows AppFabric  
 Das Verwenden von IIS mit AppFabric ist die bevorzugte Hostmethode für Workflows. Die Hostanwendung für Workflows mit AppFabric ist Windows Activation Service (WAS). Durch diesen Dienst wird nur die Abhängigkeit von "HTTP over IIS" entfernt.  
  
## <a name="hosting-workflows-in-iis-alone"></a>Hosten von Workflows nur in IIS  
 Mit IIS 7.0 allein sollte nicht vorliegen, Verwaltungs- und Überwachungstools mit AppFabric verfügbar sind, die die Wartung ausgeführter Anwendungen zu erleichtern. Workflows sollten nur in IIS 7.0 nur, wenn Infrastrukturprobleme dem Wechsel zu AppFabric gehostet werden.  
  
> [!WARNING]
>  IIS 7.0 wird Anwendungspools in regelmäßigen Abständen aus verschiedenen Gründen wiederverwendet. Wenn ein Anwendungspool wiederverwendet wird, akzeptiert IIS keine an den alten Pool gerichteten Nachrichten und instanziiert einen neuen Anwendungspool, um neue Anforderungen zu akzeptieren. Wenn ein Workflow weiter nach dem Senden einer Antwort, IIS 7.0 werden nicht über die Arbeit und möglicherweise der hostanwendungspool wiederverwendet. Wenn dies geschieht, wird der Workflow abgebrochen und Überwachungsdienste zeichnen eine [1004 - WorkflowInstanceAborted](1004-workflowinstanceaborted.md) Nachricht mit einem leeren Feld "Grund".  
>   
>  Wenn Persistenz verwendet wird, müssen die seit dem letzten Persistenzpunkt abgebrochenen Instanzen explizit neu gestartet werden.  
>   
>  Bei Verwendung von AppFabric setzt der Workflowverwaltungsdienst die Ausführung des Workflows schließlich ab dem letzten erfolgreichen Persistenzpunkt fort, wenn Persistenz verwendet wird. Wenn keine Persistenz verwendet wird und der Workflow Vorgänge außerhalb eines Anforderungs-/Wartemusters ausführt, gehen die Daten beim Workflowabbruch verloren.  
  
## <a name="hosting-a-workflow-in-a-custom-windows-service"></a>Hosten eines Workflows in einem benutzerdefinierten Windows-Dienst  
 Wenn ein benutzerdefinierter Workflowdienst zum Hosten des Workflows erstellt wird, muss der Entwickler viele Funktionen, die von AppFabric standardmäßig bereitgestellt werden, duplizieren. Gleichzeitig erhöht dies jedoch auch die Flexibilität bei benutzerdefinierten Funktionen. Diese Möglichkeit sollte nur in Betracht gezogen werden, wenn AppFabric nicht verwendet werden kann.
