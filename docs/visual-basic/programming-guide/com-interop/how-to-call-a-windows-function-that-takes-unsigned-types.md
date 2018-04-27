---
title: 'Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: dd0738300ec846041e78f19836f29e7adff1c821
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert (Visual Basic)
Wenn Sie eine Klasse, Modul oder Struktur, die Mitglieder der Ganzzahltypen ohne Vorzeichen in Anspruch genommen, können Sie diese Elemente mit Visual Basic zugreifen.  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Aufrufen eine Windows-Funktion, die einen Typ ohne Vorzeichen akzeptiert.  
  
1.  Verwenden einer [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) Visual Basic mitteilen, welche Bibliothek die Funktion enthält, was seinen Namen in diese Bibliothek ist, was die Aufrufsequenz ist und wie Zeichenfolgen konvertiert, wenn der Aufruf ist.  
  
2.  In der `Declare` -Anweisung sollten Sie `UInteger`, `ULong`, `UShort`, oder `Byte` je nach Bedarf für jeden Parameter mit einem Datentyp ohne Vorzeichen.  
  
3.  Die Dokumentation für die Windows-Funktion, die Sie aufrufen, suchen Sie die Namen und Werten der Konstanten, die verwendet wird. Viele davon werden in der Datei WinUser.h definiert.  
  
4.  Deklarieren Sie die erforderlichen Konstanten im Code. Viele Windows-Konstanten sind 32-Bit-Werten ohne Vorzeichen, und deklarieren Sie diese `As``UInteger`.  
  
5.  Rufen Sie die Funktion auf die übliche Weise. Im folgenden Beispiel wird die Windows-Funktion `MessageBox`, der eine ganze Zahl ohne Vorzeichen-Argument akzeptiert.  
  
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
  
     Sie können die Funktion testen `messageThroughWindows` durch den folgenden Code.  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  Die `UInteger`, `ULong`, `UShort`, und `SByte` Datentypen sind nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), d. h. CLS-kompatiblem Code kann keine Komponente verwenden, werden diese verwendet.  
  
    > [!IMPORTANT]
    >  Aufruf von nicht verwaltetem Code, z. B. die Windows-Anwendungsprogrammierschnittstelle (API), macht den Code auf potenzielle Sicherheitsrisiken.  
  
    > [!IMPORTANT]
    >  Aufrufen der Windows-API erfordert die Berechtigung für nicht verwalteten Code, der die Ausführung in teilweise vertrauenswürdigen Umgebungen auswirken. Weitere Informationen finden Sie unter <xref:System.Security.Permissions.SecurityPermission> und [Codezugriffsberechtigungen](http://msdn.microsoft.com/library/e5ae402f-6dda-4732-bbe8-77296630f675).  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
