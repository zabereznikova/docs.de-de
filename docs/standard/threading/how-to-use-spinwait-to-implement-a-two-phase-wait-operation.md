---
title: "How to: Use SpinWait to Implement a Two-Phase Wait Operation | Microsoft Docs"
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
  - "SpinWait, how to synchronize two-phase wait"
ms.assetid: b2ac4e4a-051a-4f65-b4b9-f8e103aff195
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Use SpinWait to Implement a Two-Phase Wait Operation
Im folgenden Beispiel wird gezeigt, wie ein <xref:System.Threading.SpinWait?displayProperty=fullName>\-Objekt verwendet wird, um einen Wartevorgang mit zwei Phasen zu implementieren.  In der ersten Phase führt das Synchronisierungsobjekt, ein `Latch`, für einige Zyklen Spinvorgänge durch, während geprüft wird, ob die Sperre verfügbar geworden ist.  In der zweiten Phase, wenn die Sperre verfügbar wird, kehrt die `Wait`\-Methode zurück, ohne den Wartevorgang mithilfe von <xref:System.Threading.ManualResetEvent?displayProperty=fullName> auszuführen; andernfalls führt `Wait` den Wartevorgang aus.  
  
## Beispiel  
 Dieses Beispiel zeigt eine sehr grundlegende Implementierung einer Latch\-Synchronisierungsprimitive.  Sie können diese Datenstruktur verwenden, wenn die Wartezeiten voraussichtlich sehr kurz sind.  Dieses Beispiel dient nur der Veranschaulichung.  Wenn Sie die Latchtyp\-Funktion im Programm benötigen, sollten Sie die Verwendung von <xref:System.Threading.ManualResetEventSlim?displayProperty=fullName> erwägen.  
  
 [!code-csharp[CDS_SpinWait#03](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait03.cs#03)]
 [!code-vb[CDS_SpinWait#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/spinwait2.vb#03)]  
  
 Der Latch verwendet das [SpinOnce](assetId:///SpinOnce?qualifyHint=False&amp;autoUpgrade=True)\-Objekt, um an der Stelle Spinvorgänge durchzuführen, bis der nächste Aufruf von `T:System.Threading.SpinWait` bewirkt, dass das <xref:System.Threading.SpinWait>\-Objekt die Zeitscheibe des Threads bereitstellt.  An diesem Punkt verursacht der Latch durch Aufruf von <xref:System.Threading.WaitHandle.WaitOne%2A> auf <xref:System.Threading.ManualResetEvent> und durch Übergeben des Rests des Timeoutwerts einen eigenen Kontextwechsel.  
  
 Die Protokollierungsausgabe zeigt an, wie oft der der Latch in der Lage war, die Leistung durch Anfordern der Sperre zu verbessern, ohne <xref:System.Threading.ManualResetEvent> zu verwenden.  
  
## Siehe auch  
 [SpinWait](../../../docs/standard/threading/spinwait.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)