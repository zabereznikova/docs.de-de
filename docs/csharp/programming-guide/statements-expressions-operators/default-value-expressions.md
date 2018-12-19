---
title: Standardwertausdrücke – C#-Programmierhandbuch
ms.custom: seodec18
description: Standardwertausdrücke erzeugen den Standardwert für jeden Verweistyp oder Werttyp.
ms.date: 04/25/2018
helpviewer_keywords:
- generics [C#], default keyword
- default keyword [C#], generic programming
ms.openlocfilehash: 4b14714a55f77763425299ffc13ba579ead57810
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53237284"
---
# <a name="default-value-expressions-c-programming-guide"></a>Standardwertausdrücke (C#-Programmierhandbuch)

Ein Standardwertausdruck `default(T)` erzeugt den Standardwert für einen Typ `T`. In der folgenden Tabelle wird dargestellt, welche Werte für verschiedene Typen erstellt werden:

|Typ|Standardwert|
|---------|---------|
|Verweistyp|`null`|
|Numerischer Werttyp|Zero|
|[bool](../../language-reference/keywords/bool.md)|`false`|
|[char](../../language-reference/keywords/char.md)|`'\0'`|
|[enum](../../language-reference/keywords/enum.md)|Der Wert, der vom Ausdruck `(E)0` erzeugt wird, bei dem `E` der Enumerationsbezeichner ist.|
|[struct](../../language-reference/keywords/struct.md)|Der Wert, der erzeugt wird, indem alle Werttypfelder auf ihre Standardwerte und alle Verweistypfelder auf `null` festgelegt werden.|
|Nullable-Typ|Eine Instanz, für die die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft `false` und die <xref:System.Nullable%601.Value%2A>-Eigenschaft nicht definiert ist.|

Standardwertausdrücke sind besonders nützlich in generischen Klassen und Methoden. Das Zuweisen eines Standardwerts zu einem parametrisierten Typ `T` wird beim Verwenden von Generika erschwert, wenn folgende Punkte im Voraus noch unklar sind:

- Ob `T` ein Verweistyp oder ein Werttyp ist.
- Wenn `T` ein Werttyp ist, unabhängig davon, ob es ein numerischer Wert oder eine Struktur ist.

 Angenommen, dass eine Variable `t` vom parametrisierten Typ `T` vorliegt, ist die Anweisung `t = null` nur gültig, wenn `T` ein Verweistyp ist. Die Zuweisung `t = 0` funktioniert nur für numerische Werttypen, nicht aber für Strukturen. Verwenden Sie einen Standardwertausdruck, um dieses Problem zu lösen:

```csharp
T t = default(T);
```

Der Ausdruck `default(T)` ist nicht auf generische Klassen und Methoden beschränkt. Standardwertausdrücke können mit jedem verwalteten Typ verwendet werden. Jeder der folgenden Ausdrücke ist gültig:

 [!code-csharp[csProgGuideGenerics#1](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-value-expressions.cs)]

 Im folgenden Beispiel aus der Klasse `GenericList<T>` wird die Verwendung des Operators `default(T)` in einer generischen Klasse veranschaulicht. Weitere Informationen finden Sie unter [Introduction to Generics (Einführung in Generika)](../generics/introduction-to-generics.md).

 [!code-csharp[csProgGuideGenerics#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#Snippet41)]

## <a name="default-literal-and-type-inference"></a>Standardliterale und Typrückschluss

Ab C# 7.1 kann das `default`-Literal für Standardwertausdrücke verwendet werden, wenn der Compiler den Typ des Ausdrucks ableiten kann. Das `default`-Literal erzeugt die gleichen Werte wie das entsprechende `default(T)`, bei dem `T` der abgeleitete Typ ist. Dadurch kann der Code präziser werden, indem Redundanzen durch das mehrmalige Deklarieren eines Typs reduziert werden. Das `default`-Literal kann in jeder der folgenden Positionen verwendet werden:

- Variableninitialisierer
- Variablenzuweisung
- Deklarieren des Standardwerts für einen optionalen Parameter
- Bereitstellen des Werts für ein Methodenaufrufargument
- Zurückgeben einer Anweisung (oder eines Ausdrucks in einem Ausdruckskörpermember)

Das folgende Beispiel demonstriert die Verwendung des `default`-Literals in einem Standardwertausdruck:

[!code-csharp[csProgGuideGenerics#3](../../../../samples/snippets/csharp/programming-guide/statements-expressions-operators/default-literal.cs)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic>  
- [C#-Programmierhandbuch](../index.md)  
- [Generika (C#-Programmierleitfaden)](../generics/index.md)  
- [Generische Methoden](../generics/generic-methods.md)  
- [Generika in .NET](~/docs/standard/generics/index.md)  
- [Tabelle für Standardwerte](../../language-reference/keywords/default-values-table.md)
