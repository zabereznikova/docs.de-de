---
title: Lese-/Schreibsperren
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df06e83165906199774f99de4140ace9b7396cbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="reader-writer-locks"></a>Lese-/Schreibsperren
Die <xref:System.Threading.ReaderWriterLockSlim> Klasse ermöglicht es mehreren Threads auf eine Ressource gleichzeitig lesen, aber es muss einen Thread warten, eine exklusive Sperre zum Schreiben in die Ressource.  
  
 Sie können eine <xref:System.Threading.ReaderWriterLockSlim> in Ihrer Anwendung kooperative Synchronisierung zwischen Threads bereitstellen, die eine freigegebene Ressource zugreifen. Sperren werden auf die <xref:System.Threading.ReaderWriterLockSlim> selbst.  
  
 Wie mit jedem Threadsynchronisierungsmechanismus Sie sicherstellen müssen, dass keine Threads das Sperren umgehen von bereitgestellten <xref:System.Threading.ReaderWriterLockSlim>. Eine Möglichkeit, dies sicherzustellen ist eine Klasse, die die freigegebene Ressource kapselt. Diese Klasse würde Member, die auf die private freigegebene Ressource zugreifen und eine private, bereitstellen <xref:System.Threading.ReaderWriterLockSlim> für die Synchronisierung. Ein Beispiel finden Sie im Codebeispiel für die <xref:System.Threading.ReaderWriterLockSlim> Klasse. <xref:System.Threading.ReaderWriterLockSlim>ist effizient verwendet werden, um einzelne Objekte synchronisiert.  
  
 Strukturieren Sie Ihre Anwendung zu minimieren, die Dauer der Lese- und Schreibvorgänge. Lange Schreibvorgänge Einfluss Durchsatz direkt auf, da die Schreibsperre exklusiv ist. Lange Lesevorgänge blockieren wartende Schreibvorgänge lesen, und mindestens einen Thread für den Schreibzugriff wartet, Threads, die Lesezugriff auf Anforderung blockiert werden ebenfalls.  
  
> [!NOTE]
>  Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] verfügt über zwei Lese-/ Schreibsperren, <xref:System.Threading.ReaderWriterLockSlim> und <xref:System.Threading.ReaderWriterLock>. <xref:System.Threading.ReaderWriterLockSlim>wird für alle Neuentwicklungen empfohlen. <xref:System.Threading.ReaderWriterLockSlim>ähnelt dem <xref:System.Threading.ReaderWriterLock>, aber es wurde vereinfacht, Regeln für die Rekursion zu aktualisieren und zu Downgrades Zustand der remotesperre. <xref:System.Threading.ReaderWriterLockSlim>wird häufig potenzielle Deadlocks vermieden. Darüber hinaus die Leistung des <xref:System.Threading.ReaderWriterLockSlim> ist wesentlich besser als <xref:System.Threading.ReaderWriterLock>.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)
