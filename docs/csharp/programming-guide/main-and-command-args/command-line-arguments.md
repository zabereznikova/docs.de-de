---
title: Befehlszeilenargumente (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- command-line arguments [C#]
ms.assetid: 0e597e0d-ea7a-41ba-a38a-0198122f3c26
ms.openlocfilehash: 92b3f916b58f72ab2f2f542d3a611d35861afebe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="command-line-arguments-c-programming-guide"></a>Befehlszeilenargumente (C#-Programmierhandbuch)
Sie können Argumente an die `Main`- Methode senden, indem Sie die Methode auf eine der folgenden Arten definieren:  
  
 [!code-csharp[csProgGuideMain#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_1.cs)]  
  
 [!code-csharp[csProgGuideMain#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_2.cs)]  
  
> [!NOTE]
>  Um in der `Main`-Methode in einer Windows Forms-Anwendung Befehlszeilenargumente zu aktivieren, müssen Sie die Signatur von `Main` in „program.cs“ manuell ändern. Im vom Windows Forms-Designer generierten Code wird ein `Main` ohne einen Eingabeparameter erstellt. Sie können auch <xref:System.Environment.CommandLine%2A?displayProperty=nameWithType> oder <xref:System.Environment.GetCommandLineArgs%2A?displayProperty=nameWithType> verwenden, um von einem beliebigen Punkt in einer Konsolen- oder Windows-Anwendung auf die Befehlszeilenargumente zuzugreifen.  
  
 Der Parameter der `Main`-Methode ist ein <xref:System.String>-Array, das die Befehlszeilenargumente darstellt. Normalerweise bestimmen Sie, ob Argumente vorhanden sind, indem Sie z. B. die `Length`-Eigenschaft testen:  
  
 [!code-csharp[csProgGuideMain#4](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_3.cs)]  
  
 Sie können die Zeichenfolgenargumente auch mit der <xref:System.Convert>-Klasse oder der `Parse`-Methode in numerische Typen konvertieren. Die folgende Anweisung konvertiert z. B. `string` mithilfe der `long`-Methode in eine <xref:System.Int64.Parse%2A>-Zahl:  
  
```  
long num = Int64.Parse(args[0]);  
```  
  
 Sie können auch den C#-Typ `long` verwenden, der als Alias für `Int64` fungiert:  
  
```  
long num = long.Parse(args[0]);  
```  
  
 Sie können für dieselbe Aufgabe auch die `Convert`-Klassenmethode `ToInt64` verwenden:  
  
```  
long num = Convert.ToInt64(s);  
```  
  
 Weitere Informationen finden Sie unter <xref:System.Int64.Parse%2A> und <xref:System.Convert>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Befehlszeilenargumente in einer Konsolenanwendung verwendet werden. Die Anwendung übernimmt zur Laufzeit ein Argument, konvertiert das Argument in eine ganze Zahl und berechnet die Fakultät der Zahl. Wenn keine Argumente übergeben werden, erzeugt die Anwendung eine Meldung, in der die richtige Verwendung des Programms erläutert wird.  
  
 Führen Sie die folgenden Schritte aus, um die Anwendung von einer Eingabeaufforderung aus zu kompilieren und auszuführen:  
  
1.  Fügen Sie den folgenden Code in einem beliebigen Text-Editor ein, und speichern Sie die Datei als Textdatei mit dem Namen `Factorial.cs`.  
  
     [!code-csharp[csProgGuideMain#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/command-line-arguments_4.cs)]  
  
2.  Öffnen Sie über den Bildschirm **Starten** oder das Menü **Starten** eine Visual Studio **Developer-Eingabeaufforderung**, und navigieren Sie dann zu dem Ordner, der die Datei enthält, die Sie gerade erstellt haben.  
  
3.  Geben Sie den folgenden Befehl ein, um die Anwendung zu kompilieren.  
  
     `csc Factorial.cs`  
  
     Wenn die Anwendung keine Kompilierungsfehler aufweist, wird eine ausführbare Datei mit dem Namen `Factorial.exe` erstellt.  
  
4.  Geben Sie den folgenden Befehl ein, um die Fakultät von 3 zu berechnen:  
  
     `Factorial 3`  
  
5.  Durch den Befehl wird die folgende Ausgabe generiert: `The factorial of 3 is 6.`  
  
> [!NOTE]
>  Wenn Sie eine Anwendung in Visual Studio ausführen, können Sie Befehlszeilenargumente auf der [Seite „Debuggen“, Projekt-Designer](/visualstudio/ide/reference/debug-page-project-designer) angeben.  
  
 Weitere Beispiele zur Verwendung von Befehlszeilenargumenten finden Sie unter [Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Environment?displayProperty=nameWithType>  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Main() und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/index.md)  
 [Gewusst wie: Anzeigen von Befehlszeilenargumenten](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)  
 [Gewusst wie: Zugreifen auf Befehlszeilenargumente mithilfe von foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)  
 [Main()-Rückgabewerte](../../../csharp/programming-guide/main-and-command-args/main-return-values.md)  
 [Klassen](../../../csharp/programming-guide/classes-and-structs/classes.md)
