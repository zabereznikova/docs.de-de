---
title: "Erstellen von Threads und Übergeben von Daten zur Startzeit"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [.NET Framework], creating
- threading [.NET Framework], passing data to threads
- threading [.NET Framework], retrieving data from threads
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61808dc804cc627ab368a5250414dfcc5f54c87e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="creating-threads-and-passing-data-at-start-time"></a>Erstellen von Threads und Übergeben von Daten zur Startzeit
Wenn ein Betriebssystem-Prozess erstellt wird, wird das Betriebssystem einen Thread, um die Ausführung von Code in diesem Prozess, einschließlich der ursprünglichen Anwendungsdomäne eingefügt. Ab diesem Zeitpunkt können Anwendungsdomänen erstellt und gelöscht werden, ohne alle Betriebssystemthreads notwendigerweise erstellt oder zerstört werden. Wenn der ausgeführte Code verwaltet wird Code, ein <xref:System.Threading.Thread> -Objekt für die vom Thread ausgeführten in die aktuelle Anwendungsdomäne abgerufen werden kann durch Abrufen der statischen <xref:System.Threading.Thread.CurrentThread%2A> Eigenschaft vom Typ <xref:System.Threading.Thread>. Dieses Thema beschreibt Threaderstellung und alternativen für die Übergabe von Daten an die Threadprozedur erläutert.  
  
## <a name="creating-a-thread"></a>Erstellen eines Threads  
 Erstellen eines neuen <xref:System.Threading.Thread> Objekt einen neuen verwalteten Thread erstellt. Die <xref:System.Threading.Thread> -Klasse verfügt über Konstruktoren, die eine <xref:System.Threading.ThreadStart> delegieren oder eine <xref:System.Threading.ParameterizedThreadStart> Delegieren; der Delegat umschließt die Methode, die von dem neuen Thread, beim Aufrufen aufgerufen wird der <xref:System.Threading.Thread.Start%2A> Methode. Aufrufen von <xref:System.Threading.Thread.Start%2A> mehr als einmal bewirkt, dass eine <xref:System.Threading.ThreadStateException> ausgelöst wird.  
  
 Die <xref:System.Threading.Thread.Start%2A> Methodenrückgabe sofort, bevor der neue Thread tatsächlich gestartet wurde. Sie können die <xref:System.Threading.Thread.ThreadState%2A> und <xref:System.Threading.Thread.IsAlive%2A> Eigenschaften zum Ermitteln des Status des Threads jederzeit, aber diese Eigenschaften sollten nie zum Synchronisieren der Aktivitäten von Threads verwendet werden.  
  
> [!NOTE]
>  Sobald ein Thread gestartet wird, ist es nicht notwendig, behalten einen Verweis auf die <xref:System.Threading.Thread> Objekt. Der Thread weiterhin ausgeführt, bis die Threadprozedur beendet.  
  
 Das folgende Codebeispiel erstellt zwei neue Threads, um Instanz- und statische Methoden für ein anderes Objekt aufzurufen.  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads-and-retrieving-data-from-threads"></a>Übergeben von Daten an Threads und Abrufen von Daten aus Threads  
 In .NET Framework, Version 2.0 die <xref:System.Threading.ParameterizedThreadStart> Delegaten bietet eine einfache Möglichkeit, übergeben Sie ein Objekt mit den Daten, die einem Thread beim Aufrufen der <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> -methodenüberladung. Ein Codebeispiel finden Sie unter <xref:System.Threading.ParameterizedThreadStart>.  
  
 Mithilfe der <xref:System.Threading.ParameterizedThreadStart> Delegat ist eine typsichere Möglichkeit zur Übergabe von Daten nicht, da die <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType> methodenüberladung akzeptiert jedes Objekt. Eine Alternative besteht darin, die Threadprozedur und die Daten in eine Hilfsklasse zu kapseln und Verwenden der <xref:System.Threading.ThreadStart> Delegaten zum Ausführen der Threadprozedur. Diese Technik ist in den beiden Codebeispielen dargestellt, die folgen.  
  
 Beide Methoden Delegaten verfügt über einen Rückgabewert aus, da es keine Möglichkeit, die Daten aus einem asynchronen Aufruf zurückgegeben wird. Um die Ergebnisse einer Methode Threads abzurufen, können Sie eine Rückrufmethode verwenden, wie im zweiten Codebeispiel wird veranschaulicht.  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### <a name="retrieving-data-with-callback-methods"></a>Abrufen von Daten mit Rückrufmethoden  
 Das folgende Beispiel veranschaulicht eine Rückrufmethode, die Daten von einem anderen Thread abruft. Der Konstruktor für die Klasse enthält die Daten und die Threadmethode nimmt auch einen Delegaten, der die Rückrufmethode darstellt; bevor die Threadmethode beendet wird, ruft er den Rückrufdelegaten auf.  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadStart>  
 <xref:System.Threading.ParameterizedThreadStart>  
 <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Verwenden von Threads und Threading](../../../docs/standard/threading/using-threads-and-threading.md)
