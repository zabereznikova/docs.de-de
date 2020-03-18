---
title: Verwenden von Objekten, die IDisposable implementieren
ms.date: 04/07/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
ms.openlocfilehash: c5232aa89064c514e71f3a18bc754159e9c9b15b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160279"
---
# <a name="using-objects-that-implement-idisposable"></a>Verwenden von Objekten, die IDisposable implementieren

Der Garbage Collector der Common Language Runtime gibt den Speicher frei, der von verwalteten Objekten verwendet wird. Typen jedoch, die nicht verwaltete Ressourcen verwenden, implementieren die <xref:System.IDisposable>-Schnittstelle, damit der Speicher, der diesen nicht verwalteten Ressourcen zugeordnet ist, freigegeben werden kann. Wenn Sie ein Objekt, das <xref:System.IDisposable> implementiert, nicht mehr verwenden, sollten Sie die <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung des Objekts aufrufen. Dazu haben Sie zwei Möglichkeiten:  
  
- Verwenden der `using`-Anweisung in C# oder der `Using`-Anweisung in Visual Basic.  
  
- Implementieren eines `try/finally`-Blocks.  

## <a name="the-using-statement"></a>Die using-Anweisung

Die `using`-Anweisung in C# und die `Using`-Anweisung in Visual Basic vereinfachen den Code, den Sie schreiben müssen, um ein Objekt zu erstellen und zu bereinigen. Die `using`-Anweisung ruft eine oder mehrere Ressourcen ab, führt die von Ihnen angegebenen Anweisungen aus und verwirft dann das Objekt automatisch. Die `using`-Anweisung ist jedoch nur hilfreich bei Objekten, die im Bereich der Methode verwendet werden, in der sie erstellt werden.  
  
Im folgenden Beispiel wird die `using`-Anweisung verwendet, um ein <xref:System.IO.StreamReader?displayProperty=nameWithType>-Objekt zu erstellen und freizugeben.  
  
[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]  
  
Beachten Sie Folgendes: Obwohl die <xref:System.IO.StreamReader>-Klasse die <xref:System.IDisposable>-Schnittstelle implementiert, die angibt, dass sie eine nicht verwaltete Ressource verwendet, wird in dem Beispiel nicht explizit die <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType>-Methode aufgerufen. Wenn der C#- oder Visual Basic-Compiler die `using`-Anweisung findet, gibt er Zwischensprache (Intermediate Language, IL) aus, die dem folgenden Code entspricht, der explizit einen `try/finally`-Block enthält.  
  
[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]  
  
Mit der `using`-Anweisung in C# können Sie auch mehrere Ressourcen in einer einzigen Anweisung abrufen. Intern entspricht dies geschachtelten `using`-Anweisungen. Im folgenden Beispiel werden zwei <xref:System.IO.StreamReader>-Objekte instanziiert, um den Inhalt von zwei verschiedenen Dateien zu lesen.  
  
[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a>Try-/Finally-Block

Anstatt einen `try/finally`-Block in einer `using`-Anweisung zu umschließen, haben Sie die Möglichkeit, den `try/finally`-Block direkt zu implementieren. Dies kann Ihr persönlicher Codierungsstil sein, oder Sie möchten dies eventuell aus einem der folgenden Gründe durchführen:  
  
- Um einen `catch`-Block einzufügen, um im `try`-Block ausgelöste Ausnahmen zu behandeln. Andernfalls bleiben alle Ausnahmen, die von der `using`-Anweisung ausgelöst werden, unbehandelt, so wie Ausnahmen, die innerhalb des `using`-Blocks ausgelöst werden, wenn kein `try/catch`-Block vorhanden ist.  
  
- Um ein Objekt zu instanziieren, das <xref:System.IDisposable> implementiert, dessen Bereich für den Block, in dem es deklariert ist, nicht lokal ist.  
  
Das folgende Beispiel ähnelt dem vorhergehenden, es wird jedoch ein `try/catch/finally`-Block verwendet, um ein <xref:System.IO.StreamReader>-Objekt zu instanziieren, zu verwenden und zu verwerfen, und um alle Ausnahmen zu behandeln, die von dem <xref:System.IO.StreamReader>-Konstruktor und dessen <xref:System.IO.StreamReader.ReadToEnd%2A>-Methode ausgelöst werden. Beachten Sie, dass der Code im `finally`-Block überprüft, ob das Objekt, das <xref:System.IDisposable> implementiert, nicht `null` ist, bevor die <xref:System.IDisposable.Dispose%2A>-Methode aufgerufen wird. Wird dies nicht ausgeführt, kann es zu einer <xref:System.NullReferenceException>-Ausnahme zur Laufzeit kommen.  
  
[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]  
  
Sie können dieses grundlegende Muster beibehalten, wenn Sie einen `try/finally`-Block implementieren möchten oder müssen, da Ihre Programmiersprache eine `using`-Anweisung nicht unterstützt, jedoch direkte Aufrufe der <xref:System.IDisposable.Dispose%2A>-Methode erlaubt.
  
## <a name="see-also"></a>Weitere Informationen

- [Bereinigen von nicht verwalteten Ressourcen](../../../docs/standard/garbage-collection/unmanaged.md)
- [using-Anweisung (C#-Referenz)](../../csharp/language-reference/keywords/using-statement.md)
- [Using-Anweisung (Visual Basic)](../../visual-basic/language-reference/statements/using-statement.md)
