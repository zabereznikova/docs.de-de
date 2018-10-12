---
title: Interlocked-Vorgänge
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Interlocked class, about Interlocked class
- threading [.NET Framework], Interlocked class
ms.assetid: cbda7114-c752-4f3e-ada1-b1e8dd262f2b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 069a95656e7ceaf454c01c47d61ff391bcbed2fe
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46538884"
---
# <a name="interlocked-operations"></a>Interlocked-Vorgänge

Die <xref:System.Threading.Interlocked?displayProperty=nameWithType>-Klasse stellt Methoden bereit, die den Zugriff auf eine Variable synchronisieren, die von mehreren Threads gemeinsam genutzt wird. Threads aus verschiedenen Prozessen können diesen Mechanismus verwenden, wenn sich die Variable im freigegebenen Speicher befindet. Interlocked-Vorgänge sind unteilbare (atomare) Vorgänge: Der gesamte Vorgang ist eine Einheit, die durch einen anderen Vorgang mit derselben Variablen nicht unterbrochen werden kann. Dies ist in Betriebssystemen mit präemptivem Multithreading von Bedeutung, bei denen ein Thread nach dem Laden eines Werts aus einer Speicheradresse unterbrochen werden kann, bevor der Wert geändert oder gespeichert wurde.  
  
 Die <xref:System.Threading.Interlocked>-Klasse bietet folgende Vorgänge:  
  
-   Die <xref:System.Threading.Interlocked.Add%2A?displayProperty=nameWithType>-Methode fügt einer Variablen einen ganzzahligen Wert hinzu und gibt den neuen Wert der Variablen zurück.  
  
-   Die <xref:System.Threading.Interlocked.Read%2A?displayProperty=nameWithType>-Methode liest einen 64-Bit-Ganzzahlwert in einem atomaren Vorgang. Dies ist von Vorteil für 32-Bit-Betriebssysteme, bei denen das Lesen eines 64-Bit-Ganzzahlwerts normalerweise keinen atomaren Vorgang darstellt.  
  
-   Die <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>- und <xref:System.Threading.Interlocked.Decrement%2A?displayProperty=nameWithType>-Methode inkrementieren oder dekrementieren eine Variable und geben den resultierenden Wert zurück.  
  
-   Die <xref:System.Threading.Interlocked.Exchange%2A?displayProperty=nameWithType>-Methode führt einen atomaren Werteaustausch in einer bestimmten Variablen aus. Dabei wird dieser Wert zurückgegeben und durch einen neuen Wert ersetzt. Verwenden Sie eine generische <xref:System.Threading.Interlocked.Exchange%60%601%28%60%600%40%2C%60%600%29>-Überladung dieser Methode, um den Austausch für eine Variable eines beliebigen Verweistyps auszuführen.  
  
-   Die <xref:System.Threading.Interlocked.CompareExchange%2A?displayProperty=nameWithType>-Methode tauscht außerdem zwei Werte aus, jedoch abhängig vom Ergebnis eines Vergleichs. Verwenden Sie eine generische <xref:System.Threading.Interlocked.CompareExchange%60%601%28%60%600%40%2C%60%600%2C%60%600%29>-Überladung dieser Methode, um den Austausch für eine Variable eines beliebigen Verweistyps auszuführen.  
  
 Bei modernen Prozessoren können die Methoden der <xref:System.Threading.Interlocked>-Klasse oft durch eine einzige Anweisung implementiert werden. Sie bieten folglich eine Hochleistungssynchronisierung und können verwendet werden, um Mechanismen für höherstufige Synchronisierung zu erstellen (z.B. Spinlocks).  
  
 Ein Beispiel, in dem die <xref:System.Threading.Monitor>- und <xref:System.Threading.Interlocked>-Klasse in Kombination verwendet werden, finden Sie unter [Monitor-Klasse](https://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db).  
  
## <a name="compareexchange-example"></a>CompareExchange-Beispiel

 Mit der <xref:System.Threading.Interlocked.CompareExchange%2A>-Methode können Sie Berechnungen schützen, die komplexer sind als einfaches Inkrementieren und Dekrementieren. Im folgenden Beispiel wird eine threadsichere Methode dargestellt, durch die einer als Gleitkommazahl gespeicherten laufenden Summe Werte hinzugefügt werden. (Für ganze Zahlen ist die <xref:System.Threading.Interlocked.Add%2A>-Methode eine einfachere Lösung.) Vollständige Codebeispiele finden Sie unter den Überladungen von <xref:System.Threading.Interlocked.CompareExchange%2A>, die Argumente mit einfacher Genauigkeit und Gleitkommaargumente mit doppelter Genauigkeit (<xref:System.Threading.Interlocked.CompareExchange%28System.Single%40%2CSystem.Single%2CSystem.Single%29> und <xref:System.Threading.Interlocked.CompareExchange%28System.Double%40%2CSystem.Double%2CSystem.Double%29>) annehmen.  
  
 [!code-cpp[Conceptual.Interlocked#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Interlocked#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source1.cs#1)]
 [!code-vb[Conceptual.Interlocked#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source1.vb#1)]  
  
## <a name="untyped-overloads-of-exchange-and-compareexchange"></a>Nicht typisierte Überladungen von Exchange und CompareExchange

 Die Methoden <xref:System.Threading.Interlocked.Exchange%2A> und <xref:System.Threading.Interlocked.CompareExchange%2A> verfügen über Überladungen, die Argumente des Typs <xref:System.Object> annehmen. Das erste Argument für jede dieser Überladungen ist `ref Object` (`ByRef … As Object` in Visual Basic). Die Typsicherheit erfordert, dass die an dieses Argument übergebene Variable strikt als <xref:System.Object> typisiert sein muss. Sie können beim Aufruf dieser Methoden das erste Argument nicht ohne Weiteres in den Typ <xref:System.Object> umwandeln.  
  
> [!NOTE]
>  In .NET Framework Version 2.0 und höheren Versionen verwenden Sie die generische Überladung der <xref:System.Threading.Interlocked.Exchange%2A>- und <xref:System.Threading.Interlocked.CompareExchange%2A>-Methode für den Austausch stark typisierter Variablen.  
  
 Das folgende Codebeispiel enthält eine Eigenschaft vom Typ `ClassA`, die nur einmal festgelegt werden kann, da sie möglicherweise in .NET Framework Version 1.0 oder 1.1 implementiert wurde.  
  
 [!code-cpp[Conceptual.Interlocked#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interlocked/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Interlocked#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interlocked/cs/source2.cs#2)]
 [!code-vb[Conceptual.Interlocked#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interlocked/vb/source2.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Interlocked?displayProperty=nameWithType>  
- <xref:System.Threading.Monitor?displayProperty=nameWithType>  
- [Threading](index.md)  
- [Threadingobjekte und -funktionen](threading-objects-and-features.md)
