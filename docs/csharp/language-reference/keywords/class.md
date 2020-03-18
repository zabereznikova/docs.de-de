---
title: class-Schlüsselwort – C#-Referenz
ms.date: 07/18/2017
f1_keywords:
- class_CSharpKeyword
- class
helpviewer_keywords:
- class keyword [C#]
ms.assetid: b95d8815-de18-4c3f-a8cc-a0a53bdf8690
ms.openlocfilehash: 500160d3bc9280b866e5f5ba24c5edc623e752c1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77673094"
---
# <a name="class-c-reference"></a>class (C#-Referenz)

Klassen werden mithilfe des Schlüsselworts `class` deklariert, wie im folgenden Beispiel dargestellt:

```csharp
class TestClass
{
    // Methods, properties, fields, events, delegates
    // and nested classes go here.
}
```

## <a name="remarks"></a>Hinweise

In C# ist nur die einfache Vererbung zulässig. Eine Klasse kann also Implementierungen aus nur einer Basisklasse erben. Es kann allerdings mehr als eine Schnittstelle implementiert werden. Die folgende Tabelle zeigt Beispiele für Klassenvererbung und Implementierung der Schnittstelle:

|Vererbung|Beispiel|
|-----------------|-------------|
|Keine|`class ClassA { }`|
|Single|`class DerivedClass : BaseClass { }`|
|Keine, Implementierung von zwei Schnittstellen|`class ImplClass : IFace1, IFace2 { }`|
|Single, Implementierung einer Schnittstelle|`class ImplDerivedClass : BaseClass, IFace1 { }`|

Klassen, die Sie direkt innerhalb eines Namespace und nicht in anderen Klassen geschachtelt deklarieren, können entweder [public](./public.md) oder [internal](./internal.md) sein. Klassen sind standardmäßig `internal`.

Klassenmember, einschließlich geschachtelter Klassen, können [öffentlich](public.md), [intern geschützt](protected-internal.md), [geschützt](protected.md), [intern](internal.md), [privat geschützt](private.md) oder [privat](private-protected.md) sein. Member sind standardmäßig `private`.

Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../../programming-guide/classes-and-structs/access-modifiers.md).

Sie können generische Klassen deklarieren, die über Typparameter verfügen. Weitere Informationen finden Sie unter [Generische Klassen](../../programming-guide/generics/generic-classes.md).

Eine Klasse kann Deklarationen der folgenden Member enthalten:

- [Konstruktoren](../../programming-guide/classes-and-structs/constructors.md)

- [Konstanten](../../programming-guide/classes-and-structs/constants.md)

- [Felder](../../programming-guide/classes-and-structs/fields.md)

- [Finalizer](../../programming-guide/classes-and-structs/destructors.md)

- [Methoden](../../programming-guide/classes-and-structs/methods.md)

- [Eigenschaften](../../programming-guide/classes-and-structs/properties.md)

- [Indexer](../../programming-guide/indexers/index.md)

- [Operatoren](../operators/index.md)

- [Ereignisse](../../programming-guide/events/index.md)

- [Delegaten](../../programming-guide/delegates/index.md)

- [Klassen](../../programming-guide/classes-and-structs/classes.md)

- [Schnittstellen](../../programming-guide/interfaces/index.md)

- [Strukturtypen](../builtin-types/struct.md)

- [Enumerationstypen](../builtin-types/enum.md)

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt das Deklarieren von Klassenfeldern, Konstruktoren und Methoden. Darüber hinaus veranschaulicht es Objektinstanziierung und Ausgabe von Instanzdaten. In diesem Beispiel werden zwei Klassen deklariert. Die erste Klasse, `Child`, enthält zwei private Felder (`name` und `age`), zwei öffentliche Konstruktoren und eine öffentliche Methode. Die zweite Klasse, `StringTest`, enthält `Main`.

[!code-csharp[csrefKeywordsTypes#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#5)]

## <a name="comments"></a>Kommentare

Beachten Sie, dass im vorherigen Beispiel nur über die öffentliche Methode der Klasse `Child` auf die privaten Felder (`name` und `age`) zugegriffen werden kann. Sie können z.B. den Namen des untergeordneten Elements nicht aus der `Main`-Methode mit einer Anweisung wie folgt drucken:

```csharp
Console.Write(child1.name);   // Error
```

Zugriff auf private Member der `Child` von `Main` wäre nur möglich, wenn `Main` ein Member der Klasse wäre.

Typen, die innerhalb einer Klasse ohne Zugriffsmodifizierer deklariert werden, sind standardmäßig `private`, sodass die Datenmember in diesem Beispiel dennoch `private` wären, wenn das Schlüsselwort entfernt worden wäre.

Beachten Sie schließlich, dass für das Objekt, das mit dem parameterlosen Konstruktor (`child3`) erstellt wurde, das Feld `age` standardmäßig auf 0 (null) initialisiert wurde.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](./index.md)
- [Verweistypen](./reference-types.md)
