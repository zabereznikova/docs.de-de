---
title: Runnable Instances Detection Period
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a78f8404d5e6b9d63c9455d059dcbb9a76f8c18
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="runnable-instances-detection-period"></a>Runnable Instances Detection Period
Der SQL-Workflowinstanzspeicher führt eine interne Aufgabe aus, die in regelmäßigen Abständen aktiviert wird und ausführbare oder aktivierbare Instanzen in der Persistenzdatenbank ermittelt. Die **Runnable Instances Detection Period** Eigenschaft des SQL-Workflowinstanzspeichers gibt den Zeitraum, nach dem der SQL-Workflowinstanzspeicher eine erkennungsaufgabe, um alle ausführbaren oder aktivierbaren Workflow erkennen ausführt, Instanzen in der Persistenzdatenbank nach dem vorhergehenden ermittlungslauf.  
  
 Das Festlegen eines kürzeren Intervalls für diese Eigenschaft verringert den Zeitraum zwischen dem Ablauf eines Timers, der einer Workflowinstanz zugeordnet ist, und dem Signalisieren des Ereignisses sowie dem nachfolgendem Laden der Instanz. Dadurch wird jedoch gleichzeitig die Auslastung eines Hosts erhöht und empfiehlt sich deshalb meist nicht bei Szenarien mit wenig Fehlern auf Seiten von permanenten Zeitgebern und/oder dem Host. Der Eigenschaftstyp ist TimeSpan, der Wert der Eigenschaft folgt dem Format: hh:mm:ss. Der Mindestwert für diese Eigenschaft ist 00:00:01. Der Standardwert für die Eigenschaft ist 00:00:05.  
  
 Weitere Informationen erkennen und Aktivieren von ausführbaren und aktivierbare Workflowinstanzen finden Sie unter [Instanzaktivierung](../../../docs/framework/windows-workflow-foundation/instance-activation.md).
