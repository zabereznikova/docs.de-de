---
title: Timer
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], timers
- timers, about timers
ms.assetid: 7091500d-be18-499b-a942-95366ce185e5
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 80b4cee03e934d3aec98ca323aac43f934c56455
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="timers"></a>Timer
Timer sind kompakte Objekte, mit denen angegeben werden kann, dass ein Delegat zu einem bestimmten Zeitpunkt aufgerufen werden soll. Der Wartevorgang wird von einem Thread im Threadpool ausgeführt.  
  
 Die Verwendung der <xref:System.Threading.Timer?displayProperty=nameWithType>-Klasse ist einfach. Sie erstellen einen **Timer**, der einen <xref:System.Threading.TimerCallback>-Delegaten an die Rückrufmethode übergibt, ein Objekt, das den an den Rückruf zu übergebenden Zustand darstellt, einen Zeitpunkt für den ersten Aufruf und eine Zeitspanne, die das Intervall zwischen den Aufrufen des Rückrufs darstellt. Um einen anstehenden Timer zu löschen, rufen Sie die **Timer.Dispose**-Funktion auf.  
  
> [!NOTE]
>  Es gibt zwei weitere Timerklassen. Die <xref:System.Windows.Forms.Timer?displayProperty=nameWithType>-Klasse ist ein Steuerelement, dass mit visuellen Designern arbeitet und für die Verwendung im Benutzeroberflächenkontext vorgesehen ist. Es löst Ereignisse für den Benutzeroberflächenthread aus. Die <xref:System.Timers.Timer?displayProperty=nameWithType>-Klasse ist von <xref:System.ComponentModel.Component> abgeleitet und kann daher mit visuellen Designern verwendet werden. Sie löst ebenfalls Ereignisse aus, jedoch für einen <xref:System.Threading.ThreadPool>-Thread. Die <xref:System.Threading.Timer?displayProperty=nameWithType>-Klasse nimmt Rückrufe für einen <xref:System.Threading.ThreadPool>-Thread vor und verwendet das Ereignismodell nicht. Im Gegensatz zu anderen Zeitgebern stellt sie der Rückrufmethode auch ein Zustandsobjekt bereit. Dies ist eine sehr einfache Klasse.  
  
 Im folgenden Codebeispiel wird ein Timer gestartet, der nach einer Sekunde (1.000 Millisekunden) startet und jede Sekunde hochzählt, bis die **Enter**-Taste gedrückt wird. Bei der Variablen mit dem Verweis auf den Timer handelt es sich um ein Feld auf Klassenebene, um zu verhindern, dass der Timer während der Ausführung von der Garbage Collection erfasst wird. Weitere Informationen über die aggressive Garbage Collection finden Sie unter <xref:System.GC.KeepAlive%2A>.  
  
 [!code-cpp[System.Threading.Timer#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.Timer/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.Timer#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.Timer/CS/source2.cs#2)]
 [!code-vb[System.Threading.Timer#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.Timer/VB/source2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Timer>  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)
