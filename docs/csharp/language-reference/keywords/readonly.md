---
title: readonly-Schlüsselwort – C#-Referenz
ms.date: 06/21/2018
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: f9fa6f893e7f999564c4dcb43d40755547d3c793
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713117"
---
# <a name="readonly-c-reference"></a>readonly (C#-Referenz)

Das Schlüsselwort `readonly` ist ein Modifizierer, der in vier Kontexten verwendet werden kann:

- In einer [Felddeklaration](#readonly-field-example) gibt `readonly` an, dass die Zuweisung zum Feld nur als Teil der Deklaration oder in einem Konstruktor derselben Klasse erfolgen kann. Ein readonly-Feld kann innerhalb der Felddeklaration und des Konstruktors mehrmals zugewiesen und neu zugewiesen werden. 
  
  Ein `readonly`-Feld kann nicht zugewiesen werden, sobald der Konstruktor vorhanden ist. Diese Regel hat verschiedene Auswirkungen auf Wert- und Verweistypen:
  
  - Da Werttypen ihre Daten direkt enthalten, ist ein Feld des Werttyps `readonly` unveränderlich. 
  - Da Verweistypen einen Verweis auf ihre Daten enthalten, muss ein Feld des Verweistyps `readonly` immer auf das gleiche Objekt verweisen. Dieses Objekt ist nicht unveränderlich. Der `readonly`-Modifizierer verhindert, dass das Feld durch eine andere Instanz des Verweistyps ersetzt wird. Der Modifizierer verhindert jedoch nicht, dass die Instanzdaten des Felds durch das schreibgeschützte Feld geändert werden.

  > [!WARNING]
  > Ein extern sichtbarer Typ, der ein extern sichtbares schreibgeschütztes Feld enthält, bei dem es sich um einen änderbaren Verweistyp handelt, kann ein Sicherheitsrisiko darstellen und die folgende Warnung auslösen: [CA2104](/visualstudio/code-quality/ca2104): „Schreibgeschützte änderbare Verweistypen nicht deklarieren.“

- In einer [`readonly struct`-Definition](#readonly-struct-example) gibt `readonly` an, dass `struct` unveränderlich ist.
- In einer [`readonly`-Memberdefinition](#readonly-member-examples) gibt `readonly` an, dass ein Member von `struct` den internen Zustand der Struktur nicht verändert.
- In einer [`ref readonly`-Methodenrückgabe](#ref-readonly-return-example) gibt der `readonly`-Modifizierer an, dass die Methode eine Referenz zurückgibt, und Schreibvorgänge für diese Referenz nicht zulässig sind.

Die `readonly struct`- und `ref readonly`-Kontexte wurden in C# 7.2 hinzugefügt. `readonly`-Strukturmember wurden in C# 8.0 hinzugefügt.

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

Diese Konstruktorkontexte sind auch die einzigen Kontexte, in denen es zulässig ist, ein `readonly`-Feld als [out](out-parameter-modifier.md)- oder [ref](ref.md)-Parameter zu übergeben.

> [!NOTE]
> Das Schlüsselwort `readonly` unterscheidet sich vom Schlüsselwort [const](const.md). Ein `const`-Feld kann nur bei der Deklaration des Felds initialisiert werden. Ein `readonly`-Feld kann mehrere Male in der Felddeklaration und in einem Konstruktor zugewiesen werden. Daher können `readonly`-Felder abhängig vom verwendeten Konstruktor über unterschiedliche Werte verfügen. Außerdem ist ein `const`-Feld eine Kompilierzeitkonstante, während ein `readonly`-Feld wie im folgenden Beispiel für Laufzeitkonstanten verwendet werden kann:
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

Wenn Sie im vorherigen Beispiel eine Anweisung wie die folgende verwenden:

```csharp
p2.y = 66;        // Error
```

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

Das Hinzufügen eines nicht als `readonly` markierten Felds generiert den Compilerfehler `CS8340`: Instanzfelder von schreibgeschützten Strukturen müssen schreibgeschützt sein.

## <a name="readonly-member-examples"></a>Beispiele für readonly-Member

Gegebenenfalls möchten Sie eine Struktur erstellen, die Veränderungen unterstützt. In diesen Fällen wird der interne Zustand der Struktur durch einige der Instanzmember wahrscheinlich nicht verändert. Dann können Sie diese Instanzmember mit dem `readonly`-Modifizierer deklarieren. Mithilfe des Compilers können Sie die Umsetzung Ihrer Absicht erzwingen. Wenn dieses Member den Zustand direkt ändert oder auf ein Member zugreift, das nicht ebenfalls mit dem `readonly`-Modifizierer deklariert ist, führt dies zu einem Kompilierzeitfehler. Der `readonly`-Modifizierer ist für `struct`-Member gültig, nicht für `class`- oder `interface`-Memberdeklarationen.

Es ergeben sich zwei Vorteile, wenn Sie den `readonly`-Modifizierer auf anwendbare `struct`-Methoden anwenden. Der wichtigste Vorteil ist, dass der Compiler Ihre Absicht durchsetzt. Den Zustand verändernder Code ist in einer `readonly`-Methode nicht gültig. Auch der `readonly`-Modifizierer kann vom Compiler eingesetzt werden, um Leistungsoptimierungen zu ermöglichen. Wenn große `struct`-Typen durch den `in`-Verweis übergeben werden, muss der Compiler eine defensive Kopie erzeugen, falls der Zustand der Struktur geändert wird. Wenn nur auf `readonly`-Member zugegriffen wird, darf der Compiler die defensive Kopie nicht erstellen.

Der `readonly`-Modifizierer ist für die meisten Member einer `struct`-Methode gültig, einschließlich Methoden, die die in <xref:System.Object?displayProperty=nameWithType> deklarierte Methoden außer Kraft setzen. Es gibt einige Einschränkungen:

- Sie können keine statischen `readonly`-Methoden oder -Eigenschaften deklarieren.
- Sie können keine `readonly`-Konstruktoren deklarieren.

Sie können den `readonly`-Modifizierer zu einer Eigenschafts- oder Indexerdeklaration hinzufügen:

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

Außerdem können Sie den `readonly`-Modifizierer zu einzelnen `get`- oder `set`-Accessoren einer Eigenschaft oder eines Indexers hinzufügen:

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

Sie dürfen den `readonly`-Modifizierer nicht sowohl zu einer Eigenschaft als auch zu einem Accessor bzw. mehreren Accessoren derselben Eigenschaft hinzufügen. Für Indexer gilt die gleiche Einschränkung.

Der Compiler wendet den `readonly`-Modifizierer implizit auf automatisch implementierte Eigenschaften an, bei denen der vom Compiler implementierte Code den Zustand nicht ändert. Dies entspricht den folgenden Deklarationen:

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
``` 

An diesen Stellen können Sie den `readonly`-Modifizierer hinzufügen, aber er hat keinen sinnvollen Effekt. Sie dürfen den `readonly`-Modifizierer nicht zu einem Setter für eine automatisch implementierte Eigenschaft oder zu einer automatisch implementierten Eigenschaft für Lese-/Schreibzugriff hinzufügen.

## <a name="ref-readonly-return-example"></a>Rückgabebeispiel für ref readonly

Der `readonly`-Modifizierer für `ref return` gibt an, dass der zurückgegebene Verweis nicht geändert werden kann. Das folgende Beispiel gibt einen Verweis auf den Ursprung zurück. Dabei wird über den `readonly`-Modifizierer angegeben, dass die aufrufenden Funktionen den Ursprung nicht ändern können:

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]
Der zurückgegebene Typ muss nicht `readonly struct` aufweisen. Jeder Typ, der von `ref` zurückgegeben werden kann, kann auch von `ref readonly` zurückgegeben werden.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

Sehen Sie sich auch die Vorschläge zur Sprachspezifikation an:

- [readonly-Referenz und readonly-Struktur](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [readonly-Strukturmember](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Modifizierer](index.md)
- [const](const.md)
- [Felder](../../programming-guide/classes-and-structs/fields.md)
