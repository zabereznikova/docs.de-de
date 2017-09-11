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
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7b6b1d46b6ccab0ec8d63fb8b7d8722b518b81b4
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="ce2f9-102">Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ce2f9-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>
<span data-ttu-id="ce2f9-103">Wenn Sie eine Klasse, Moduls oder der Struktur, die Mitglieder der Ganzzahltypen ohne Vorzeichen verwenden, können Sie diese Elemente mit zugreifen [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span><span class="sxs-lookup"><span data-stu-id="ce2f9-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="ce2f9-104">Eine Windows-Funktion aufrufen, die einen Typ ohne Vorzeichen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-104">To call a Windows function that takes an unsigned type</span></span>  
  
1.  <span data-ttu-id="ce2f9-105">Verwenden einer [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) anzuweisen, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] die Bibliothek die Funktion enthalten, welchen Namen Sie in dieser Bibliothek hat, wie ihre Aufruffolge lautet und wie Zeichenfolgen konvertiert, wenn der Aufruf.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-105">Use a [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) to tell [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>  
  
2.  <span data-ttu-id="ce2f9-106">In der `Declare` -Anweisung sollten Sie `UInteger`, `ULong`, `UShort`, oder `Byte` nach Bedarf für jeden Parameter mit einem Typ ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>  
  
3.  <span data-ttu-id="ce2f9-107">Lesen Sie die Dokumentation für die Windows-Funktion, die Sie aufrufen, um die Namen und Werte der Konstanten verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="ce2f9-108">Viele davon werden in der Datei WinUser.h definiert.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-108">Many of these are defined in the WinUser.h file.</span></span>  
  
4.  <span data-ttu-id="ce2f9-109">Deklarieren Sie die erforderlichen Konstanten im Code.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="ce2f9-110">Viele Windows-Konstanten sind 32-Bit-Werte ohne Vorzeichen, deklarieren Sie diese `As``UInteger`.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As``UInteger`.</span></span>  
  
5.  <span data-ttu-id="ce2f9-111">Rufen Sie die Funktion auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-111">Call the function in the normal way.</span></span> <span data-ttu-id="ce2f9-112">Im folgenden Beispiel wird die Windows-Funktion `MessageBox`, der ein Ganzzahlargument ohne Vorzeichen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>  
  
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
  
     <span data-ttu-id="ce2f9-113">Sie können die Funktion testen `messageThroughWindows` durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-113">You can test the function `messageThroughWindows` with the following code.</span></span>  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="ce2f9-114">Die `UInteger`, `ULong`, `UShort`, und `SByte` Datentypen sind nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](https://msdn.microsoft.com/library/12a7a7h3) (CLS), d. h. CLS-kompatibler Code kann keine Komponente verwenden, die sie verwendet.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](https://msdn.microsoft.com/library/12a7a7h3) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ce2f9-115">Einen Anruf an nicht verwalteten Code, z. B. die Windows-Anwendungsprogrammierschnittstelle (API), macht den Code auf potenzielle Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="ce2f9-116">Aufrufen der Windows-API erfordert eine Berechtigung nicht verwaltetem Code die Ausführung in teilweise vertrauenswürdigen Umgebungen beeinflussen kann.</span><span class="sxs-lookup"><span data-stu-id="ce2f9-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="ce2f9-117">Weitere Informationen finden Sie unter <xref:System.Security.Permissions.SecurityPermission>und [Codezugriffsberechtigungen](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</xref:System.Security.Permissions.SecurityPermission></span><span class="sxs-lookup"><span data-stu-id="ce2f9-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce2f9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce2f9-118">See Also</span></span>  
 <span data-ttu-id="ce2f9-119">[Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="ce2f9-119">[Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="ce2f9-120"> [Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="ce2f9-120"> [Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md) </span></span>  
<span data-ttu-id="ce2f9-121"> [UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="ce2f9-121"> [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) </span></span>  
<span data-ttu-id="ce2f9-122"> [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ce2f9-122"> [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) </span></span>  
<span data-ttu-id="ce2f9-123"> [Exemplarische Vorgehensweise: Aufrufen von Windows-APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)</span><span class="sxs-lookup"><span data-stu-id="ce2f9-123"> [Walkthrough: Calling Windows APIs](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)</span></span>
