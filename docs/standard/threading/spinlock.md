---
title: SpinLock
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- synchronization primitives, SpinLock
ms.assetid: f9af93bb-7a0d-4ba5-afe8-74f48b6b6958
ms.openlocfilehash: a5202be5e3055702954ad7a1565999ad2496eaea
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291122"
---
# <a name="spinlock"></a>SpinLock
Die <xref:System.Threading.SpinLock>-Struktur ist eine Synchronisierungsprimitive auf niedriger Ebene mit gegenseitigem Ausschluss, die die Schleife durchläuft, während sie darauf wartet, eine Sperre abzurufen. Wenn Wartezeiten auf Mehrkerncomputern kurz und Konflikte minimal sein sollen, bietet <xref:System.Threading.SpinLock> einen Leistungsvorteil gegenüber anderen Arten von Sperren. Sie sollten <xref:System.Threading.SpinLock> jedoch nur verwenden, wenn Sie durch Profilerstellung bestimmen, dass die <xref:System.Threading.Monitor?displayProperty=nameWithType>- oder <xref:System.Threading.Interlocked>-Methode die Leistung des Programms erheblich beeinträchtigen.  
  
 <xref:System.Threading.SpinLock> könnte das Zeitsegment des Threads selbst dann erzeugen, wenn die Sperre noch nicht abgerufen wurde. Dies soll eine Umkehrung der Threadpriorität vermeiden und den Fortschritt des Garbage Collectors aktivieren. Stellen Sie bei Verwendung von <xref:System.Threading.SpinLock> sicher, dass kein Thread die Sperre für mehr als einen sehr kurzen Zeitraum aufrechterhalten kann, und dass kein Thread blockieren kann, während er die Sperre aufrechterhält.  
  
 Da SpinLock ein Werttyp ist, müssen Sie SpinLock explizit als Verweis übergeben, wenn die beiden Kopien auf die gleiche Sperre verweisen sollen.  
  
 Weitere Informationen zum Verwenden dieses Typs finden Sie unter <xref:System.Threading.SpinLock?displayProperty=nameWithType>. Ein Beispiel finden Sie unter [Gewusst wie: Synchronisierung auf niedriger Ebene mit SpinLock](how-to-use-spinlock-for-low-level-synchronization.md).  
  
 <xref:System.Threading.SpinLock> unterstützt einen *Thread*-*Nachverfolgungsmodus*, mit dem Sie während der Entwicklungsphase den Thread nachverfolgen können, der die Sperre zu einem bestimmten Zeitpunkt aufrechterhält. Der Thread-Nachverfolgungsmodus ist sehr nützlich für das Debuggen, aber Sie sollten ihn in der endgültigen Produktversion des Programms deaktivieren, da er die Leistung beeinträchtigen könnte. Weitere Informationen finden Sie unter [Gewusst wie: Aktivieren des Modus zum Nachverfolgen von Threads in SpinLock](how-to-enable-thread-tracking-mode-in-spinlock.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [Threading Objects and Features (Threadingobjekte und -funktionen)](threading-objects-and-features.md)
