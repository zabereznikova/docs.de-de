---
description: readonly-Schlüsselwort – C#-Referenz
title: readonly-Schlüsselwort – C#-Referenz
ms.date: 04/14/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: b1bab5af18216fcef2162179493dbbb59e3470cf
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137174"
---
# <a name="readonly-c-reference"></a>readonly (C#-Referenz)

Das Schlüsselwort `readonly` ist ein Modifizierer, der in vier Kontexten verwendet werden kann:

- In einer [Felddeklaration](#readonly-field-example) gibt `readonly` an, dass die Zuweisung zum Feld nur als Teil der Deklaration oder in einem Konstruktor derselben Klasse erfolgen kann. Ein readonly-Feld kann innerhalb der Felddeklaration und des Konstruktors mehrmals zugewiesen und neu zugewiesen werden.
  
  Ein `readonly`-Feld kann nicht zugewiesen werden, sobald der Konstruktor vorhanden ist. Diese Regel hat verschiedene Auswirkungen auf Wert- und Verweistypen:
  
  - Da Werttypen ihre Daten direkt enthalten, ist ein Feld des Werttyps `readonly` unveränderlich.
  - Da Verweistypen einen Verweis auf ihre Daten enthalten, muss ein Feld des Verweistyps `readonly` immer auf das gleiche Objekt verweisen. Dieses Objekt ist nicht unveränderlich. Der `readonly`-Modifizierer verhindert, dass das Feld durch eine andere Instanz des Verweistyps ersetzt wird. Der Modifizierer verhindert jedoch nicht, dass die Instanzdaten des Felds durch das schreibgeschützte Feld geändert werden.

  > [!WARNING]
  > Ein extern sichtbarer Typ, der ein extern sichtbares schreibgeschütztes Feld enthält, bei dem es sich um einen änderbaren Verweistyp handelt, kann ein Sicherheitsrisiko darstellen und die folgende Warnung auslösen: [CA2104](/visualstudio/code-quality/ca2104): „Schreibgeschützte änderbare Verweistypen nicht deklarieren.“

- In einer `readonly struct`-Typdefinition weist `readonly` darauf hin, dass der Strukturtyp unveränderlich ist. Weitere Informationen finden Sie im Abschnitt zur [`readonly`-Struktur](../builtin-types/struct.md#readonly-struct) des Artikels [Strukturtypen](../builtin-types/struct.md).
- In einer Instanzmemberdeklaration innerhalb eines Strukturtyps gibt `readonly` an, dass ein Instanzmember den Zustand einer Struktur nicht ändert. Weitere Informationen finden Sie im Abschnitt [`readonly`-Instanzmember](../builtin-types/struct.md#readonly-instance-members) des Artikels [Strukturtypen](../builtin-types/struct.md).
- In einer [`ref readonly`-Methodenrückgabe](#ref-readonly-return-example) gibt der `readonly`-Modifizierer an, dass die Methode eine Referenz zurückgibt, und Schreibvorgänge für diese Referenz nicht zulässig sind.

Die `readonly struct`- und `ref readonly`-Kontexte wurden in C# 7.2 hinzugefügt. `readonly`-Strukturmember wurden in C# 8.0 hinzugefügt.

## <a name="readonly-field-example"></a>Beispiel für ein readonly-Feld

In diesem Beispiel kann der Wert des Felds `year` nicht zur Methode `ChangeYear` geändert werden, obwohl ihm im Klassenkonstruktor ein Wert zugewiesen ist:

[!code-csharp[Readonly Field example](snippets/ReadonlyKeywordExamples.cs#ReadonlyField)]

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

[!code-csharp[Initialize readonly Field example](snippets/ReadonlyKeywordExamples.cs#InitReadonlyField)]

Wenn Sie im vorherigen Beispiel eine Anweisung wie die folgende verwenden:

```csharp
p2.y = 66;        // Error
```

erhalten Sie die Compilerfehlermeldung:

**Einem schreibgeschützten Feld kann nichts zugewiesen werden (außer in einem Konstruktor oder Variableninitialisierer)**

## <a name="ref-readonly-return-example"></a>Rückgabebeispiel für ref readonly

Der `readonly`-Modifizierer für `ref return` gibt an, dass der zurückgegebene Verweis nicht geändert werden kann. Das folgende Beispiel gibt einen Verweis auf den Ursprung zurück. Dabei wird über den `readonly`-Modifizierer angegeben, dass die aufrufenden Funktionen den Ursprung nicht ändern können:

[!code-csharp[readonly return example](snippets/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

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
