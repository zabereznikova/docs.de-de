---
title: "Interlocked-Vorgänge"
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
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 122058b7e826e27fe6c60c5b07610f7c63e64f78
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="interlocked-operations"></a>Interlocked-Vorgänge
Die <xref:System.Threading.Interlocked> Klasse enthält Methoden, die Zugriff auf eine Variable zu synchronisieren, die von mehreren Threads gemeinsam verwendet wird. Threads aus verschiedenen Prozessen können diesen Mechanismus verwenden, wenn sich die Variable im freigegebenen Speicher befindet. Interlocked-Vorgänge sind unteilbare (atomarische) Vorgänge. Der gesamte Vorgang ist eine Einheit, die durch einen anderen Interlocked-Vorgang mit derselben Variablen nicht unterbrochen werden kann. Dies ist in Betriebssystemen mit präemptivem Multithreading von Bedeutung, bei denen ein Thread nach dem Laden eines Werts aus einer Speicheradresse unterbrochen werden kann, bevor der Wert geändert oder gespeichert wurde.  
  
 Die <xref:System.Threading.Interlocked> Klasse bietet die folgenden Vorgänge:  
  
-   In .NET Framework, Version 2.0 die <xref:System.Threading.Interlocked.Add%2A> Methode fügt einen ganzzahligen Wert einer Variablen und gibt den neuen Wert der Variablen zurück.  
  
-   In .NET Framework, Version 2.0 die <xref:System.Threading.Interlocked.Read%2A> Methode liest einen 64-Bit-Ganzzahlwert einer atomaren Operation. Dies ist von Vorteil für 32-Bit-Betriebssysteme, bei denen das Lesen eines 64-Bit-Ganzzahlwerts normalerweise keinen atomaren Vorgang darstellt.  
  
-   Die <xref:System.Threading.Interlocked.Increment%2A> und <xref:System.Threading.Interlocked.Decrement%2A> Methoden inkrementieren oder dekrementieren eine Variable und den resultierenden Wert zurückgeben.  
  
-   Die <xref:System.Threading.Interlocked.Exchange%2A> -Methode führt einen unteilbaren Austauschvorgang des Werts in einer angegebenen Variablen, diesen Wert zurückgeben, und ersetzen es durch einen neuen Wert. In .NET Framework Version 2.0 kann eine generische Überladung dieser Methode verwendet werden, um diesen Austausch für eine Variable eines beliebigen Referenztyps auszuführen. Siehe <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>.  
  
-   Die <xref:System.Threading.Interlocked.CompareExchange%2A> Methode außerdem tauscht zwei Werte jedoch abhängig vom Ergebnis eines Vergleichs. In .NET Framework Version 2.0 kann eine generische Überladung dieser Methode verwendet werden, um diesen Austausch für eine Variable eines beliebigen Referenztyps auszuführen. Siehe <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>.  
  
 Moderne Prozessoren, die Methoden der <xref:System.Threading.Interlocked> -Klasse kann häufig durch eine einzige Anweisung implementiert werden. Sie bieten folglich eine Hochleistungssynchronisierung und können verwendet werden, um Mechanismen für höherstufige Synchronisierung zu erstellen (z.B. Spinlocks).  
  
 Ein Beispiel, verwendet der <xref:System.Threading.Monitor> und <xref:System.Threading.Interlocked> Klassen in Kombination, finden Sie unter [Monitore](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="compareexchange-example"></a>CompareExchange-Beispiel  
 Die <xref:System.Threading.Interlocked.CompareExchange%2A> Methode kann verwendet werden, um Berechnungen zu schützen, die komplizierter als einfache Inkrementieren und dekrementieren. Im folgenden Beispiel wird eine threadsichere Methode dargestellt, durch die einer als Gleitkommazahl gespeicherten laufenden Summe Werte hinzugefügt werden. (Für ganze Zahlen, die <xref:System.Threading.Interlocked.Add%2A> Methode ist eine einfachere Lösung.) Vollständige Codebeispiele finden Sie unter der Überladungen der <xref:System.Threading.Interlocked.CompareExchange%2A> , die Argumente mit einfacher Genauigkeit und mit doppelter Genauigkeit Gleitkomma (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> und <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>).  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a>Nicht typisierte Überladungen von Exchange und CompareExchange  
 Die <xref:System.Threading.Interlocked.Exchange%2A> und <xref:System.Threading.Interlocked.CompareExchange%2A> Methoden verfügen über Überladungen, die Argumente des Typs <xref:System.Object>. Das erste Argument der einzelnen diese Überladungen ist `ref Object` (`ByRef … As Object` in Visual Basic), und typsicherheit erfordert die Variable übergeben, um dieses Argument als streng typisiert werden <xref:System.Object>; Sie können nicht einfach das erste Argument in den Typ umwandeln <xref:System.Object> Wenn diese Methoden aufrufen.  
  
> [!NOTE]
>  In .NET Framework, Version 2.0, verwenden Sie die generische Überladung von der <xref:System.Threading.Interlocked.Exchange%2A> und <xref:System.Threading.Interlocked.CompareExchange%2A> Methoden für den Austausch von stark typisierten Variablen.  
  
 Das folgende Codebeispiel enthält eine Eigenschaft vom Typ `ClassA`, die nur einmal festgelegt werden kann, da sie möglicherweise in .NET Framework Version 1.0 oder 1.1 implementiert wurde.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Interlocked>  
 <xref:System.Threading.Monitor>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)
