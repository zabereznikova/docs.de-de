---
title: Runnable Instances Detection Period
ms.date: 03/30/2017
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
ms.openlocfilehash: 7b12353c3bd18367618825d22d020391b14ec3f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513236"
---
# <a name="runnable-instances-detection-period"></a>Runnable Instances Detection Period
Der SQL-Workflowinstanzspeicher führt eine interne Aufgabe aus, die in regelmäßigen Abständen aktiviert wird und ausführbare oder aktivierbare Instanzen in der Persistenzdatenbank ermittelt. Die **Runnable Instances Detection Period** Eigenschaft des SQL-Workflowinstanzspeichers gibt den Zeitraum, nach dem der SQL-Workflowinstanzspeicher eine erkennungsaufgabe, um alle ausführbaren oder aktivierbaren Workflow erkennen ausführt, Instanzen in der Persistenzdatenbank nach dem vorhergehenden ermittlungslauf.  
  
 Das Festlegen eines kürzeren Intervalls für diese Eigenschaft verringert den Zeitraum zwischen dem Ablauf eines Timers, der einer Workflowinstanz zugeordnet ist, und dem Signalisieren des Ereignisses sowie dem nachfolgendem Laden der Instanz. Dadurch wird jedoch gleichzeitig die Auslastung eines Hosts erhöht und empfiehlt sich deshalb meist nicht bei Szenarien mit wenig Fehlern auf Seiten von permanenten Zeitgebern und/oder dem Host. Der Eigenschaftstyp ist TimeSpan, der Wert der Eigenschaft folgt dem Format: hh:mm:ss. Der Mindestwert für diese Eigenschaft ist 00:00:01. Der Standardwert für die Eigenschaft ist 00:00:05.  
  
 Weitere Informationen erkennen und Aktivieren von ausführbaren und aktivierbare Workflowinstanzen finden Sie unter [Instanzaktivierung](../../../docs/framework/windows-workflow-foundation/instance-activation.md).
