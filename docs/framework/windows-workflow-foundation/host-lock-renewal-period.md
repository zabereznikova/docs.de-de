---
title: Host Lock Renewal Period
ms.date: 03/30/2017
ms.assetid: f8ba94fc-27e0-4d8e-8f85-50a6d2a3cd43
ms.openlocfilehash: 91d83259c766120f7e3ffc9e49f1cf1b18c32a18
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945612"
---
# <a name="host-lock-renewal-period"></a>Host Lock Renewal Period
Die **Host Lock Renewal Period** Eigenschaft von der SQL-Workflow-Instanz Store können Sie den Zeitraum angeben, in dem der Host seine Sperre für eine Workflowinstanz erneuert. Die Sperre bleibt für den Host Lock Renewal Period-Zeitraum und 30 Sekunden danach gültig. Falls der Host die Sperre innerhalb dieses Zeitraums nicht erneuert (anders ausgedrückt: den Lease verlängert), läuft die Sperre ab, und der Persistenzanbieter entsperrt die Instanz. Der Wert für diese Eigenschaft ist vom Typ "TimeSpan" im Format "hh". Der zulässige Mindestwert beträgt "00: 00:01" (1 Sekunde). Der Standardwert dieser Eigenschaft ist "00: 00:30" (30 Sekunden).  
  
 Diese Eigenschaft ist in Szenarien wichtig, in denen auf einem Workflowdiensthost ein Fehler auftritt, bevor dieser eine Workflowdienstinstanz entsperren kann, die in seinem Besitz ist. In diesem Szenario wird die Sperre der Workflowdienstinstanz in der Persistenzdatenbank vom Persistenzanbieter entfernt, nachdem die Sperre abgelaufen ist. Dann kann ein anderer Workflowdiensthost, der auf dem gleichen Computer oder einem anderen Computer in einer Serverfarm ausgeführt wird, die Sperre abrufen und die Workflowdienstinstanz in den Arbeitsspeicher laden, um die Ausführung ab dem letzten beibehaltenen Zustand fortzusetzen.  
  
 Wenn Sie für diese Eigenschaft einen höheren Wert festlegen, werden die Workflowdienstinstanzen länger in der Persistenzdatenbank gesperrt, sodass sich die Wiederherstellung am letzten Persistenzpunkt verzögert. Wenn Sie für diese Eigenschaft ein kurzes Intervall festlegen, übernimmt die neue Instanz des Workflowdiensthosts die fehlerhafte Workflowdienstinstanz schnell, verursacht für den Workflowdiensthost und die SQL Server-Datenbank jedoch einen Anstieg der Auslastung.  
  
 Der SQL-Workflowinstanzspeicher führt eine interne Aufgabe aus, die in regelmäßigen Abständen aktiviert wird und Instanzen mit abgelaufenen Sperren ermittelt. Falls dabei Instanzen mit abgelaufenen Sperren gefunden werden, werden die Instanzen in die RunnableInstances-Tabelle eingefügt, sodass ein Workflowhost diese Instanzen übernehmen und ausführen kann.
