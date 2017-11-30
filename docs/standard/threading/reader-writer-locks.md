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
# <a name="reader-writer-locks"></a><span data-ttu-id="0d50b-102">Lese-/Schreibsperren</span><span class="sxs-lookup"><span data-stu-id="0d50b-102">Reader-Writer Locks</span></span>
<span data-ttu-id="0d50b-103">Die <xref:System.Threading.ReaderWriterLockSlim> Klasse ermöglicht es mehreren Threads auf eine Ressource gleichzeitig lesen, aber es muss einen Thread warten, eine exklusive Sperre zum Schreiben in die Ressource.</span><span class="sxs-lookup"><span data-stu-id="0d50b-103">The <xref:System.Threading.ReaderWriterLockSlim> class enables multiple threads to read a resource concurrently, but requires a thread to wait for an exclusive lock in order to write to the resource.</span></span>  
  
 <span data-ttu-id="0d50b-104">Sie können eine <xref:System.Threading.ReaderWriterLockSlim> in Ihrer Anwendung kooperative Synchronisierung zwischen Threads bereitstellen, die eine freigegebene Ressource zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0d50b-104">You might use a <xref:System.Threading.ReaderWriterLockSlim> in your application to provide cooperative synchronization among threads that access a shared resource.</span></span> <span data-ttu-id="0d50b-105">Sperren werden auf die <xref:System.Threading.ReaderWriterLockSlim> selbst.</span><span class="sxs-lookup"><span data-stu-id="0d50b-105">Locks are taken on the <xref:System.Threading.ReaderWriterLockSlim> itself.</span></span>  
  
 <span data-ttu-id="0d50b-106">Wie mit jedem Threadsynchronisierungsmechanismus Sie sicherstellen müssen, dass keine Threads das Sperren umgehen von bereitgestellten <xref:System.Threading.ReaderWriterLockSlim>.</span><span class="sxs-lookup"><span data-stu-id="0d50b-106">As with any thread synchronization mechanism, you must ensure that no threads bypass the locking that is provided by <xref:System.Threading.ReaderWriterLockSlim>.</span></span> <span data-ttu-id="0d50b-107">Eine Möglichkeit, dies sicherzustellen ist eine Klasse, die die freigegebene Ressource kapselt.</span><span class="sxs-lookup"><span data-stu-id="0d50b-107">One way to ensure this is to design a class that encapsulates the shared resource.</span></span> <span data-ttu-id="0d50b-108">Diese Klasse würde Member, die auf die private freigegebene Ressource zugreifen und eine private, bereitstellen <xref:System.Threading.ReaderWriterLockSlim> für die Synchronisierung.</span><span class="sxs-lookup"><span data-stu-id="0d50b-108">This class would provide members that access the private shared resource and that use a private <xref:System.Threading.ReaderWriterLockSlim> for synchronization.</span></span> <span data-ttu-id="0d50b-109">Ein Beispiel finden Sie im Codebeispiel für die <xref:System.Threading.ReaderWriterLockSlim> Klasse.</span><span class="sxs-lookup"><span data-stu-id="0d50b-109">For an example, see the code example for the <xref:System.Threading.ReaderWriterLockSlim> class.</span></span> <span data-ttu-id="0d50b-110"><xref:System.Threading.ReaderWriterLockSlim>ist effizient verwendet werden, um einzelne Objekte synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="0d50b-110"><xref:System.Threading.ReaderWriterLockSlim> is efficient enough to be used to synchronize individual objects.</span></span>  
  
 <span data-ttu-id="0d50b-111">Strukturieren Sie Ihre Anwendung zu minimieren, die Dauer der Lese- und Schreibvorgänge.</span><span class="sxs-lookup"><span data-stu-id="0d50b-111">Structure your application to minimize the duration of read and write operations.</span></span> <span data-ttu-id="0d50b-112">Lange Schreibvorgänge Einfluss Durchsatz direkt auf, da die Schreibsperre exklusiv ist.</span><span class="sxs-lookup"><span data-stu-id="0d50b-112">Long write operations affect throughput directly because the write lock is exclusive.</span></span> <span data-ttu-id="0d50b-113">Lange Lesevorgänge blockieren wartende Schreibvorgänge lesen, und mindestens einen Thread für den Schreibzugriff wartet, Threads, die Lesezugriff auf Anforderung blockiert werden ebenfalls.</span><span class="sxs-lookup"><span data-stu-id="0d50b-113">Long read operations block waiting writers, and if at least one thread is waiting for write access, threads that request read access will be blocked as well.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0d50b-114">Die [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] verfügt über zwei Lese-/ Schreibsperren, <xref:System.Threading.ReaderWriterLockSlim> und <xref:System.Threading.ReaderWriterLock>.</span><span class="sxs-lookup"><span data-stu-id="0d50b-114">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] has two reader-writer locks, <xref:System.Threading.ReaderWriterLockSlim> and <xref:System.Threading.ReaderWriterLock>.</span></span> <span data-ttu-id="0d50b-115"><xref:System.Threading.ReaderWriterLockSlim>wird für alle Neuentwicklungen empfohlen.</span><span class="sxs-lookup"><span data-stu-id="0d50b-115"><xref:System.Threading.ReaderWriterLockSlim> is recommended for all new development.</span></span> <span data-ttu-id="0d50b-116"><xref:System.Threading.ReaderWriterLockSlim>ähnelt dem <xref:System.Threading.ReaderWriterLock>, aber es wurde vereinfacht, Regeln für die Rekursion zu aktualisieren und zu Downgrades Zustand der remotesperre.</span><span class="sxs-lookup"><span data-stu-id="0d50b-116"><xref:System.Threading.ReaderWriterLockSlim> is similar to <xref:System.Threading.ReaderWriterLock>, but it has simplified rules for recursion and for upgrading and downgrading lock state.</span></span> <span data-ttu-id="0d50b-117"><xref:System.Threading.ReaderWriterLockSlim>wird häufig potenzielle Deadlocks vermieden.</span><span class="sxs-lookup"><span data-stu-id="0d50b-117"><xref:System.Threading.ReaderWriterLockSlim> avoids many cases of potential deadlock.</span></span> <span data-ttu-id="0d50b-118">Darüber hinaus die Leistung des <xref:System.Threading.ReaderWriterLockSlim> ist wesentlich besser als <xref:System.Threading.ReaderWriterLock>.</span><span class="sxs-lookup"><span data-stu-id="0d50b-118">In addition, the performance of <xref:System.Threading.ReaderWriterLockSlim> is significantly better than <xref:System.Threading.ReaderWriterLock>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d50b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d50b-119">See Also</span></span>  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [<span data-ttu-id="0d50b-120">Threading</span><span class="sxs-lookup"><span data-stu-id="0d50b-120">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="0d50b-121">Threading Objects and Features (Threadingobjekte und -funktionen)</span><span class="sxs-lookup"><span data-stu-id="0d50b-121">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
