---
title: "Main Procedure in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Main"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Main procedure"
  - "Main method [Visual Basic]"
  - "main function"
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Main Procedure in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Jede Visual Basic\-Anwendung muss eine Prozedur mit der Bezeichnung `Main` enthalten.  Diese Prozedur fungiert als Ausgangspunkt und Gesamtsteuerung für die Anwendung.  Wenn .NET Framework die Anwendung geladen hat und die Steuerung an sie übergeben kann, wird die `Main`\-Prozedur aufgerufen.  Sofern Sie keine Windows Forms\-Anwendung erstellen, müssen Sie die `Main`\-Prozedur für Anwendungen schreiben, die eigenständig ausgeführt werden.  
  
 `Main` enthält den Code, der zuerst ausgeführt wird.  In `Main` können Sie festlegen, welches Formular beim Programmstart zuerst geladen wird, feststellen, ob eine Kopie der Anwendung bereits auf dem System ausgeführt wird, eine Reihe von Variablen für die Anwendung definieren oder eine Datenbank öffnen, die für die Anwendung erforderlich ist.  
  
## Anforderungen für die Main\-Prozedur  
 Eine Datei, die eigenständig ausgeführt wird \(normalerweise mit der Erweiterung .exe\), muss eine `Main`\-Prozedur enthalten.  Eine Bibliothek \(z. B. mit der Erweiterung .dll\) wird nicht eigenständig ausgeführt und erfordert keine `Main`\-Prozedur.  Für die unterschiedlichen Typen von Projekten, die Sie erstellen können, gelten folgende Anforderungen:  
  
-   Konsolenanwendungen werden eigenständig ausgeführt, und Sie müssen mindestens eine `Main`\-Prozedur angeben.  .  
  
-   Windows Forms\-Anwendungen werden eigenständig ausgeführt.  Jedoch generiert der Visual Basic\-Compiler automatisch eine `Main`\-Prozedur in einer solchen Anwendung, und Sie müssen sie nicht schreiben.  
  
-   Klassenbibliotheken erfordern keine `Main`\-Prozedur.  Zu diesen zählen Windows\-Steuerelementbibliotheken und Websteuerelementbibliotheken.  Webanwendungen werden als Klassenbibliotheken bereitgestellt.  
  
## Deklarieren der Main\-Prozedur  
 Es gibt vier Möglichkeiten, die `Main`\-Prozedur zu deklarieren.  Sie kann Argumente akzeptieren oder keine Argumente akzeptieren und einen Wert zurückgeben oder keinen Wert zurückgeben.  
  
> [!NOTE]
>  Wenn Sie `Main` in einer Klasse deklarieren, müssen Sie das `Shared`\-Schlüsselwort verwenden.  In einem Modul muss `Main` dagegen nicht `Shared` sein.  
  
-   Das einfachste Verfahren ist das Deklarieren einer `Sub`\-Prozedur, die keine Argumente akzeptiert und keinen Wert zurückgibt.  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   `Main` kann auch einen `Integer`\-Wert zurückgeben, der vom Betriebssystem als Exitcode für das Programm verwendet wird.  Andere Programme können diesen Code testen, indem Sie den Windows\-Wert ERRORLEVEL prüfen.  Um Exitcode zurückzugeben, müssen Sie `Main` als eine `Function`\-Prozedur und nicht als `Sub`\-Prozedur deklarieren.  
  
    ```  
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
  
-   `Main` kann auch ein `String`\-Array als Argument enthalten.  Jede Zeichenfolge im Array enthält eines der Befehlszeilenargumente, die zum Aufrufen des Programms verwendet werden.  In Abhängigkeit von den Werten können Sie unterschiedliche Aktionen vornehmen.  
  
    ```  
    Module mainModule  
        Function Main(ByVal cmdArgs() As String) As Integer  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
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
  
-   Sie können `Main` deklarieren, um Befehlszeilenargumente zu überprüfen, ohne Exitcode zurückzugeben \(siehe folgendes Beispiel\).  
  
    ```  
    Module mainModule  
        Sub Main(ByVal cmdArgs() As String)  
            MsgBox("The Main procedure is starting the application.")  
            Dim returnValue As Integer = 0  
            ' See if there are any arguments.  
            If cmdArgs.Length > 0 Then  
                For argNum As Integer = 0 To UBound(cmdArgs, 1)  
                    ' Insert code to examine cmdArgs(argNum) and take  
                    ' appropriate action based on its value.  
                Next argNum  
            End If  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>   
 <xref:System.Array.Length%2A>   
 <xref:Microsoft.VisualBasic.Information.UBound%2A>   
 [Structure of a Visual Basic Program](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)   
 [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/de-de/9d030b60-e148-4366-a462-69532f02294c)   
 [\/main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md)