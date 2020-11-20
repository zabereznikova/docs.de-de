---
title: Dekonstruieren von Tupeln und anderen Typen
description: Informationen zum Dekonstruieren von Tupeln und anderen Typen.
ms.technology: csharp-fundamentals
ms.date: 11/23/2017
ms.assetid: 0b0c4b0f-4a47-4f66-9b8e-f5c63b195960
ms.openlocfilehash: 96168b729ae3ec11d7a38444b8c100bdbff4efbf
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439702"
---
# <a name="deconstructing-tuples-and-other-types"></a>Dekonstruieren von Tupeln und anderen Typen

Ein Tupel stellt einen einfachen Weg bereit, um mehrere Werte aus einem Methodenaufruf abzurufen. Sobald Sie den Tupel abrufen, müssen Sie jedoch seine individuellen Elemente bearbeiten. Jedes Element einzeln zu bearbeiten ist jedoch mühselig, wie das folgende Beispiel zeigt. Die Methode `QueryCityData` gibt ein 3-Tupel zurück, und jedes seiner Elemente wird in einem separaten Vorgang einer Variable zugewiesen.

[!code-csharp[WithoutDeconstruction](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple1.cs)]

Das Abrufen von mehreren Feld- und Eigenschaftswerten aus einem Objekt kann genauso mühselig sein: Sie müssen einen Feld- oder Eigenschaftswert einer Variable zuweisen, indem Sie jedes Element einzeln eingeben.

Ab C# 7.0 können Sie mit einem einzigen *Dekonstruieren*-Vorgang mehrere Elemente aus einem Tupel oder mehrere berechnete, Feld- und Eigenschaftswerte aus einem Objekt abrufen. Wenn Sie ein Tupel dekonstruieren, weisen Sie seine Elemente einzelnen Variablen zu. Wenn Sie ein Objekt dekonstruieren, weisen Sie bestimmte Elemente einzelnen Variablen zu.

## <a name="deconstructing-a-tuple"></a>Dekonstruieren eines Tupel

Die Features von C# bieten eine integrierte Unterstützung für Dekonstruieren von Tupeln, sodass Sie alle Elemente in einem Tupel mit einem einzigen Vorgang entpacken können. Die allgemeine Syntax für das Dekonstruieren eines Tupel ist ähnlich der Syntax für das Definieren eines Tupel: Auf der linken Seite einer Zuweisungsanweisung umschließen Sie die Variablen, denen die Elemente zugewiesen werden sollen, mit Klammern. Die folgende Anweisung weist die Elemente eines 4-Tupels beispielsweise vier einzelnen Variablen zu:

```csharp
var (name, address, city, zip) = contact.GetAddressInfo();
```

Es gibt drei Wege zum Dekonstruieren eines Tupels:

- Sie können den Typ jedes Felds innerhalb der Klammern explizit deklarieren. Das folgende Beispiel verwendet diese Methode, um den 3-Tupel zu dekonstruieren, der von der Methode `QueryCityData` zurückgegeben wurde.

    [!code-csharp[Deconstruction-Explicit](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple2.cs#1)]

- Sie können das Schlüsselwort `var` verwenden, damit C# den Typ jeder Variable herleitet. Platzieren Sie das Schlüsselwort `var` außerhalb der Klammern. Im folgenden Beispiel wird ein Typrückschluss beim Dekonstruieren des von der Methode `QueryCityData` zurückgegebenen 3-Tupel verwendet.

    [!code-csharp[Deconstruction-Infer](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple3.cs#1)]

    Sie können das Schlüsselwort `var` auch einzeln mit beliebigen oder allen Variablendeklarationen innerhalb der Klammern verwenden.

    [!code-csharp[Deconstruction-Infer-Some](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple4.cs#1)]

    Dies ist jedoch sehr mühselig und wird nicht empfohlen.

- Schließlich können Sie das Tupel in bereits deklarierte Variablen dekonstruieren.

    [!code-csharp[Deconstruction-Declared](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-tuple5.cs#1)]

Beachten Sie, dass Sie einen bestimmten Typ außerhalb der Klammern nicht spezifizieren können, auch wenn jedes Feld im Tupel den selben Typ hat. Dadurch wird der Compilerfehler CS8136 „Durch die Dekonstruktion der Form „var (...)“ wird ein bestimmter Typ für „var“ unzulässig.“ generiert.

Beachten Sie, dass Sie ebenfalls jedes Element des Tupel einer Variable zuweisen müssen. Wenn Sie Elemente auslassen, generiert der Compiler den Fehler: CS8132, „Tupel mit x Elementen kann nicht in y Variablen dekonstruiert werden.“

Beachten Sie, dass Sie Deklarationen und Zuweisungen nicht mit den vorhandenen Variablen auf der linken Seite einer Dekonstruktion vermischen können. Der Compiler generiert die Fehlermeldung CS8184 "a deconstruction cannot mix declarations and expressions on the left-hand-side." (Eine Dekonstruktion kann Deklarationen und Ausdrücke auf der linken Seite nicht mischen.), wenn die Member neu deklarierte und vorhandene Variablen enthalten.

## <a name="deconstructing-tuple-elements-with-discards"></a>Dekonstruieren von Tupelelementen mit Ausschüssen

Häufig sind Sie beim Dekonstruieren eines Tupel nur an den Werten mancher Elemente interessiert. Ab C# 7.0 können Sie die Unterstützung von C# für *Ausschüsse* nutzen, bei denen es sich um lesegeschützte Variablen handelt, die Sie ignorieren möchten. Ein Ausschuss wird in einer Zuweisung durch einen Unterstrich („\_“) angegeben. Sie können beliebig viele Werte verwerfen, diese werden alle in einem einzigen Ausschuss dargestellt, `_`.

Das folgende Beispiel veranschaulicht die Verwendung von Tupels mit Ausschüssen. Die Methode `QueryCityDataForYears` gibt einen 6-Tupel mit dem Namen einer Stadt, ihrer Fläche, einer Jahreszahl, der Bevölkerung der Stadt in diesem Jahr, einer zweiten Jahreszahl und der Bevölkerung der Stadt im zweiten Jahr zurück. Das Beispiel zeigt die Veränderung der Bevölkerung zwischen diesen beiden Jahren. Von den Daten, die im Tupel verfügbar sind, ist die Fläche der Stadt nicht relevant für uns und außerdem kennen wir den Namen der Stadt und die zwei Datumswerte zur Entwurfszeit. Darum sind wir nur an den zwei Bevölkerungsgwerten interessiert, die im Tupel gespeichert sind und behandeln die restlichen Werte als Ausschuss.  

[!code-csharp[Tuple-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

## <a name="deconstructing-user-defined-types"></a>Dekonstruieren von benutzerdefinierten Typen

C# bietet keine integrierte Unterstützung für das Dekonstruieren von Typen, die kein Tupel sind. Als Autor einer Klasse, Struktur oder Schnittstelle können Sie jedoch den Instanzen des Typs das Dekonstruieren durch die Implementierung von mindestens einer Methode `Deconstruct` gestatten. Die Methode gibt „void“ zurück und jeder Wert, der dekonstruiert werden soll, wird durch den Parameter [out](language-reference/keywords/out-parameter-modifier.md) in der Methodensignatur angegeben. Die folgende Methode `Deconstruct` einer `Person`-Klasse gibt beispielsweise den Vor-, Zweit- und Nachnamen zurück:

[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class1.cs#1)]

Sie können dann eine Instanz der Klasse `Person` mit dem Namen `p` mit einer Zuweisung wie im folgenden Beispiel dekonstruieren:

[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class1.cs#2)]

Das folgende Beispiel überlädt die Methode `Deconstruct`, um verschiedene Kombinationen von Eigenschaften eines `Person`-Objekts zurückzugeben. Einzelne Überladungen geben Folgendes zurück:

- Einen Vor- und Nachnamen.
- Ein Vorname, ein zweiter Vorname und ein Nachname
- Einen Vor- und Nachnamen, einen Namen einer Stadt und eines Staats.

[!code-csharp[Class-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-class2.cs)]

Da Sie die Methode `Deconstruct` überladen können, um Gruppen von Daten zurückzusenden, die häufig aus einem Objekt extrahiert werden, sollten Sie bei der Definition von `Deconstruct`-Methoden darauf achten, dass deren Signaturen unverkennbar und eindeutig sind. Mehrere `Deconstruct`-Methoden, die über dieselbe Anzahl an `out`-Parametern oder über dieselbe Anzahl und dieselben Typen von `out`-Parametern in unterschiedlicher Reihenfolge verfügen, können zu Verwirrung führen.

Die überladene Methode `Deconstruct` im folgenden Beispiel veranschaulicht eine mögliche Quelle der Verwirrung. Die erste Überladung gibt den Vor-, Zweit- und Nachnamen und das Alter eines `Person`-Objekts in dieser Reihenfolge zurück. Die zweite Überladung gibt die Informationen zu den Namen nur zusammen mit dem jährlichen Einkommen zurück. Die Reihenfolge von Vor-, Zweit- und Nachname ist jedoch eine andere. Dadurch kann die Reihenfolge eines Arguments beim Dekonstruieren einer `Person`-Instanz leicht verwechselt werden.

[!code-csharp[Deconstruct-ambiguity](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-ambiguous.cs)]

## <a name="deconstructing-a-user-defined-type-with-discards"></a>Dekonstruieren eines benutzerdefinierten Typs mit Ausschüssen

Genau wie bei [Tupels](#deconstructing-tuple-elements-with-discards) können Sie Ausschüsse verwenden, um ausgewählte Elemente zu ignorieren, die von einer `Deconstruct`-Methode zurückgegeben werden. Jeder Ausschuss wird von einer Variable mit dem Namen „\_“ definiert, und ein einziger Dekonstruierungsvorgang kann mehrere Ausschüsse beinhalten.

Im folgenden Beispiel wird ein `Person`-Objekt in vier Zeichenfolgen (den Vor- und Nachnamen, die Stadt und den Staat) dekonstruiert, der Nachname und der Staat werden jedoch verworfen.

[!code-csharp[Class-discard](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/class-discard1.cs#1)]

## <a name="deconstructing-a-user-defined-type-with-an-extension-method"></a>Dekonstruieren eines benutzerdefinierten Typs mit einer Erweiterungsmethode

Wenn Sie nicht der Autor einer Klasse, Struktur oder Schnittstelle sind, können Sie die Objekte dieses Typs dennoch dekonstruieren, indem Sie eine oder mehrere `Deconstruct` [extension methods (Erweiterungsmethoden)](programming-guide/classes-and-structs/extension-methods.md) implementieren, um die Werte zurückzugeben, an denen Sie interessiert sind.

Im folgenden Beispiel werden zwei `Deconstruct`-Erweiterungsmethoden für die Klasse <xref:System.Reflection.PropertyInfo?displayProperty=nameWithType> definiert. Die erste gibt einen Satz von Werten zurück, der die Merkmale der Eigenschaft angibt, einschließlich ihres Typs, ob es sich dabei um eine statische oder eine Instanzeigenschaft handelt und ob die Eigenschaft schreibgeschützt oder indiziert ist. Die zweite gibt die Zugriffsebene der Eigenschaft an. Da die Zugriffsebene von Get- und Set-Zugriffsmethoden Unterschiede aufweisen kann, geben boolesche Werte an, ob die Eigenschaft über separate Get- und Set-Zugriffsmethoden verfügt und, wenn dies der Fall ist, ob sie über dieselbe Zugriffsebene verfügen. Wenn es nur eine Zugriffsmethode gibt oder die Get- und Set-Zugriffsmethode über dieselbe Zugriffsebene verfügen, gibt die Variable `access` die Zugriffsebene der Eigenschaft als Ganzes an. Andernfalls wird die Zugriffsebene der Get- und Set-Zugriffsmethoden von den Variablen `getAccess` und `setAccess` angezeigt.

[!code-csharp[Extension-deconstruct](../../samples/snippets/csharp/programming-guide/deconstructing-tuples/deconstruct-extension1.cs)]

## <a name="see-also"></a>Siehe auch

- [Verwerfen](discards.md)
- [Tupeltypen](language-reference/builtin-types/value-tuples.md)
