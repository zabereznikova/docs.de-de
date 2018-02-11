---
title: Tupel in Visual Basic
ms.custom: 
ms.date: 04/23/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- tuples [Visual Basic]
ms.assetid: 3e66cd1b-3432-4e1d-8c37-5ebacae8f53f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2653b9dc8a6ecbcb718c20be8bd6275edf4cfb6e
ms.sourcegitcommit: be1fb5d9447ad459bef22b91a91c72e3e0b2d916
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2018
---
# <a name="tuples-visual-basic"></a>Tupel (Visual Basic)

Visual Basic 2017 ab, die Sprache Visual Basic bietet integrierte Unterstützung für Tupel, mit der, Tupel erstellen und den Zugriff auf die Elemente von Tupeln einfacher. Ein Tupel ist ein Lightweight-Datenstruktur, die eine bestimmte Anzahl und die Sequenz von Werten aufweist. Wenn Sie das Tupel instanziieren, definieren Sie die Anzahl und den Datentyp der einzelnen Wert (oder Element). Ein 2-Tupel (oder ein Paar) hat beispielsweise zwei Elemente auf. Die erste ist möglicherweise eine `Boolean` Wert, während die zweite ist eine `String`. Da Tupel mehrere Werte in ein einzelnes Objekt speichern erleichtern, werden sie häufig als einfache Möglichkeit, mehrere Werte zurückgegeben werden, von einer Methode verwendet.

> [!IMPORTANT]
> Tupel unterstützt wird, muss die <xref:System.ValueTuple> Typ. Wenn der .NET Framework-4.7 nicht installiert ist, müssen Sie das NuGet-Paket hinzufügen `System.ValueTuple`, die auf der NuGet Gallery verfügbar ist. Ohne dieses Paket können Sie erhalten einen Kompilierungsfehler wie "Vordefinierte Typ 'ValueTuple(Of,,,)' nicht definiert oder importiert wird."

## <a name="instantiating-and-using-a-tuple"></a>Instanziieren und verwenden ein Tupel

Instanziieren Sie ein Tupel durch die Werte durch Kommas getrennte Instant Messaging-Diensten Klammern einschließen. Jeder dieser Werte wird dann ein Feld des Tupels. Z. B. der folgende Code definiert eine Triple (oder 3-Tupel) mit einem `Date` als ersten Wert ein `String` als den zweiten und eine `Boolean` als den dritten.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#1)]

Wird standardmäßig der Name jedes Felds in einem Tupel besteht aus der Zeichenfolge `Item` zusammen mit dem Feld einsbasierte Positionen im Tupel. Für diese 3-Tupel die `Date` Feld ist `Item1`, `String` Feld ist `Item2`, und die `Boolean` Feld ist `Item3`. Das folgende Beispiel zeigt die Werte der Felder des Tupels in der vorherigen Codezeile instanziiert

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#2)]

Die Felder eines Visual Basic-Tupels sind Lese-/ Schreibzugriff. Nachdem Sie ein Tupel instanziiert haben, können Sie dessen Werte ändern. Im folgende Beispiel ändert zwei der drei Felder des Tupels im vorherigen Beispiel erstellt und das Ergebnis wird angezeigt.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#3)]

## <a name="instantiating-and-using-a-named-tuple"></a>Instanziieren und verwenden eine benannte Tupel

Statt die Standardnamen für ein Tupel Felder, instanziieren Sie ein *mit dem Namen Tupel* durch das Tupel-Elementen mit Ihren eigenen Namen zugewiesen. Das Tupel-Felder können dann durch ihre zugewiesenen Namen zugegriffen werden *oder* durch ihre Standardnamen. Das folgende Beispiel instanziiert die gleiche 3-Tupel als zuvor mit dem Unterschied, dass es das erste Feld explizit benannt `EventDate`, das zweite `Name`, und der dritte `IsHoliday`. Es dann zeigt die Feldwerte, ändert sie und die Feldwerte erneut angezeigt.

[!code-vb[Instantiate](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple1.vb#4)]

## <a name="inferred-tuple-element-names"></a>Abgeleitete Tupel Elementnamen

Beginnend mit Visual Basic 15.3, kann Visual Basic die Namen der Tupelelemente ableiten; Sie müssen keinen explizit zuweisen. Abgeleitete Tupel Namen sind hilfreich, wenn Sie ein Tupel aus einem Satz von Variablen initialisieren, und der Elementname Tupel mit dem Variablennamen identisch sein sollen. 

Das folgende Beispiel erstellt eine `stateInfo` Tupel, das drei explizit enthält benannten Elementen, `state`, `stateName`, und `capital`. Beachten Sie, dass bei der Benennung der Elemente, Tupel Initialisierung die Anweisung einfach benannten Elemente der Werte von gleichnamigen Variablen weist.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#1)]
 
Da Elemente und Variablen, die denselben Namen haben, kann die Visual Basic-Compiler die Namen der Felder, wie im folgenden Beispiel gezeigt ableiten.

[!code-vb[ExplicitlyNamed](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/named-tuples/program.vb#2)]

Um interred Tupel Elementnamen zu aktivieren, müssen Sie die Version von Visual Basic-Compiler in Visual Basic-Projekt verwendet definieren (\*.vbproj) Datei: 

```xml 
<PropertyGroup> 
  <LangVersion>15.3</LangVersion> 
</PropertyGroup> 

The version number can be any version of the Visual Basic compiler starting with 15.3. Rather than hard-coding a specific compiler version, you can also specify "Latest" as the value of `LangVersion` to compile with the most recent version of the Visual Basic compiler installed on your system.

In some cases, the Visual Basic compiler cannot infer the tuple element name from the candidate name, and the tuple field can only be referenced using its default name, such as `Item1`, `Item2`, etc. These include:

- The candidate name is the same as the name of a tuple member, such as `Item3`, `Rest`, or `ToString`.

- The candidate name is duplicated in the tuple.
 
When field name inference fails, Visual Basic does not generate a compiler error, nor is an exception thrown at runtime. Instead, tuple fields must be referenced by their predefined names, such as `Item1` and `Item2`. 
  
## Tuples versus structures

A Visual Basic tuple is a value type that is an instance of one of the a **System.ValueTuple** generic types. For example, the `holiday` tuple defined in the previous example is an instance of the <xref:System.ValueTuple%603> structure. It is designed to be a lightweight container for data. Since the tuple aims to make it easy to create an object with multiple data items, it lacks some of the features that a custom structure might have. These include:

- Customer members. You cannot define your own properties, methods, or events for a tuple.

- Validation. You cannot validate the data assigned to fields.

- Immutability. Visual Basic tuples are mutable. In contrast, a custom structure allows you to control whether an instance is mutable or immutable.

If custom members, property and field validation, or immutability are important, you should use the Visual Basic [Structure](../../../language-reference/statements/structure-statement.md) statement to define a custom value type.

A Visual Basic tuple does inherit the members of its **ValueTuple** type. In addition to its fields, these include the following methods:

| Member | Description |
| ---|---|
| CompareTo | Compares the current tuple to another tuple with the same number of elements. |
| Equals | Determines whether the current tuple is equal to another tuple or object. |
| GetHashCode | Calculates the hash code for the current instance. |
| ToString | Returns the string representation of this tuple, which takes the form `(Item1, Item2...)`, where `Item1` and `Item2` represent the values of the tuple's fields. |

In addition, the **ValueTuple** types implement <xref:System.Collections.IStructuralComparable> and <xref:System.Collections.IStructuralEquatable> interfaces, which allow you to define customer comparers.

## Assignment and tuples

Visual Basic supports assignment between tuple types that have the same number of fields. The field types can be converted if one of the following is true:

- The source and target field are of the same type.

- A widening (or implicit) conversion of the source type to the target type is defined. 

- `Option Strict` is `On`, and a narrowing (or explicit) conversion of the source type to the target type is defined. This conversion can throw an exception if the source value is outside the range of the target type.

Other conversions are not considered for assignments. Let's look at the kinds of assignments that are allowed between tuple types.

Consider these variables used in the following examples:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#1)]

The first two variables, `unnamed` and `anonymous`, do not have semantic names provided for the fields. Their field names are the default `Item1` and `Item2`. The last two variables, `named` and `differentName` have semantic field names. Note that these two tuples have different names for the fields.

All four of these tuples have the same number of fields (referred to as 'arity'), and the types of those fields are identical. Therefore, all of these assignments work:

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#2)]

Notice that the names of the tuples are not assigned. The values of the fields are assigned following the order of the fields in the tuple.

Finally, notice that we can assign the `named` tuple to the `conversion` tuple, even though the first field of `named` is an `Integer`, and the first field of `conversion` is a `Long`. This assignment succeeds because converting an `Integer` to a `Long` is a widening conversion.

[!code-vb[Assign](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple3.vb#3)]

Tuples with different numbers of fields are not assignable:

```vb
' Does not compile.
' VB30311: Value of type '(Integer, Integer, Integer)' cannot be converted
'          to '(Answer As Integer, Message As String)'
var differentShape = (1, 2, 3)
named = differentShape
```

## <a name="tuples-as-method-return-values"></a>Tupel als Methodenrückgabewert

Eine Methode kann nur einen einzelnen Wert zurückgeben. In vielen Fällen jedoch soll einen Methodenaufruf an mehrere Werte zurückgegeben werden. Es gibt mehrere Möglichkeiten, diese Einschränkung zu umgehen:

- Sie können eine benutzerdefinierte Klasse oder Struktur erstellen, dessen Eigenschaften oder Felder darstellen, von der Methode zurückgegebenen Werte. Daher ist eine Heavyweight-Lösung. Es erfordert, dass Sie einen benutzerdefinierten Typ definieren, deren einzige zum Abrufen der Werte aus einem Methodenaufruf dient.

- Sie können einen einzelnen Wert zurückgeben, von der Methode und die verbleibenden Werte zurück, durch die sie als Verweis an die Methode übergeben werden. Führen Sie dazu den Aufwand für das Instanziieren einer Variablen und Risiken, die den Wert der Variablen, die Sie als Verweis übergeben versehentlich überschrieben.

- Sie können ein Tupel, eine einfache Lösung bietet für das Abrufen von mehreren Rückgabewerten.

Z. B. die **TryParse** Methoden in .NET Rückgabe einer `Boolean` Wert, der angibt, ob der Analysevorgang erfolgreich war. Das Ergebnis des Analysevorgangs wird in einer Variablen als Verweis an die Methode übergebene zurückgegeben. In der Regel wird ein Aufruf der einer Analysemethode, z. B. <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> sieht wie folgt:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#1)]

Wir können ein Tupel aus der Analysevorgang zurückgeben, wenn es den Aufruf zum Umschließen der <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> Methode in eigenen-Methode. Im folgenden Beispiel `NumericLibrary.ParseInteger` Aufrufe der <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> Methode und eine benannte Tupel mit zwei Elementen zurück. 

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#2)]

Sie können dann die Methode mit Code wie folgt aufrufen:

[!code-vb[Return](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple-returns.vb#3)]

## <a name="visual-basic-tuples-and-tuples-in-the-net-framework"></a>Visual Basic-Tupel und Tupel in .NET Framework

Ein Visual Basic-Tupel ist eine Instanz einer von der **System.ValueTuple** generischen Typen, die in der .NET Framework-4.7 eingeführt wurden. .NET Framework enthält auch eine Reihe von generischen **System.Tuple** Klassen. Diese Klassen unterscheiden sich jedoch von Visual Basic-Tupeln und **System.ValueTuple** generische Typen, die eine Reihe von Möglichkeiten:

- Die Elemente der **Tupel** Klassen sind Eigenschaften, die mit dem Namen `Item1`, `Item2`und so weiter. In Visual Basic-Tupeln und **ValueTuple** Tupelelementen-Datentypen sind Felder.

- Sie können keine Elemente des aussagekräftige Namen zuweisen eine **Tupel** Instanz oder eine **ValueTuple** Instanz. Visual Basic können Sie Namen zuweisen, die die Bedeutung der Felder zu kommunizieren.

- Die Eigenschaften einer **Tupel** Instanz schreibgeschützt sind, die Tupel sind unveränderlich. In Visual Basic-Tupeln und **ValueTuple** Typen Tupel Felder sind Lese-/ Schreibzugriff; die Tupel sind änderbar.

- Die generische **Tupel** -Typen sind Referenztypen. Mit diesen **Tupel** Typen bedeutet, dass das Zuordnen von Objekten. Auf dem langsamsten Pfad kann das einen messbaren Einfluss auf die Leistung Ihrer Anwendungen haben. Visual Basic-Tupeln und **ValueTuple** Typen sind Werttypen.

Erweiterungsmethoden in den <xref:System.TupleExtensions> Klasse erleichtern das Konvertieren zwischen Tupel Visual Basic und .NET **Tupel** Objekte. Die **ToTuple** Methode konvertiert ein Visual Basic-Tupel in einer .NET **Tupel** -Objekt, und die **ToValueTuple** Methode konvertiert ein .NET **Tupel** Um ein Visual Basic-Tupel-Objekt.

Das folgende Beispiel erstellt ein Tupel, konvertiert es in einer .NET **Tupel** Objekt und konvertiert sie zurück in ein Visual Basic-Tupel. Im Beispiel vergleicht dieses Tupel mit dem ursprünglichen Stellen Sie sicher, dass sie gleich sind.

[!code-vb[Convert](../../../../../samples/snippets/visualbasic/programming-guide/language-features/data-types/tuple2.vb#1)]

## <a name="see-also"></a>Siehe auch

[Sprachreferenz zu Visual Basic](index.md)  
