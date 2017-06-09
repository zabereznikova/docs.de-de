---
title: "How to: Iterate File Directories with PLINQ | Microsoft Docs"
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
  - "PLINQ queries, how to iterate directories"
ms.assetid: 354e8ce3-35c4-431c-99ca-7661d1f3901b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# How to: Iterate File Directories with PLINQ
In diesem Beispiel werden zwei einfache Möglichkeiten gezeigt, Vorgänge für Dateiverzeichnisse zu parallelisieren.  Die erste Abfrage verwendet die <xref:System.IO.Directory.GetFiles%2A>\-Methode, um ein Array von Dateinamen in einem Verzeichnis und allen Unterverzeichnissen aufzufüllen.  Diese Methode wird erst zurückgegeben, wenn das gesamte Array aufgefüllt ist. Daher kann zu Beginn des Vorgangs Wartezeit auftreten.  Nachdem das Array aufgefüllt wurde, kann es jedoch sehr schnell von PLINQ parallel verarbeitet werden.  
  
 In der zweiten Abfrage werden die statische <xref:System.IO.Directory.EnumerateDirectories%2A>\-Methode und die statische <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>\-Methode verwendet, die sofort Ergebnisse zurückgeben.  Dieser Ansatz kann schneller sein, wenn umfangreiche Verzeichnisstrukturen durchlaufen werden, obwohl im Gegensatz zum ersten Beispiel die Verarbeitungszeit von vielen Faktoren abhängen kann.  
  
> [!WARNING]
>  Diese Beispiele sollen die Verwendung veranschaulichen, und sie werden möglicherweise nicht schneller als die entsprechende sequenzielle LINQ to Objects\-Abfrage ausgeführt.  Weitere Informationen über Geschwindigkeitssteigerungen finden Sie unter [Understanding Speedup in PLINQ](../../../docs/standard/parallel-programming/understanding-speedup-in-plinq.md).  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie in einfachen Szenarien, in denen Sie Zugriff auf alle Verzeichnisse in der Struktur haben, die Dateien nicht sehr groß sind und die Zugriffszeit nicht erheblich ist, Dateiverzeichnisse durchlaufen werden.  Diese Vorgehensweise beinhaltet Wartezeit zu Beginn, während das Array von Dateinamen erstellt wird.  
  
 [!code-csharp[PLINQ#33](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#33)]  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie in einfachen Szenarien, in denen Sie Zugriff auf alle Verzeichnisse in der Struktur haben, die Dateien nicht sehr groß sind und die Zugriffszeit nicht erheblich ist, Dateiverzeichnisse durchlaufen werden.  Bei dieser Vorgehensweise werden Ergebnisse schneller als beim vorherigen Beispiel erzeugt.  
  
 [!code-csharp[PLINQ#34](../../../samples/snippets/csharp/VS_Snippets_Misc/plinq/cs/plinqfileiteration.cs#34)]  
  
 Wenn Sie <xref:System.IO.Directory.GetFiles%2A> verwenden, stellen Sie sicher, dass Sie über ausreichende Berechtigungen für alle Verzeichnisse in der Struktur verfügen.  Andernfalls wird eine Ausnahme ausgelöst, und es werden keine Ergebnisse zurückgegeben.  Bei Verwendung von <xref:System.IO.Directory.EnumerateDirectories%2A> in einer PLINQ\-Abfrage ist es schwierig, E\/A\-Ausnahmen ordnungsgemäß zu behandeln, damit die Iteration fortgesetzt werden kann.  Wenn der Code E\/A\-Ausnahmen oder Ausnahmen aufgrund von unberechtigtem Zugriff behandeln muss, sollten Sie die in [Gewusst wie: Iterieren von Dateiverzeichnissen der Parallel\-Klasse](../../../docs/standard/parallel-programming/how-to-iterate-file-directories-with-the-parallel-class.md) beschriebene Vorgehensweise verwenden.  
  
 Wenn E\/A\-Wartezeit ein Problem ist, beispielsweise bei Datei\-E\/A in einem Netzwerk, können Sie, eines der Verfahren für asynchrone E\/A verwenden, die in [TPL and Traditional .NET Framework Asynchronous Programming](../../../docs/standard/parallel-programming/tpl-and-traditional-async-programming.md) und in beschrieben werden [Blogbeitrag](http://go.microsoft.com/fwlink/?LinkID=186458).  
  
## Siehe auch  
 [Parallel LINQ \(PLINQ\)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)