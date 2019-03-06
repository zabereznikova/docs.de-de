---
title: 'Vorgehensweise: Rufen Sie eine Windows-Funktion, die vorzeichenlose Typen (Visual Basic) akzeptiert'
ms.date: 07/20/2015
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
ms.openlocfilehash: d1a679242f89c17e58a837ac2d356e1594972fb3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57374556"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Vorgehensweise: Rufen Sie eine Windows-Funktion, die vorzeichenlose Typen (Visual Basic) akzeptiert

Wenn Sie eine Klasse, Modul oder der Struktur, die Mitglieder von Ganzzahltypen ohne Vorzeichen enthält verwenden, können Sie diese Mitglieder mit Visual Basic zugreifen.

### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>Eine Windows-Funktion aufrufen, die einen Typ ohne Vorzeichen akzeptiert.

1. Verwenden einer [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) Visual Basic zu informieren, welche Bibliothek die Funktion enthalten, was ihr Name in dieser Bibliothek ist, was die Aufrufsequenz ist und das Konvertieren von Zeichenfolgen bei deren Aufruf.

2. In der `Declare` -Anweisung sollten Sie `UInteger`, `ULong`, `UShort`, oder `Byte` entsprechend für jeden Parameter mit einen Typ ohne Vorzeichen.

3. Lesen Sie die Dokumentation für die Windows-Funktion, die Sie finden die Namen und Werte der Konstanten verwendeten aufrufen. Viele davon werden in der WinUser.h-Datei definiert.

4. Deklarieren Sie die erforderlichen Konstanten in Ihrem Code. Viele Windows-Konstanten sind 32-Bit-Werten ohne Vorzeichen, deklarieren Sie diese `As UInteger`.

5. Aufrufen der Funktion auf die übliche Weise. Im folgenden Beispiel wird die Windows-Funktion `MessageBox`, der eine ganze Zahl ohne Vorzeichen-Argument akzeptiert.

    ```vb
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

    ```vb
    Public Sub consumeWindowsMessage()
        Dim w As New windowsMessage
        w.messageThroughWindows()
    End Sub
    ```

    > [!CAUTION]
    > Die `UInteger`, `ULong`, `UShort`, und `SByte` Datentypen sind nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), damit die CLS-kompatiblem Code kann keine Komponente verwenden, werden diese verwendet.

    > [!IMPORTANT]
    > Anruf nicht verwaltetem Code, z. B. die Windows-Anwendungsprogrammierschnittstelle (API), macht Ihren Code auf potenzielle Sicherheitsrisiken.

    > [!IMPORTANT]
    > Die Windows-API aufruft, erfordert eine Berechtigung nicht verwalteten Code die Ausführung in teilweise vertrauenswürdigen Umgebungen auswirken. Weitere Informationen finden Sie unter <xref:System.Security.Permissions.SecurityPermission> und [Codezugriffsberechtigungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).

## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)
- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
