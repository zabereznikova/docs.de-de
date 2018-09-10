---
title: Schlüsselwort „enum“ (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: a64559ac1127f5ec296cf3892dd521c3ad8ac2be
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086149"
---
# <a name="enum-c-reference"></a>enum (C#-Referenz)

Das Schlüsselwort `enum` wird zum Deklarieren einer Enumeration verwendet. Dies ist ein eigener Typ, der aus einer Gruppe benannter Konstanten besteht, die Enumeratorliste genannt wird.  

In der Regel ist es am besten, eine Enumeration direkt innerhalb eines Namespaces so zu definieren, dass alle Klassen im Namespace auf gleiche Weise darauf zugreifen können. Eine Enumeration kann aber auch innerhalb einer Klasse oder einer Struktur geschachtelt werden.

Der erste Enumerator hat standardmäßig den Wert 0. Der Wert jedes nachfolgenden Enumerators wird um 1 erhöht. In der folgenden Enumeration gilt z. B.: `Sat` ist `0`, `Sun` ist `1`, `Mon` ist `2`usw.

```csharp
enum Day {Sat, Sun, Mon, Tue, Wed, Thu, Fri};
```

Enumeratoren können mithilfe von Initialisierern die Standardwerte überschreiben, wie im folgenden Beispiel gezeigt.

```csharp
enum Day {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

In dieser Enumeration wird erzwungen, dass die Abfolge von Elementen mit `1` und nicht mit `0`beginnt. Allerdings wird das Einfügen einer Konstanten mit dem Wert 0 empfohlen. Weitere Informationen finden Sie unter [Enumerationstypen](../../programming-guide/enumeration-types.md).

Jeder Enumerationstyp hat einen zugrunde liegenden Typ, bei dem es sich um jeden ganzzahligen Typ außer [char](char.md) handeln kann. Der zugrunde liegende Standardtyp von Enumerationselementen ist [int](int.md). Um eine Enumeration eines anderen ganzzahligen Typs, z. B. [byte](byte.md)zu deklarieren, setzen Sie einen Doppelpunkt hinter dem Bezeichner, auf den der Typ folgt, wie im folgenden Beispiel gezeigt.

```csharp
enum Day : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};
```

Die zulässigen Typen für eine Enumeration sind [byte](byte.md), [sbyte](sbyte.md), [short](short.md), [ushort](ushort.md), [int](int.md), [uint](uint.md), [long](long.md) und [ulong](ulong.md).

Einer Variablen des Typs `Day` kann jeder Wert im Werbebereich des zugrunde liegenden Typs zugewiesen werden. Die Werte sind nicht auf benannte Konstanten beschränkt.

Der Standardwert von `enum E` ist der Wert, der vom Ausdruck `(E)0`erzeugt wird.

> [!NOTE]
> Namen von Enumeratoren dürfen keine Leerzeichen enthalten.

Der zugrunde liegende Typ gibt an, wie viel Speicher für jeden Enumerator reserviert wird. Eine explizite Typumwandlung ist jedoch erforderlich, um einen `enum` -Typ in einen ganzzahligen Typ zu konvertieren. Durch die folgende Anweisung wird der `Sun` -Enumerator beispielsweise einer Variablen des Typs [int](int.md) zugewiesen. Dabei erfolgt für die Konvertierung von `enum` in `int`eine Typumwandlung.

```csharp
int x = (int)Day.Sun;
```

Wenn <xref:System.FlagsAttribute?displayProperty=nameWithType> auf eine Enumeration mit Elementen angewendet wird, die mit einer bitweisen `OR` -Operation kombiniert werden können, beeinflusst das Attribut das Verhalten von `enum` bei der Verwendung bestimmter Tools. Solche Änderungen sind bei Verwendung von Tools wie den Methoden der <xref:System.Console> -Klasse und der Ausdrucksauswertung zu beobachten. (Siehe das dritte Beispiel.)

## <a name="robust-programming"></a>Stabile Programmierung

Wie bei Konstanten werden zur Kompilierzeit alle Verweise auf die einzelnen Werte einer Enumeration in numerische Literale konvertiert. Dies kann, wie unter [Konstanten](../../programming-guide/classes-and-structs/constants.md) beschrieben, zu möglichen Versionsproblemen führen.

Das Zuweisen zusätzlicher Werte zu neuen Enumerationsversionen oder das Ändern der Werte von Enumerationsmembern in einer neuen Version kann für abhängigen Quellcode Probleme verursachen. Enumerationswerte werden oft in [switch](switch.md) -Anweisungen verwendet. Wenn dem `enum` -Typ weitere Elemente hinzugefügt wurden, kann der Standardabschnitt der „switch“-Anweisung unerwartet ausgewählt werden.

Falls andere Entwickler Ihren Code verwenden, sollten Sie Richtlinien festlegen, die angeben, wie deren Code reagieren soll, wenn `enum` -Typen neue Elemente hinzugefügt werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Enumeration `Day`deklariert. Zwei Enumeratoren werden explizit in ganze Zahlen konvertiert und „Integer“-Variablen zugewiesen.

[!code-csharp[csrefKeywordsTypes#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#10)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Basistypoption verwendet, um ein `enum` zu deklarieren, dessen Member den Typ `long`haben. Beachten Sie, dass obwohl der Enumeration der Typ `long`zugrunde liegt, die Enumerationsmember noch explizit mithilfe einer Typumwandlung in den Typ `long` umgewandelt werden müssen.

[!code-csharp[csrefKeywordsTypes#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#11)]

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel werden die Verwendung des <xref:System.FlagsAttribute?displayProperty=nameWithType> -Attributs in einer `enum` -Deklaration und seine Wirkung veranschaulicht.

[!code-csharp[csrefKeywordsTypes#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#12)]

## <a name="comments"></a>Kommentare

Wenn Sie `Flags`entfernen, werden im Beispiel die folgenden Werte angezeigt:

`5`

`5`

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)  
- [Enumerationstypen](../../programming-guide/enumeration-types.md)  
- [C#-Schlüsselwörter](index.md)  
- [Tabelle ganzzahliger Typen](integral-types-table.md)  
- [Tabelle integrierter Typen](built-in-types-table.md)  
- [Tabelle für implizite numerische Konvertierungen](implicit-numeric-conversions-table.md)  
- [Tabelle für explizite numerische Konvertierungen](explicit-numeric-conversions-table.md)  
- [Benennungskonventionen für Enumerationen](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
