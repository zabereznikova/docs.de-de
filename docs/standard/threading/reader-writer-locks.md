---
title: "Reader-Writer Locks | Microsoft Docs"
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
  - "ReaderWriterLock class, about ReaderWriterLock class"
  - "threading [.NET Framework], ReaderWriterLock class"
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Reader-Writer Locks
Die <xref:System.Threading.ReaderWriterLockSlim>\-Klasse ermöglicht mehreren Threads, eine Ressource gleichzeitig zu lesen. Um in die Ressource zu schreiben, muss ein Thread jedoch auf eine exklusive Sperre warten.  
  
 Innerhalb einer Anwendung können Sie <xref:System.Threading.ReaderWriterLockSlim> beispielsweise verwenden, um eine kooperative Synchronisierung der Threads zu ermöglichen, die auf eine freigegebene Ressource zugreifen.  Sperren werden auf <xref:System.Threading.ReaderWriterLockSlim> selbst angewendet.  
  
 Wie bei jedem Threadsynchronisierungsmechanismus müssen Sie sicherstellen, dass keine Threads die durch <xref:System.Threading.ReaderWriterLockSlim> bereitgestellte Sperre umgehen.  Eine Möglichkeit hierfür besteht darin, eine Klasse zu entwerfen, die die freigegebene Ressource kapselt.  Diese Klasse würde Member bereitstellen, die auf die private freigegebene Ressource zugreifen und eine private <xref:System.Threading.ReaderWriterLockSlim> zur Synchronisierung verwenden.  Ein entsprechendes Beispiel ist das Codebeispiel für die <xref:System.Threading.ReaderWriterLockSlim>\-Klasse.  <xref:System.Threading.ReaderWriterLockSlim> ist effizient genug, um zur Synchronisierung einzelner Objekte verwendet zu werden.  
  
 Strukturieren Sie Anwendungen so, dass die Dauer von Lese\- und Schreibvorgängen minimiert wird.  Lange Schreibvorgänge wirken sich in unmittelbarer Weise auf den Durchsatz aus, da die Schreibsperre exklusiv ist.  Lange Lesevorgänge blockieren wartende Schreibvorgänge. Wenn mindestens ein Thread auf Schreibzugriff wartet, werden Threads, die Lesezugriff anfordern, ebenfalls blockiert.  
  
> [!NOTE]
>  Der [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] verfügt über zwei Lese\-\/Schreibsperren: <xref:System.Threading.ReaderWriterLockSlim> und <xref:System.Threading.ReaderWriterLock>.  <xref:System.Threading.ReaderWriterLockSlim> wird für alle Neuentwicklungen empfohlen.  <xref:System.Threading.ReaderWriterLockSlim> ähnelt <xref:System.Threading.ReaderWriterLock>, verwendet jedoch einfachere Regeln für die Rekursion und das Hoch\- und Herabstufen des Sperrzustands.  <xref:System.Threading.ReaderWriterLockSlim> kann in dieser Form eine Vielzahl potenzieller Deadlocks vermeiden.  Zudem wird mit <xref:System.Threading.ReaderWriterLockSlim> eine deutlich höhere Leistung erzielt als mit <xref:System.Threading.ReaderWriterLock>.  
  
## Siehe auch  
 <xref:System.Threading.ReaderWriterLockSlim>   
 <xref:System.Threading.ReaderWriterLock>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)