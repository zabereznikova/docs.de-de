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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d17ef8a199061f56f00e39fa887e2e64f64427ec
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="creating-threads-and-passing-data-at-start-time"></a>Erstellen von Threads und Übergeben von Daten zur Startzeit
Wenn ein Betriebssystemprozess erstellt wird, führt das Betriebssystem einen Thread ein, um Code in diesem Prozess auszuführen, einschließlich einer etwaigen ursprünglichen Anwendungsdomäne. Ab diesem Punkt können Anwendungsdomänen erstellt und gelöscht werden, ohne dass notwendigerweise Betriebssystemthreads erstellt oder zerstört werden. Wenn der ausgeführte Code verwalteter Code ist, kann ein <xref:System.Threading.Thread> -Objekt für die Threadausführung in der aktuellen Anwendungsdomäne durch Abrufen der statischen <xref:System.Threading.Thread.CurrentThread%2A>-Eigenschaft des Typs <xref:System.Threading.Thread> abgerufen werden. Dieses Thema beschreibt die Threaderstellung und erläutert Alternativen für die Übergabe von Daten an die Threadprozedur.  
  
## <a name="creating-a-thread"></a>Erstellen eines Threads  
 Beim Erstellen eines neuen <xref:System.Threading.Thread>-Objekts wird ein neuer verwalteter Thread erstellt. Die <xref:System.Threading.Thread>-Klasse verfügt über Konstruktoren, die einen <xref:System.Threading.ThreadStart>- oder <xref:System.Threading.ParameterizedThreadStart>-annehmen; der Delegat umschließt die Methode, die von dem neuen Thread aufgerufen wird, wenn Sie die <xref:System.Threading.Thread.Start%2A>-Methode aufrufen. Bei mehrmaligem Aufrufen von <xref:System.Threading.Thread.Start%2A> wird eine <xref:System.Threading.ThreadStateException> ausgelöst.  
  
 Die Rückgabe der <xref:System.Threading.Thread.Start%2A>-Methode erfolgt sofort, oft bevor der neue Thread tatsächlich gestartet wurde. Sie können mit den Eigenschaften <xref:System.Threading.Thread.ThreadState%2A> und <xref:System.Threading.Thread.IsAlive%2A> jederzeit den Status des Threads ermitteln, aber diese Eigenschaften sollten nie zum Synchronisieren der Aktivitäten von Threads verwendet werden.  
  
> [!NOTE]
>  Sobald ein Thread gestartet wird, ist es nicht notwendig, einen Verweis auf das <xref:System.Threading.Thread>-Objekt beizubehalten. Der Thread wird weiterhin ausgeführt, bis die Threadprozedur endet.  
  
 Das folgende Codebeispiel erstellt zwei neue Threads, um Instanz- und statische Methode auf einem anderen Objekt aufzurufen.  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## <a name="passing-data-to-threads-and-retrieving-data-from-threads"></a>Übergeben von Daten an Threads und Abrufen von Daten aus Threads  
 In .NET Framework Version 2.0 bietet der <xref:System.Threading.ParameterizedThreadStart>-Delegat eine einfache Möglichkeit, ein Objekt mit Daten an einen Thread zu übergeben, wenn Sie die <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>-Methodenüberladung aufrufen. Ein Codebeispiel finden Sie unter <xref:System.Threading.ParameterizedThreadStart>.  
  
 Die Verwendung des <xref:System.Threading.ParameterizedThreadStart>-Delegaten ist keine typsichere Möglichkeit zur Übergabe von Daten, da die <xref:System.Threading.Thread.Start%2A?displayProperty=nameWithType>-Methodenüberladung jedes Objekt akzeptiert. Eine Alternative ist, die Threadprozedur und die Daten in eine Hilfsklasse zu kapseln und die Threadprozedur mit dem <xref:System.Threading.ThreadStart>-Delegaten auszuführen. Diese Technik ist in den beiden folgenden Codebeispielen dargestellt.  
  
 Keiner dieser Delegaten hat einen Rückgabewert, da es keinen Ort gibt, an den die Daten aus einem asynchronen Aufruf zurückgegeben werden können. Um die Ergebnisse einer Threadmethode abzurufen, können Sie eine Rückrufmethode verwenden, wie im zweiten Codebeispiel gezeigt.  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### <a name="retrieving-data-with-callback-methods"></a>Abrufen von Daten mit Rückrufmethoden  
 Das folgende Beispiel veranschaulicht eine Rückrufmethode, die Daten von einem anderen Thread abruft. Der Konstruktor für die Klasse, die die Daten enthält, und auch die Threadmethode akzeptieren einen Delegaten, der die Rückrufmethode darstellt; bevor die Threadmethode endet, ruft sie den Rückrufdelegaten auf.  
  
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
