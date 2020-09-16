---
title: 'Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert'
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
ms.openlocfilehash: 5b78c808de4a16060d37844ad0f17e89fa6f6d84
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548077"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a>Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert (Visual Basic)

Wenn Sie eine Klasse, ein Modul oder eine Struktur mit Membern von ganzzahligen Typen ohne Vorzeichen verwenden, können Sie mit Visual Basic auf diese Member zugreifen.

## <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a>So wird eine Windows-Funktion aufgerufen, die einen nicht signierten Typ annimmt

1. Verwenden Sie eine [Declare-Anweisung](../../language-reference/statements/declare-statement.md) , um zu ermitteln, Visual Basic welche Bibliothek die Funktion enthält, wie sich Ihr Name in dieser Bibliothek befindet, welche Aufruf Sequenz Sie enthält und wie Zeichen folgen beim Aufrufen konvertiert werden.

2. Verwenden Sie in der- `Declare` Anweisung `UInteger` , `ULong` , `UShort` oder `Byte` nach Bedarf für jeden Parameter mit einem unsignierten Typ.

3. In der Dokumentation für die Windows-Funktion, die Sie aufrufen, finden Sie die Namen und Werte der Konstanten, die Sie verwendet. Viele davon sind in der Datei "Winuser. h" definiert.

4. Deklarieren Sie die erforderlichen Konstanten in Ihrem Code. Viele Windows-Konstanten sind 32-Bit-Werte ohne Vorzeichen, und Sie sollten diese deklarieren `As UInteger` .

5. Die-Funktion wird auf die übliche Weise aufgerufen. Im folgenden Beispiel wird die Windows-Funktion aufgerufen `MessageBox` , die ein ganzzahliges Argument ohne Vorzeichen annimmt.

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

     Sie können die Funktion `messageThroughWindows` mit dem folgenden Code testen.

    ```vb
    Public Sub consumeWindowsMessage()
        Dim w As New windowsMessage
        w.messageThroughWindows()
    End Sub
    ```

    > [!CAUTION]
    > Die `UInteger` `ULong` `UShort` Datentypen,, und `SByte` sind nicht Teil der [Sprachunabhängigkeit und sprachunabhängigen Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS). Daher kann CLS-kompatibler Code keine Komponente verwenden, die Sie verwendet.

    > [!IMPORTANT]
    > Wenn Sie nicht verwalteten Code, wie z. b. die Windows-API (Application Programming Interface), anrufen, wird der Code für potenzielle Sicherheitsrisiken verfügbar gemacht.

    > [!IMPORTANT]
    > Der Aufruf der Windows-API erfordert die Berechtigung "nicht verwalteter Code", die sich in teilweise vertrauenswürdigen Situationen auf die Ausführung auswirken kann. Weitere Informationen finden Sie unter <xref:System.Security.Permissions.SecurityPermission> und [Code Zugriffsberechtigungen](/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).

## <a name="see-also"></a>Siehe auch

- [Datentypen](../../language-reference/data-types/index.md)
- [Integer-Datentyp](../../language-reference/data-types/integer-data-type.md)
- [UInteger-Datentyp](../../language-reference/data-types/uinteger-data-type.md)
- [Declare Statement](../../language-reference/statements/declare-statement.md)
- [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](walkthrough-calling-windows-apis.md)
