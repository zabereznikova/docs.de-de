---
title: 'Gewusst wie: Aufrufen eine Windows-Funktion, die vorzeichenlose Typen akzeptiert (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Windows functions, calling
- unsigned data types
- UShort data type, using
- functions [Visual Basic], calling Windows functions
- ULong data type, using
- UInteger data type, using
- data types [Visual Basic], using
- unsigned types
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types, using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
caps.latest.revision: 18
author: stevehoag
ms.author: shoag
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fbff07f4923b0633a2bc9b4fd558d9d51f64370a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert (Visual Basic)
Wenn Sie eine Klasse, Moduls oder der Struktur, die Mitglieder der Ganzzahltypen ohne Vorzeichen verwenden, können Sie diese Elemente mit zugreifen [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Eine Windows-Funktion aufrufen, die einen Typ ohne Vorzeichen akzeptiert.  
  
1.  Verwenden einer [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) anzuweisen, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] die Bibliothek die Funktion enthalten, welchen Namen Sie in dieser Bibliothek hat, wie ihre Aufruffolge lautet und wie Zeichenfolgen konvertiert, wenn der Aufruf.  
  
2.  In der `Declare` -Anweisung sollten Sie `UInteger`, `ULong`, `UShort`, oder `Byte` nach Bedarf für jeden Parameter mit einem Typ ohne Vorzeichen.  
  
3.  Lesen Sie die Dokumentation für die Windows-Funktion, die Sie aufrufen, um die Namen und Werte der Konstanten verwendet. Viele davon werden in der Datei WinUser.h definiert.  
  
4.  Deklarieren Sie die erforderlichen Konstanten im Code. Viele Windows-Konstanten sind 32-Bit-Werte ohne Vorzeichen, deklarieren Sie diese `As``UInteger`.  
  
5.  Rufen Sie die Funktion auf die übliche Weise. Im folgenden Beispiel wird die Windows-Funktion `MessageBox`, der ein Ganzzahlargument ohne Vorzeichen akzeptiert.  
  
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
    >  Die `UInteger`, `ULong`, `UShort`, und `SByte` Datentypen sind nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), d. h. CLS-kompatibler Code kann keine Komponente verwenden, die sie verwendet.  
  
    > [!IMPORTANT]
    >  Einen Anruf an nicht verwalteten Code, z. B. die Windows-Anwendungsprogrammierschnittstelle (API), macht den Code auf potenzielle Sicherheitsrisiken.  
  
    > [!IMPORTANT]
    >  Aufrufen der Windows-API erfordert eine Berechtigung nicht verwaltetem Code die Ausführung in teilweise vertrauenswürdigen Umgebungen beeinflussen kann. Weitere Informationen finden Sie unter <xref:System.Security.Permissions.SecurityPermission>und [Codezugriffsberechtigungen](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</xref:System.Security.Permissions.SecurityPermission>  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)   
 [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)   
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
