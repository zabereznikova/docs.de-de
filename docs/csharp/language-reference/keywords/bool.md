---
title: bool-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- bool_CSharpKeyword
- bool
helpviewer_keywords:
- bool keyword [C#]
ms.assetid: 551cfe35-2632-4343-af49-33ad12da08e2
ms.openlocfilehash: 958b58b31193dbf4c03709e4ab7ba38f7f30e0ac
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590479"
---
# <a name="bool-c-reference"></a>bool (C#-Referenz)

Das Schlüsselwort `bool` ist ein Alias von <xref:System.Boolean?displayProperty=nameWithType>. Es wird zur Deklaration von Variablen zur Speicherung der booleschen Werte [TRUE](true-literal.md) und [FALSE](false-literal.md) verwendet.

> [!NOTE]
> Wenn Sie einen booleschen Wert benötigen, der auch einen Wert von `null` aufweisen kann, verwenden Sie `bool?`. Weitere Informationen finden Sie im Abschnitt [Der „bool?“-Typ](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) im Artikel [Verwenden von Typen mit Nullwert](../../programming-guide/nullable-types/using-nullable-types.md).

## <a name="literals"></a>Literale

Sie können einer `bool`-Variablen einen booleschen Wert zuweisen. Sie können außerdem einer `bool`-Variablen einen Ausdruck, der `bool` ergibt, zuweisen.

[!code-csharp[csrefKeywordsTypes#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#1)]

Der Standardwert einer `bool`-Variablen ist `false`. Der Standardwert einer `bool?`-Variablen ist `null`.

## <a name="conversions"></a>Konvertierungen

Der Wert des Typs `bool` kann in C++ in einen Wert des Typs `int` konvertiert werden, d.h. `false` entspricht null und `true` entspricht einem Wert ungleich null. In C# gibt es keine Konvertierung von Typ `bool` und anderen Typen. Beispielsweise ist die folgende `if`-Anweisung in C# unzulässig:

[!code-csharp[csrefKeywordsTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#2)]

Um eine Variable des Typs `int` zu testen, müssen Sie sie explizit mit einem Wert, wie z.B. null, vergleichen:

[!code-csharp[csrefKeywordsTypes#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#3)]

## <a name="example"></a>Beispiel

In diesem Beispiel geben Sie ein Zeichen über die Tastatur ein, und das Programm prüft, ob es sich bei dem eingegebene Zeichen um einen Buchstaben handelt. Wenn es sich um einen Buchstaben handelt, wird geprüft, ob er groß oder klein geschrieben ist. Dies wird mit <xref:System.Char.IsLetter%2A> und <xref:System.Char.IsLower%2A> geprüft, die beiden den Typ `bool` zurückgeben:

[!code-csharp[csrefKeywordsTypes#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#4)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../../csharp/language-reference/index.md)
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)
- [Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md)
- [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
