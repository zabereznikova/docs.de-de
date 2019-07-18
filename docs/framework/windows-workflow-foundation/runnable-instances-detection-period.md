---
title: Runnable Instances Detection Period
ms.date: 03/30/2017
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
ms.openlocfilehash: 9652dd811f64e5324219b8aa0700ab8219edeeb0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937955"
---
# <a name="runnable-instances-detection-period"></a>Runnable Instances Detection Period
Der SQL-Workflowinstanzspeicher führt eine interne Aufgabe aus, die in regelmäßigen Abständen aktiviert wird und ausführbare oder aktivierbare Instanzen in der Persistenzdatenbank ermittelt. Die **Runnable Instances Detection Period** Eigenschaft von der SQL-Workflow-Instanz Store gibt den Zeitraum, nach dem die SQL-Workflow-Instanz Store, eine erkennungsaufgabe zum Erkennen von einem Workflow ausführbare oder aktivierbare ausführt, die Instanzen in der Persistenzdatenbank nach dem vorhergehenden ermittlungslauf.  
  
 Das Festlegen eines kürzeren Intervalls für diese Eigenschaft verringert den Zeitraum zwischen dem Ablauf eines Timers, der einer Workflowinstanz zugeordnet ist, und dem Signalisieren des Ereignisses sowie dem nachfolgendem Laden der Instanz. Dadurch wird jedoch gleichzeitig die Auslastung eines Hosts erhöht und empfiehlt sich daher meist nicht in Szenarien in denen wenige Fehler auf Seiten von permanenten Timern und/oder dem Host auftreten. Der Eigenschaftstyp ist TimeSpan, der Wert der Eigenschaft folgt dem Format: hh:mm:ss. Der Mindestwert für diese Eigenschaft ist 00:00:01. Der Standardwert für die Eigenschaft ist 00:00:05.  
  
 Weitere Informationen finden können, erkennen und Aktivieren von ausführbaren und aktivierbaren Workflowinstanzen zu [Instanzaktivierung](instance-activation.md).
