---
title: Threads und Threading
description: Hier erfahren Sie mehr über Threading (Prozesse und Threads), wann Sie mehrere Threads verwenden können und wie Sie Multithreading verwenden können, um die Reaktionsfähigkeit oder den Durchsatz in .NET zu erhöhen.
ms.date: 11/08/2018
helpviewer_keywords:
- multiple threads
- threading [.NET]
- threading [.NET], multiple threads
ms.assetid: 5baac3aa-e603-4fa6-9f89-0f2c1084e6b1
ms.openlocfilehash: 20550b597e27c75f00d16528871007988dd6b885
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94819538"
---
# <a name="threads-and-threading"></a>Threads und Threading

Mit Multithreading können Sie die Reaktionsfähigkeit Ihrer Anwendung und deren Durchsatz erhöhen, falls Ihre Anwendung in einem Multiprozessor- oder Multicoresystem ausgeführt wird.

## <a name="processes-and-threads"></a>Prozesse und Threads

Ein *Prozess* ist ein ausführendes Programm. Ein Betriebssystem verwendet Prozesse, um Anwendungen voneinander zu trennen, die ausgeführt werden. Ein *Thread* ist die grundlegende Einheit, in der ein Betriebssystem die Prozessorzeit belegt. Jeder Thread verfügt über eine [Planungspriorität](scheduling-threads.md) und verwaltet eine Reihe von Strukturen, mit denen das System den Threadkontext speichert, bis die Threadausführung angehalten wird. Der Threadkontext enthält alle Informationen, die der Thread benötigt, um die Ausführung nahtlos fortzusetzen. Dies schließt auch seine CPU-Register und seinen Stapel ein. Im Kontext eines Prozesses können mehrere Threads ausgeführt werden. Alle Threads eines Prozesses teilen sich dessen virtuellen Adressraum. Ein Thread kann einen beliebigen Teil des Programmcodes ausführen, einschließlich der Teile, die aktuell von einem anderen Thread ausgeführt werden.

> [!NOTE]
> Mit dem .NET Framework können Anwendungen innerhalb eines Prozesses mithilfe von *Anwendungsdomänen* isoliert werden. (Anwendungsdomänen sind auf .NET Core nicht verfügbar.) Weitere Informationen finden Sie im Abschnitt [Anwendungsdomänen und Threads](../../framework/app-domains/application-domains.md#application-domains-and-threads) im Artikel [Anwendungsdomänen](../../framework/app-domains/application-domains.md).

Normalerweise wird ein .NET-Programm mit einem einzelnen Thread gestartet, der oft als *primärer* Thread bezeichnet wird. Es kann jedoch zusätzliche Threads erstellen, um Code parallel oder gleichzeitig mit dem primären Thread auszuführen. Diese Threads werden auch als *Arbeitsthreads* bezeichnet.

## <a name="when-to-use-multiple-threads"></a>Verwendung mehrerer Threads

Sie verwenden mehrere Threads, um die Reaktionsfähigkeit Ihrer Anwendung zu erhöhen und um die Vorteile eines Multiprozessor- oder Multicoresystems zu nutzen, die den Anwendungsdurchsatz erhöhen.

Ziehen Sie eine Desktopanwendung in Betracht, in der der primäre Thread für Benutzeroberflächenelemente verantwortlich ist und auf Benutzeraktionen reagiert. Verwenden Sie Arbeitsthreads, um zeitaufwendige Vorgänge durchzuführen, die andernfalls den primären Thread einnehmen würden und so dazu führen würden, dass die Benutzeroberfläche nicht mehr reagiert. Sie können auch einen dedizierten Thread verwenden, damit die Netzwerk- oder Gerätekommunikation auf eingehende Nachrichten oder Ereignisse besser reagiert.

Wenn Ihr Programm Vorgänge ausführt, die parallel durchgeführt werden können, kann die Gesamtausführungszeit verringert werden, indem diese Vorgänge in separaten Threads durchgeführt und das Programm auf einem Multiprozessor- oder Multicoresystem ausgeführt wird. Auf solch einem System kann die Verwendung von Multithreading den Durchsatz erhöhen und gleichzeitig kann die Reaktionsfähigkeit verbessert werden.

## <a name="how-to-use-multithreading-in-net"></a>Verwenden des Multithreadings in .NET

Ab .NET Framework 4 wird für die Nutzung von Multithreading empfohlen, [Task Parallel Library (TPL)](../parallel-programming/task-parallel-library-tpl.md) und [Parallel LINQ (PLINQ)](../parallel-programming/introduction-to-plinq.md) zu verwenden. Weitere Informationen finden Sie unter [Parallele Programmierung in .NET](../parallel-programming/index.md).

TPL und PLINQ basieren jeweils auf den <xref:System.Threading.ThreadPool>-Threads. Die <xref:System.Threading.ThreadPool?displayProperty=nameWithType>-Klasse stellt einer .NET-Anwendung einen Pool von Arbeitsthreads bereit. Sie können auch Threadpoolthreads verwenden. Weitere Informationen finden Sie unter [Der verwaltete Threadpool](the-managed-thread-pool.md).

Zum Schluss können Sie die <xref:System.Threading.Thread?displayProperty=nameWithType>-Klasse verwenden, die einen verwalteten Thread darstellt. Weitere Informationen finden Sie unter [Verwenden von Threads und Threading](using-threads-and-threading.md).

Mehrere Threads müssen möglicherweise auf eine freigegebene Ressource zugreifen. Damit die Ressource nicht beschädigt wird und um Racebedingungen zu vermeiden, müssen Sie den Threadzugriff darauf synchronisieren. Sie sollten ebenso die Interaktion mehrerer Threads koordinieren. .NET bietet eine Reihe von Typen, mit denen Sie den Zugriff auf eine freigegebene Ressource synchronisieren oder die Threadinteraktion koordinieren können. Weitere Informationen finden Sie unter [Übersicht über Synchronisierungsprimitiven](overview-of-synchronization-primitives.md).

Behandeln Sie Ausnahmen in Threads. Nicht behandelte Ausnahmen in Threads beenden in der Regel den Prozess. Weitere Informationen finden Sie unter [Ausnahmen in verwalteten Threads](exceptions-in-managed-threads.md).

## <a name="see-also"></a>Siehe auch

- [Threadingobjekte und -funktionen](threading-objects-and-features.md)
- [Empfohlene Vorgehensweise für das verwaltete Threading](managed-threading-best-practices.md)
- [Parallel Processing, Concurrency, and Async Programming in .NET (Parallelverarbeitung, Parallelität und asynchrone Programmierung in .NET)](../parallel-processing-and-concurrency.md)
- [About Processes and Threads (Informationen zu Prozessen und Threads)](/windows/desktop/procthread/about-processes-and-threads)
