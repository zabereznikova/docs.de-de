---
description: In diesem Artikel werden Werttypen, ihre Arten und die in C# integrierten Werttypen vorgestellt.
title: 'Werttypen: C#-Referenz'
ms.date: 01/22/2020
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 6fb33ad2eb3f6a5e8f6506527f3807f31bf33fdc
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "92471650"
---
# <a name="value-types-c-reference"></a>Werttypen (C#-Referenz)

*Werttypen* und [Verweistypen](../keywords/reference-types.md) sind die beiden Hauptkategorien von C#-Typen. Eine Variable eines Werttyps enthält eine Instanz des Typs. Dies unterscheidet sich von einer Variablen eines Verweistyps, die einen Verweis auf eine Instanz des Typs enthält. Standardmäßig werden die Variablenwerte bei der [Zuweisung](../operators/assignment-operator.md) kopiert, dabei handelt es sich um die Übergabe eines Arguments an eine Methode oder die Rückgabe eines Methodenergebnisses. Im Fall von Werttypvariablen werden die entsprechenden Typinstanzen kopiert. Das folgende Beispiel veranschaulicht dieses Verhalten:

[!code-csharp[copy of values](snippets/shared/ValueTypes.cs#ValueTypeCopied)]

Wie das vorhergehende Beispiel zeigt, wirken sich Vorgänge auf eine Werttypvariable nur auf die in der Variable gespeicherte Instanz des Werttyps aus.

Wenn ein Werttyp einen Datenmember eines Verweistyps enthält, wird beim Kopieren einer Werttypinstanz nur der Verweis auf die Instanz des Verweistyps kopiert. Sowohl die kopierte als auch die ursprüngliche Werttypinstanz haben Zugriff auf dieselbe Verweistypinstanz. Das folgende Beispiel veranschaulicht dieses Verhalten:

[!code-csharp[shallow copy](snippets/shared/ValueTypes.cs#ShallowCopy)]

> [!NOTE]
> Definieren und verwenden Sie unveränderliche Werttypen, um Ihren Code weniger fehleranfällig und stabiler zu machen. In diesem Artikel werden veränderbare Werttypen nur zur Veranschaulichung verwendet.

## <a name="kinds-of-value-types"></a>Varianten von Werttypen

Ein Werttyp kann einer der zwei folgenden Varianten sein:

- ein [Strukturtyp](struct.md), der Daten und zugehörige Funktionen einschließt
- ein [Enumerationstyp](enum.md), der durch mehrere benannte Konstanten definiert wird und eine Auswahl oder Auswahlmöglichkeiten darstellt

Ein [Werttyp, der NULL zulässt](nullable-value-types.md) wie `T?`, stellt alle Werte des zugrunde liegenden Werttyps `T` und einen zusätzlichen [NULL](../keywords/null.md)-Wert dar. Sie können einer Variablen eines Werttyps nicht `null` zuweisen, es sei denn, es handelt sich um einen Werttyp,der NULL zulässt.

## <a name="built-in-value-types"></a>Integrierte Werttypen

C# bietet die folgenden integrierten Werttypen, die auch als *einfache Typen* bekannt sind:

- [Integrale numerische Typen](integral-numeric-types.md)
- [Numerische Gleitkommatypen](floating-point-numeric-types.md)
- [bool](bool.md), der einen booleschen Wert darstellt
- [char](char.md), der ein Unicode-Zeichen in UTF-16-Codierung darstellt

Alle einfachen Typen sind Strukturtypen und unterscheiden sich von anderen Strukturtypen dadurch, dass sie bestimmte zusätzliche Vorgänge erlauben:

- Sie können Literale verwenden, um einen Wert eines einfachen Typs bereitzustellen. `'A'` ist beispielsweise ein Literal vom Typ `char`, und `2001` ist ein Literal vom Typ `int`.

- Konstanten der einfachen Typen können Sie mit dem Schlüsselwort [const](../keywords/const.md) deklarieren. Es ist nicht möglich, Konstanten anderer Strukturtypen zu haben.

- Konstante Ausdrücke, deren Operanden alle Konstanten der einfachen Typen sind, werden zur Kompilierzeit ausgewertet.

Ab C# 7.0 unterstützt C# [Werttupel](value-tuples.md). Ein Werttupel ist ein Werttyp, aber kein einfacher Typ.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Werttypen](~/_csharplang/spec/types.md#value-types)
- [Einfache Typen](~/_csharplang/spec/types.md#simple-types)
- [Variablen](~/_csharplang/spec/variables.md)

## <a name="see-also"></a>Weitere Informationen

- [C#-Referenz](../index.md)
- <xref:System.ValueType?displayProperty=nameWithType>
- [Verweistypen](../keywords/reference-types.md)
