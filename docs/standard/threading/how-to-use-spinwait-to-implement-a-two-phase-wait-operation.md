---
title: 'Gewusst wie: Implementieren eines Wartevorgangs mit zwei Phasen mit SpinWait'
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
helpviewer_keywords: SpinWait, how to synchronize two-phase wait
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2717ba2d63e4ecf40638c369b66f2c696e396a5e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-spinwait-to-implement-a-two-phase-wait-operation"></a>Gewusst wie: Implementieren eines Wartevorgangs mit zwei Phasen mit SpinWait
Das folgende Beispiel zeigt, wie Sie eine <xref:System.Threading.SpinWait?displayProperty=nameWithType> Objekt implementiert einen zweiphasigen Wartevorgang. In der ersten Phase werden die Synchronisierungsobjekt eine `Latch`, für einige Zyklen Spinvorgänge, während er überprüft, ob die Sperre verfügbar geworden ist. In der zweiten Phase, wenn die Sperre verfügbar ist, wird die `Wait` Methodenrückgabe ohne Verwendung der <xref:System.Threading.ManualResetEvent?displayProperty=nameWithType> warten; ausführen, andernfalls `Wait` den Wartevorgang ausführt.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt eine sehr grundlegende Implementierung einer Latch Synchronisierung primitive. Sie können diese Datenstruktur verwenden, wenn die Wartezeiten voraussichtlich sehr kurz sind. In diesem Beispiel wird nur zu Demonstrationszwecken. Wenn Sie in Ihrem Programm Latch-Funktionalität benötigen, erwägen Sie <xref:System.Threading.ManualResetEventSlim?displayProperty=nameWithType>.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 Der Latch verwendet die <xref:System.Threading.SpinWait> Objekt nur bis zum nächsten Aufruf von festliegen installiertem `SpinOnce` bewirkt, dass die <xref:System.Threading.SpinWait> die Zeitscheibe des Threads bereitstellt. An diesem Punkt wird der Latch bewirkt, dass einen eigene Kontextwechsel durch Aufrufen von <xref:System.Threading.WaitHandle.WaitOne%2A> auf die <xref:System.Threading.ManualResetEvent> und im weiteren Verlauf des Timeoutwerts übergeben.  
  
 Die Protokollausgabe wird gezeigt, wie oft der Latch Leistung zu erhöhen, indem Sie ohne die Sperre konnte die <xref:System.Threading.ManualResetEvent>.  
  
## <a name="see-also"></a>Siehe auch  
 [SpinWait](../../../docs/standard/threading/spinwait.md)  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)
