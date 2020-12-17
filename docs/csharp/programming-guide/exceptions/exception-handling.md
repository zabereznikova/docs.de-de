---
title: Ausnahmebehandlung – C#-Programmierhandbuch
description: Erfahren Sie mehr über die Ausnahmebehandlung. Hier finden Sie Beispiele für try-catch-, try-finally- und try-catch-finally-Anweisungen.
ms.date: 12/09/2020
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: fabf1413ba498232e67f45460195fe96e25fab0a
ms.sourcegitcommit: 9b877e160c326577e8aa5ead22a937110d80fa44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "97110194"
---
# <a name="exception-handling-c-programming-guide"></a>Ausnahmebehandlung (C#-Programmierhandbuch)

Ein [try](../../language-reference/keywords/try-catch.md)-Block wird von C#-Programmierern verwendet, um Code zu partitionieren, der von einer Ausnahme betroffen sein könnte. Zugeordnete [catch](../../language-reference/keywords/try-catch.md)-Blöcke werden verwendet, um die sich ergebenden Ausnahmen zu behandeln. Ein [finally](../../language-reference/keywords/try-finally.md)-Block enthält Code, der unabhängig davon ausgeführt wird, ob eine Ausnahme im `try`-Block ausgelöst wird, z. B. beim Freigeben von Ressourcen, die im `try`-Block zugewiesen sind. Ein `try`-Block erfordert einen oder mehrere zugeordnete `catch`-Blöcke oder ein `finally`-Block oder beides.

Die folgenden Beispiele zeigen eine `try-catch`-Anweisung eine `try-finally`-Anweisung und eine `try-catch-finally`-Anweisung.

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryCatchStructure":::

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryFinallyStructure":::

:::code language="csharp" source="snippets/exceptions/Program.cs" id="TryCatchFinallyStructure":::

Ein `try`-Block ohne einen `catch`- oder `finally`-Block verursachen einen Compilerfehler.

## <a name="catch-blocks"></a>catch-Blöcke

Ein `catch`-Block kann den Typ der Ausnahme angeben, die abgefangen werden soll. Die Typspezifikation wird einen *Ausnahmefilter* aufrufen. Der Typ der Ausnahme sollte von <xref:System.Exception> abgeleitet werden. Im Allgemeinen sollten Sie <xref:System.Exception> nicht als Ausnahmefilter festlegen, sofern Sie nicht entweder alle Ausnahmen behandeln können, die möglicherweise im `try`-Block ausgelöst werden, oder Sie nicht eine [throw](../../language-reference/keywords/throw.md)-Anweisung am Ende des `catch`-Blocks eingeschlossen haben.

Mehrere `catch`-Blöcke mit verschiedenen Ausnahmeklassen können miteinander verkettet werden. Die `catch`-Blöcke werden von oben nach unten in Ihrem Code überprüft, aber nur ein `catch`-Block wird für jede Ausnahme, die ausgelöst wird, ausgeführt. Der erste `catch`-Block, der den exakten Typ oder eine Basisklasse der ausgelösten Ausnahme angibt, wird ausgeführt. Wenn kein `catch`-Block eine passende Ausnahmeklasse angibt, wird ein `catch`-Block, der über keinen Typ verfügt, ausgewählt, wenn einer in der Anweisung vorhanden ist. Es ist wichtig, `catch`-Blöcke mit den spezifischsten (d. h. am stärksten abgeleiteten) Ausnahmeklassen als erstes zu positionieren.

Fangen Sie Ausnahmen ab, wenn die folgenden Bedingungen erfüllt sind:

- Sie verstehen, warum die Ausnahme ausgelöst werden kann, und Sie können eine bestimmte Wiederherstellung implementieren, wie z.B. den Benutzer auffordern, einen neuen Dateinamen einzugeben, wenn Sie ein Objekt <xref:System.IO.FileNotFoundException> abfangen.
- Sie können eine neue und spezifischere Ausnahme erstellen und auslösen.
  :::code language="csharp" source="snippets/exceptions/Program.cs" id="ThrowMoreSpecificException":::
- Sie möchten eine Ausnahme teilweise behandeln, bevor Sie sie für eine zusätzliche Behandlung weitergeben. Im folgenden Beispiel wird ein `catch`-Block verwendet, um dem Fehlerprotokoll einen Eintrag hinzufügen, bevor die Ausnahme wieder ausgelöst wird.
  :::code language="csharp" source="snippets/exceptions/Program.cs" id="RethrowError":::

Sie können auch *Ausnahmefilter* festlegen, um einen booleschen Ausdruck zu einer Catch-Klausel hinzuzufügen. Diese geben an, dass eine spezifische Catch-Klausel nur übereinstimmt, wenn diese Bedingung erfüllt ist. Im folgenden Beispiel verwenden beide Catch-Klauseln dieselbe Ausnahmeklasse, jedoch wird eine zusätzliche Bedingung überprüft, um eine andere Fehlermeldung zu erstellen:

:::code language="csharp" source="snippets/exceptions/ExceptionFilter.cs" ID="DemonstrateExceptionFilter":::

Ein Ausnahmefilter, der immer `false` zurückgibt, kann dazu verwendet werden, alle Ausnahmen zu untersuchen, aber nicht zu verarbeiten. Ein üblicher Anwendungsfall ist die Protokollierung von Ausnahmen:

:::code language="csharp" source="snippets/exceptions/ExceptionFilter.cs" ID="ShowExceptionFilter":::

Die Methode `LogException` gibt immer `false` zurück. Es besteht keine Übereinstimmung mit einer `catch`-Klausel, die diesen Ausnahmefilter verwendet. Die Catch-Klausel kann allgemein sein und <xref:System.Exception?displayProperty=nameWithType> verwenden. Spätere Klauseln können spezifischere Ausnahmeklassen verarbeiten.

## <a name="finally-blocks"></a>Finally-Blöcke

Mit einem `finally`-Block können Sie Aktionen bereinigen, die in einem `try`-Block ausgeführt werden. Falls vorhanden, wird der `finally`-Block zuletzt ausgeführt, nach dem `try`-Block und jedem übereinstimmenden `catch` Block. Ein `finally`-Block wird immer ausgeführt, unabhängig davon, ob eine Ausnahme ausgelöst wird oder ein `catch`-Block gefunden wird, der mit dem Ausnahmetyp übereinstimmt.

Der `finally`-Block kann zum Freigeben von Ressourcen verwendet werden, wie z.B. Dateistreams, Datenbankverbindungen und Grafikhandles, ohne Warten auf den Garbage Collector in der Laufzeit, um die Objekte zu beenden. Weitere Informationen finden Sie unter [using-Anweisung](../../language-reference/keywords/using-statement.md).

Im folgenden Beispiel wird der `finally`-Block verwendet, um eine Datei, die im `try`-Block geöffnet ist, zu schließen. Beachten Sie, dass der Status des Dateihandles überprüft wird, bevor die Datei geschlossen wird. Wenn der `try`-Block die Datei nicht öffnen kann, verfügt das Dateihandle immer noch über den Wert `null`, und der `finally`-Block versucht nicht, die Datei zu schließen. Stattdessen schließt der `finally`-Block die geöffnete Datei, wenn die Datei im `try`-Block erfolgreich geöffnet wird.

:::code language="csharp" source="snippets/exceptions/Program.cs" id="CleanupIfNotNull":::

## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation

Weitere Informationen finden Sie unter [Ausnahmen](~/_csharplang/spec/exceptions.md) und [Die try-Anweisung](~/_csharplang/spec/statements.md#the-try-statement) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../language-reference/index.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
- [Using-Anweisung](../../language-reference/keywords/using-statement.md)
