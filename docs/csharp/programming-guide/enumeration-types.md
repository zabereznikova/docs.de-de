---
title: Enumerationstypen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 09/10/2017
helpviewer_keywords:
- enumerations [C#]
- enums [C#]
- C# Language, enums
- bit flags [C#]
ms.assetid: 64a9b731-9e3c-4336-8a09-018db2aa10b7
ms.openlocfilehash: 3573959a1e10b475a9867631767de5d10a08b9ea
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73969767"
---
# <a name="enumeration-types-c-programming-guide"></a>Enumerationstypen (C#-Programmierhandbuch)

Ein Enumerationstyp (auch Enumeration oder enum genannt) bietet eine effiziente Möglichkeit zum Definieren von benannten ganzzahligen Konstanten, die einer Variablen zugewiesen werden können. Nehmen wir beispielsweise an, Sie müssen eine Variable definieren, deren Wert einen Tag der Woche darstellt. Es gibt nur sieben sinnvolle Werte, die diese Variable speichern kann. Sie können einen Enumerationstyp verwenden, der mithilfe des [enum](../language-reference/keywords/enum.md)-Schlüsselworts deklariert wurde, um diese Werte zu definieren.

[!code-csharp[csProgGuideEnums#1](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#1)]

Standardmäßig ist [int](../language-reference/builtin-types/integral-numeric-types.md) der zugrunde liegende Typ jedes Elements in enum. Sie können mithilfe eines Doppelpunktes einen anderen ganzzahligen numerischen Typ angeben, wie im vorherigen Beispiel gezeigt. Eine vollständige Liste der möglichen Typen finden Sie unter [enum (C#-Referenz)](../language-reference/keywords/enum.md).

Sie können die zugrunde liegenden numerischen Werte durch Umwandeln in den zugrunde liegenden Typ, wie im folgenden Beispiel gezeigt, überprüfen.

```csharp
Day today = Day.Monday;
int dayNumber =(int)today;
Console.WriteLine("{0} is day number #{1}.", today, dayNumber);

Month thisMonth = Month.Dec;
byte monthNumber = (byte)thisMonth;
Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);

// Output:
// Monday is day number #1.
// Dec is month number #11.
```

Im Folgenden werden die Vorteile der Verwendung eines enum anstelle eines numerischen Typs gezeigt:

- Sie geben für Clientcode eindeutig die Werte an, die für die Variable gültig sind.

- In Visual Studio listet IntelliSense die definierten Werte auf.

Wenn Sie keine Werte für die Elemente in der Enumeratorliste angeben, werden die Werte automatisch um 1 erhöht. Im vorherigen Beispiel hat `Day.Sunday` den Wert 0, `Day.Monday` hat den Wert 1 und so weiter. Beim Erstellen eines neuen `Day`-Objekt, wird es den Standardwert `Day.Sunday` (0) aufweisen, wenn Sie nicht explizit einen Wert zuweisen. Wenn Sie ein enum erstellen, wählen Sie den logischen Standardwert aus und weisen Sie ihm einen Wert von Null zu. Dadurch werden alle Enumerationen über diesen Standardwert verfügen, wenn sie nicht explizit einen Wert zugewiesen bekommen, wenn sie erstellt werden.

Wenn die Variable `meetingDay` vom Typ `Day` ist, dann können Sie (ohne eine explizite Umwandlung) für sie nur einen der durch `Day` definierten Werte zuweisen. Und wenn sich der Sitzungstag ändert, können Sie einen neuen Wert von `Day` auf `meetingDay` zuweisen:

[!code-csharp[csProgGuideEnums#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#4)]

> [!NOTE]
> Es ist möglich, einen beliebigen ganzzahligen Wert an `meetingDay` zuzuweisen. Diese Codezeile ergibt z.B. keinen Fehler: `meetingDay = (Day) 42`. Allerdings sollten Sie dies nicht tun, da implizit erwartet wird, dass eine Enumerationensvariable nur einen der von enum definierten Werte enthält. Einen beliebigen Wert einer Variablen eines Enumerationstyps zuzuweisen bedeutet, ein hohes Fehlerrisiko einzuführen.

Sie können den Elementen in der Enumeratorliste eines Enumerationstyps Werte zuweisen, und Sie können auch berechnete Werte verwenden:

[!code-csharp[csProgGuideEnums#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#3)]

## <a name="enumeration-types-as-bit-flags"></a>Enumerationstypen als Bitflags

Sie können einen Enumerationstyp zum Definieren von Bitflags verwenden. Dadurch kann eine Instanz des Enumerationstyps eine beliebige Kombination der Werte speichern, die in der Enumeratorliste definiert sind. (Natürlich können einige Kombinationen nicht sinnvoll oder in Ihrem Programmcode nicht zulässig sein.)

Sie erstellen ein Bitflags-Enum durch Anwenden des Attributs <xref:System.FlagsAttribute?displayProperty=nameWithType> und definieren die Werte entsprechend, damit die bitweisen Operationen `AND`, `OR`, `NOT` und `XOR` ausgeführt werden können. In einem Bitflag-Enum ist eine benannte Konstante mit dem Wert Null enthalten, das bedeutet, dass „keine Flags festgelegt sind“. Geben Sie einem Flag keinen Wert Null, wenn es nicht bedeutet, dass „keine Flags festgelegt sind“.

Im folgenden Beispiel ist eine andere Version der `Day`-Enum mit dem Namen `Days` definiert. `Days` verfügt über das `Flags`-Attribut, und jedem Wert wird die nächste höhere Potenz von 2 zugewiesen. Dies ermöglicht Ihnen die Erstellung einer `Days`-Variable, deren Wert `Days.Tuesday | Days.Thursday` ist.

[!code-csharp[csProgGuideEnums#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#2)]

Um ein Flag für einen enum festzulegen, verwenden Sie den bitweisen `OR` Operator, wie im folgenden Beispiel gezeigt:

[!code-csharp[csProgGuideEnums#6](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#6)]

Verwenden Sie einen bitweisen `AND`-Vorgang, wie im folgenden Beispiel gezeigt, um zu bestimmen, ob ein bestimmtes Flag festgelegt ist:

[!code-csharp[csProgGuideEnums#7](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#7)]

Weitere Informationen zu den notwendigen Überlegungen beim Definieren von Enumerationstypen mit dem <xref:System.FlagsAttribute?displayProperty=nameWithType>-Attribut finden Sie unter <xref:System.Enum?displayProperty=nameWithType>.

## <a name="using-the-systemenum-methods-to-discover-and-manipulate-enum-values"></a>Verwenden der Methoden System.Enum zum Ermitteln und Bearbeiten der Enumerationswerte

Alle Enumerationen sind Instanzen des Typs <xref:System.Enum?displayProperty=nameWithType>. Sie können keine neuen Klassen von <xref:System.Enum?displayProperty=nameWithType> ableiten, aber Sie können die zugehörigen Methoden verwenden, um Informationen zu ermitteln und Werte in einer enum-Instanz zu bearbeiten.

[!code-csharp[csProgGuideEnums#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEnums/CS/Enums.cs#5)]

Weitere Informationen finden Sie unter <xref:System.Enum?displayProperty=nameWithType>.

Sie können auch mithilfe einer Erweiterungsmethode eine neue Methode für ein enum erstellen. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen einer neuen Methode für eine Enumeration](./classes-and-structs/how-to-create-a-new-method-for-an-enumeration.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.Enum?displayProperty=nameWithType>
- [C#-Programmierhandbuch](./index.md)
- [enum](../language-reference/keywords/enum.md)
