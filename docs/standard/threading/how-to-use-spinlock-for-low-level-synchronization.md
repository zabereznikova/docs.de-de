---
title: 'Gewusst wie: Synchronisierung auf niedriger Ebene mit SpinLock'
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
helpviewer_keywords: SpinLock, how to use
ms.assetid: a9ed3e4e-4f29-4207-b730-ed0a51ecbc19
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 30ddc7d340b210aaad4a04ea43e89555d2701f20
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-use-spinlock-for-low-level-synchronization"></a>Gewusst wie: Synchronisierung auf niedriger Ebene mit SpinLock
Im folgenden Beispiel wird veranschaulicht, wie eine <xref:System.Threading.SpinLock>.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel der kritische Abschnitt führt eine minimale Menge an Arbeit, wodurch einen guten Kandidat für eine <xref:System.Threading.SpinLock>. Erhöhen die Arbeit eine kleine Menge verbessert die Leistung von der <xref:System.Threading.SpinLock> im Vergleich zu standard-Sperre. Ab einem bestimmten Punkt wird ein SpinLock jedoch aufwändiger als eine Standardsperre. Mit der neuen Parallelitätsprofilerstellungsfunktion in den Profilerstellungstools können Sie feststellen, welcher Sperrentyp in Ihrem Programm die bessere Leistung bietet. Weitere Informationen finden Sie unter [Parallelitätsschnellansicht](/visualstudio/profiling/concurrency-visualizer).  
  
 [!code-csharp[CDS_SpinLock#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#02)]
 [!code-vb[CDS_SpinLock#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_vb.vb#02)]  
  
 <xref:System.Threading.SpinLock>kann nützlich sein, wenn eine Sperre für eine freigegebene Ressource ist nicht für aufrechterhalten werden als sehr lange. In solchen Fällen wird auf Multikerncomputern möglicherweise ein effizientes Verhalten erzielt, wenn der blockierte Thread einige Spinzyklen ausführt, bis die Sperre aufgehoben wird. Durch die Spinzyklen wird der Thread nicht blockiert, was zu einer hohen CPU-Auslastung führt. <xref:System.Threading.SpinLock>wird unter bestimmten Bedingungen auf der logischen Prozessoren oder die Umkehrung der Priorität auf Systemen mit Hyperthreading gewissen stoppt.  
  
 Dieses Beispiel verwendet die <xref:System.Collections.Generic.Queue%601?displayProperty=nameWithType> -Klasse, die benutzersynchronisierung für Multithreadzugriff erfordert. In Anwendungen, die auf .NET Framework, Version 4 abzielen, eine andere Möglichkeit ist die Verwendung der <xref:System.Collections.Concurrent.ConcurrentQueue%601?displayProperty=nameWithType>, dem alle Benutzersperren nicht erfordert.  
  
 Beachten Sie die Verwendung von `false` (`False` in Visual Basic) im Aufruf von <xref:System.Threading.SpinLock.Exit%2A>. Dieser Ansatz bietet die beste Leistung. Geben Sie bei IA64-Architekturen `true` (`True`) an, um die Arbeitsspeicherumgrenzung zu verwenden. Dadurch werden die Schreibpuffer geleert, um sicherzustellen, dass die Sperre jetzt verfügbar ist und andere Threads beendet werden können.  
  
## <a name="see-also"></a>Siehe auch  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)
