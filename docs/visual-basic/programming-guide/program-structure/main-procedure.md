---
title: Main-Prozedur in Visual Basic
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: 109bf94eb91292cfca700a9e456c8ab53e83d68f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33652151"
---
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="6bfc2-102">Main-Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6bfc2-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="6bfc2-103">Alle Visual Basic-Anwendung muss eine Prozedur namens enthalten `Main`.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="6bfc2-104">Diese Prozedur dient, wie die Start- und gesamtsteuerung für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="6bfc2-105">Die .NET Framework Aufrufe der `Main` -Prozedur, wenn die Anwendung geladen hat und bereit für die Steuerung an sie übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="6bfc2-106">Wenn Sie eine Windows Forms-Anwendung erstellen, müssen Sie schreiben die `Main` Verfahren für Anwendungen, die auf ihre eigenen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>  
  
 <span data-ttu-id="6bfc2-107">`Main` enthält den Code, der zuerst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="6bfc2-108">In `Main`, Sie bestimmen, welche Form zuerst geladen werden, wenn das Programm gestartet wird, festzustellen, ob eine Kopie der Anwendung bereits auf dem System ausgeführt wird, richten Sie einen Satz von Variablen für die Anwendung oder öffnen Sie eine Datenbank, die die Anwendung erfordert.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>  
  
## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="6bfc2-109">Anforderungen für die Main-Prozedur</span><span class="sxs-lookup"><span data-stu-id="6bfc2-109">Requirements for the Main Procedure</span></span>  
 <span data-ttu-id="6bfc2-110">Eine Datei, die einen eigenen (normalerweise mit der Erweiterung .exe) wird ausgeführt auf darf eine `Main` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="6bfc2-111">Eine Bibliothek (z. B. mit der Erweiterung .dll) wird nicht eigenständig ausgeführt und erfordert keine `Main` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="6bfc2-112">Die Anforderungen für die verschiedenen Typen von Projekten, die Sie erstellen können, lauten folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="6bfc2-112">The requirements for the different types of projects you can create are as follows:</span></span>  
  
-   <span data-ttu-id="6bfc2-113">Konsolenanwendungen führen Sie auf ihre eigenen, und geben Sie an mindestens eine `Main` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span> <span data-ttu-id="6bfc2-114">sein.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-114">.</span></span>  
  
-   <span data-ttu-id="6bfc2-115">Führen Sie auf ihren eigenen Windows Forms-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-115">Windows Forms applications run on their own.</span></span> <span data-ttu-id="6bfc2-116">Visual Basic-Compiler automatisch generiert jedoch eine `Main` Prozedur z. B. eine Anwendung, und Sie müssen nicht schreiben.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-116">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>  
  
-   <span data-ttu-id="6bfc2-117">Klassenbibliotheken erfordern keine `Main` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-117">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="6bfc2-118">Dazu gehören Windows-Steuerelement-Bibliotheken und Websteuerelementbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-118">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="6bfc2-119">Webanwendungen werden als Klassenbibliotheken bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-119">Web applications are deployed as class libraries.</span></span>  
  
## <a name="declaring-the-main-procedure"></a><span data-ttu-id="6bfc2-120">Deklarieren Sie die Main-Prozedur</span><span class="sxs-lookup"><span data-stu-id="6bfc2-120">Declaring the Main Procedure</span></span>  
 <span data-ttu-id="6bfc2-121">Es gibt vier Möglichkeiten zum Deklarieren der `Main` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-121">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="6bfc2-122">Es kann Argumente annehmen, oder nicht, und sie können einen Wert zurückgeben, oder nicht.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-122">It can take arguments or not, and it can return a value or not.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6bfc2-123">Wenn Sie deklarieren `Main` in einer Klasse, verwenden Sie die `Shared` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-123">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="6bfc2-124">In einem Modul `Main` muss nicht werden `Shared`.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-124">In a module, `Main` does not need to be `Shared`.</span></span>  
  
-   <span data-ttu-id="6bfc2-125">Die einfachste Möglichkeit ist das Deklarieren einer `Sub` Prozedur, die keine Argumente übernehmen oder einen Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-125">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>  
  
    ```  
    Module mainModule  
        Sub Main()  
            MsgBox("The Main procedure is starting the application.")  
            ' Insert call to appropriate starting place in your code.  
            MsgBox("The application is terminating.")  
        End Sub  
    End Module  
    ```  
  
-   <span data-ttu-id="6bfc2-126">`Main` kann auch Zurückgeben einer `Integer` -Wert, der das Betriebssystem als Exitcode für das Programm verwendet.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-126">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="6bfc2-127">Andere Programme können diesen Code mithilfe den Windows-ERRORLEVEL-Wert zu testen.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-127">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="6bfc2-128">Um einen Exitcode zurückzugeben, müssen Sie deklarieren `Main` als eine `Function` Prozedur anstelle von einer `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-128">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>  
  
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
  
-   <span data-ttu-id="6bfc2-129">`Main` akzeptieren können auch eine `String` Array als Argument.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-129">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="6bfc2-130">Jede Zeichenfolge im Array enthält einen der Befehlszeilenargumente verwendet, um das Programm aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-130">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="6bfc2-131">Sie können unterschiedliche Aktionen abhängig von deren Werten ausführen.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-131">You can take different actions depending on their values.</span></span>  
  
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
  
-   <span data-ttu-id="6bfc2-132">Sie können deklarieren, `Main` , überprüfen Sie die Befehlszeilenargumente, jedoch wie folgt einen Exitcode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6bfc2-132">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6bfc2-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6bfc2-133">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
 <xref:System.Array.Length%2A>  
 <xref:Microsoft.VisualBasic.Information.UBound%2A>  
 [<span data-ttu-id="6bfc2-134">Struktur eines Visual Basic-Programms</span><span class="sxs-lookup"><span data-stu-id="6bfc2-134">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="6bfc2-135">/main</span><span class="sxs-lookup"><span data-stu-id="6bfc2-135">/main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)  
 [<span data-ttu-id="6bfc2-136">Shared</span><span class="sxs-lookup"><span data-stu-id="6bfc2-136">Shared</span></span>](../../../visual-basic/language-reference/modifiers/shared.md)  
 [<span data-ttu-id="6bfc2-137">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6bfc2-137">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [<span data-ttu-id="6bfc2-138">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6bfc2-138">Function Statement</span></span>](../../../visual-basic/language-reference/statements/function-statement.md)  
 [<span data-ttu-id="6bfc2-139">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="6bfc2-139">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)  
 [<span data-ttu-id="6bfc2-140">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="6bfc2-140">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)
