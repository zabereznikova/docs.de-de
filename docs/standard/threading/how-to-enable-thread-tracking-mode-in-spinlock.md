---
title: 'Gewusst wie: Aktivieren des Modus zum Nachverfolgen von Threads in SpinLock'
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
helpviewer_keywords: SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca5f1b6eace7a24a6bbb7fd541858246828fa757
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a>Gewusst wie: Aktivieren des Modus zum Nachverfolgen von Threads in SpinLock
<xref:System.Threading.SpinLock?displayProperty=nameWithType>ist eine Low-Level gegenseitigen Ausschluss-Sperre, die Sie für Szenarien verwenden können, die sehr kurze Wartezeiten aufweisen. <xref:System.Threading.SpinLock>ist nicht wiedereintrittsfähig. Nach ein Thread die Sperre angefordert hat, muss er die Sperre ordnungsgemäß beenden, bevor er erneut eingeben kann. In der Regel können jeder Versuch, die Sperre erneut einen Deadlock verursachen würde, und Deadlocks sehr schwer zu beheben. Als Hilfe bei der Entwicklung <xref:System.Threading.SpinLock?displayProperty=nameWithType> unterstützt einen Modus zum Nachverfolgen von Threads, die bewirkt, eine Ausnahme ausgelöst werden dass, wenn ein Thread versucht, eine Sperre, die sie bereits enthält, erneut eingeben. Dadurch können Sie, die mehrere den Punkt suchen Sie mit dem die Sperre nicht ordnungsgemäß beendet wurde. Thread-Nachverfolgungsmodus einschalten, mithilfe der <xref:System.Threading.SpinLock> Konstruktor, der einen boolescher Wert akzeptiert Eingabeparameter, und übergeben ein Argument des `true`. Deaktivieren Sie nach Abschluss der Entwicklung und Testphase Modus zum Nachverfolgen von Threads für eine bessere Leistung.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Thread-Nachverfolgungsmodus. Die Zeilen, die die Sperre ordnungsgemäß beenden sind auskommentiert, um einen Codefehler zu simulieren, die bewirkt, eines der folgenden Ergebnisse dass:  
  
-   Eine Ausnahme wird ausgelöst, wenn die <xref:System.Threading.SpinLock> wurde erstellt, mit dem Argument der `true` (`True` in Visual Basic).  
  
-   Wenn ein Deadlock auftreten der <xref:System.Threading.SpinLock> wurde erstellt, mit dem Argument der `false` (`False` in Visual Basic).  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a>Siehe auch  
 [SpinLock](../../../docs/standard/threading/spinlock.md)
