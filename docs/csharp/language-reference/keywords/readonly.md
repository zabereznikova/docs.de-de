---
title: Schlüsselwort „readonly“ (C#-Referenz)
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: d09ce4ea972a3064298eebdf0b8b80999ee8441e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43480980"
---
# <a name="readonly-c-reference"></a>readonly (C#-Referenz)

Das Schlüsselwort `readonly` ist ein Modifizierer, der in drei Kontexten verwendet werden kann:

- In einer [Felddeklaration](#readonly-field-example) gibt `readonly` an, dass die Zuweisung zum Feld nur als Teil der Deklaration oder in einem Konstruktor derselben Klasse erfolgen kann.
- In einer [`readonly struct`-Definition](#readonly-struct-example) gibt `readonly` an, dass `struct` unveränderlich ist.
- In einer [`ref readonly`-Methodenrückgabe](#ref-readonly-return-example) gibt der `readonly`-Modifizierer an, dass die Methode eine Referenz zurückgibt, und Schreibvorgänge für diese Referenz nicht zulässig sind.

Die letzten beiden Kontexte wurden in C# 7.2 hinzugefügt.

## <a name="readonly-field-example"></a>Beispiel für ein readonly-Feld

In diesem Beispiel kann der Wert des Felds `year` nicht zur Methode `ChangeYear` geändert werden, obwohl ihm im Klassenkonstruktor ein Wert zugewiesen ist:

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

Sie können einem `readonly`-Feld nur in den folgenden Kontexten einen Wert zuweisen:

- Wenn die Variable in der Deklaration initialisiert ist, z.B.:

```csharp
public readonly int y = 5;
```

- In einem Instanzenkonstruktor der Klasse, die die Deklaration des Instanzfelds enthält.
- Im statischen Konstruktor der Klasse, die die Deklaration des statischen Felds enthält.

Diese Konstruktorkontexte sind auch die einzigen Kontexte, in denen es gültig ist, ein `readonly`-Feld als [out](out-parameter-modifier.md)- oder [ref](ref.md)-Parameter zu übergeben.

> [!NOTE]
> Das Schlüsselwort `readonly` unterscheidet sich vom Schlüsselwort [const](const.md). Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden. Ein `readonly`-Feld kann entweder bei der Deklaration oder in einem Konstruktor initialisiert werden. Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen. Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld wie im folgenden Beispiel für Laufzeitkonstanten verwendet werden kann:

```csharp
public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

Wenn Sie im vorherigen Beispiel eine Anweisung wie die folgende verwenden:

`p2.y = 66;        // Error`

erhalten Sie die Compilerfehlermeldung:

`A readonly field cannot be assigned to (except in a constructor or a variable initializer)`

## <a name="readonly-struct-example"></a>Beispiel für readonly struct

Der `readonly`-Modifizierer für eine `struct`-Definition deklariert, dass die Struktur **unveränderlich** ist. Jedes Instanzfeld für `struct` muss mit `readonly` markiert sein, wie im folgenden Beispiel gezeigt:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyStruct)]

Das vorhergehende Beispiel verwendet [schreibgeschützte automatische Eigenschaften](../../properties.md#read-only), um den Speicher zu deklarieren. Dadurch wird der Compiler angewiesen, `readonly`-Unterstützungsfelder für diese Eigenschaften zu erstellen. Sie können `readonly`-Felder auch direkt deklarieren:

```csharp
public readonly struct Point
{
    public readonly double X;
    public readonly double Y;

    public Point(double x, double y) => (X, Y) = (x, y);

    public override string ToString() => $"({X}, {Y})";
}
```

Das Hinzufügen eines Felds, das nicht mit `readonly` markiert ist, erzeugt den Compilerfehler `CS8340`: „Instanzfelder oder schreibgeschützten Strukturen müssen schreibgeschützt sein.“

## <a name="ref-readonly-return-example"></a>Rückgabebeispiel für ref readonly

Der Modifizierer `readonly` für `ref return` gibt an, dass die zurückgegebene Referenz nicht geändert werden kann. Das folgende Beispiel gibt einen Verweis auf den Ursprung zurück. Der `readonly`-Modifizierer gibt dabei an, dass die aufrufenden Funktionen den Ursprung nicht ändern können:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
Der zurückgegebene Typ muss nicht `readonly struct` aufweisen. Jeder Typ, der von `ref` zurückgegeben werden kann, kann auch von `ref readonly` zurückgegeben werden.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Modifizierer](modifiers.md)
- [const](const.md)
- [Felder](../../programming-guide/classes-and-structs/fields.md)
