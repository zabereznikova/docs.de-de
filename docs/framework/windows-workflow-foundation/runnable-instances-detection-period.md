---
title: Runnable Instances Detection Period
ms.date: 03/30/2017
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
ms.openlocfilehash: aefde2726bb2ccc15f9e68009e5e141602b13b10
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245769"
---
# <a name="runnable-instances-detection-period"></a>Runnable Instances Detection Period

Der SQL-Workflowinstanzspeicher führt eine interne Aufgabe aus, die in regelmäßigen Abständen aktiviert wird und ausführbare oder aktivierbare Instanzen in der Persistenzdatenbank ermittelt. Die Eigenschaft Ausführungs Zeitraum für Ausführ **Bare Instanzen** des SQL-workflowinstanzspeichers gibt den Zeitraum an, nach dem der SQL-workflowinstanzspeicher eine Erkennungs Aufgabe ausführt, um ausführbare oder aktivierbare Workflow Instanzen in der Persistenzdatenbank nach dem vorherigen Erkennungs Durchlauf zu erkennen.  
  
 Das Festlegen eines kürzeren Intervalls für diese Eigenschaft verringert den Zeitraum zwischen dem Ablauf eines Timers, der einer Workflowinstanz zugeordnet ist, und dem Signalisieren des Ereignisses sowie dem nachfolgendem Laden der Instanz. Dadurch wird jedoch gleichzeitig die Auslastung eines Hosts erhöht und empfiehlt sich daher meist nicht in Szenarien in denen wenige Fehler auf Seiten von permanenten Timern und/oder dem Host auftreten. Der Eigenschaftstyp ist TimeSpan, der Wert der Eigenschaft folgt dem Format: hh:mm:ss. Der Mindestwert für diese Eigenschaft ist 00:00:01. Der Standardwert für die Eigenschaft ist 00:00:05.  
  
 Weitere Informationen zum erkennen und Aktivieren von ausführbaren und aktivierbaren Workflow Instanzen finden Sie unter [instanzaktivierung](instance-activation.md).
