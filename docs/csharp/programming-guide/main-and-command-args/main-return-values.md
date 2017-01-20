---
title: "Main()-R&#252;ckgabewerte (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Main-Methode [C#], Rückgabewerte"
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
caps.latest.revision: 20
caps.handback.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Main()-R&#252;ckgabewerte (C#-Programmierhandbuch)
Die `Main`\-Methode kann `void` zurückgeben.  
  
 [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]  
  
 Sie kann außerdem `int` zurückgeben:  
  
 [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]  
  
 Wenn der Rückgabewert von `Main` nicht verwendet wird, kann der Code durch das Zurückgeben von `void` geringfügig vereinfacht werden.  Das Zurückgeben einer ganzen Zahl ermöglicht es dem Programm jedoch, Statusinformationen an andere Programme oder Skripts weiterzugeben, von denen die ausführbare Datei aufgerufen wird.  Im folgenden Beispiel wird gezeigt, wie auf den Rückgabewert von `Main` zugegriffen werden kann.  
  
## Beispiel  
 In diesem Beispiel wird eine Batchdatei verwendet, um ein Programm auszuführen und den Rückgabewert der `Main`\-Funktion zu testen.  Beim Ausführen eines Programms unter Windows wird ein evtl. von der `Main`\-Funktion zurückgegebener Wert in einer Umgebungsvariablen mit dem Namen `ERRORLEVEL` gespeichert.  Batchdateien können das Ergebnis der Ausführung bestimmen, indem sie die `ERRORLEVEL`\-Variable überprüfen.  In der Regel signalisiert ein Rückgabewert von 0 \(null\) die erfolgreiche Ausführung.  Im folgenden Beispiel wird mit einem einfachen Programm der Wert \(null\) von der `Main`\-Funktion zurückgegeben.  Der Wert 0 \(null\) gibt an, dass das Programm erfolgreich ausgeführt wurde.  Speichern Sie das Programm unter den Namen MainReturnValTest.cs.  
  
 [!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]  
  
## Beispiel  
 Da in diesem Beispiel eine Batchdatei verwendet wird, empfiehlt es sich, den Code von einer Eingabeaufforderung aus zu kompilieren.  Folgen Sie den Anweisungen in [How to: Set Environment Variables for the Visual Studio Command Line](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md), um Befehlszeilenbuilds zu aktivieren, oder verwenden Sie die Visual Studio\-Eingabeaufforderung im Menü **Start** unter **Visual Studio Tools**.  Navigieren Sie von der Eingabeaufforderung zum Ordner, in dem Sie das Programm gespeichert haben.  Mit dem folgenden Befehl wird MainReturnValTest.cs kompiliert und die ausführbaren Datei MainReturnValTest.exe erzeugt.  
  
 `csc MainReturnValTest.cs`  
  
 Erstellen Sie anschließend eine Batchdatei, um MainReturnValTest.exe auszuführen und das Ergebnis anzuzeigen.  Fügen Sie den folgenden Code in eine Textdatei ein, und speichern Sie diese als `test.bat` in dem Ordner, der die Dateien MainReturnValTest.cs und MainReturnValTest.exe enthält.  Führen Sie die Batchdatei aus, indem Sie `test` an der Eingabeaufforderung eingeben.  
  
 Da 0 \(null\) vom Code zurückgegeben wird, gibt die Batchdatei eine Erfolgsmeldung aus.  Wenn Sie jedoch MainReturnValTest.cs ändern, um einen Wert ungleich 0 \(null\) zurückzugeben, und dann das Programm erneut kompilieren, wird bei der folgenden Ausführung der Batchdatei ein Fehler gemeldet.  
  
```  
rem test.bat  
@echo off  
MainReturnValTest  
@if "%ERRORLEVEL%" == "0" goto good  
  
:fail  
    echo Execution Failed  
    echo return value = %ERRORLEVEL%  
    goto end  
  
:good  
    echo Execution succeeded  
    echo Return value = %ERRORLEVEL%  
    goto end  
  
:end  
```  
  
## Beispielausgabe  
 `Execution succeeded`  
  
 `Return value = 0`  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C\#\-Referenz](../../../csharp/language-reference/index.md)   
 [Main\(\) und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/main-and-command-line-arguments.md)   
 [Gewusst wie: Anzeigen von Befehlszeilenargumenten](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Gewusst wie: Zugreifen auf Befehlszeilenargumente mithilfe von foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)