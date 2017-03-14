---
title: "How to: Call a Windows Function that Takes Unsigned Types (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Windows functions, calling"
  - "unsigned data types"
  - "UShort data type, using"
  - "functions [Visual Basic], calling Windows functions"
  - "ULong data type, using"
  - "UInteger data type, using"
  - "data types [Visual Basic], using"
  - "unsigned types"
  - "data types [Visual Basic], unsigned"
  - "data types [Visual Basic], numeric"
  - "unsigned types, using"
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Wenn Sie eine Klasse, ein Modul oder eine Struktur mit Membern aus Ganzzahltypen ohne Vorzeichen verwenden, können Sie mit [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] auf diese Member zugreifen.  
  
### So rufen Sie eine Windows\-Funktion auf, die einen Typ ohne Vorzeichen akzeptiert  
  
1.  Teilen Sie [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] mit einer [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) mit, in welcher Bibliothek die Funktion enthalten ist, welchen Namen sie in dieser Bibliothek hat, wie ihre Aufruffolge lautet und wie Zeichenfolgen bei deren Aufruf konvertiert werden.  
  
2.  Verwenden Sie in der `Declare`\-Anweisung nach Bedarf `UInteger`, `ULong`, `UShort` oder `Byte` für jeden Parameter mit einem Typ ohne Vorzeichen.  
  
3.  Ziehen Sie die Dokumentation für die aufzurufende Windows\-Funktion zu Rate, um die Namen und die Werte der von ihr verwendeten Konstanten zu bestimmen.  Viele davon sind in der Datei WinUser.h definiert.  
  
4.  Deklarieren Sie die erforderlichen Konstanten im Code.  Viele Windows\-Konstanten sind 32\-Bit\-Werte ohne Vorzeichen. Sie sollten diese als `As` `UInteger` deklarieren.  
  
5.  Rufen Sie die Funktion wie gewohnt auf.  Im folgenden Beispiel wird die Windows\-Funktion `MessageBox` aufgerufen, die ein Ganzzahlargument ohne Vorzeichen akzeptiert.  
  
    ```  
    Public Class windowsMessage  
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (  
            ByVal hWnd As Integer,   
            ByVal lpText As String,   
            ByVal lpCaption As String,   
            ByVal uType As UInteger) As Integer  
        Private Const MB_OK As UInteger = 0  
        Private Const MB_ICONEXCLAMATION As UInteger = &H30  
        Private Const IDOK As UInteger = 1  
        Private Const IDCLOSE As UInteger = 8  
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION  
        Public Function messageThroughWindows() As String  
            Dim r As Integer = mb(0, "Click OK if you see this!",   
                "Windows API call", c)  
            Dim s As String = "Windows API MessageBox returned " &  
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &  
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"  
            Return s  
        End Function  
    End Class  
    ```  
  
     Sie können die Funktion `messageThroughWindows` mit dem folgenden Code testen.  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  Die Datentypen `UInteger`, `ULong`, `UShort` und `SByte` sind nicht Teil der CLS \([Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\), sodass CLS\-kompatibler Code keine Komponente verwenden kann, die diese Datentypen nutzt.  
  
    > [!IMPORTANT]
    >  Bei einem Aufruf an nicht verwalteten Code, wie z. B. die Windows\-API, wird der Code potenziellen Sicherheitsrisiken ausgesetzt.  
  
    > [!IMPORTANT]
    >  Der Aufruf der Windows\-API erfordert eine Berechtigung für nicht verwalteten Code. Dies könnte sich auf ihre Ausführung in teilweise vertrauenswürdigen Kontexten auswirken.  Weitere Informationen finden Sie unter <xref:System.Security.Permissions.SecurityPermission> und unter [Code Access Permissions](http://msdn.microsoft.com/de-de/e5ae402f-6dda-4732-bbe8-77296630f675).  
  
## Siehe auch  
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)