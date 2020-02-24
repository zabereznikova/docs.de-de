---
title: Strukturen - Leitfaden für C#
description: Erfahren Sie mehr über den Typ „Struktur“ und wie Sie diesen erstellen
ms.date: 10/12/2016
ms.technology: csharp-fundamentals
ms.assetid: a7094b8c-7229-4b6f-82fc-824d0ea0ec40
ms.openlocfilehash: 540742ea6a215e09f0cc31b218ac10fbf6192352
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503991"
---
# <a name="structs"></a>Strukturen

Eine *Struktur* ist ein Werttyp. Wenn eine Struktur erstellt wird, enthält die Variable, der die Struktur zugewiesen wird, die eigentlichen Daten der Struktur. Wenn die Struktur einer neuen Variable zugewiesen wird, werden diese kopiert. Die neue Variable und die ursprüngliche Variable enthalten daher zwei separate Kopien der gleichen Daten. Änderungen an einer Kopie wirken sich nicht auf die andere Kopie aus.

Werttypvariablen enthalten die zugehörigen Werte direkt, d. h., der Speicher wird inline in dem Kontext belegt, in dem die Variable deklariert ist. Für Werttypvariablen erfolgt keine getrennte Heapzuordnung oder ein Mehraufwand für die Garbage Collection.

Zwei Kategorien von Werttypen sind verfügbar: [struct](language-reference/keywords/struct.md) und [enum](language-reference/builtin-types/enum.md).

Die integrierten numerischen Typen sind Strukturen und verfügen über Eigenschaften und Methoden, auf die Sie zugreifen können:

[!code-csharp[Static Method](../../samples/snippets/csharp/concepts/structs/static-method.cs)]

Sie deklarieren diese jedoch und weisen ihnen Werte zu, als wären es einfache, nicht aggregierte Typen:

[!code-csharp[Assign Values](../../samples/snippets/csharp/concepts/structs/assign-value.cs)]

Werttypen sind *versiegelt* (sealed). Dies bedeutet z.B., dass Sie keinen Typ von <xref:System.Int32> ableiten können und dass eine Struktur nicht von einer benutzerdefinierten Klasse oder Struktur erben kann, weil eine Struktur nur von <xref:System.ValueType> erben kann. Eine Struktur kann jedoch eine oder mehrere Schnittstellen implementieren. Sie können einen Strukturtyp in einen Schnittstellentyp umwandeln. Dadurch wird ein *Boxing*-Vorgang gestartet, mit dem die Struktur von einem Referenztypobjekt im verwalteten Heap umschlossen wird. Boxing-Vorgänge werden auch ausgeführt, wenn Sie einen Werttyp an eine Methode übergeben, die <xref:System.Object> als Eingabeparameter akzeptiert. Weitere Informationen finden Sie unter [Boxing und Unboxing](./programming-guide/types/boxing-and-unboxing.md ).

Sie können das [struct](./language-reference/keywords/struct.md)-Schlüsselwort verwenden, um eigene benutzerdefinierte Werttypen zu erstellen. In der Regel wird eine Struktur als Container für einen kleinen Satz verwandter Variablen verwendet, wie im folgenden Beispiel dargestellt:

[!code-csharp[Struct Keyword](../../samples/snippets/csharp/concepts/structs/struct-keyword.cs)]

Weitere Informationen über Werttypen im .NET Framework finden Sie unter [Allgemeines Typsystem](../standard/common-type-system.md).

Strukturen teilen sich einen großen Teil der Syntax mit Klassen, obwohl Strukturen eingeschränkter als Klassen sind:

- Innerhalb einer Strukturdeklaration können Felder nicht initialisiert werden, außer Sie werden als `const` oder `static` deklariert.

- Eine Struktur kann keinen parameterlosen Konstruktor (einen Konstruktor ohne Parameter) oder Finalizer deklarieren.

- Strukturen werden bei Zuweisung kopiert. Wenn eine Struktur einer neuen Variable zugewiesen wird, werden alle Daten kopiert, und jede Änderung an der neuen Kopie ändert nicht die Daten für das Original. Es ist wichtig, sich das zu merken, wenn Sie mit Auflistungen von Wertetypen wie Dictionary<string, myStruct> arbeiten.

- Strukturen sind Werttypen, und Klassen sind Verweistypen.

- Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.

- Strukturen können Konstruktoren deklarieren, die Parameter besitzen.

- Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein. Alle Strukturen erben direkt von <xref:System.ValueType>, das von <xref:System.Object> erbt.

- Eine Struktur kann wie eine Klasse Schnittstellen implementieren.

## <a name="nullable-value-types"></a>Auf NULL festlegbare Werttypen

Gewöhnliche Werttypen können den Wert [NULL](language-reference/keywords/null.md) nicht aufweisen. Sie können jedoch auf NULL festlegbare Werttypen erstellen, indem Sie nach dem Typ ein `?` anfügen. Zum Beispiel ist `int?` ein `int`-Typ, der auch den Wert [NULL](./language-reference/keywords/null.md) aufweisen kann. Nullable-Werttypen sind Instanzen des generischen Strukturtyps <xref:System.Nullable%601>. Nullable-Werttypen sind besonders hilfreich, wenn Sie Daten an und aus Datenbanken übergeben, in denen die numerischen Werte NULL oder nicht definiert sein können. Weitere Informationen finden Sie unter [Nullable-Werttypen](language-reference/builtin-types/nullable-value-types.md).

## <a name="see-also"></a>Siehe auch

- [Klassen](programming-guide/classes-and-structs/classes.md)
- [Grundlegende Typen](basic-types.md)
