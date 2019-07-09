---
title: explicit-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 08/24/2018
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: a260c6f1ccac6e09770f1cb8f43d5d872b4b2650
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610099"
---
# <a name="explicit-c-reference"></a>explicit (C#-Referenz)

Das `explicit`-Schlüsselwort deklariert einen benutzerdefinierten Typkonvertierungsoperator, der mit einer Umwandlung aufgerufen werden muss.

Im folgenden Beispiel wird der Operator definiert, der eine Konvertierung aus einer `Fahrenheit`-Klasse in eine `Celsius`-Klasse durchführt. Der Operator muss entweder in einer `Fahrenheit`-Klasse oder in einer `Celsius`-Klasse definiert sein:

[!code-csharp[csrefKeywordsConversion#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#2)]

Rufen Sie den definierten Konvertierungsoperator mit einer Umwandlung ab, wie im folgenden Beispiel dargestellt wird:

[!code-csharp[csrefKeywordsConversion#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#3)]

Der Konvertierungsoperator konvertiert aus einem Quelltyp in einen Zieltyp. Der Quelltyp stellt den Konvertierungsoperator bereit. Im Gegensatz zur impliziten Konvertierung müssen explizite Konvertierungsoperatoren mittels einer Umwandlung aufgerufen werden. Wenn eine Konvertierungsoperation Ausnahmen verursachen oder Informationen verlieren kann, kennzeichnen Sie es mit `explicit`. Dadurch wird verhindert, dass der Compiler den Konvertierungsvorgang mit möglicherweise unerwarteten Folgen aufruft.

Das Auslassen der Umwandlung verursacht den Kompilierzeitfehler CS0266.

Weitere Informationen finden Sie unter [Verwenden von Konvertierungsoperatoren](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine `Fahrenheit`- und `Celsius`-Klasse bereitgestellt, von denen jede einen expliziten Konvertierungsoperator für die andere Klasse bereitstellt.

[!code-csharp[csrefKeywordsConversion#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#1)]

## <a name="example"></a>Beispiel

Das folgende Beispiel definiert eine Struktur, `Digit`, die eine einzelne Dezimalstelle darstellt. Ein Operator ist für die Konvertierungen von `byte` auf `Digit` definiert, aber da nicht alle Bytes in `Digit` konvertiert werden können, ist die Konvertierung explizit.

[!code-csharp[csrefKeywordsConversion#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#4)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [implicit](implicit.md)
- [Operatorüberladung](../operators/operator-overloading.md)
- [Vorgehensweise: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
- [Chained user-defined explicit conversions in C# (Verkettete benutzerdefinierte, explizite Konvertierungen in C#)](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
