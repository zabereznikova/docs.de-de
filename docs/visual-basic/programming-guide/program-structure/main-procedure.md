---
title: Main-Prozedur
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: 61cd397b82b4bb9a8b24a1a7d30eaea68e37368f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347359"
---
# <a name="main-procedure-in-visual-basic"></a>Main-Prozedur in Visual Basic
Jede Visual Basic Anwendung muss eine Prozedur mit dem Namen `Main`enthalten. Diese Prozedur dient als Ausgangspunkt und allgemeine Kontrolle für Ihre Anwendung. Der .NET Framework ruft Ihre `Main` Prozedur auf, wenn Sie Ihre Anwendung geladen hat und an Sie übergeben werden kann. Wenn Sie keine Windows Forms Anwendung erstellen, müssen Sie die `Main` Prozedur für Anwendungen schreiben, die eigenständig ausgeführt werden.

 `Main` enthält den Code, der zuerst ausgeführt wird. In `Main`können Sie bestimmen, welches Formular zuerst geladen werden soll, wenn das Programm gestartet wird. Sie können herausfinden, ob bereits eine Kopie der Anwendung auf dem System ausgeführt wird, eine Gruppe von Variablen für die Anwendung erstellen oder eine Datenbank öffnen, die für die Anwendung erforderlich ist.

## <a name="requirements-for-the-main-procedure"></a>Anforderungen für die Main-Prozedur
 Eine Datei, die eigenständig (normalerweise mit der Erweiterung. exe) ausgeführt wird, muss eine `Main` Prozedur enthalten. Eine Bibliothek (z. b. mit der Erweiterung. dll) wird nicht eigenständig ausgeführt und erfordert keine `Main` Prozedur. Folgende Anforderungen gelten für die verschiedenen Projekttypen, die Sie erstellen können:

- Konsolen Anwendungen werden eigenständig ausgeführt, und Sie müssen mindestens eine `Main` Prozedur angeben.

- Windows Forms Anwendungen selbst ausgeführt werden. Der Visual Basic Compiler generiert jedoch automatisch eine `Main` Prozedur in einer solchen Anwendung, die Sie nicht schreiben müssen.

- Klassenbibliotheken erfordern keine `Main` Prozedur. Hierzu gehören Windows-Steuerelement Bibliotheken und websteuer Element Bibliotheken. Webanwendungen werden als Klassenbibliotheken bereitgestellt.

## <a name="declaring-the-main-procedure"></a>Deklarieren der Main-Prozedur
 Es gibt vier Möglichkeiten, die `Main` Prozedur zu deklarieren. Sie kann Argumente annehmen oder nicht, und Sie kann einen Wert zurückgeben.

> [!NOTE]
> Wenn Sie `Main` in einer Klasse deklarieren, müssen Sie das `Shared`-Schlüsselwort verwenden. In einem Modul muss `Main` nicht `Shared`werden.

- Die einfachste Möglichkeit besteht darin, eine `Sub` Prozedur zu deklarieren, die keine Argumente annimmt oder einen Wert zurückgibt.

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- `Main` kann auch einen `Integer` Wert zurückgeben, den das Betriebssystem als Exitcode für das Programm verwendet. Andere Programme können diesen Code testen, indem Sie den Windows ERRORLEVEL-Wert untersuchen. Um einen Exitcode zurückzugeben, müssen Sie `Main` als `Function` Prozedur anstelle einer `Sub` Prozedur deklarieren.

    ```vb
    Module mainModule
        Function Main() As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' Insert call to appropriate starting place in your code.
            ' On return, assign appropriate value to returnValue.
            ' 0 usually means successful completion.
            MsgBox("The application is terminating with error level " &
                 CStr(returnValue) & ".")
            Return returnValue
        End Function
    End Module
    ```

- `Main` können auch ein `String` Array als Argument annehmen. Jede Zeichenfolge im Array enthält eines der Befehlszeilenargumente, die zum Aufrufen des Programms verwendet werden. Sie können je nach ihren Werten unterschiedliche Aktionen ausführen.

    ```vb
    Module mainModule
        Function Main(ByVal cmdArgs() As String) As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            ' On return, assign appropriate value to returnValue.
            ' 0 usually means successful completion.
            MsgBox("The application is terminating with error level " &
                 CStr(returnValue) & ".")
            Return returnValue
        End Function
    End Module
    ```

- Sie können `Main` deklarieren, um die Befehlszeilenargumente zu untersuchen, aber nicht wie folgt einen Exitcode zurückgeben.

    ```vb
    Module mainModule
        Sub Main(ByVal cmdArgs() As String)
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [Struktur eines Visual Basic Programms](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [String-Datentyp](../../../visual-basic/language-reference/data-types/string-data-type.md)
