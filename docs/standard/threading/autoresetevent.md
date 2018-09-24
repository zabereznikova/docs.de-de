---
title: AutoResetEvent
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], AutoResetEvent class
- AutoResetEvent class
ms.assetid: 6d39c48d-6b37-4a9b-8631-f2924cfd9c18
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38efbe0ecd88c02752d610de4b1eec8b62eca1f8
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2018
ms.locfileid: "46937545"
---
# <a name="autoresetevent"></a>AutoResetEvent
Die <xref:System.Threading.AutoResetEvent>-Klasse stellt ein lokales Wait-Handleereignis dar, das, sofern es den Zustand „signalisiert“ aufweist, automatisch zurückgesetzt wird, nachdem ein einzelner wartender Thread freigegeben wurde. Diese Klasse stellt einen Sonderfall ihrer Basisklasse <xref:System.Threading.EventWaitHandle> dar. Informationen zur Verwendung und zu den Features von Ereignissen für automatisches Zurücksetzen finden Sie in der Dokumentation zu [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 Ein <xref:System.Threading.AutoResetEvent>-Objekt wird nach der Freigabe eines einzelnen wartenden Threads vom System automatisch auf den Zustand „nicht signalisiert“ zurückgesetzt. Wenn sich keine Threads in Warteposition befinden, verbleibt das Ereignisobjekt im signalisierten Zustand.
  
 Ein Beispiel, in dem <xref:System.Threading.AutoResetEvent> verwendet wird, finden Sie unter <xref:System.Threading.Monitor>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.ManualResetEvent>  
- <xref:System.Threading.Monitor>  
- [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
- [Threading](../../../docs/standard/threading/index.md)  
- [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)  
- [Wait-Handles](https://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
