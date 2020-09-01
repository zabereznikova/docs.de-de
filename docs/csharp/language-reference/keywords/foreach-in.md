---
description: foreach, in (C#-Referenz)
title: foreach-Anweisung in C#
ms.date: 07/22/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 2ed89fa52b2d3d369d668bf79ab32eaf7be18a8a
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142075"
---
# <a name="foreach-in-c-reference"></a>foreach, in (C#-Referenz)

Die Anweisung `foreach` führt eine Anweisung oder einen Block von Anweisungen für jedes Element in einer Instanz des Typs aus, der die Schnittstellen <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> implementiert. Dies wird im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

Die Anweisung `foreach` ist nicht auf diese Typen beschränkt. Sie können sie mit einer Instanz eines beliebigen Typs verwenden, der die folgenden Bedingungen erfüllt:

- Ein Typ weist die öffentliche parameterlose Methode `GetEnumerator` auf, deren Rückgabetyp entweder eine Klasse, eine Struktur oder ein Schnittstellentyp ist.
- Der Rückgabetyp der Methode `GetEnumerator` weist die öffentliche Eigenschaft `Current` und die öffentliche parameterlose Methode `MoveNext` auf, deren Rückgabetyp <xref:System.Boolean> ist.

Im folgenden Beispiel wird die Anweisung `foreach` mit einer Instanz des Typs <xref:System.Span%601?displayProperty=nameWithType> verwendet, der keine Schnittstellen implementiert:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

Ab C# 7.3 können Sie die Iterationsvariable mit den Modifizierern `ref` oder `ref readonly` deklarieren, wenn die Eigenschaft `Current` des Enumerators einen [Verweisrückgabewert](ref.md#reference-return-values) (`ref T`, wobei `T` dem Typ des Sammlungselements entspricht) zurückgibt. Dies wird im folgenden Beispiel gezeigt:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

Ab C# 8.0 können Sie die Anweisung `await foreach` verwenden, um einen asynchronen Datenstrom zu verarbeiten, also den Sammlungstyp, der die Schnittstelle <xref:System.Collections.Generic.IAsyncEnumerable%601> implementiert. Jede Iteration der Schleife kann unterbrochen werden, während das nächste Element asynchron abgerufen wird. Im folgenden Beispiel wird veranschaulicht, wie Sie die Anweisung `await foreach` verwenden:

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

Standardmäßig werden Streamelemente im erfassten Kontext verarbeitet. Wenn Sie die Erfassung des Kontexts deaktivieren möchten, verwenden Sie die Erweiterungsmethode <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType>. Weitere Informationen über Synchronisierungskontexte und die Erfassung des aktuellen Kontexts finden Sie im Artikel [Verwenden des aufgabenbasierten asynchronen Musters](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md). Weitere Informationen finden Sie im Abschnitt [Asynchrone Datenströme](../../whats-new/csharp-8.md#asynchronous-streams) des Artikels [Neues in C# 8.0](../../whats-new/csharp-8.md).

Sie können die Schleife an jedem Punkt im `foreach`-Anweisungsblock mit der Anweisung [break](break.md) unterbrechen oder mit der Anweisung [continue](continue.md) direkt zum nächsten Durchlauf der Schleife springen. Sie können eine `foreach`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.

Wenn die `foreach`-Anweisung auf `null` angewendet wird, wird <xref:System.NullReferenceException> ausgelöst. Falls die Quellsammlung der `foreach`-Anweisung leer ist, wird der Text der `foreach`-Schleife nicht ausgeführt und übersprungen.

## <a name="type-of-an-iteration-variable"></a>Typ einer Iterationsvariablen

Sie können das Schlüsselwort `var` verwenden, damit der Compiler den Typ einer Iterationsvariablen in der Anweisung `foreach` ableiten kann. Dies wird im folgenden Code gezeigt:

```csharp
foreach (var item in collection) { }
```

Sie können auch wie im folgenden Code explizit den Typ einer Iterationsvariablen angeben:

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

Im obigen Formular muss der Typ `T` eines Sammlungselements implizit oder explizit in Typ `V` einer Iterationsvariablen konvertierbar sein. Wenn eine explizite Konvertierung von `T` in `V` zur Laufzeit fehlschlägt, löst die Anweisung `foreach` eine <xref:System.InvalidCastException> aus. Wenn `T` z. B. ein nicht versiegelter Klassentyp ist, kann `V` ein beliebiger Schnittstellentyp sein – sogar der Typ, den `T` nicht implementiert. Zur Laufzeit kann der Typ eines Sammlungselements der Typ sein, der von `T` abgeleitet wird und `V` implementiert. Wenn dies nicht der Fall ist, wird eine <xref:System.InvalidCastException> ausgelöst.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Die foreach-Anweisung](~/_csharplang/spec/statements.md#the-foreach-statement) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Schlüsselwörter](index.md)
- [Verwenden von foreach mit Arrays](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [for-Anweisung](for.md)
