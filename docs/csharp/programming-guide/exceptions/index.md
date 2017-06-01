---
title: Ausnahmen und Ausnahmebehandlung (C#-Programmierhandbuch) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- exception handling [C#]
- exceptions [C#]
- C# language, exceptions
ms.assetid: 0001887f-4fa2-47e2-8034-2819477e2344
caps.latest.revision: 33
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 561113241f7433d8e0f7f1f1f96f0338ebe81ae3
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="exceptions-and-exception-handling-c-programming-guide"></a>Ausnahmen und Ausnahmebehandlung (C#-Programmierhandbuch)
Die C#-Funktionen zur Ausnahmebehandlung helfen Ihnen dabei, unerwartete oder außergewöhnliche Situationen zu verarbeiten, die beim Ausführen von Programmen auftreten können. Die Ausnahmebehandlung verwendet die Schlüsselwörter `try`, `catch` und `finally`, um Aktionen zu testen, die möglicherweise nicht erfolgreich sind, um Fehler zu behandeln, wenn Sie entscheiden, dass dies vernünftig ist, und um später Ressourcen zu bereinigen. Ausnahmen können von der Common Language Runtime (CLR), vom .NET Framework bzw. anderen Drittanbieterbibliotheken oder vom Anwendungscode generiert werden. Ausnahmen werden mit dem Schlüsselwort `throw` erstellt.  
  
 In vielen Fällen wird eine Ausnahme nicht von einer Methode ausgelöst, die von Ihrem Code direkt aufgerufen wurde, sondern von einer anderen Methode weiter unten in der Aufrufliste. In diesem Fall entlädt die CLR die Liste, sucht nach einer Methode mit einem `catch`-Block für den spezifischen Ausnahmetyp und führt den ersten gefundenen `catch`-Block aus. Wenn kein geeigneter `catch`-Block in der Aufrufliste gefunden wird, beendet die CLR den Prozess und zeigt eine Meldung für den Benutzer an.  
  
 In diesem Beispiel testet eine Methode, ob eine Division durch Null möglich ist, und fängt den Fehler ab. Ohne Ausnahmebehandlung würde dieses Programm mit dem Fehler **DivideByZeroException wurde nicht behandelt** beendet.  
  
 [!code-cs[csProgGuideExceptions#18](../../../csharp/programming-guide/exceptions/codesnippet/CSharp/exceptions-and-exception-handling_1.cs)]  
  
## <a name="exceptions-overview"></a>Übersicht über Ausnahmen  
 Ausnahmen weisen folgende Eigenschaften auf:  
  
-   Bei Ausnahmen handelt es sich um Typen, die alle letztlich von `System.Exception` abgeleitet werden.  
  
-   Verwenden Sie einen `try`-Block um die Anweisungen, die möglicherweise Ausnahmen auslösen.  
  
-   Sobald eine Ausnahme im `try`-Block auftritt, springt der Steuerungsfluss zum ersten zugeordneten Ausnahmehandler, der sich an einer beliebigen Stelle in der Aufrufliste befindet. In C# wird das Schlüsselwort `catch` zum Definieren eines Ausnahmehandlers verwendet.  
  
-   Wenn für eine bestimmte Ausnahme kein Ausnahmehandler vorhanden ist, beendet das Programm die Ausführung mit einer Fehlermeldung.  
  
-   Fangen Sie Ausnahmen nur dann ab, wenn Sie sie behandeln und die Anwendung in einem bekannten Zustand belassen können. Wenn Sie `System.Exception` abfangen, lösen Sie diese mithilfe des Schlüsselworts `throw` am Ende des `catch`-Blocks erneut aus.  
  
-   Wenn ein `catch`-Block eine Ausnahmevariable definiert, können Sie diese verwenden, um weitere Informationen zum Typ der aufgetretenen Ausnahme abzurufen.  
  
-   Ausnahmen können von einem Programm mithilfe des Schlüsselworts `throw` explizit generiert werden.  
  
-   Ausnahmeobjekte enthalten detaillierte Informationen über den Fehler, z.B. den Zustand der Aufrufliste und eine Textbeschreibung des Fehlers.  
  
-   Code in einem `finally`-Block wird auch dann ausgeführt, wenn eine Ausnahme ausgelöst wurde. Verwenden Sie einen `finally`-Block, um Ressourcen freizugeben, beispielsweise um Streams oder Dateien zu schließen, die im `try`-Block geöffnet wurden.  
  
-   Zusätzlich zum strukturierten Win32-Mechanismus zur Ausnahmebehandlung wurden im .NET Framework verwaltete Ausnahmen implementiert. Weitere Informationen finden Sie unter [Structured Exception Handling (C/C++)](https://docs.microsoft.com/cpp/cpp/structured-exception-handling-c-cpp) (Strukturierte Ausnahmebehandlung [C/C++]) und [A Crash Course on the Depths of Win32 Structured Exception Handling](http://go.microsoft.com/fwlink/?LinkId=119654) (Schnellkurs zu den Details der strukturierten Win32-Ausnahmebehandlung).  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen zu Ausnahmen und zur Ausnahmebehandlung finden Sie in den folgenden Themen:  
  
-   [Verwenden von Ausnahmen](../../../csharp/programming-guide/exceptions/using-exceptions.md)  
  
-   [Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exception-handling.md)  
  
-   [Erstellen und Auslösen von Ausnahmen](../../../csharp/programming-guide/exceptions/creating-and-throwing-exceptions.md)  
  
-   [Vom Compiler generierte Ausnahmen](../../../csharp/programming-guide/exceptions/compiler-generated-exceptions.md)  
  
-   [Gewusst wie: Behandeln einer Ausnahme mit try/catch (C#-Programmierhandbuch)](../../../csharp/programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md)  
  
-   [Gewusst wie: Ausführen von Bereinigungscode mit finally](../../../csharp/programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.SystemException>   
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [Ausnahmen](../../../standard/exceptions/index.md)   
 [Ausnahmenhierarchie](http://msdn.microsoft.com/library/f7d68675-be06-40fb-a555-05f0c5a6f66b)   
 [Schreiben von zuverlässigem .NET-Code](http://go.microsoft.com/fwlink/?LinkId=112400)   
 [Minidumps für bestimmte Ausnahmen](http://go.microsoft.com/fwlink/?LinkId=112408)
