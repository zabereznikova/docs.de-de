---
title: Main-Prozedur
ms.date: 07/20/2015
f1_keywords:
- vb.Main
helpviewer_keywords:
- Main procedure
- Main method [Visual Basic]
- main function
ms.assetid: f0db283e-f283-4464-b521-b90858cc1b44
ms.openlocfilehash: cf6003206566dfe8f70a7f75cd4d7ec7565794a5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403173"
---
# <a name="main-procedure-in-visual-basic"></a><span data-ttu-id="b49a5-102">Main-Prozedur in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b49a5-102">Main Procedure in Visual Basic</span></span>
<span data-ttu-id="b49a5-103">Jede Visual Basic Anwendung muss eine Prozedur mit dem Namen enthalten `Main` .</span><span class="sxs-lookup"><span data-stu-id="b49a5-103">Every Visual Basic application must contain a procedure called `Main`.</span></span> <span data-ttu-id="b49a5-104">Diese Prozedur dient als Ausgangspunkt und allgemeine Kontrolle für Ihre Anwendung.</span><span class="sxs-lookup"><span data-stu-id="b49a5-104">This procedure serves as the starting point and overall control for your application.</span></span> <span data-ttu-id="b49a5-105">Der .NET Framework ruft die `Main` Prozedur auf, wenn Sie Ihre Anwendung geladen hat, und ist bereit, die Steuerung an Sie zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="b49a5-105">The .NET Framework calls your `Main` procedure when it has loaded your application and is ready to pass control to it.</span></span> <span data-ttu-id="b49a5-106">Wenn Sie keine Windows Forms Anwendung erstellen, müssen Sie das `Main` Verfahren für Anwendungen schreiben, die eigenständig ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b49a5-106">Unless you are creating a Windows Forms application, you must write the `Main` procedure for applications that run on their own.</span></span>

 <span data-ttu-id="b49a5-107">`Main`enthält den Code, der zuerst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b49a5-107">`Main` contains the code that runs first.</span></span> <span data-ttu-id="b49a5-108">In `Main` können Sie bestimmen, welches Formular zuerst geladen werden soll, wenn das Programm gestartet wird. Sie können herausfinden, ob bereits eine Kopie der Anwendung auf dem System ausgeführt wird, eine Gruppe von Variablen für die Anwendung einrichten oder eine Datenbank öffnen, die für die Anwendung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b49a5-108">In `Main`, you can determine which form is to be loaded first when the program starts, find out if a copy of your application is already running on the system, establish a set of variables for your application, or open a database that the application requires.</span></span>

## <a name="requirements-for-the-main-procedure"></a><span data-ttu-id="b49a5-109">Anforderungen für die Main-Prozedur</span><span class="sxs-lookup"><span data-stu-id="b49a5-109">Requirements for the Main Procedure</span></span>
 <span data-ttu-id="b49a5-110">Eine Datei, die eigenständig (normalerweise mit der Erweiterung. exe) ausgeführt wird, muss eine `Main` Prozedur enthalten.</span><span class="sxs-lookup"><span data-stu-id="b49a5-110">A file that runs on its own (usually with extension .exe) must contain a `Main` procedure.</span></span> <span data-ttu-id="b49a5-111">Eine Bibliothek (z. b. mit der Erweiterung. dll) wird nicht eigenständig ausgeführt und erfordert keine `Main` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="b49a5-111">A library (for example with extension .dll) does not run on its own and does not require a `Main` procedure.</span></span> <span data-ttu-id="b49a5-112">Folgende Anforderungen gelten für die verschiedenen Projekttypen, die Sie erstellen können:</span><span class="sxs-lookup"><span data-stu-id="b49a5-112">The requirements for the different types of projects you can create are as follows:</span></span>

- <span data-ttu-id="b49a5-113">Konsolen Anwendungen werden nacheinander ausgeführt, und Sie müssen mindestens ein `Main` Verfahren angeben.</span><span class="sxs-lookup"><span data-stu-id="b49a5-113">Console applications run on their own, and you must supply at least one `Main` procedure.</span></span>

- <span data-ttu-id="b49a5-114">Windows Forms Anwendungen selbst ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b49a5-114">Windows Forms applications run on their own.</span></span> <span data-ttu-id="b49a5-115">Der Visual Basic Compiler generiert jedoch automatisch eine `Main` Prozedur in einer solchen Anwendung, die Sie nicht schreiben müssen.</span><span class="sxs-lookup"><span data-stu-id="b49a5-115">However, the Visual Basic compiler automatically generates a `Main` procedure in such an application, and you do not need to write one.</span></span>

- <span data-ttu-id="b49a5-116">Klassenbibliotheken erfordern keine- `Main` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="b49a5-116">Class libraries do not require a `Main` procedure.</span></span> <span data-ttu-id="b49a5-117">Hierzu gehören Windows-Steuerelement Bibliotheken und websteuer Element Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="b49a5-117">These include Windows Control Libraries and Web Control Libraries.</span></span> <span data-ttu-id="b49a5-118">Webanwendungen werden als Klassenbibliotheken bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b49a5-118">Web applications are deployed as class libraries.</span></span>

## <a name="declaring-the-main-procedure"></a><span data-ttu-id="b49a5-119">Deklarieren der Main-Prozedur</span><span class="sxs-lookup"><span data-stu-id="b49a5-119">Declaring the Main Procedure</span></span>
 <span data-ttu-id="b49a5-120">Es gibt vier Möglichkeiten, die Prozedur zu deklarieren `Main` .</span><span class="sxs-lookup"><span data-stu-id="b49a5-120">There are four ways to declare the `Main` procedure.</span></span> <span data-ttu-id="b49a5-121">Sie kann Argumente annehmen oder nicht, und Sie kann einen Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b49a5-121">It can take arguments or not, and it can return a value or not.</span></span>

> [!NOTE]
> <span data-ttu-id="b49a5-122">Wenn Sie `Main` in einer Klasse deklarieren, müssen Sie das- `Shared` Schlüsselwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="b49a5-122">If you declare `Main` in a class, you must use the `Shared` keyword.</span></span> <span data-ttu-id="b49a5-123">In einem Modul `Main` muss nicht sein `Shared` .</span><span class="sxs-lookup"><span data-stu-id="b49a5-123">In a module, `Main` does not need to be `Shared`.</span></span>

- <span data-ttu-id="b49a5-124">Die einfachste Möglichkeit besteht darin, eine Prozedur zu deklarieren `Sub` , die keine Argumente annimmt oder einen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="b49a5-124">The simplest way is to declare a `Sub` procedure that does not take arguments or return a value.</span></span>

    ```vb
    Module mainModule
        Sub Main()
            MsgBox("The Main procedure is starting the application.")
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```

- <span data-ttu-id="b49a5-125">`Main`kann auch einen- `Integer` Wert zurückgeben, den das Betriebssystem als Exitcode für das Programm verwendet.</span><span class="sxs-lookup"><span data-stu-id="b49a5-125">`Main` can also return an `Integer` value, which the operating system uses as the exit code for your program.</span></span> <span data-ttu-id="b49a5-126">Andere Programme können diesen Code testen, indem Sie den Windows ERRORLEVEL-Wert untersuchen.</span><span class="sxs-lookup"><span data-stu-id="b49a5-126">Other programs can test this code by examining the Windows ERRORLEVEL value.</span></span> <span data-ttu-id="b49a5-127">Um einen Exitcode zurückzugeben, müssen Sie `Main` `Function` anstelle einer Prozedur als Prozedur deklarieren `Sub` .</span><span class="sxs-lookup"><span data-stu-id="b49a5-127">To return an exit code, you must declare `Main` as a `Function` procedure instead of a `Sub` procedure.</span></span>

    ```vb
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

- <span data-ttu-id="b49a5-128">`Main`kann auch ein `String` Array als Argument annehmen.</span><span class="sxs-lookup"><span data-stu-id="b49a5-128">`Main` can also take a `String` array as an argument.</span></span> <span data-ttu-id="b49a5-129">Jede Zeichenfolge im Array enthält eines der Befehlszeilenargumente, die zum Aufrufen des Programms verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b49a5-129">Each string in the array contains one of the command-line arguments used to invoke your program.</span></span> <span data-ttu-id="b49a5-130">Sie können je nach ihren Werten unterschiedliche Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="b49a5-130">You can take different actions depending on their values.</span></span>

    ```vb
    Module mainModule
        Function Main(ByVal cmdArgs() As String) As Integer
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
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

- <span data-ttu-id="b49a5-131">Sie können deklarieren, `Main` um die Befehlszeilenargumente zu untersuchen, aber nicht wie folgt einen Exitcode zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="b49a5-131">You can declare `Main` to examine the command-line arguments but not return an exit code, as follows.</span></span>

    ```vb
    Module mainModule
        Sub Main(ByVal cmdArgs() As String)
            MsgBox("The Main procedure is starting the application.")
            Dim returnValue As Integer = 0
            ' See if there are any arguments.
            If cmdArgs.Length > 0 Then
                For argNum As Integer = 0 To UBound(cmdArgs, 1)
                    ' Insert code to examine cmdArgs(argNum) and take
                    ' appropriate action based on its value.
                Next
            End If
            ' Insert call to appropriate starting place in your code.
            MsgBox("The application is terminating.")
        End Sub
    End Module
    ```
  
## <a name="see-also"></a><span data-ttu-id="b49a5-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b49a5-132">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>
- <xref:System.Array.Length%2A>
- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="b49a5-133">Struktur von Visual Basic-Programmen</span><span class="sxs-lookup"><span data-stu-id="b49a5-133">Structure of a Visual Basic Program</span></span>](structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="b49a5-134">-main</span><span class="sxs-lookup"><span data-stu-id="b49a5-134">-main</span></span>](../../reference/command-line-compiler/main.md)
- [<span data-ttu-id="b49a5-135">Freigegeben</span><span class="sxs-lookup"><span data-stu-id="b49a5-135">Shared</span></span>](../../language-reference/modifiers/shared.md)
- [<span data-ttu-id="b49a5-136">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b49a5-136">Sub Statement</span></span>](../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="b49a5-137">Function-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b49a5-137">Function Statement</span></span>](../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="b49a5-138">Integer-Datentyp</span><span class="sxs-lookup"><span data-stu-id="b49a5-138">Integer Data Type</span></span>](../../language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="b49a5-139">String-Datentyp</span><span class="sxs-lookup"><span data-stu-id="b49a5-139">String Data Type</span></span>](../../language-reference/data-types/string-data-type.md)
