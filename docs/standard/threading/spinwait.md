---
title: "SpinWait | Microsoft Docs"
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
  - "synchronization primitives, SpinWait"
ms.assetid: 36012f42-34e5-4f86-adf4-973f433ed6c6
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# SpinWait
<xref:System.Threading.SpinWait?displayProperty=fullName> ist ein einfacher Synchronisierungstyp, den Sie in Low\-Level\-Szenarien verwenden können, um teure Kontextwechsel und Kernelübergänge zu vermeiden, die für Kernelereignisse erforderlich sind.  Wenn auf Mehrkerncomputern eine Ressource voraussichtlich nur für kurze Zeit gehalten wird, kann es für einen wartenden Thread effizienter sein, im Benutzermodus für einige Dutzend oder Hundert Zyklen Spinvorgänge durchzuführen und dann erneut zu versuchen, die Ressource abzurufen.  Wenn die Ressource nach den Spinvorgängen verfügbar ist, haben Sie mehrere tausend Zyklen gespart.  Wenn die Ressource immer noch nicht verfügbar ist, haben Sie nur einige Zyklen durchlaufen und können immer noch in einen kernelbasierten Wartevorgang eintreten.  Diese Kombination aus Spin\- und Wartevorgängen wird auch als *zweiphasiger Wartevorgang* bezeichnet.  
  
 <xref:System.Threading.SpinWait> ist für die Verwendung in Verbindung mit den .NET Framework\-Typen vorgesehen, die Kernelereignisse wie z. B. <xref:System.Threading.ManualResetEvent> umschließen.  <xref:System.Threading.SpinWait> kann auch eigenständig für grundlegende Spinfunktionen in nur einem Programm verwendet werden.  
  
 <xref:System.Threading.SpinWait> ist mehr als nur eine leere Schleife.  Der Synchronisierungstyp wird sorgfältig implementiert, um richtiges Spinverhalten im Allgemeinen bereitzustellen, und initiiert eigenständig Kontextwechsel, wenn die Spinvorgänge lang genug sind \(ungefähr die für einen Kernelübergang erforderliche Zeitspanne\).  Auf Einzelkerncomputern liefert <xref:System.Threading.SpinWait> beispielsweise sofort die Zeitscheibe des Threads, da Spinvorgänge den Fortschritt auf allen Threads blockiert.  <xref:System.Threading.SpinWait> wird auch auf Mehrkerncomputern verwendet, um zu verhindern, dass der wartende Thread die Threads mit höherer Priorität oder den Garbage Collector blockiert.  Wenn Sie daher <xref:System.Threading.SpinWait> in einem zweiphasigen Wartevorgang verwenden, empfiehlt es sich, den Kernelwartevorgang aufzurufen, bevor der <xref:System.Threading.SpinWait> selbst einen Kontextwechsel initiiert.  <xref:System.Threading.SpinWait> stellt die <xref:System.Threading.SpinWait.NextSpinWillYield%2A>\-Eigenschaft bereit, die Sie vor jedem Aufruf von <xref:System.Threading.SpinWait.SpinOnce%2A> überprüfen können.  Wenn die Eigenschaft `true` zurückgibt, initiieren Sie einen eigenen Wartevorgang.  Ein Beispiel finden Sie unter [How to: Use SpinWait to Implement a Two\-Phase Wait Operation](../../../docs/standard/threading/how-to-use-spinwait-to-implement-a-two-phase-wait-operation.md).  
  
 Wenn Sie keinen zweiphasigen Wartevorgang initiieren, sondern nur Spinvorgänge durchführen, bis eine Bedingung erfüllt wird, können Sie <xref:System.Threading.SpinWait> aktivieren, um Kontextwechsel auszuführen und Aufgaben in der Windows\-Betriebssystemumgebung zu übernehmen.  Das folgende grundlegende Beispiel veranschaulicht <xref:System.Threading.SpinWait> in einem sperrenfreien Stapel.  Wenn Sie einen leistungsstarken, threadsicheren Stapel benötigen, erwägen Sie die Verwendung von <xref:System.Collections.Concurrent.ConcurrentStack%601?displayProperty=fullName>.  
  
 [!code-csharp[CDS_SpinWait#05](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_spinwait/cs/spinwait.cs#05)]
 [!code-vb[CDS_SpinWait#05](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_spinwait/vb/cds_spinwait1.vb#05)]  
  
## Siehe auch  
 <xref:System.Threading.Thread.SpinWait%2A>   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)