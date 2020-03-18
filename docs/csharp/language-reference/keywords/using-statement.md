---
title: using-Anweisung – C#-Referenz
ms.date: 10/15/2019
helpviewer_keywords:
- using statement [C#]
ms.assetid: afc355e6-f0b9-4240-94dd-0d93f17d9fc3
ms.openlocfilehash: 52cde99fd029ce50f159b2a87fbfbf47fc79dccc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712961"
---
# <a name="using-statement-c-reference"></a>using-Anweisung (C#-Referenz)

Bietet eine praktische Syntax, die den ordnungsgemäßen Einsatz von <xref:System.IDisposable>-Objekten sicherstellt

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie Sie die Anweisung `using` verwenden.

[!code-csharp[csrefKeywordsNamespace#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#4)]

Ab C# 8,0 können Sie die folgende alternative Syntax für die `using`-Anweisung verwenden, die keine geschweiften Klammern erfordert:

[!code-csharp[csrefKeywordsNamespace#New](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#ModernUsing)]

## <a name="remarks"></a>Hinweise

<xref:System.IO.File> und <xref:System.Drawing.Font> sind Beispiele für verwaltete Typen, die auf nicht verwaltete Ressourcen zugreifen (in diesem Fall Dateihandles und Gerätekontexte). Es gibt viele andere Arten von nicht verwalteten Ressourcen und Klassenbibliothekstypen, die sie einschließen. Alle Typen dieser Art müssen die <xref:System.IDisposable>-Schnittstelle implementieren.

Wenn die Lebensdauer eines `IDisposable`-Objekts auf eine einzige Methode beschränkt ist, sollten Sie es in der `using`-Anweisung deklarieren und instanziieren. Die `using`-Anweisung ruft die Methode <xref:System.IDisposable.Dispose%2A> ordnungsgemäß für das Objekt auf. Wenn Sie sie, wie vorher gezeigt, verwenden, führt dies auch dazu, dass das Objekt den gültigen Bereich verlässt, sobald <xref:System.IDisposable.Dispose%2A> aufgerufen wird. Innerhalb des `using`-Blocks ist das Objekt schreibgeschützt und kann nicht geändert oder neu zugewiesen werden.

Mit der Anweisung `using` wird sichergestellt, dass <xref:System.IDisposable.Dispose%2A> aufgerufen wird, selbst wenn eine Ausnahme im `using`-Block auftritt. Sie können das gleiche Ergebnis erzielen, indem Sie das Objekt in einen `try`-Block einfügen und dann <xref:System.IDisposable.Dispose%2A> in einem `finally`-Block aufrufen. So übersetzt der Compiler die Anweisung `using`. Das vorherige Codebeispiel wird zur Kompilierzeit auf den folgenden Code erweitert (beachten Sie die zusätzlichen geschweiften Klammern zum Erstellen des eingeschränkten Gültigkeitsbereichs für das Objekt):

[!code-csharp[csrefKeywordsNamespace#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#5)]

Die neuere Syntax der `using`-Anweisung wird in sehr ähnlichen Code übersetzt. Der `try`-Block wird geöffnet, in dem die Variable deklariert wird. Der `finally`-Block wird am Ende des einschließenden Blocks hinzugefügt, in der Regel am Ende einer Methode.

Weitere Informationen über die Anweisung `try`-`finally` finden Sie im Artikel zu [try-finally](try-finally.md).

Wie im folgenden Beispiel gezeigt, können mehrere Instanzen eines Typs in einer `using`-Anweisung deklariert werden:

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#6)]

Sie können auch mehrere Deklarationen desselben Typs mithilfe der neuen Syntax kombinieren, die mit C# 8 eingeführt wurde. Dies wird im folgenden Beispiel gezeigt:

[!code-csharp[csrefKeywordsNamespace#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#MultipleUsing)]

Sie können das Ressourcenobjekt instanziieren und die Variable an die `using`-Anweisung übergeben; dies wird jedoch nicht empfohlen. In diesem Fall verbleibt das Objekt im Gültigkeitsbereich, nachdem das Steuerelement den `using`-Block verlassen hat, obwohl es wahrscheinlich keinen Zugriff auf dessen nicht verwaltete Ressourcen hat. Das heißt, dass es nicht mehr vollständig initialisiert wird. Wenn Sie versuchen, das Objekt außerhalb des `using`-Blocks zu verwenden, riskieren Sie, dass eine Ausnahme ausgelöst wird. Aus diesem Grund ist es im Allgemeinen besser, das Objekt in der `using`-Anweisung zu instanziieren und dessen Bereich auf den `using`-Block zu begrenzen.

[!code-csharp[csrefKeywordsNamespace#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsNamespace/CS/csrefKeywordsNamespace.cs#7)]

Weitere Informationen zum Verwerfen von `IDisposable`-Objekten finden Sie unter [Verwenden von Objekten, die IDisposable implementieren](../../../standard/garbage-collection/using-objects.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie unter [Die using-Anweisung](~/_csharplang/spec/statements.md#the-using-statement) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [using-Direktive](using-directive.md)
- [Garbage Collection](../../../standard/garbage-collection/index.md)
- [Verwenden von Objekten, die IDisposable implementieren](../../../standard/garbage-collection/using-objects.md)
- [IDisposable-Schnittstelle](xref:System.IDisposable)
- [using-Anweisung in C# 8.0](~/_csharplang/proposals/csharp-8.0/using.md)
