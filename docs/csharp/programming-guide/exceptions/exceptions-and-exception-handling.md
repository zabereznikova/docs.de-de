---
redirect_url: /dotnet/articles/csharp/programming-guide/exceptions/
caps.handback.revision: 33
---
# Ausnahmen und Ausnahmebehandlung (C#-Programmierhandbuch)
Die Features zur Ausnahmebehandlung in C\# helfen Ihnen, wenn bei der Ausführung eines Programms unerwartete oder außergewöhnliche Situationen auftreten.  Bei der Ausnahmebehandlung wird mithilfe der Schlüsselwörter `try`, `catch` und `finally` versucht, Aktionen auszuführen, die möglicherweise fehlschlagen, um Fehler zu behandeln und anschließend die Ressourcen zu bereinigen.  Ausnahmen können von der Common Language Runtime \(CLR\), durch .NET Framework oder Bibliotheken von Drittanbietern oder durch den Anwendungscode generiert werden.  Ausnahmen werden mit dem `throw`\-Schlüsselwort erstellt.  
  
 In vielen Fällen wird eine Ausnahme nicht von einer Methode ausgelöst, die direkt durch den Code aufgerufen wurde, sondern von einer anderen Methode, die sich weiter unten in der Aufrufliste befindet.  In diesem Fall entlädt die CLR die Aufrufliste, sucht eine Methode mit einem `catch`\-Block für den spezifischen Ausnahmetyp und führt den ersten `catch`\-Block aus, der gefunden wird.  Falls kein entsprechender `catch`\-Block in der Aufrufliste gefunden wird, wird der Prozess beendet und eine Meldung für den Benutzer angezeigt.  
  
 In diesem Beispiel testet eine Methode auf eine Division durch 0 und fängt den Fehler ab.  Ohne diese Ausnahmebehandlung würde das Programm mit der Fehlermeldung **DivideByZeroException wurde nicht behandelt** beendet werden.  
  
 [!code-cs[csProgGuideExceptions#18](../../../csharp/programming-guide/exceptions/codesnippet/csharp/exceptions-and-exception_1.cs)]  
  
## Übersicht über Ausnahmen  
 Ausnahmen verfügen über folgende Eigenschaften:  
  
-   Ausnahmen sind Typen, die letztlich alle von `System.Exception` abgeleitet werden.  
  
-   Verwenden Sie einen `try`\-Block um Anweisungen, die möglicherweise Ausnahmen generieren.  
  
-   Sobald eine Ausnahme im `try`\-Block auftritt, springt die Ablaufsteuerung zum ersten vorhandenen und verknüpften Ausnahmehandler, sofern in der Aufrufliste vorhanden.  In C\# werden Ausnahmehandler mit dem `catch`\-Schlüsselwort definiert.  
  
-   Wenn für eine bestimmte Ausnahme kein Ausnahmehandler vorhanden ist, wird die Ausführung des Programms mit einer Fehlermeldung angehalten.  
  
-   Fangen Sie keine Ausnahme ab, es sei denn, Sie können sie bearbeiten, und belassen Sie die Anwendung in einem bekannten Zustand.  Wenn Sie `System.Exception` abfangen, lösen Sie es erneut mit dem `catch`\-Schlüsselwort am Ende des `throw`\-Blocks aus.  
  
-   Wenn ein `catch`\-Block eine Ausnahmevariable definiert, können Sie damit mehr Informationen über den Typ der Ausnahme erhalten.  
  
-   Ausnahmen können mithilfe des `throw`\-Schlüsselworts explizit von einem Programm generiert werden.  
  
-   Ausnahmeobjekte enthalten ausführliche Informationen zum Fehler, z. B. den Zustand der Aufrufliste und eine Textbeschreibung des Fehlers.  
  
-   Code in einem `finally`\-Block wird ausgeführt, auch wenn eine Ausnahme ausgelöst wird.  Verwenden Sie einen `finally`\-Block, um Ressourcen freizugeben, z. B. zum Schließen von im `try`\-Block geöffneten Streams oder Dateien.  
  
-   Verwaltete Ausnahmen in .NET Framework werden zusätzlich zum Win32\-Mechanismus für die strukturierte Ausnahmebehandlung implementiert.  Weitere Informationen finden Sie unter [Strukturierte Ausnahmebehandlung](/visual-cpp/cpp/structured-exception-handling-c-cpp) und [A Crash Course on the Depths of Win32 Structured Exception Handling](http://go.microsoft.com/fwlink/?LinkId=119654)  
  
## Verwandte Abschnitte  
 Weitere Informationen über Ausnahmen und Ausnahmebehandlung finden Sie in den folgenden Themen:  
  
-   [Verwenden von Ausnahmen](../../../csharp/programming-guide/exceptions/using-exceptions.md)  
  
-   [Ausnahmebehandlung](../../../csharp/programming-guide/exceptions/exception-handling.md)  
  
-   [Erstellen und Auslösen von Ausnahmen](../../../csharp/programming-guide/exceptions/creating-and-throwing-exceptions.md)  
  
-   [Vom Compiler generierte Ausnahmen](../../../csharp/programming-guide/exceptions/compiler-generated-exceptions.md)  
  
-   [Gewusst wie: Behandeln einer Ausnahme mit try\/catch](../../../csharp/programming-guide/exceptions/how-to-handle-an-exception-using-try-catch.md)  
  
-   [Gewusst wie: Ausführen von Bereinigungscode mit finally](../../../csharp/programming-guide/exceptions/how-to-execute-cleanup-code-using-finally.md)  
  
## C\#\-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## Siehe auch  
 <xref:System.SystemException>   
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)   
 [throw](../../../csharp/language-reference/keywords/throw.md)   
 [try\-catch](../../../csharp/language-reference/keywords/try-catch.md)   
 [try\-finally](../../../csharp/language-reference/keywords/try-finally.md)   
 [try\-catch\-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)   
 [Ausnahmen](../Topic/Handling%20and%20Throwing%20Exceptions.md)   
 [Ausnahmenhierarchie](../Topic/Exception%20Hierarchy.md)   
 [Schreiben .NET\-Codes zuverlässigen](http://go.microsoft.com/fwlink/?LinkId=112400)   
 [Minidump für bestimmte Ausnahmen](http://go.microsoft.com/fwlink/?LinkId=112408)