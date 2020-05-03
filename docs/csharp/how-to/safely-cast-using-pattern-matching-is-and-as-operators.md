---
title: 'Vorgehensweise: Sicheres Umwandeln mit Musterabgleich und den Operatoren „is“ und „as“'
description: Erfahren Sie, wie Sie Techniken für den Musterabgleich anwenden, um Variablen sicher in einen anderen Typ umzuwandeln. Sie können sowohl den Musterabgleich als auch die Operatoren „is“ und „as“ verwenden, um Typen sicher umzuwandeln.
ms.date: 09/05/2018
helpviewer_keywords:
- cast operators [C#], as and is operators
- as operator [C#]
- is operator [C#]
ms.openlocfilehash: 9f5690e6840098f94360dba89f09fb23b258b782
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739050"
---
# <a name="how-to-safely-cast-by-using-pattern-matching-and-the-is-and-as-operators"></a>Vorgehensweise: Sicheres Umwandeln mit Musterabgleich und den Operatoren „is“ und „as“

Da Objekte polymorph sind, ist es möglich, dass eine Variable eines Basisklassentyps einen abgeleiteten [Typ](../programming-guide/types/index.md) enthalten kann. Für den Zugriff auf die Instanzmember des abgeleiteten Typs ist es erforderlich, dass Sie den Wert wieder in den abgeleiteten Typ [umwandeln](../programming-guide/types/casting-and-type-conversions.md). Allerdings entsteht durch eine Umwandlung das Risiko, eine <xref:System.InvalidCastException>-Ausnahme auszulösen. C# stellt [Musterabgleich](../pattern-matching.md)-Anweisungen bereit, die eine Umwandlung unter der Bedingung ausführen, dass sie erfolgreich sein wird. C# bietet außerdem die Operatoren [is](../language-reference/operators/type-testing-and-cast.md#is-operator) und [as](../language-reference/operators/type-testing-and-cast.md#as-operator), um zu testen, ob ein Wert einen bestimmten Typ aufweist.

Das folgende Beispiel zeigt die Verwendung der `is`-Anweisung zum Musterabgleich:

[!code-csharp[Pattern matching is statement](../../../samples/snippets/csharp/how-to/safelycast/patternmatching/Program.cs#PatternMatchingIs)]

Im vorhergehenden Beispiel werden einige Features der Syntax für den Musterabgleich veranschaulicht. Die `if (a is Mammal m)`-Anweisung kombiniert den Test mit einer Initialisierungszuweisung. Die Zuweisung tritt nur auf, wenn der Test erfolgreich ist. Die Variable `m` befindet sich nur im Bereich der eingebetteten `if`-Anweisung, dem sie zugewiesen wurde. Sie können in der gleichen Methode später nicht auf `m` zugreifen. Das vorstehende Beispiel zeigt auch, wie der [`as`-Operator](../language-reference/operators/type-testing-and-cast.md#as-operator) zum Konvertieren eines Objekts in einen bestimmten Typ verwendet wird.

Sie können mithilfe der gleichen Syntax testen, ob ein [Nullable-Werttyp](../language-reference/builtin-types/nullable-value-types.md) einen Wert aufweist, wie im folgenden Beispiel gezeigt:

[!code-csharp[Pattern matching with nullable types](../../../samples/snippets/csharp/how-to/safelycast/nullablepatternmatching/Program.cs#PatternMatchingNullable)]

Im vorhergehenden Beispiel werden weitere Features des Musterabgleichs veranschaulicht, die mit Konvertierungen verwendet werden können. Sie können eine Variable für das NULL-Muster prüfen, indem Sie spezifisch nach dem `null`-Wert sehen. Wenn der Laufzeitwert der Variable `null` ist, gibt eine `is`-Anweisung, die nach einem Typ prüft, immer `false` zurück. Die `is`-Anweisung für den Musterabgleich lässt keinen Nullable-Typ für den Wert zu, z.B. `int?` oder `Nullable<int>`, jedoch können Sie nach jedem anderen Werttyp prüfen. Die `is`-Muster aus dem vorherigen Beispiel sind nicht auf die Nullable-Werttypen beschränkt. Sie können diese Muster auch verwenden, um zu testen, ob eine Variable eines Verweistyps über einen Wert oder verfügt oder `null` ist.

Im vorangegangenen Beispiel wird auch gezeigt, wie Sie das Typmuster in einer `switch`-Anweisung verwenden, bei der die Variable einen von vielen verschiedenen Typen aufweisen kann.

Wenn Sie testen möchten, ob eine Variable einen bestimmten Typ aufweist, Sie aber keine neue Variable zuweisen möchten, können Sie die Operatoren `is` und `as` für Verweistypen und Nullable-Werttypen verwenden. Im folgenden Code wird veranschaulicht, wie Sie die Anweisungen `is` und `as` verwenden, die Teil der C#-Sprache waren, bevor der Musterabgleich eingeführt wurde, um zu überprüfen, ob eine Variable einen bestimmten Typ aufweist:

[!code-csharp[testing variable types with the is and as statements](../../../samples/snippets/csharp/how-to/safelycast/asandis/Program.cs#IsAndAs)]

Wie Sie durch Vergleichen dieses Codes mit dem Code für den Musterabgleich sehen können, stellt die Syntax für den Musterabgleich robustere Features bereit, indem der Test und die Zuweisung in einer einzelnen Anweisung kombiniert werden. Verwenden Sie nach Möglichkeit die Syntax für den Musterabgleich.

Sie können diese Beispiele ausprobieren, indem Sie sich den Code in unserem [GitHub-Repository](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/how-to/safelycast) ansehen. Alternativ dazu können Sie die Beispiele [als ZIP-Datei](../../../samples/snippets/csharp/how-to/safelycast.zip) herunterladen.
