---
title: volatile – C#-Referenz
ms.date: 10/24/2018
f1_keywords:
- volatile_CSharpKeyword
- volatile
helpviewer_keywords:
- volatile keyword [C#]
ms.assetid: 78089bc7-7b38-4cfd-9e49-87ac036af009
ms.openlocfilehash: c7a6c442c33ac2b41f652805837f455a957819de
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712844"
---
# <a name="volatile-c-reference"></a>volatile (C#-Referenz)

Das Schlüsselwort `volatile` gibt an, dass ein Feld von mehreren Threads geändert werden kann, die zur gleichen Zeit ausgeführt werden. Der Compiler, das Runtimesystem und sogar die Hardware können aus Leistungsgründen die Lese- und Schreibvorgänge in den Speicherorten neu anordnen. Felder, die als `volatile` deklariert sind, sind von dieser Optimierungen nicht betroffen. Durch Hinzufügen des `volatile`-Modifizierers stellen Sie sicher, dass alle Threads volatile Schreibvorgänge, die von einem anderen Thread ausgeführt werden, in der Reihenfolge ihrer Ausführung berücksichtigen. Es gibt keine Garantie für eine einzelne Gesamtsortierung von volatile-Schreibvorgängen aus der Sicht aller ausgeführten Threads.

Das Schlüsselwort `volatile` kann auf Felder der folgenden Typen angewendet werden:

- Verweistypen.
- Zeigertypen (in unsicherem Kontext). Beachten Sie, dass der Zeiger selbst als „volatile“ deklariert sein kann, das Objekt, auf das er zeigt aber nicht. Anders ausgedrückt können Sie keinen „Zeiger auf ‚volatile‘“ deklarieren.
- Einfacher Typen wie `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `char`, `float` und `bool`.
- Ein `enum`-Typ mit einem der folgenden Basistypen: `byte`, `sbyte`, `short`, `ushort`, `int` oder `uint`.
- Generische Typparameter, die als Verweistypen bekannt sind.
- <xref:System.IntPtr> und <xref:System.UIntPtr>.

Andere Typen, einschließlich `double` und `long`, können nicht mit `volatile` markiert werden, da Lese- und Schreibvorgänge in die Felder dieser Typen nicht unbedingt atomar sind. Um den Multithreadzugriff auf diese Feldtypen zu schützen, verwenden Sie die Klassenmitglieder <xref:System.Threading.Interlocked> oder schützen Sie den Zugriff mit der Anweisung [`lock`](lock-statement.md).

Das Schlüsselwort `volatile` kann nur auf Felder einer `class` oder `struct` angewendet werden. Lokale Variablen können nicht als `volatile` deklariert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird die Deklaration einer öffentlichen Feldvariable als `volatile` dargestellt.

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Declaration)]

Im folgenden Beispiel wird veranschaulicht, wie ein Hilfs- oder Arbeitsthread erstellt wird und für das Ausführen der Verarbeitung parallel mit dem primären Thread verwendet werden kann. Weitere Informationen zum Multithreading finden Sie unter [Verwaltetes Threading](../../../standard/threading/index.md).

[!code-csharp[declareVolatile](~/samples/snippets/csharp/language-reference/keywords/volatile/Program.cs#Volatile)]

Wenn der `volatile`-Modifizierer der Deklaration von `_shouldStop` hinzugefügt wird, erhalten Sie immer die gleichen Ergebnisse (ähnlich dem Auszug aus dem vorhergehenden Code). Ohne diesen Modifizierer für das `_shouldStop`-Mitglied ist das Verhalten unvorhersehbar. Die `DoWork`-Methode kann den Mitgliederzugriff optimieren, was zum Lesen veralteter Daten führt. Aufgrund der Natur der Multithreadprogrammierung ist die Anzahl der veraltete Lesevorgänge unvorhersehbar. Verschiedene Programmläufe führen zu etwas unterschiedlichen Ergebnissen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Weitere Informationen

- [C#-Sprachspezifikation: Schlüsselwort „volatile“](../../../../_csharplang/spec/classes.md#volatile-fields)
- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [Modifizierer](index.md)
- [lock-Anweisung](lock-statement.md)
- <xref:System.Threading.Interlocked>
