---
title: Host Lock Renewal Period
ms.date: 03/30/2017
ms.assetid: f8ba94fc-27e0-4d8e-8f85-50a6d2a3cd43
ms.openlocfilehash: 82073377353be6d4f8a7d0a343c31f2b49a2873f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96268195"
---
# <a name="host-lock-renewal-period"></a>Host Lock Renewal Period

Mit der Eigenschaft **Host Sperr Erneuerungs Zeitraum** des SQL-workflowinstanzspeichers können Sie den Zeitraum angeben, in dem der Host die Sperre für eine Workflow Instanz erneuert. Die Sperre bleibt für den Host Lock Renewal Period-Zeitraum und 30 Sekunden danach gültig. Falls der Host die Sperre innerhalb dieses Zeitraums nicht erneuert (anders ausgedrückt: den Lease verlängert), läuft die Sperre ab, und der Persistenzanbieter entsperrt die Instanz. Der Wert für diese Eigenschaft ist vom Typ TimeSpan im Format "hh: mm: SS". Der zulässige Minimalwert ist "00:00:01" (1 Sekunde). Der Standardwert dieser Eigenschaft ist "00:00:30" (30 Sekunden).  
  
 Diese Eigenschaft ist in Szenarien wichtig, in denen auf einem Workflowdiensthost ein Fehler auftritt, bevor dieser eine Workflowdienstinstanz entsperren kann, die in seinem Besitz ist. In diesem Szenario wird die Sperre der Workflowdienstinstanz in der Persistenzdatenbank vom Persistenzanbieter entfernt, nachdem die Sperre abgelaufen ist. Dann kann ein anderer Workflowdiensthost, der auf dem gleichen Computer oder einem anderen Computer in einer Serverfarm ausgeführt wird, die Sperre abrufen und die Workflowdienstinstanz in den Arbeitsspeicher laden, um die Ausführung ab dem letzten beibehaltenen Zustand fortzusetzen.  
  
 Wenn Sie für diese Eigenschaft einen höheren Wert festlegen, werden die Workflowdienstinstanzen länger in der Persistenzdatenbank gesperrt, sodass sich die Wiederherstellung am letzten Persistenzpunkt verzögert. Wenn Sie für diese Eigenschaft ein kurzes Intervall festlegen, übernimmt die neue Instanz des Workflowdiensthosts die fehlerhafte Workflowdienstinstanz schnell, verursacht für den Workflowdiensthost und die SQL Server-Datenbank jedoch einen Anstieg der Auslastung.  
  
 Der SQL-Workflowinstanzspeicher führt eine interne Aufgabe aus, die in regelmäßigen Abständen aktiviert wird und Instanzen mit abgelaufenen Sperren ermittelt. Falls dabei Instanzen mit abgelaufenen Sperren gefunden werden, werden die Instanzen in die RunnableInstances-Tabelle eingefügt, sodass ein Workflowhost diese Instanzen übernehmen und ausführen kann.
