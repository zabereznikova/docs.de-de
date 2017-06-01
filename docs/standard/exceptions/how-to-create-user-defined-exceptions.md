---
title: "Gewusst wie: Erstellen benutzerdefinierter Ausnahmen | Microsoft Docs"
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
  - "Ausnahmen, Beispiele"
  - "Ausnahmen, Benutzerdefiniert"
  - "Benutzerdefinierte Ausnahmen"
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 8
---
# Gewusst wie: Erstellen benutzerdefinierter Ausnahmen
Wenn Benutzer in der Lage sein sollen, programmgesteuert zwischen mehreren Fehlerzuständen zu unterscheiden, können Sie Ihre eigenen benutzerdefinierten Ausnahmen erstellen.  .NET Framework stellt eine Hierarchie von Ausnahmeklassen bereit, die letztlich alle von der Basisklasse <xref:System.Exception> abgeleitet werden.  Jede dieser Klassen definiert eine spezifische Ausnahme, sodass Sie in vielen Fällen nur noch die jeweilige Ausnahme abfangen müssen.  Sie können auch Ihre eigenen Ausnahmeklassen durch Ableitung von der <xref:System.Exception>\-Klasse erstellen.  
  
 Beim Erstellen eigener Ausnahmen ist es sinnvoll, deren Klassennamen auf das Wort "Exception" enden zu lassen. Außerdem ist es ratsam, die im folgenden Beispiel gezeigten drei empfohlenen allgemeinen Konstruktoren zu implementieren.  
  
> [!NOTE]
>  Wenn Sie Remoting verwenden, müssen Sie sicherstellen, dass die Metadaten für alle benutzerdefinierten Ausnahmen auf dem Server \(der aufgerufen wird\) und für den Client \(Proxyobjekt oder Aufrufer\) verfügbar sind.  Zum Beispiel muss Code, durch den eine Methode in einer anderen Anwendungsdomäne aufgerufen wird, die Assembly finden können, in der die durch einen Remoteaufruf ausgelöste Ausnahme enthalten ist.  Weitere Informationen finden Sie unter [Empfohlene Vorgehensweise für die Ausnahmebehandlung](../../../docs/standard/exceptions/best-practices-for-exceptions.md).  
  
 Im folgenden Beispiel wird die neue Ausnahmeklasse `EmployeeListNotFoundException` von der <xref:System.Exception> abgeleitet.  In der Klasse werden drei Konstruktoren definiert, jeder mit anderen Parametern.  
  
## Beispiel  
 [!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
 [!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
 [!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  
  
## Siehe auch  
 [Gewusst wie: Verwenden des Try\-Catch\-Blocks zum Abfangen von Ausnahmen](../../../docs/standard/exceptions/how-to-use-the-try-catch-block-to-catch-exceptions.md)   
 [Gewusst wie: Verwenden spezifischer Ausnahmen in einem Catch\-Block](../../../docs/standard/exceptions/how-to-use-specific-exceptions-in-a-catch-block.md)   
 [Best Practices für Ausnahmen](../../../docs/standard/exceptions/best-practices-for-exceptions.md)   
 [Grundlagen der Ausnahmebehandlung](../../../docs/standard/exceptions/exception-handling-fundamentals.md)