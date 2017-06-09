---
title: "How to: Enable Thread-Tracking Mode in SpinLock | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "SpinLock, how to enable thread-tracking"
ms.assetid: 62ee2e68-0bdd-4869-afc9-f0a57a11ae01
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Enable Thread-Tracking Mode in SpinLock
<xref:System.Threading.SpinLock?displayProperty=fullName> ist eine gegenseitige Ausschlusssperre auf niedriger Ebene, die Sie für Szenarien verwenden können, die sehr kurze Wartezeiten haben.  <xref:System.Threading.SpinLock> ist nicht eintrittsinvariant.  Nachdem ein Thread die Sperre angefordert hat, muss er die Sperre ordnungsgemäß beenden, bevor er sie wieder anfordern kann.  In der Regel verursacht jeder Versuch, die Sperre erneut anzufordern, einen Deadlock, und das Debuggen von Deadlocks kann sehr schwierig sein.  Als Hilfe bei der Entwicklung unterstützt <xref:System.Threading.SpinLock?displayProperty=fullName> einen Modus zum Nachverfolgen von Threads. In diesem Modus wird eine Ausnahme ausgelöst, wenn ein Thread versucht, eine Sperre, die er bereits besitzt, erneut anzufordern.  Auf diese Weise können Sie die Stelle, an der die Sperre nicht ordnungsgemäß beendet wurde, leichter finden.  Sie können den Modus zum Nachverfolgen von Threads mit dem <xref:System.Threading.SpinLock>\-Konstruktor aktivieren, der einen booleschen Eingabeparameter akzeptiert, und das Argument `true` übergeben.  Nachdem Sie die Entwicklungs\- und Testphase abgeschlossen haben, deaktivieren Sie den Modus zum Nachverfolgen von Threads, um eine bessere Leistung zu erzielen.  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht den Modus zum Nachverfolgen von Threads.  Die Zeilen, die die Sperre ordnungsgemäß beenden, sind auskommentiert, um einen Codierungsfehler zu simulieren, der zu einem der folgenden Ergebnisse führt:  
  
-   Eine Ausnahme wird ausgelöst, wenn <xref:System.Threading.SpinLock> mit dem Argument `true` \(`True` in Visual Basic\) erstellt wurde.  
  
-   Ein Deadlock tritt auf, wenn <xref:System.Threading.SpinLock> mit dem Argument `false` \(`False` in Visual Basic\) erstellt wurde.  
  
 [!code-csharp[CDS_SpinLock#01](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinlock/cs/spinlockdemo.cs#01)]
 [!code-vb[CDS_SpinLock#01](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinlock/vb/spinlock_threadtracking.vb#01)]  
  
## Siehe auch  
 [SpinLock](../../../docs/standard/threading/spinlock.md)