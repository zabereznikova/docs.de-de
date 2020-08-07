---
title: Ausnahmebehandlung – C#-Programmierhandbuch
description: Erfahren Sie mehr über die Ausnahmebehandlung. Hier finden Sie Beispiele für try-catch-, try-finally- und try-catch-finally-Anweisungen.
ms.date: 07/20/2015
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
ms.openlocfilehash: 8e55b44573c40f594e567fc5a4501689e66c7af4
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302034"
---
# <a name="exception-handling-c-programming-guide"></a>Ausnahmebehandlung (C#-Programmierhandbuch)
Ein [try](../../language-reference/keywords/try-catch.md)-Block wird von C#-Programmierern verwendet, um Code zu partitionieren, der von einer Ausnahme betroffen sein könnte. Zugeordnete [catch](../../language-reference/keywords/try-catch.md)-Blöcke werden verwendet, um die sich ergebenden Ausnahmen zu behandeln. Ein [finally](../../language-reference/keywords/try-finally.md)-Block enthält Code, der ausgeführt wird, unabhängig davon, ob eine Ausnahme im `try`-Block ausgelöst wird, z.B. das Freigeben von Ressourcen, die im `try`-Block zugeordnet werden. Ein `try`-Block erfordert einen oder mehrere zugeordnete `catch`-Blöcke oder ein `finally`-Block oder beides.  
  
 Die folgenden Beispiele zeigen eine `try-catch`-Anweisung eine `try-finally`-Anweisung und eine `try-catch-finally`-Anweisung.  
  
 [!code-csharp[csProgGuideExceptions#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#6)]  
  
 [!code-csharp[csProgGuideExceptions#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#7)]  
  
 [!code-csharp[csProgGuideExceptions#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#8)]  
  
 Ein `try`-Block ohne einen `catch`- oder `finally`-Block verursachen einen Compilerfehler.  
  
## <a name="catch-blocks"></a>catch-Blöcke  
 Ein `catch`-Block kann den Typ der Ausnahme angeben, die abgefangen werden soll. Die Typspezifikation wird einen *Ausnahmefilter* aufrufen. Der Typ der Ausnahme sollte von <xref:System.Exception> abgeleitet werden. Im Allgemeinen sollten Sie <xref:System.Exception> nicht als Ausnahmefilter angeben, sofern Sie nicht entweder alle Ausnahmen behandeln können, die möglicherweise im `try`-Block ausgelöst werden, oder Sie nicht eine [throw](../../language-reference/keywords/throw.md)-Anweisung am Ende des `catch`-Blocks eingeschlossen haben.  
  
 Mehrere `catch`-Blöcke mit verschiedenen Ausnahmefiltern können miteinander verkettet werden. Die `catch`-Blöcke werden von oben nach unten in Ihrem Code überprüft, aber nur ein `catch`-Block wird für jede Ausnahme, die ausgelöst wird, ausgeführt. Der erste `catch`-Block, der den exakten Typ oder eine Basisklasse der ausgelösten Ausnahme angibt, wird ausgeführt. Wenn kein `catch`-Block einen passenden Ausnahmefilter angibt, wird ein `catch`-Block, der über keinen Filter verfügt, ausgewählt, wenn einer in der Anweisung vorhanden ist. Es ist wichtig, `catch`-Blöcke mit den spezifischsten (d.h. am stärksten abgeleiteten) Ausnahmetypen als erstes zu positionieren.  
  
 Sie sollten die Ausnahmen abfangen, wenn Folgendes zutrifft:  
  
- Sie verstehen, warum die Ausnahme ausgelöst werden kann, und Sie können eine bestimmte Wiederherstellung implementieren, wie z.B. den Benutzer auffordern, einen neuen Dateinamen einzugeben, wenn Sie ein Objekt <xref:System.IO.FileNotFoundException> abfangen.  
  
- Sie können eine neue und spezifischere Ausnahme erstellen und auslösen.  
  
     [!code-csharp[csProgGuideExceptions#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#9)]  
  
- Sie möchten eine Ausnahme teilweise behandeln, bevor Sie sie für eine zusätzliche Behandlung weitergeben. Im folgenden Beispiel wird ein `catch`-Block verwendet, um dem Fehlerprotokoll einen Eintrag hinzufügen, bevor die Ausnahme erneut ausgelöst wird.  
  
     [!code-csharp[csProgGuideExceptions#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#10)]  
  
## <a name="finally-blocks"></a>Finally-Blöcke  
 Mit einem `finally`-Block können Sie Aktionen bereinigen, die in einem `try`-Block ausgeführt werden. Falls vorhanden, wird der `finally`-Block zuletzt ausgeführt, nach dem `try`-Block und jedem übereinstimmenden `catch` Block. Ein `finally`-Block wird immer ausgeführt, unabhängig davon, ob eine Ausnahme ausgelöst wird oder ein `catch`-Block gefunden wird, der mit dem Ausnahmetyp übereinstimmt.  
  
 Der `finally`-Block kann zum Freigeben von Ressourcen verwendet werden, wie z.B. Dateistreams, Datenbankverbindungen und Grafikhandles, ohne Warten auf den Garbage Collector in der Laufzeit, um die Objekte zu beenden. Weitere Informationen finden Sie unter [using-Anweisung](../../language-reference/keywords/using-statement.md).  
  
 Im folgenden Beispiel wird der `finally`-Block verwendet, um eine Datei, die im `try`-Block geöffnet ist, zu schließen. Beachten Sie, dass der Status des Dateihandles überprüft wird, bevor die Datei geschlossen wird. Wenn der `try`-Block die Datei nicht öffnen kann, verfügt das Dateihandle immer noch über den Wert `null`, und der `finally`-Block versucht nicht, es zu schließen. Alternativ schließt der `finally`-Block die geöffnete Datei, wenn die Datei im `try`-Block erfolgreich geöffnet wird.  
  
 [!code-csharp[csProgGuideExceptions#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#11)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  

Weitere Informationen finden Sie unter [Ausnahmen](~/_csharplang/spec/exceptions.md) und [Die try-Anweisung](~/_csharplang/spec/statements.md#the-try-statement) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction). Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.
  
## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../language-reference/index.md)
- [C#-Programmierhandbuch](../index.md)
- [Ausnahmen und Ausnahmebehandlung](./index.md)
- [try-catch](../../language-reference/keywords/try-catch.md)
- [try-finally](../../language-reference/keywords/try-finally.md)
- [try-catch-finally](../../language-reference/keywords/try-catch-finally.md)
- [Using-Anweisung](../../language-reference/keywords/using-statement.md)
