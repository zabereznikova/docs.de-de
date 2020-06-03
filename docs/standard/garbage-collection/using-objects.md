---
title: Verwenden von Objekten, die IDisposable implementieren
ms.date: 05/13/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- try/finally block
- garbage collection, encapsulating resources
ms.assetid: 81b2cdb5-c91a-4a31-9c83-eadc52da5cf0
ms.openlocfilehash: 87eefe2bd347ba1564b2f06d49bbee3b85efdb97
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287596"
---
# <a name="using-objects-that-implement-idisposable"></a>Verwenden von Objekten, die IDisposable implementieren

Der Garbage Collector der Common Language Runtime gibt den Speicher frei, der von verwalteten Objekten verwendet wird. Typen jedoch, die nicht verwaltete Ressourcen verwenden, implementieren die <xref:System.IDisposable>-Schnittstelle, damit die Ressourcen, die von diesen nicht verwalteten Ressourcen benötigt werden, freigegeben werden können. Wenn Sie ein Objekt, das <xref:System.IDisposable> implementiert, nicht mehr verwenden, sollten Sie die <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>-Implementierung des Objekts aufrufen. Dazu haben Sie zwei Möglichkeiten:

- Mit der C#-Anweisung `using` (`Using` in Visual Basic).
- Durch Implementieren eines `try/finally`-Blocks und Aufrufen von <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> in `finally`.

## <a name="the-using-statement"></a>Die using-Anweisung

Die [`using`-Anweisung](../../csharp/language-reference/keywords/using-statement.md) in C# und die [`Using`-Anweisung](../../visual-basic/language-reference/statements/using-statement.md) in Visual Basic vereinfachen den Code, den Sie schreiben müssen, um ein Objekt zu bereinigen. Die `using`-Anweisung ruft eine oder mehrere Ressourcen ab, führt die von Ihnen angegebenen Anweisungen aus und verwirft dann das Objekt automatisch. Die `using`-Anweisung ist jedoch nur hilfreich bei Objekten, die im Bereich der Methode verwendet werden, in der sie erstellt werden.

Im folgenden Beispiel wird die `using`-Anweisung verwendet, um ein <xref:System.IO.StreamReader?displayProperty=nameWithType>-Objekt zu erstellen und freizugeben.

[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using1.vb#1)]

Obwohl die <xref:System.IO.StreamReader>-Klasse die <xref:System.IDisposable>-Schnittstelle implementiert, die angibt, dass sie eine nicht verwaltete Ressource verwendet, wird in dem Beispiel nicht explizit die <xref:System.IO.StreamReader.Dispose%2A?displayProperty=nameWithType>-Methode aufgerufen. Wenn der C#- oder Visual Basic-Compiler die `using`-Anweisung findet, gibt er Zwischensprache (Intermediate Language, IL) aus, die dem folgenden Code entspricht, der explizit einen `try/finally`-Block enthält.

[!code-csharp[Conceptual.Disposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using3.cs#3)]
[!code-vb[Conceptual.Disposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using3.vb#3)]

Mit der `using`-Anweisung in C# können Sie auch mehrere Ressourcen in einer einzigen Anweisung abrufen. Intern entspricht dies geschachtelten `using`-Anweisungen. Im folgenden Beispiel werden zwei <xref:System.IO.StreamReader>-Objekte instanziiert, um den Inhalt von zwei verschiedenen Dateien zu lesen.

[!code-csharp[Conceptual.Disposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using4.cs#4)]

## <a name="tryfinally-block"></a>Try-/Finally-Block

Anstatt einen `try/finally`-Block in einer `using`-Anweisung zu umschließen, haben Sie die Möglichkeit, den `try/finally`-Block direkt zu implementieren. Dies kann Ihr persönlicher Codierungsstil sein, oder Sie möchten dies eventuell aus einem der folgenden Gründe durchführen:

- Um einen `catch`-Block einzufügen, um im `try`-Block ausgelöste Ausnahmen zu behandeln. Andernfalls werden alle in der `using`-Anweisung ausgelösten Ausnahmen nicht behandelt.

- Um ein Objekt zu instanziieren, das <xref:System.IDisposable> implementiert, dessen Bereich für den Block, in dem es deklariert ist, nicht lokal ist.

Das folgende Beispiel ähnelt dem vorhergehenden, es wird jedoch ein `try/catch/finally`-Block verwendet, um ein <xref:System.IO.StreamReader>-Objekt zu instanziieren, zu verwenden und zu verwerfen, und um alle Ausnahmen zu behandeln, die von dem <xref:System.IO.StreamReader>-Konstruktor und dessen <xref:System.IO.StreamReader.ReadToEnd%2A>-Methode ausgelöst werden. Der Code im `finally`-Block überprüft, ob das Objekt, das <xref:System.IDisposable> implementiert, nicht `null` ist, bevor die <xref:System.IDisposable.Dispose%2A>-Methode aufgerufen wird. Wird dies nicht ausgeführt, kann es zu einer <xref:System.NullReferenceException>-Ausnahme zur Laufzeit kommen.

[!code-csharp[Conceptual.Disposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/using5.cs#6)]
[!code-vb[Conceptual.Disposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/using5.vb#6)]

Sie können dieses grundlegende Muster beibehalten, wenn Sie einen `try/finally`-Block implementieren möchten oder müssen, da Ihre Programmiersprache eine `using`-Anweisung nicht unterstützt, jedoch direkte Aufrufe der <xref:System.IDisposable.Dispose%2A>-Methode erlaubt.

## <a name="idisposable-instance-members"></a>IDisposable-Instanzmember

Wenn eine Klasse eine <xref:System.IDisposable>-Implementierung als Instanzmember enthält, entweder ein Feld oder eine Eigenschaft, sollte die Klasse auch <xref:System.IDisposable> implementieren. Weitere Informationen finden Sie unter [Weitergeben von Dispose-Aufrufen](implementing-dispose.md#cascade-dispose-calls).

## <a name="see-also"></a>Siehe auch

- [Bereinigen von nicht verwalteten Ressourcen](unmanaged.md)
- [using-Anweisung (C#-Referenz)](../../csharp/language-reference/keywords/using-statement.md)
- [Using-Anweisung (Visual Basic)](../../visual-basic/language-reference/statements/using-statement.md)
