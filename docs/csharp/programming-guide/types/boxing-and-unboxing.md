---
title: Boxing und Unboxing – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- cs.boxing
helpviewer_keywords:
- C# language, boxing
- C# language, unboxing
- unboxing [C#]
- boxing [C#]
ms.assetid: 8da9bbf4-bce9-4b08-b2e5-f64c11c56514
ms.openlocfilehash: 62df08bf4ae3580e9b8d5b3aab0697d396674ca1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745416"
---
# <a name="boxing-and-unboxing-c-programming-guide"></a>Boxing und Unboxing (C#-Programmierhandbuch)

Beim Boxing handelt es sich um die Konvertierung eines [Werttyps](../../language-reference/builtin-types/value-types.md) in den Typ `object` oder in einen beliebigen anderen Schnittstellentyp, der durch diesen Werttyp implementiert wird. Wenn die Common Language Runtime (CLR) für einen Werttyp das Boxing durchführt, wird der Wert mit einer <xref:System.Object?displayProperty=nameWithType>-Instanz umschlossen und im verwalteten Heap gespeichert. Durch Unboxing wird der Werttyp aus dem Objekt extrahiert. Boxing ist implizit, Unboxing ist explizit. Das Konzept von Boxing und Unboxing unterliegt der einheitlichen C#-Ansicht des Typsystems, in dem ein Wert eines beliebigen Typs als Objekt behandelt werden kann.

Im folgenden Beispiel wird die ganzzahlige Variable `i` mittels *Boxing* konvertiert und dem Objekt `o` zugewiesen.

[!code-csharp[csProgGuideTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#14)]

Das Objekt `o` kann dann mittels Unboxing zurückkonvertiert und der ganzzahligen Variablen `i` zugewiesen werden:

[!code-csharp[csProgGuideTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#15)]

Die folgenden Beispiele veranschaulichen, wie Boxing in C# verwendet wird.

[!code-csharp[csProgGuideTypes#47](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#47)]

## <a name="performance"></a>Leistung

Im Verhältnis zu einfachen Zuweisungen sind Boxing und Unboxing rechentechnisch aufwändige Prozesse. Wenn ein Werttyp mittels Boxing konvertiert wird, muss ein neues Objekt zugeordnet und erstellt werden. Die für Unboxing erforderliche Umwandlung ist ebenfalls, jedoch in geringerem Maße rechentechnisch aufwändig. Weitere Informationen finden Sie unter [Leistung](../../../framework/performance/performance-tips.md).

## <a name="boxing"></a>Boxing

Boxing wird verwendet, um Werttypen im Heap der Garbage Collection zu speichern. Beim Boxing handelt es sich um die implizite Konvertierung eines [Werttyps](../../language-reference/builtin-types/value-types.md) in den Typ `object` oder in einen beliebigen anderen Schnittstellentyp, der durch diesen Werttyp implementiert wird. Beim Boxing eines Werttyps wird auf dem Heap eine Objektinstanz zugeordnet. Anschließend wird der Wert in das neue Objekt kopiert.

Beachten Sie die folgende Deklaration einer Werttypvariablen:

[!code-csharp[csProgGuideTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#17)]

Mit der folgenden Anweisung wird der Boxing-Vorgang implizit auf die Variable `i` angewendet:

[!code-csharp[csProgGuideTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#18)]

Diese Anweisung bewirkt, dass der Objektverweis `o` auf dem Stapel erstellt wird, der auf einen Wert vom Typ `int` auf dem Heap verweist. Dieser Wert ist eine Kopie des Werttyps, der der Variablen `i` zugewiesen ist. In der folgenden Abbildung der Boxing-Konversation ist der Unterschied zwischen den Variablen `i` und `o` dargestellt.

![Abbildung, die den Unterschied zwischen den Variablen „i“ und „o“ zeigt.](./media/boxing-and-unboxing/boxing-operation-i-o-variables.gif)

Es auch möglich, das Boxing wie im folgenden Beispiel explizit auszuführen. Explizites Boxing ist jedoch nie erforderlich:

[!code-csharp[csProgGuideTypes#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#19)]

## <a name="description"></a>Beschreibung

In diesem Beispiel wird die Ganzzahlvariable `i` mittels Boxing in das Objekt `o` konvertiert. Anschließend wird der in der Variablen `i` gespeicherte Wert von `123` in `456` geändert. Das Beispiel veranschaulicht, dass der ursprüngliche Werttyp und das durch Boxing entstehende Objekt unterschiedliche Speicherorte verwenden und daher verschiedene Werte speichern können.

## <a name="example"></a>Beispiel

[!code-csharp[csProgGuideTypes#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#16)]

## <a name="unboxing"></a>Unboxing

Beim Unboxing handelt es sich um eine explizite Konvertierung vom `object`-Typ in einen [Werttyp](../../language-reference/builtin-types/value-types.md) bzw. von einem Schnittstellentyp in einen Werttyp, durch den die Schnittstelle implementiert wird. Ein Unboxing-Vorgang umfasst folgende Schritte:

- Überprüfen der Objektinstanz, um sicherzustellen, dass es sich um einen mittels Boxing "verpackten" Wert des jeweiligen Werttyps handelt.

- Kopieren des Werts aus der Instanz in die Werttypvariable.

Anhand der folgenden Anweisungen werden sowohl Boxing-Vorgänge als auch Unboxing-Vorgänge veranschaulicht:

[!code-csharp[csProgGuideTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#21)]

In der folgenden Abbildung ist das Ergebnis der vorherigen Anweisungen dargestellt:

![Abbildung einer Unboxing-Konvertierung.](./media/boxing-and-unboxing/unboxing-conversion-operation.gif)

Damit das Unboxing eines Werttypen zur Laufzeit erfolgreich verläuft, muss das zu konvertierende Element ein Verweis auf ein Objekt sein, das zuvor durch Boxing einer Instanz dieses Werttyps erstellt wurde. Der Versuch, ein Unboxing durchzuführen, `null` löst ein <xref:System.NullReferenceException> aus. Der Versuch, einen Verweis auf einen nicht kompatiblen Werttyp mittels Unboxing zu konvertieren, führt zu einer <xref:System.InvalidCastException>.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein Fall von ungültigem Unboxing und der sich daraus ergebenden `InvalidCastException` veranschaulicht. Bei Verwendung von `try` und `catch` wird eine Fehlermeldung angezeigt, wenn der Fehler auftritt.

[!code-csharp[csProgGuideTypes#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#20)]

Dieses Programm gibt Folgendes aus:

`Specified cast is not valid. Error: Incorrect unboxing.`

Wenn Sie die Anweisung

```csharp
int j = (short) o;
```

in:

```csharp
int j = (int) o;
```

ändern, wird die Konvertierung ausgeführt und Folgendes ausgegeben.

`Unboxing OK.`

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Verweistypen](../../language-reference/keywords/reference-types.md)
- [Werttypen](../../language-reference/builtin-types/value-types.md)
