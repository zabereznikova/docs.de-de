---
title: struct – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- struct_CSharpKeyword
helpviewer_keywords:
- struct keyword [C#]
- structs [C#], struct keyword
ms.assetid: ff3dd9b7-dc93-4720-8855-ef5558f65c7c
ms.openlocfilehash: a78488ad902b0a96a30ad197b0ece043543c3d69
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422312"
---
# <a name="struct-c-reference"></a>struct (C#-Referenz)

Ein `struct`-Typ ist ein ein Werttyp, der in der Regel verwendet wird, um eine kleine Gruppe verwandter Variablen zusammenzufassen, z. B. Koordinaten eines Rechtecks oder die Merkmale eines Lagerartikels. Im folgenden Beispiel wird eine einfache Strukturdeklaration veranschaulicht:

```csharp
public struct Book
{
    public decimal price;
    public string title;
    public string author;
}
```

## <a name="remarks"></a>Anmerkungen

Strukturen können auch [Konstruktoren](../../programming-guide/classes-and-structs/constructors.md), [Konstanten](../../programming-guide/classes-and-structs/constants.md), [Felder](../../programming-guide/classes-and-structs/fields.md), [Methoden](../../programming-guide/classes-and-structs/methods.md), [Eigenschaften](../../programming-guide/classes-and-structs/properties.md), [Indexer](../../programming-guide/indexers/index.md), [Operatoren](../operators/index.md), [Ereignisse](../../programming-guide/events/index.md) und [geschachtelte Typen](../../programming-guide/classes-and-structs/nested-types.md) enthalten. Wenn jedoch mehrere solche Member erforderlich sind, sollten Sie sich überlegen, den Typ in eine Klasse umzuwandeln.

Beispiele finden Sie unter [Verwenden von Strukturen](../../programming-guide/classes-and-structs/using-structs.md).

Strukturen können eine Schnittstelle implementieren, aber nicht von einer anderen Struktur erben. Aus diesem Grund können Strukturmember nicht als `protected` deklariert werden.

Weitere Informationen finden Sie unter [Strukturen](../../programming-guide/classes-and-structs/structs.md).

## <a name="examples"></a>Beispiele

Weitere Beispiele und Informationen finden Sie unter [Verwenden von Strukturen](../../programming-guide/classes-and-structs/using-structs.md).

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Beispiele finden Sie unter [Verwenden von Strukturen](../../programming-guide/classes-and-structs/using-structs.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Tabelle für Standardwerte](default-values-table.md)
- [Tabelle integrierter Typen](built-in-types-table.md)
- [Typen](/dotnet/csharp/language-reference/keywords)
- [Werttypen](value-types.md)
- [class](class.md)
- [interface](interface.md)
- [Klassen und Strukturen](../../programming-guide/classes-and-structs/index.md)
