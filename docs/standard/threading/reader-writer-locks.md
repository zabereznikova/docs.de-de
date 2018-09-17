---
title: Lese-/Schreibsperren
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8be9b4eef30333fbbdc26915635d17157176d6fc
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/16/2018
ms.locfileid: "45640932"
---
# <a name="reader-writer-locks"></a>Lese-/Schreibsperren
Die <xref:System.Threading.ReaderWriterLockSlim>-Klasse ermöglicht mehreren Threads, eine Ressource gleichzeitig zu lesen, aber ein Thread muss zum Schreiben in die Ressource auf eine exklusive Sperre warten.  
  
 Sie könnten mit <xref:System.Threading.ReaderWriterLockSlim> in Ihrer Anwendung eine kooperative Synchronisierung zwischen Threads bereitstellen, die auf eine freigegebene Ressource zugreifen. Sperren werden auf <xref:System.Threading.ReaderWriterLockSlim> selbst vorgenommen.  
  
 Wie bei jedem Mechanismus zur Threadsynchronisierung müssen Sie sicherstellen, dass keine Threads die von <xref:System.Threading.ReaderWriterLockSlim> bereitgestellte Sperrung umgehen. Eine Möglichkeit, dies sicherzustellen, ist der Entwurf einer Klasse, die die freigegebene Ressource kapselt. Diese Klasse würde Member bereitstellen, die auf die private freigegebene Ressource zugreifen und ein privates <xref:System.Threading.ReaderWriterLockSlim> für die Synchronisierung nutzen. Ein Beispiel finden Sie im Codebeispiel für die <xref:System.Threading.ReaderWriterLockSlim>-Klasse. <xref:System.Threading.ReaderWriterLockSlim> ist effizient genug zum Synchronisieren einzelner Objekte.  
  
 Strukturieren Sie Ihre Anwendung zum Minimieren der Dauer von Lese- und Schreibvorgängen. Lange Schreibvorgänge beeinflussen den Durchsatz direkt, da die Schreibsperre exklusiv ist. Lange Lesevorgänge blockieren wartende Schreiber, und mindestens ein Thread wartet auf den Schreibzugriff; Threads, die Lesezugriff anfordern, werden ebenfalls blockiert.  
  
> [!NOTE]
>  [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] verfügt über zwei Lese-/Schreibsperren, <xref:System.Threading.ReaderWriterLockSlim> und <xref:System.Threading.ReaderWriterLock>. <xref:System.Threading.ReaderWriterLockSlim> wird für alle Neuentwicklungen empfohlen. <xref:System.Threading.ReaderWriterLockSlim> ähnelt <xref:System.Threading.ReaderWriterLock>, verfügt aber über vereinfachte Regeln für Rekursion sowie für Upgrade und Downgrade des Sperrstatus. <xref:System.Threading.ReaderWriterLockSlim> vermeidet viele potenzielle Deadlocks. Darüber hinaus ist die Leistung von <xref:System.Threading.ReaderWriterLockSlim> wesentlich besser als die von <xref:System.Threading.ReaderWriterLock>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.ReaderWriterLockSlim>  
- <xref:System.Threading.ReaderWriterLock>  
- [Threading](../../../docs/standard/threading/index.md)  
- [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)
