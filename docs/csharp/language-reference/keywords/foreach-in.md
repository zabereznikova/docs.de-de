---
title: foreach-Anweisung in C#
ms.date: 06/29/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: d84c68eb102d55b31ba20a6b6b5c01b96963924d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524248"
---
# <a name="foreach-in-c-reference"></a>foreach, in (C#-Referenz)

Die Anweisung `foreach` führt eine Anweisung oder einen Block von Anweisungen für jedes Element in einer Instanz des Typs aus, der die Schnittstelle <xref:System.Collections.IEnumerable?displayProperty=nameWithType> oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> implementiert. Die Anweisung `foreach` ist nicht auf diese Typen beschränkt und kann auf eine Instanz eines beliebigen Typs angewendet werden, der die folgenden Bedingungen erfüllt:

- Er weist die öffentliche parameterlose Methode `GetEnumerator` auf, deren Rückgabetyp entweder Klasse, Struktur oder Schnittstellentyp ist.
- Der Rückgabetyp der Methode `GetEnumerator` weist die öffentliche Eigenschaft `Current` und die öffentliche parameterlose Methode `MoveNext` auf, deren Rückgabetyp <xref:System.Boolean> ist.

Sie können die Schleife an jedem Punkt im `foreach`-Anweisungsblock mit der Anweisung [break](break.md) unterbrechen oder mit der Anweisung [continue](continue.md) direkt zum nächsten Durchlauf der Schleife springen. Sie können eine `foreach`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.

## <a name="examples"></a>Beispiele

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

Das folgende Beispiel zeigt die Syntax der Anweisung `foreach` mit einer Instanz des Typs <xref:System.Collections.Generic.List%601>, der die Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> implementiert:

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

Im nächste Beispiel wird die Anweisung `foreach` mit einer Instanz des Typs <xref:System.Span%601?displayProperty=nameWithType> verwendet, der keine Schnittstellen implementiert:

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

Ab C# 7.3 können Sie die Iterationsvariable mit den Modifizierern `ref` oder `ref readonly` deklarieren, wenn die `Current`-Eigenschaft des Enumerators einen [Verweisrückgabewert](../../programming-guide/classes-and-structs/ref-returns.md) (`ref T`, wobei `T` dem Typ des Auflistungselements entspricht) zurückgibt. Im folgenden Beispiel wird eine `ref`-Iterationsvariable verwendet, um die Werte der Elemente in einem stackalloc-Array festzulegen. Die Version `ref readonly` durchläuft die Auflistung, um alle Werte auszugeben. Die `readonly`-Deklaration verwendet eine implizite lokale Variablendeklaration. Implizite Variablendeklarationen können wie explizit typisierte Variablendeklarationen mit `ref`- oder `ref readonly`-Deklarationen verwendet werden.

[!code-csharp-interactive[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [Die foreach-Anweisung (C#-Spezifikation)](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)
- [Verwenden von foreach mit Arrays](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [for](for.md)
- [Iterationsanweisungen](iteration-statements.md)
- [C#-Schlüsselwörter](index.md)
- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
