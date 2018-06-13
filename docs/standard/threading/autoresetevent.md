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
ms.openlocfilehash: a4ab06993eed4b39746875a6ef3ebfad5edbd2e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33581702"
---
# <a name="autoresetevent"></a>AutoResetEvent
Die <xref:System.Threading.AutoResetEvent>-Klasse stellt ein lokales Wait-Handleereignis dar, das, sofern es den Zustand „signalisiert“ aufweist, automatisch zurückgesetzt wird, nachdem ein einzelner wartender Thread freigegeben wurde. Diese Klasse stellt einen Sonderfall ihrer Basisklasse <xref:System.Threading.EventWaitHandle> dar. Informationen zur Verwendung und zu den Features von Ereignissen für automatisches Zurücksetzen finden Sie in der Dokumentation zu [EventWaitHandle](../../../docs/standard/threading/eventwaithandle.md).  
  
 Ein <xref:System.Threading.AutoResetEvent>-Objekt wird nach der Freigabe eines einzelnen wartenden Threads vom System automatisch auf den Zustand „nicht signalisiert“ zurückgesetzt. Wenn sich keine Threads in Warteposition befinden, verbleibt das Ereignisobjekt im signalisierten Zustand. <xref:System.Threading.AutoResetEvent> entspricht einem Win32-`CreateEvent`-Aufruf, wobei `false` für das `bManualReset`-Argument angegeben wird.  
  
 Ein Beispiel, in dem <xref:System.Threading.AutoResetEvent> verwendet wird, finden Sie unter [Monitor](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.ManualResetEvent>  
 <xref:System.Threading.Monitor>  
 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Wait-Handles](http://msdn.microsoft.com/library/48d10b6f-5fd7-407c-86ab-0179aef72489)
