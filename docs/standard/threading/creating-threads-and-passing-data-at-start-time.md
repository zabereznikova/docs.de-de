---
title: "Creating Threads and Passing Data at Start Time | Microsoft Docs"
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
  - "threading [.NET Framework], creating"
  - "threading [.NET Framework], passing data to threads"
  - "threading [.NET Framework], retrieving data from threads"
ms.assetid: 52b32222-e185-4f42-91a7-eaca65c0ab6d
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Creating Threads and Passing Data at Start Time
Beim Erstellen eines Prozesses im Betriebssystem wird ein Thread eingeschleust, um Code in diesem Prozess auszuführen, einschließlich jeder ursprünglichen Anwendungsdomäne.  Ab diesem Zeitpunkt können Anwendungsdomänen erstellt und gelöscht werden, ohne dass Betriebssystemthreads erstellt oder gelöscht werden müssen.  Bei verwaltetem ausgeführtem Code kann ein <xref:System.Threading.Thread>\-Objekt für den in der aktuellen Anwendungsdomäne ausführenden Thread abgerufen werden. Dies erfolgt durch Abruf der statischen <xref:System.Threading.Thread.CurrentThread%2A>\-Eigenschaft vom Typ <xref:System.Threading.Thread>.  In diesem Thema wird die Threaderstellung beschrieben, und es werden Alternativen zur Übergabe von Daten an die Threadprozedur erläutert.  
  
## Erstellen eines Threads  
 Beim Erstellen eines neuen <xref:System.Threading.Thread>\-Objekts wird ein neuer verwalteter Thread erstellt.  Die <xref:System.Threading.Thread>\-Klasse verfügt über Konstruktoren, die einen <xref:System.Threading.ThreadStart>\-Delegaten oder einen <xref:System.Threading.ParameterizedThreadStart>\-Delegaten akzeptieren. Der Delegat umschließt die Methode, die beim Aufrufen der <xref:System.Threading.Thread.Start%2A>\-Methode vom neuen Thread aufgerufen wird.  Das mehrfache Aufrufen von <xref:System.Threading.Thread.Start%2A> hat zur Folge, dass <xref:System.Threading.ThreadStateException> ausgelöst wird.  
  
 Die <xref:System.Threading.Thread.Start%2A>\-Methode wird sofort beendet. Häufig geschieht dies, bevor die Ausführung des neuen Threads gestartet wurde.  Sie können die <xref:System.Threading.Thread.ThreadState%2A>\-Eigenschaft oder die <xref:System.Threading.Thread.IsAlive%2A>\-Eigenschaft verwenden, um den Zustand des Threads jederzeit zu bestimmen. Diese Eigenschaften sollten jedoch grundsätzlich nicht dazu verwendet werden, die Aktivitäten der Threads zu synchronisieren.  
  
> [!NOTE]
>  Sobald ein Thread gestartet wird, ist es nicht notwendig, einen Verweis auf das <xref:System.Threading.Thread>\-Objekt beizubehalten.  Der Thread wird bis zum Ende der Threadprozedur fortgesetzt.  
  
 Im folgenden Codebeispiel werden zwei neue Threads erstellt, um Instanz\- und statische Methoden für ein anderes Objekt aufzurufen.  
  
 [!code-cpp[System.Threading.ThreadStart2#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source2.cpp#2)]
 [!code-csharp[System.Threading.ThreadStart2#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source2.cs#2)]
 [!code-vb[System.Threading.ThreadStart2#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source2.vb#2)]  
  
## Übergeben von Daten an Threads und Abrufen von Daten aus Threads  
 In .NET Framework, Version 2.0, bietet der <xref:System.Threading.ParameterizedThreadStart>\-Delegat ein einfaches Verfahren zur Übergabe eines Objekts mit Daten an einen Thread, sobald die Überladung der <xref:System.Threading.Thread.Start%2A?displayProperty=fullName>\-Methode aufgerufen wird.  Ein Codebeispiel finden Sie unter <xref:System.Threading.ParameterizedThreadStart>.  
  
 Die Verwendung des <xref:System.Threading.ParameterizedThreadStart>\-Delegaten ist kein typsicheres Verfahren zur Übergabe von Daten, da die Überladung der <xref:System.Threading.Thread.Start%2A?displayProperty=fullName>\-Methode beliebige Objekte akzeptiert.  Eine Alternative besteht darin, die Threadprozedur und die Daten in einer Hilfsklasse zu kapseln und die Threadprozedur mit dem <xref:System.Threading.ThreadStart>\-Delegaten auszuführen.  Dieses Verfahren wird in den folgenden beiden Codebeispielen veranschaulicht.  
  
 Keiner dieser Delegaten verfügt über einen Rückgabewert, da die Rückgabe der Daten aus einem asynchronen Aufruf nicht vorgesehen ist.  Um die Ergebnisse einer Threadmethode abzurufen, können Sie eine Rückrufmethode verwenden \(siehe zweites Codebeispiel\).  
  
 [!code-cpp[System.Threading.ThreadStart2#3](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source3.cpp#3)]
 [!code-csharp[System.Threading.ThreadStart2#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source3.cs#3)]
 [!code-vb[System.Threading.ThreadStart2#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source3.vb#3)]  
  
### Abrufen von Daten mit Rückrufmethoden  
 Im folgenden Beispiel wird eine Rückrufmethode dargestellt, die Daten aus einem Thread abruft.  Der Konstruktor für die Klasse, der die Daten und die Threadmethode enthält, akzeptiert auch einen Delegaten, der die Rückrufmethode darstellt. Vor dem Ende der Threadmethode ruft er den Rückrufdelegaten auf.  
  
 [!code-cpp[System.Threading.ThreadStart2#4](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CPP/source4.cpp#4)]
 [!code-csharp[System.Threading.ThreadStart2#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Threading.ThreadStart2/CS/source4.cs#4)]
 [!code-vb[System.Threading.ThreadStart2#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Threading.ThreadStart2/VB/source4.vb#4)]  
  
## Siehe auch  
 <xref:System.Threading.Thread>   
 <xref:System.Threading.ThreadStart>   
 <xref:System.Threading.ParameterizedThreadStart>   
 <xref:System.Threading.Thread.Start%2A?displayProperty=fullName>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Using Threads and Threading](../../../docs/standard/threading/using-threads-and-threading.md)