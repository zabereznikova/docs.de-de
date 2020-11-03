---
title: Semaphore und SemaphoreSlim
description: Erfahren Sie mehr über Semaphore und SemaphoreSlim. Bei der Klasse Semaphore handelt es sich um einen einfachen Wrapper um das Win32-Semaphorobjekt. Die Klasse SemaphoreSlim ist eine schnelle, einfache Variante der Klasse Semaphore.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- counting semaphores
- semaphores
- threading [.NET], cross-process synchronization
- Semaphore class, about Semaphore class
- SemaphoreSlim class, about SemaphoreSlim class
- threading [.NET], Semaphore class
ms.assetid: 7722a333-b974-47a2-a7c0-f09097fb644e
ms.openlocfilehash: b9c13ace086b4df08108a844aea78e5d550e6958
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188938"
---
# <a name="semaphore-and-semaphoreslim"></a>Semaphore und SemaphoreSlim

Die <xref:System.Threading.Semaphore?displayProperty=nameWithType>-Klasse stellt ein benanntes (systemweites) oder lokales Semaphor dar. Dabei handelt es sich um einen einfachen Wrapper um das Win32-Semaphorobjekt. Win32-Semaphoren sind zählende Semaphoren, die zum Steuern des Zugriffs auf einen Ressourcenpool verwendet werden können.  
  
 Die <xref:System.Threading.SemaphoreSlim>-Klasse stellt ein einfaches, schnelles Semaphor dar, das zum Warten innerhalb eines einzelnen Prozesses verwendet werden kann, wenn die Wartezeiten voraussichtlich sehr kurz sind. <xref:System.Threading.SemaphoreSlim> basiert im möglichst hohen Maße auf Synchronisierungsprimitiven, die von Common Language Runtime (CLR) bereitgestellt werden. Es stellt jedoch auch verzögert initialisierte, Kernel-basierte Wait-Handles zur Unterstützung des Wartens auf mehrere Semaphoren bereit. <xref:System.Threading.SemaphoreSlim> unterstützt auch die Verwendung von Abbruchtoken, unterstützt aber keine benannten Semaphoren oder die Verwendung eines Wait-Handles für die Synchronisierung.  
  
## <a name="managing-a-limited-resource"></a>Verwalten einer beschränkten Ressource  
 Threads wechseln in den Semaphor durch Aufrufen der <xref:System.Threading.WaitHandle.WaitOne%2A>-Methode, die von der <xref:System.Threading.WaitHandle>-Klasse geerbt wird, wenn es sich um ein <xref:System.Threading.Semaphore?displayProperty=nameWithType>-Objekt handelt, bzw. von der <xref:System.Threading.SemaphoreSlim.Wait%2A?displayProperty=nameWithType>- oder <xref:System.Threading.SemaphoreSlim.WaitAsync%2A?displayProperty=nameWithType>-Methode, wenn es sich um ein <xref:System.Threading.SemaphoreSlim>-Objekt handelt. Wenn der Aufruf zurückgegeben wird, wird der Zähler des Semaphors dekrementiert. Wenn ein Thread den Zugang anfordert und die Anzahl null ist, wird der Thread blockiert. Da Threads das Semaphor durch Aufrufen von Freigeben der <xref:System.Threading.Semaphore.Release%2A?displayProperty=nameWithType>- oder <xref:System.Threading.SemaphoreSlim.Release%2A?displayProperty=nameWithType>-Methode freigeben, erhalten blockierte Threads Zugang. Für die Aufnahme von blockierten Threads in das Semaphor gibt es keine festgelegte Reihenfolge, z. B. First in, First Out (FIFO) oder Last in, First Out (LIFO).  
  
 Ein Thread kann in das Semaphor mehrfach durch wiederholtes Aufrufen der <xref:System.Threading.Semaphore?displayProperty=nameWithType>-Methode des <xref:System.Threading.WaitHandle.WaitOne%2A>-Objekts oder der <xref:System.Threading.SemaphoreSlim>-Methode des <xref:System.Threading.SemaphoreSlim.Wait%2A>-Objekts wechseln. Um das Semaphor freizugeben, kann der Thread entweder die <xref:System.Threading.Semaphore.Release?displayProperty=nameWithType>- oder <xref:System.Threading.SemaphoreSlim.Release?displayProperty=nameWithType>-Methodenüberladung aufrufen oder die <xref:System.Threading.Semaphore.Release%28System.Int32%29?displayProperty=nameWithType>- oder <xref:System.Threading.SemaphoreSlim.Release%28System.Int32%29?displayProperty=nameWithType>-Methodenüberladung aufrufen und die Anzahl der freizugebenden Einträge angeben.  
  
### <a name="semaphores-and-thread-identity"></a>Semaphoren und Threadidentität  
 Die zwei Semaphoren erzwingen keine Threadidentität für Aufrufe der Methoden <xref:System.Threading.WaitHandle.WaitOne%2A>, <xref:System.Threading.SemaphoreSlim.Wait%2A>, <xref:System.Threading.Semaphore.Release%2A> und <xref:System.Threading.SemaphoreSlim.Release%2A?displayProperty=nameWithType>. Ein häufiges Verwendungsszenario für Semaphoren umfasst beispielsweise einen Producerthread und einem Consumerthread, wobei ein Thread den Zähler des Semaphors immer erhöht und der andere ihn immer verringert.  
  
 Der Programmierer ist dafür verantwortlich, sicherzustellen, dass ein Thread das Semaphor nicht zu oft freigibt. Angenommen, ein Semaphor hat einen maximalen Zähler von zwei und Thread A sowie Thread B wechseln beide in das Semaphor. Wenn ein Programmierfehler in Thread B dazu führt, dass `Release` zweimal aufgerufen wird, sind beide Aufrufe erfolgreich. Der Zähler des Semaphors ist voll, und wenn Thread A schließlich `Release` aufruft, wird eine <xref:System.Threading.SemaphoreFullException> ausgelöst.  
  
## <a name="named-semaphores"></a>Benannte Semaphoren  
 Das Windows-Betriebssystem ermöglicht es, Semaphoren zu benennen. Ein benanntes Semaphor ist systemweit sichtbar. Das heißt, sobald das benannte Semaphor erstellt wurde, ist es für alle Threads in allen Prozessen sichtbar. Folglich kann ein benanntes Semaphore zum Synchronisieren der Aktivitäten von Prozessen und Threads verwendet werden.  
  
 Sie können ein <xref:System.Threading.Semaphore>-Objekt erstellen, das ein benanntes Systemsemaphor darstellt, indem Sie einen der Konstruktoren verwenden, die einen Namen angeben.  
  
> [!NOTE]
> Da benannte Semaphoren systemweit sichtbar sind, ist es möglich, mehrere <xref:System.Threading.Semaphore>-Objekte zu haben, die dasselbe benannte Semaphor darstellen. Bei jedem Aufruf eines Konstruktors oder der <xref:System.Threading.Semaphore.OpenExisting%2A?displayProperty=nameWithType>-Methode wird ein neues <xref:System.Threading.Semaphore>-Objekt erstellt. Wenn Sie wiederholt denselben Namen angeben, werden mehrere Objekte erstellt, die desselbe benannte Semaphor darstellen.  
  
 Vorsicht ist geboten, wenn Sie benannte Semaphoren verwenden. Da sie systemweit sichtbar sind, kann ein anderer Prozess, der den gleichen Namen verwendet, unerwartet in das Semaphor wechseln. Böswilliger Code, der auf demselben Computer ausgeführt wird, könnte dies als Grundlage für einen Denial-of-Service-Angriff verwenden.  
  
 Verwenden Sie die Zugriffssteuerungssicherheit zum Schutz eines <xref:System.Threading.Semaphore>-Objekts, das ein benanntes Semaphor darstellt, vorzugsweise unter Verwendung eines Konstruktors, der <xref:System.Security.AccessControl.SemaphoreSecurity?displayProperty=nameWithType>-Objekt angibt. Sie können die Zugriffssteuerungssicherheit auch mithilfe der <xref:System.Threading.Semaphore.SetAccessControl%2A?displayProperty=nameWithType>-Methode anwenden, allerdings bleibt so ein Verwundbarkeitszeitfenster zwischen der Erstellung und dem Schutz des Semaphors. Der Schutz von Semaphoren mit Zugriffssteuerungssicherheit hilft beim Verhindern böswilliger Angriffe, das Problem unbeabsichtigter Namenskonflikte wird dadurch aber nicht gelöst.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Semaphore>
- <xref:System.Threading.SemaphoreSlim>
- [Threading Objects and Features (Threadingobjekte und -funktionen)](threading-objects-and-features.md)
