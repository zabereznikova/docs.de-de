---
title: Optionen zum Hosten von Workflows
ms.date: 03/30/2017
ms.assetid: 37bcd668-9c5c-4e7c-81da-a1f1b3a16514
ms.openlocfilehash: 8ddb83f068eab8480bacc8b80bc5d44b7755fa59
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96293779"
---
# <a name="workflow-hosting-options"></a>Optionen zum Hosten von Workflows

In den meisten Windows Workflow Foundation WF-Beispielen (WF) werden Workflows verwendet, die in einer Konsolenanwendung gehostet werden. Dies ist jedoch kein realistisches Szenario für Workflows in der Praxis. Workflows in tatsächlichen Geschäftsanwendungen werden in persistenten Prozessen gehostet. dabei handelt es sich entweder um einen vom Entwickler erstellten Windows-Dienst oder um eine Serveranwendung wie IIS 7,0 oder AppFabric. Zwischen diesen Vorgehensweisen bestehen die folgenden Unterschiede.

## <a name="hosting-workflows-in-iis-with-windows-appfabric"></a>Hosten von Workflows in IIS mit Windows AppFabric

Das Verwenden von IIS mit AppFabric ist die bevorzugte Hostmethode für Workflows. Die Hostanwendung für Workflows mit AppFabric ist Windows Activation Service (WAS). Durch diesen Dienst wird nur die Abhängigkeit von "HTTP over IIS" entfernt.

## <a name="hosting-workflows-in-iis-alone"></a>Hosten von Workflows nur in IIS

Die Verwendung von IIS 7,0 allein ist nicht empfehlenswert, da in AppFabric Verwaltungs-und Überwachungstools verfügbar sind, die die Wartung von laufenden Anwendungen vereinfachen. Workflows sollten nur in IIS 7,0 gehostet werden, wenn Infrastrukturprobleme beim Umstieg auf AppFabric bestehen.

> [!WARNING]
> IIS 7,0 verwendet Anwendungs Pools in regelmäßigen Abständen aus verschiedenen Gründen wieder. Wenn ein Anwendungspool wiederverwendet wird, akzeptiert IIS keine an den alten Pool gerichteten Nachrichten und instanziiert einen neuen Anwendungspool, um neue Anforderungen zu akzeptieren. Wenn ein Workflow nach dem Senden einer Antwort weiterhin funktioniert, ist IIS 7,0 nicht in der Arbeit, die ausgeführt wird, und kann den hostinganwendungspool wieder verwenden. Wenn dies der Fall ist, wird der Workflow abgebrochen, und Überwachungsdienste zeichnen eine [1004-workflowinstanceabgeb Rochen-](1004-workflowinstanceaborted.md) Nachricht mit einem leeren Grund Feld auf.
>
> Wenn Persistenz verwendet wird, müssen die seit dem letzten Persistenzpunkt abgebrochenen Instanzen explizit neu gestartet werden.
>
> Bei Verwendung von AppFabric setzt der Workflowverwaltungsdienst die Ausführung des Workflows schließlich ab dem letzten erfolgreichen Persistenzpunkt fort, wenn Persistenz verwendet wird. Wenn keine Persistenz verwendet wird und der Workflow Vorgänge außerhalb eines Anforderungs-/Wartemusters ausführt, gehen die Daten beim Workflowabbruch verloren.

## <a name="hosting-a-workflow-in-a-custom-windows-service"></a>Hosten eines Workflows in einem benutzerdefinierten Windows-Dienst

Wenn ein benutzerdefinierter Workflowdienst zum Hosten des Workflows erstellt wird, muss der Entwickler viele Funktionen, die von AppFabric standardmäßig bereitgestellt werden, duplizieren. Gleichzeitig erhöht dies jedoch auch die Flexibilität bei benutzerdefinierten Funktionen. Diese Möglichkeit sollte nur in Betracht gezogen werden, wenn AppFabric nicht verwendet werden kann.
