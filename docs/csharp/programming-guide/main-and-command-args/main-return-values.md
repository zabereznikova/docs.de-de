---
title: "Main()-Rückgabewerte (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
caps.latest.revision: 20
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
ms.openlocfilehash: a24a0db126945d122db7a0c8d373d0c91e5da8a2
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="main-return-values-c-programming-guide"></a>Main()-Rückgabewerte (C#-Programmierhandbuch)
Die Methode `Main` kann `void` zurückgeben:  
  
 [!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]  
  
 Zudem kann `int` zurückgegeben werden:  
  
 [!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]  
  
 Wenn der Rückgabewert von `Main` nicht verwendet wird, ermöglicht die Rückgabe von `void` einen etwas einfacheren Code. Die Rückgabe einer Ganzzahl ermöglicht es dem Programm jedoch, Statusinformationen an andere Programme oder Skripts zu übermitteln, die die ausführbare Datei aufrufen. Im folgenden Beispiel wird gezeigt, wie auf den Rückgabewert von `Main` zugegriffen werden kann.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine Batchdatei verwendet, um ein Programm auszuführen und um den Rückgabewerte der `Main`-Funktion zu testen. Wenn ein Programm in Windows ausgeführt wird, wird jeder Wert, der von der Funktion `Main` zurückgegeben wurde, in einer Umgebungsvariable namens `ERRORLEVEL` gespeichert. Eine Batchdatei kann das Ergebnis der Ausführung bestimmen, indem sie die Variable `ERRORLEVEL` überprüft. Ein Rückgabewert von null gibt klassischerweise eine erfolgreiche Ausführung an. Das folgende Beispiel ist ein einfaches Programm, dass null von der Funktion `Main` zurückgibt. Die null gibt an, dass das Programm erfolgreich ausgeführt wurde. Speichern Sie das Programm als „MainReturnValTest.cs“.  
  
 [!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]  
  
## <a name="example"></a>Beispiel  
 Da in diesem Beispiel eine Batchdatei verwendet wird, ist es am besten, den Code in einer Eingabeaufforderung zu kompilieren. Folgen Sie den Anleitungen unter [Vorgehensweise: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md), um Befehlszeilenbuilds zu aktivieren, oder verwenden Sie die Eingabeaufforderung von Visual Studio, die über das **Start**menü unter **Visual Studio-Tools** verfügbar ist. Navigieren Sie von der Eingabeaufforderung in den Ordner, in dem Sie das Programm gespeichert haben. Der folgende Befehl kompiliert „MainReturnValTest.cs“ und erzeugt die ausführbare Datei „MainReturnValTest.exe“.  
  
 `csc MainReturnValTest.cs`  
  
 Als nächstes erstellen Sie eine Batchdatei, um MainReturnValTest.exe auszuführen und um das Ergebnis anzuzeigen. Fügen Sie den folgenden Code in eine Textdatei ein und speichern sie als `test.bat` in den Ordner, der „MainReturnValTest.cs“ und „MainReturnValTest.exe“ enthält. Führen Sie die Batchdatei aus, indem Sie in der Eingabeaufforderung `test` eingeben.  
  
 Da der Code null zurückgibt, wird die Batchdatei als erfolgreich gemeldet. Wenn Sie jedoch „MainReturnValTest.cs“ ändern, damit sie einen Wert ungleich null zurückgibt, und anschließend das Programm erneut kompilieren, wird eine nachfolgende Ausführung der Batchdatei einen Fehler melden.  
  
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
  
## <a name="sample-output"></a>Beispielausgabe  
 `Execution succeeded`  
  
 `Return value = 0`  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [C#-Referenz](../../../csharp/language-reference/index.md)   
 [Main() und Befehlszeilenargumente](../../../csharp/programming-guide/main-and-command-args/index.md)   
 [Vorgehensweise: Anzeigen von Befehlszeilenargumenten](../../../csharp/programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)   
 [Gewusst wie: Zugreifen auf Befehlszeilenargumente mithilfe von foreach](../../../csharp/programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)

