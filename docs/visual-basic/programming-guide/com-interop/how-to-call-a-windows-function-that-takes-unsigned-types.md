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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022362"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="e9f9a-102">Vorgehensweise: Rufen Sie eine Windows-Funktion, die vorzeichenlose Typen (Visual Basic) akzeptiert</span><span class="sxs-lookup"><span data-stu-id="e9f9a-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>

<span data-ttu-id="e9f9a-103">Wenn Sie eine Klasse, Modul oder der Struktur, die Mitglieder von Ganzzahltypen ohne Vorzeichen enthält verwenden, können Sie diese Mitglieder mit Visual Basic zugreifen.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with Visual Basic.</span></span>

### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="e9f9a-104">Eine Windows-Funktion aufrufen, die einen Typ ohne Vorzeichen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-104">To call a Windows function that takes an unsigned type</span></span>

1. <span data-ttu-id="e9f9a-105">Verwenden einer [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) Visual Basic zu informieren, welche Bibliothek die Funktion enthalten, was ihr Name in dieser Bibliothek ist, was die Aufrufsequenz ist und das Konvertieren von Zeichenfolgen bei deren Aufruf.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-105">Use a [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) to tell Visual Basic which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>

2. <span data-ttu-id="e9f9a-106">In der `Declare` -Anweisung sollten Sie `UInteger`, `ULong`, `UShort`, oder `Byte` entsprechend für jeden Parameter mit einen Typ ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>

3. <span data-ttu-id="e9f9a-107">Lesen Sie die Dokumentation für die Windows-Funktion, die Sie finden die Namen und Werte der Konstanten verwendeten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="e9f9a-108">Viele davon werden in der WinUser.h-Datei definiert.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-108">Many of these are defined in the WinUser.h file.</span></span>

4. <span data-ttu-id="e9f9a-109">Deklarieren Sie die erforderlichen Konstanten in Ihrem Code.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="e9f9a-110">Viele Windows-Konstanten sind 32-Bit-Werten ohne Vorzeichen, deklarieren Sie diese `As UInteger`.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As UInteger`.</span></span>

5. <span data-ttu-id="e9f9a-111">Aufrufen der Funktion auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-111">Call the function in the normal way.</span></span> <span data-ttu-id="e9f9a-112">Im folgenden Beispiel wird die Windows-Funktion `MessageBox`, der eine ganze Zahl ohne Vorzeichen-Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>

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

     <span data-ttu-id="e9f9a-113">Sie können die Funktion testen `messageThroughWindows` durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-113">You can test the function `messageThroughWindows` with the following code.</span></span>

    ```vb
    Public Sub consumeWindowsMessage()
        Dim w As New windowsMessage
        w.messageThroughWindows()
    End Sub
    ```

    > [!CAUTION]
    > <span data-ttu-id="e9f9a-114">Die `UInteger`, `ULong`, `UShort`, und `SByte` Datentypen sind nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), damit die CLS-kompatiblem Code kann keine Komponente verwenden, werden diese verwendet.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e9f9a-115">Anruf nicht verwaltetem Code, z. B. die Windows-Anwendungsprogrammierschnittstelle (API), macht Ihren Code auf potenzielle Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e9f9a-116">Die Windows-API aufruft, erfordert eine Berechtigung nicht verwalteten Code die Ausführung in teilweise vertrauenswürdigen Umgebungen auswirken.</span><span class="sxs-lookup"><span data-stu-id="e9f9a-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="e9f9a-117">Weitere Informationen finden Sie unter <xref:System.Security.Permissions.SecurityPermission> und [Codezugriffsberechtigungen](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e9f9a-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h846e9b3(v=vs.100)).</span></span>

## <a name="see-also"></a><span data-ttu-id="e9f9a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9f9a-118">See also</span></span>

- [<span data-ttu-id="e9f9a-119">Datentypen</span><span class="sxs-lookup"><span data-stu-id="e9f9a-119">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="e9f9a-120">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="e9f9a-120">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="e9f9a-121">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="e9f9a-121">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)
- [<span data-ttu-id="e9f9a-122">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e9f9a-122">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="e9f9a-123">Exemplarische Vorgehensweise: Aufrufen von Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="e9f9a-123">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
