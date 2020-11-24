---
title: 'Gewusst wie: Aktivieren des Modus zum Nachverfolgen von Threads in SpinLock'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SpinLock, how to enable thread-tracking
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
ms.openlocfilehash: 83aebc45cdeaa2330c49ef6e90dcbedcd36de6b5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826455"
---
# <a name="how-to-enable-thread-tracking-mode-in-spinlock"></a>Gewusst wie: Aktivieren des Modus zum Nachverfolgen von Threads in SpinLock
<xref:System.Threading.SpinLock?displayProperty=nameWithType> ist eine gegenseitige Low-Level- Ausschlusssperre, die Sie für Szenarien mit sehr kurzen Wartezeiten verwenden können. <xref:System.Threading.SpinLock> ist nicht wiedereintrittsfähig. Wenn ein Thread in die Sperre eintritt, muss er die Sperre ordnungsgemäß beenden, bevor er erneut eintreten kann. In der Regel würde jeder Versuch, erneut in die Sperre einzutreten, einen Deadlock verursachen, und Deadlocks sind sehr schwer zu beheben. Als Hilfe zur Entwicklung unterstützt <xref:System.Threading.SpinLock?displayProperty=nameWithType> einen Modus zum Nachverfolgen von Threads, der bewirkt, dass eine Ausnahme ausgelöst wird, wenn ein Thread versucht, erneut in eine Sperre einzutreten, in der er sich bereits befindet. So können Sie leichter den Punkt lokalisieren, an dem die Sperre nicht ordnungsgemäß beendet wurde. Sie können den Modus zum Nachverfolgen von Threads mithilfe des <xref:System.Threading.SpinLock>-Konstruktors einschalten, der einen booleschen Eingabeparameter akzeptiert, und ein `true`-Argument übergeben. Deaktivieren Sie den Modus zum Nachverfolgen von Threads nach Abschluss der Entwicklungs- und Testphase im Interesse besserer Leistung.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht den Modus zum Nachverfolgen von Threads. Die Zeilen zum ordnungsgemäßen Beenden der Sperre sind auskommentiert, um einen Codefehler zu simulieren, der eines der folgenden Ergebnisse bewirkt:  
  
- Eine Ausnahme wird ausgelöst, wenn <xref:System.Threading.SpinLock> mit dem Argument `true` (`True` in Visual Basic) erstellt wird.  
  
- Ein Deadlock wird ausgelöst, wenn <xref:System.Threading.SpinLock> mit dem Argument `false` (`False` in Visual Basic) erstellt wird.  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## <a name="see-also"></a>Weitere Informationen

- [SpinLock](spinlock.md)
