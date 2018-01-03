---
title: 'Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
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
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a3663ca5d3e0e2c94530d4a19ebff0022f495f3d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="844d0-102">Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="844d0-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>
<span data-ttu-id="844d0-103">Wenn Sie eine Klasse, Modul oder Struktur, die Mitglieder der Ganzzahltypen ohne Vorzeichen in Anspruch genommen, können Sie diese Elemente zugreifen [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span><span class="sxs-lookup"><span data-stu-id="844d0-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="844d0-104">Aufrufen eine Windows-Funktion, die einen Typ ohne Vorzeichen akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="844d0-104">To call a Windows function that takes an unsigned type</span></span>  
  
1.  <span data-ttu-id="844d0-105">Verwenden einer [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md) informieren [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] welche Bibliothek die Funktion enthält, was seinen Namen in diese Bibliothek ist, was die Aufrufsequenz ist und wie Zeichenfolgen konvertiert, wenn der Aufruf.</span><span class="sxs-lookup"><span data-stu-id="844d0-105">Use a [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) to tell [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>  
  
2.  <span data-ttu-id="844d0-106">In der `Declare` -Anweisung sollten Sie `UInteger`, `ULong`, `UShort`, oder `Byte` je nach Bedarf für jeden Parameter mit einem Datentyp ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="844d0-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>  
  
3.  <span data-ttu-id="844d0-107">Die Dokumentation für die Windows-Funktion, die Sie aufrufen, suchen Sie die Namen und Werten der Konstanten, die verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="844d0-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="844d0-108">Viele davon werden in der Datei WinUser.h definiert.</span><span class="sxs-lookup"><span data-stu-id="844d0-108">Many of these are defined in the WinUser.h file.</span></span>  
  
4.  <span data-ttu-id="844d0-109">Deklarieren Sie die erforderlichen Konstanten im Code.</span><span class="sxs-lookup"><span data-stu-id="844d0-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="844d0-110">Viele Windows-Konstanten sind 32-Bit-Werten ohne Vorzeichen, und deklarieren Sie diese `As``UInteger`.</span><span class="sxs-lookup"><span data-stu-id="844d0-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As``UInteger`.</span></span>  
  
5.  <span data-ttu-id="844d0-111">Rufen Sie die Funktion auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="844d0-111">Call the function in the normal way.</span></span> <span data-ttu-id="844d0-112">Im folgenden Beispiel wird die Windows-Funktion `MessageBox`, der eine ganze Zahl ohne Vorzeichen-Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="844d0-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>  
  
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
  
     <span data-ttu-id="844d0-113">Sie können die Funktion testen `messageThroughWindows` durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="844d0-113">You can test the function `messageThroughWindows` with the following code.</span></span>  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="844d0-114">Die `UInteger`, `ULong`, `UShort`, und `SByte` Datentypen sind nicht Teil der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../../../standard/language-independence-and-language-independent-components.md) (CLS), d. h. CLS-kompatiblem Code kann keine Komponente verwenden, werden diese verwendet.</span><span class="sxs-lookup"><span data-stu-id="844d0-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="844d0-115">Aufruf von nicht verwaltetem Code, z. B. die Windows-Anwendungsprogrammierschnittstelle (API), macht den Code auf potenzielle Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="844d0-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="844d0-116">Aufrufen der Windows-API erfordert die Berechtigung für nicht verwalteten Code, der die Ausführung in teilweise vertrauenswürdigen Umgebungen auswirken.</span><span class="sxs-lookup"><span data-stu-id="844d0-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="844d0-117">Weitere Informationen finden Sie unter <xref:System.Security.Permissions.SecurityPermission> und [Codezugriffsberechtigungen](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</span><span class="sxs-lookup"><span data-stu-id="844d0-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](http://msdn.microsoft.com/en-us/e5ae402f-6dda-4732-bbe8-77296630f675).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="844d0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="844d0-118">See Also</span></span>  
 [<span data-ttu-id="844d0-119">Datentypen</span><span class="sxs-lookup"><span data-stu-id="844d0-119">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="844d0-120">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="844d0-120">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="844d0-121">UInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="844d0-121">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
 [<span data-ttu-id="844d0-122">Declare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="844d0-122">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [<span data-ttu-id="844d0-123">Exemplarische Vorgehensweise: Aufrufen von Windows-APIs</span><span class="sxs-lookup"><span data-stu-id="844d0-123">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
