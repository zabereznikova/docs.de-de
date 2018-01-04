---
title: Host Lock Renewal Period
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f8ba94fc-27e0-4d8e-8f85-50a6d2a3cd43
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b7447d11e93cf33e69bc52d2cdec239c1be55bcd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="host-lock-renewal-period"></a>Host Lock Renewal Period
Die **Host Lock Renewal Period** -Eigenschaft des SQL-Workflowinstanzspeichers können Sie den Zeitraum angeben, anhand derer der Host seine Sperre für eine Workflowinstanz erneuert. Die Sperre bleibt für den Host Lock Renewal Period-Zeitraum und 30 Sekunden danach gültig. Falls der Host die Sperre innerhalb dieses Zeitraums nicht erneuert (anders ausgedrückt: den Lease verlängert), läuft die Sperre ab, und der Persistenzanbieter entsperrt die Instanz. Der Wert für diese Eigenschaft ist der Typ "TimeSpan" im Format "hh". Der zulässige Mindestwert beträgt "00: 00:01" (1 Sekunde). Der Standardwert dieser Eigenschaft ist "00: 00:30" (30 Sekunden).  
  
 Diese Eigenschaft ist in Szenarien wichtig, in denen auf einem Workflowdiensthost ein Fehler auftritt, bevor dieser eine Workflowdienstinstanz entsperren kann, die in seinem Besitz ist. In diesem Szenario wird die Sperre der Workflowdienstinstanz in der Persistenzdatenbank vom Persistenzanbieter entfernt, nachdem die Sperre abgelaufen ist. Dann kann ein anderer Workflowdiensthost, der auf dem gleichen Computer oder einem anderen Computer in einer Serverfarm ausgeführt wird, die Sperre abrufen und die Workflowdienstinstanz in den Arbeitsspeicher laden, um die Ausführung ab dem letzten beibehaltenen Zustand fortzusetzen.  
  
 Wenn Sie für diese Eigenschaft einen höheren Wert festlegen, werden die Workflowdienstinstanzen länger in der Persistenzdatenbank gesperrt, sodass sich die Wiederherstellung am letzten Persistenzpunkt verzögert. Wenn Sie für diese Eigenschaft ein kurzes Intervall festlegen, übernimmt die neue Instanz des Workflowdiensthosts die fehlerhafte Workflowdienstinstanz schnell, verursacht für den Workflowdiensthost und die SQL Server-Datenbank jedoch einen Anstieg der Auslastung.  
  
 Der SQL-Workflowinstanzspeicher führt eine interne Aufgabe aus, die in regelmäßigen Abständen aktiviert wird und Instanzen mit abgelaufenen Sperren ermittelt. Falls dabei Instanzen mit abgelaufenen Sperren gefunden werden, werden die Instanzen in die RunnableInstances-Tabelle eingefügt, sodass ein Workflowhost diese Instanzen übernehmen und ausführen kann.
