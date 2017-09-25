---
title: Ausnahmebehandlung (C#-Programmierhandbuch)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#], about exception handling
- exceptions [C#], handling
ms.assetid: b4e4ecf2-b907-4e58-891f-2563762258e9
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ab03e00a6b62d0c737c90fdb489be2a78f7ab6af
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="exception-handling-c-programming-guide"></a>Ausnahmebehandlung (C#-Programmierhandbuch)
Ein [try](../../../csharp/language-reference/keywords/try-catch.md)-Block wird von C#-Programmierern verwendet, um Code zu partitionieren, der von einer Ausnahme betroffen sein könnte. Zugeordnete [catch](../../../csharp/language-reference/keywords/try-catch.md)-Blöcke werden verwendet, um die sich ergebenden Ausnahmen zu behandeln. Ein [finally](../../../csharp/language-reference/keywords/try-finally.md)-Block enthält Code, der ausgeführt wird, unabhängig davon, ob eine Ausnahme im `try`-Block ausgelöst wird, z.B. das Freigeben von Ressourcen, die im `try`-Block zugeordnet werden. Ein `try`-Block erfordert einen oder mehrere zugeordnete `catch`-Blöcke oder ein `finally`-Block oder beides.  
  
 Die folgenden Beispiele zeigen eine `try-catch`-Anweisung eine `try-finally`-Anweisung und eine `try-catch-finally`-Anweisung.  
  
 [!code-cs[csProgGuideExceptions#6](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_1.cs)]  
  
 [!code-cs[csProgGuideExceptions#7](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_2.cs)]  
  
 [!code-cs[csProgGuideExceptions#8](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_3.cs)]  
  
 Ein `try`-Block ohne einen `catch`- oder `finally`-Block verursachen einen Compilerfehler.  
  
## <a name="catch-blocks"></a>catch-Blöcke  
 Ein `catch`-Block kann den Typ der Ausnahme angeben, die abgefangen werden soll. Die Typspezifikation wird einen *Ausnahmefilter* aufrufen. Der Typ der Ausnahme sollte von <xref:System.Exception> abgeleitet werden. Im Allgemeinen sollten Sie <xref:System.Exception> nicht als Ausnahmefilter angeben, sofern Sie nicht entweder alle Ausnahmen behandeln können, die möglicherweise im `try`-Block ausgelöst werden, oder Sie nicht eine [throw](../../../csharp/language-reference/keywords/throw.md)-Anweisung am Ende des `catch`-Blocks eingeschlossen haben.  
  
 Mehrere `catch`-Blöcke mit verschiedenen Ausnahmefiltern können miteinander verkettet werden. Die `catch`-Blöcke werden von oben nach unten in Ihrem Code überprüft, aber nur ein `catch`-Block wird für jede Ausnahme, die ausgelöst wird, ausgeführt. Der erste `catch`-Block, der den exakten Typ oder eine Basisklasse der ausgelösten Ausnahme angibt, wird ausgeführt. Wenn kein `catch`-Block einen passenden Ausnahmefilter angibt, wird ein `catch`-Block, der über keinen Filter verfügt, ausgewählt, wenn einer in der Anweisung vorhanden ist. Es ist wichtig, `catch`-Blöcke mit den spezifischsten (d.h. am stärksten abgeleiteten) Ausnahmetypen als erstes zu positionieren.  
  
 Sie sollten die Ausnahmen abfangen, wenn Folgendes zutrifft:  
  
-   Sie verstehen, warum die Ausnahme ausgelöst werden kann, und Sie können eine bestimmte Wiederherstellung implementieren, wie z.B. den Benutzer auffordern, einen neuen Dateinamen einzugeben, wenn Sie ein Objekt <xref:System.IO.FileNotFoundException> abfangen.  
  
-   Sie können eine neue und spezifischere Ausnahme erstellen und auslösen.  
  
     [!code-cs[csProgGuideExceptions#9](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_4.cs)]  
  
-   Sie möchten eine Ausnahme teilweise behandeln, bevor Sie sie für eine zusätzliche Behandlung weitergeben. Im folgenden Beispiel wird ein `catch`-Block verwendet, um dem Fehlerprotokoll einen Eintrag hinzufügen, bevor die Ausnahme erneut ausgelöst wird.  
  
     [!code-cs[csProgGuideExceptions#10](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_5.cs)]  
  
## <a name="finally-blocks"></a>Finally-Blöcke  
 Mit einem `finally`-Block können Sie Aktionen bereinigen, die in einem `try`-Block ausgeführt werden. Falls vorhanden, wird der `finally`-Block zuletzt ausgeführt, nach dem `try`-Block und jedem übereinstimmenden `catch` Block. Ein `finally`-Block wird immer ausgeführt, unabhängig davon, ob eine Ausnahme ausgelöst wird oder ein `catch`-Block gefunden wird, der mit dem Ausnahmetyp übereinstimmt.  
  
 Der `finally`-Block kann zum Freigeben von Ressourcen verwendet werden, wie z.B. Dateistreams, Datenbankverbindungen und Grafikhandles, ohne Warten auf den Garbage Collector in der Laufzeit, um die Objekte zu beenden. Weitere Informationen finden Sie unter [using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md).  
  
 Im folgenden Beispiel wird der `finally`-Block verwendet, um eine Datei, die im `try`-Block geöffnet ist, zu schließen. Beachten Sie, dass der Status des Dateihandles überprüft wird, bevor die Datei geschlossen wird. Wenn der `try`-Block die Datei nicht öffnen kann, verfügt das Dateihandle immer noch über den Wert `null`, und der `finally`-Block versucht nicht, es zu schließen. Alternativ schließt der `finally`-Block die geöffnete Datei, wenn die Datei im `try`-Block erfolgreich geöffnet wird.  
  
 [!code-cs[csProgGuideExceptions#11](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exception-handling_6.cs)]  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [Ausnahmen und Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/index.md)   
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [Using-Anweisung](../../../csharp/language-reference/keywords/using-statement.md)

