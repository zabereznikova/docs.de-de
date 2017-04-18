---
title: "Strukturen | Leitfaden für C#"
description: "Erfahren Sie mehr über den Typ „Struktur“ und wie Sie diesen erstellen"
keywords: .NET, .NET Core, C#
author: BillWagner
ms.author: wiwagn
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: a7094b8c-7229-4b6f-82fc-824d0ea0ec40
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1733538c605cb06c7da4d91a6780caa3ea3bec23
ms.lasthandoff: 03/13/2017

---

# <a name="structs"></a>Strukturen
Eine *Struktur* ist ein Werttyp. Wenn eine Struktur erstellt wird, enthält die Variable, der die Struktur zugewiesen wird, die eigentlichen Daten der Struktur. Wenn die Struktur einer neuen Variable zugewiesen wird, werden diese kopiert. Die neue Variable und die ursprüngliche Variable enthalten daher zwei separate Kopien der gleichen Daten. Änderungen an einer Kopie wirken sich nicht auf die andere Kopie aus.

Werttypvariablen enthalten die zugehörigen Werte direkt, d. h., der Speicher wird inline in dem Kontext belegt, in dem die Variable deklariert ist. Für Werttypvariablen erfolgt keine getrennte Heapzuordnung oder ein Mehraufwand für die Garbage Collection.  
  
Zwei Kategorien von Werttypen sind verfügbar: [struct](./language-reference/keywords/struct.md) und [enum](./language-reference/keywords/enum.md).  
  
Die integrierten numerischen Typen sind Strukturen und verfügen über Eigenschaften und Methoden, auf die Sie zugreifen können:  
  
[!code-csharp[Statische Methode](../../samples/snippets/csharp/concepts/structs/static-method.cs)]
  
Sie deklarieren diese jedoch und weisen ihnen Werte zu, als wären es einfache, nicht aggregierte Typen:  
  
[!code-csharp[Zuweisen von Werten](../../samples/snippets/csharp/concepts/structs/assign-value.cs)] 
  
Werttypen sind *versiegelt* (sealed). Dies bedeutet z.B., dass Sie keinen Typ von @System.Int32 ableiten können und dass eine Struktur nicht von einer benutzerdefinierten Klasse oder Struktur erben kann, weil eine Struktur nur von @System.ValueType erben kann. Eine Struktur kann jedoch eine oder mehrere Schnittstellen implementieren. Sie können einen Strukturtyp in einen Schnittstellentyp umwandeln. Dadurch wird ein *Boxing*-Vorgang gestartet, mit dem die Struktur von einem Referenztypobjekt im verwalteten Heap umschlossen wird. Boxing-Vorgänge werden auch ausgeführt, wenn Sie einen Werttyp an eine Methode übergeben, die @System.Object als Eingabeparameter akzeptiert. Weitere Informationen finden Sie unter [Boxing und Unboxing](./programming-guide/types/boxing-and-unboxing.md ).  
  
Sie können das [struct](./language-reference/keywords/struct.md)-Schlüsselwort verwenden, um eigene benutzerdefinierte Werttypen zu erstellen. In der Regel wird eine Struktur als Container für einen kleinen Satz verwandter Variablen verwendet, wie im folgenden Beispiel dargestellt:  
  
[!code-csharp[Struct Keyword](../../samples/snippets/csharp/concepts/structs/struct-keyword.cs)]  
  
Weitere Informationen über Werttypen im .NET Framework finden Sie unter [Allgemeines Typsystem](../standard/common-type-system.md).  
    
Strukturen teilen sich einen großen Teil der Syntax mit Klassen, obwohl Strukturen eingeschränkter als Klassen sind:  
  
-   Innerhalb einer Strukturdeklaration können Felder nicht initialisiert werden, außer Sie werden als `const` oder `static` deklariert.  
  
-   Eine Struktur kann keinen Standardkonstruktor (ein Konstruktor ohne Parameter) oder Destruktor deklarieren.  
  
-   Strukturen werden bei Zuweisung kopiert. Wenn eine Struktur einer neuen Variable zugewiesen wird, werden alle Daten kopiert, und jede Änderung an der neuen Kopie ändert nicht die Daten für das Original. Es ist wichtig, sich das zu merken, wenn Sie mit Auflistungen von Wertetypen wie Dictionary<string, myStruct> arbeiten.  
  
-   Strukturen sind Werttypen, und Klassen sind Verweistypen.  
  
-   Strukturen können im Gegensatz zu Klassen ohne den Operator `new` instanziiert werden.  
  
-   Strukturen können Konstruktoren deklarieren, die Parameter besitzen.  
  
-   Eine Struktur kann nicht von einer anderen Struktur oder Klasse erben, und sie kann auch nicht die Basis einer Klasse sein. Alle Strukturen erben direkt von @System.ValueType, das von @System.Object erbt.  
  
-   Eine Struktur kann Schnittstellen implementieren.

## <a name="literal-values"></a>Literalwerte  
In C# erhalten Literalwerte einen Typ vom Compiler. Sie können festlegen, wie ein numerisches Literal eingegeben werden soll, indem Sie am Ende der Zahl einen Buchstaben anfügen. Um z. B. anzugeben, dass der Wert 4.56 als Gleitkommazahl behandelt werden soll, fügen Sie nach der Zahl `4.56f` ein "f" oder "F" an: Wenn kein Buchstabe angefügt wird, leitet der Compiler den `double`-Typ für das Literal ab. Weitere Informationen darüber, welche Typen mit Buchstabensuffixen angegeben werden können, finden Sie auf den Referenzseiten für einzelne Typen unter [Werttypen](./language-reference/keywords/value-types.md).  
  
Da Literale typisiert sind und alle Typen letztlich von @System.Object abgeleitet werden, können Sie Code der folgenden Art erstellen und kompilieren:  
  
[!code-csharp[Literalwerte](../../samples/snippets/csharp/concepts/structs/literals.cs)]

Die letzten beiden Beispiele veranschaulichen die Sprachfunktionen, die in C# 7.0 eingeführt wurden. Mit dem Ersten können Sie ein Unterstrichzeichen als eine *Zeichentrennlinie* in numerischen Literalen verwenden. Sie können es beliebig zwischen Zahlen setzen, um die Lesbarkeit zu verbessern. Es hat keine Auswirkung auf den Wert.

Im zweiten Beispiel werden *binäre Literale* veranschaulicht, mit denen Sie ein Bitmuster direkt angeben können, anstatt Hexadezimalnotation zu verwenden.

## <a name="nullable-types"></a>Auf NULL festlegbare Typen  
Gewöhnliche Werttypen können nicht den Wert [NULL](./language-reference/keywords/null.md) aufweisen. Sie können jedoch auf NULL festlegbare Werttypen erstellen, indem Sie nach dem Typ ein **?** anfügen. after the type. Zum Beispiel ist **int?** ein **int**-Typ, der auch den Wert [NULL](./language-reference/keywords/null.md) haben kann. Im CTS sind Typen, die NULL-Werte zulassen, Instanzen vom generischen Strukturtyp @System.Nullable%601. Typen, die NULL-Werte zulassen, sind besonders hilfreich, wenn Sie Daten an und aus Datenbanken übergeben, in denen die numerischen Werte NULL sein können. Weitere Informationen finden Sie unter [Typen, die NULL-Werte zulassen (C#-Programmierhandbuch)](./programming-guide/nullable-types/index.md).

## <a name="see-also"></a>Siehe auch
[Klassen](classes.md)

[Grundlegende Typen](basic-types.md)
