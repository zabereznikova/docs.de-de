---
title: "Main()-Rückgabewerte (C#-Programmierhandbuch)"
ms.date: 2017-08-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: d019d1c5757a961c03439d756e808ae13fd8a67b
ms.openlocfilehash: 50943bdd0b7726145797faf82719537a388dad89
ms.contentlocale: de-de
ms.lasthandoff: 08/03/2017

---

# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="6efb4-102">Main()-Rückgabewerte (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="6efb4-102">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="6efb4-103">Die Methode `Main` kann `void` zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="6efb4-103">The `Main` method can return `void`:</span></span>

<span data-ttu-id="6efb4-104">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6efb4-104">[!code-cs[csProgGuideMain#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_1.cs)]</span></span>

<span data-ttu-id="6efb4-105">Zudem kann `int` zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="6efb4-105">It can also return an `int`:</span></span>

<span data-ttu-id="6efb4-106">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6efb4-106">[!code-cs[csProgGuideMain#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_2.cs)]</span></span>

<span data-ttu-id="6efb4-107">Wenn der Rückgabewert von `Main` nicht verwendet wird, ermöglicht die Rückgabe von `void` einen etwas einfacheren Code.</span><span class="sxs-lookup"><span data-stu-id="6efb4-107">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="6efb4-108">Die Rückgabe einer Ganzzahl ermöglicht es dem Programm jedoch, Statusinformationen an andere Programme oder Skripts zu übermitteln, die die ausführbare Datei aufrufen.</span><span class="sxs-lookup"><span data-stu-id="6efb4-108">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="6efb4-109">Der Rückgabewert von `Main` wird als Exitcode für den Prozess behandelt.</span><span class="sxs-lookup"><span data-stu-id="6efb4-109">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="6efb4-110">Im folgenden Beispiel wird gezeigt, wie auf den Rückgabewert von `Main` zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="6efb4-110">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="6efb4-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6efb4-111">Example</span></span>

<span data-ttu-id="6efb4-112">Dieses Beispiel verwendet [.NET Core](../../../core/index.md) -Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="6efb4-112">This example uses [.NET Core](../../../core/index.md) command line tools.</span></span> <span data-ttu-id="6efb4-113">Wenn Sie mit den .NET Core-Befehlszeilentools nicht vertraut sind, finden Sie weitere Informationen darüber im [Get started topic (Thema Erste Schritte)](../../../core/tutorials/using-with-xplat-cli.md).</span><span class="sxs-lookup"><span data-stu-id="6efb4-113">If you are unfamilar with .NET Core command line tools, you can learn about them in this [Get started topic](../../../core/tutorials/using-with-xplat-cli.md).</span></span>

<span data-ttu-id="6efb4-114">Ändern Sie die Methode `Main` in *program.cs* folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="6efb4-114">Modify the `Main` method in *program.cs* as follows:</span></span>

<span data-ttu-id="6efb4-115">[!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="6efb4-115">[!code-cs[csProgGuideMain#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-return-values_3.cs)]</span></span>

<span data-ttu-id="6efb4-116">Wenn ein Programm in Windows ausgeführt wird, wird jeder Wert, der von der Funktion `Main` zurückgegeben wurde, in einer Umgebungsvariable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6efb4-116">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="6efb4-117">Diese Umgebungsvariable kann abgerufen werden, indem `ERRORLEVEL` aus einer Batchdatei oder `$LastExitCode` aus PowerShell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6efb4-117">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from powershell.</span></span>

<span data-ttu-id="6efb4-118">Sie können die Anwendung mithilfe des Befehls [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` erstellen.</span><span class="sxs-lookup"><span data-stu-id="6efb4-118">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="6efb4-119">Als nächstes erstellen Sie ein PowerShell-Skript, das die Anwendung ausführt und die Ergebnisse anzeigt.</span><span class="sxs-lookup"><span data-stu-id="6efb4-119">Next, create a Powershell script to run the application and display the result.</span></span> <span data-ttu-id="6efb4-120">Fügen Sie folgenden Code in eine Textdatei ein und speichern Sie diese als `test.ps1` in dem Ordner, der das Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="6efb4-120">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="6efb4-121">Führen Sie das PowerShell-Skript aus, indem Sie `test.ps1` in die PowerShell-Eingabeaufforderung eingeben.</span><span class="sxs-lookup"><span data-stu-id="6efb4-121">Run the powershell script by typing `test.ps1` at the powershell prompt.</span></span>

<span data-ttu-id="6efb4-122">Da der Code null zurückgibt, wird die Batchdatei als erfolgreich gemeldet.</span><span class="sxs-lookup"><span data-stu-id="6efb4-122">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="6efb4-123">Wenn Sie jedoch „MainReturnValTest.cs“ ändern, damit sie einen Wert ungleich null zurückgibt, und anschließend das Programm erneut kompilieren, wird eine nachfolgende Ausführung des PowerShell-Skripts einen Fehler melden.</span><span class="sxs-lookup"><span data-stu-id="6efb4-123">However, if you change MainReturnValTest.cs to return a non-zero value and then re-compile the program, subsequent execution of the powershell script will report failure.</span></span>

```powershell
dotnet run
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a><span data-ttu-id="6efb4-124">Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="6efb4-124">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="6efb4-125">Asynchrone Hauptrückgabewerte</span><span class="sxs-lookup"><span data-stu-id="6efb4-125">Async Main return values</span></span>

<span data-ttu-id="6efb4-126">Asynchrone Hauptrückgabewerte verschieben die Codebausteine, die zum Abrufen von asynchronen Methoden benötigt werden, nach `Main` zu dem Code, der vom Compiler generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="6efb4-126">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="6efb4-127">Bisher mussten Sie dieses Konstrukt schreiben, um asynchronen Code abzurufen und prüfen, ob Ihr Programm ausgeführt wurde, bevor der asynchrone Vorgang abgeschlossen ist:</span><span class="sxs-lookup"><span data-stu-id="6efb4-127">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

```csharp
public static void Main()
{
    AsyncConsoleWork().GetAwaiter().GetResult();
}

private static async Task<int> AsyncConsoleWork()
{
    // Main body here
    return 0;
}
```

<span data-ttu-id="6efb4-128">Dies kann nun durch Folgendes ersetzt werden:</span><span class="sxs-lookup"><span data-stu-id="6efb4-128">Now, this can be replaced by:</span></span>

<span data-ttu-id="6efb4-129">[!code-csharp[AsyncMain (Asynchrone Hauptelemente)](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]</span><span class="sxs-lookup"><span data-stu-id="6efb4-129">[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]</span></span>

<span data-ttu-id="6efb4-130">Der Vorteil der neuen Syntax ist, dass der Compiler immer den richtigen Code generiert.</span><span class="sxs-lookup"><span data-stu-id="6efb4-130">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="6efb4-131">Vom Compiler generierter Code</span><span class="sxs-lookup"><span data-stu-id="6efb4-131">Compiler generated code</span></span>

<span data-ttu-id="6efb4-132">Wenn der Einstiegspunkt der Anwendung `Task` oder `Task<int>` zurückgibt, generiert der Compiler einen neuen Eingangspunkt, der die Eingangspunktmethode abruft, die im Anwendungscode deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="6efb4-132">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="6efb4-133">Unter der Annahme, dass dieser Einstiegspunkt als `$GeneratedMain` bezeichnet wird, generiert der Compiler den folgenden Code für diese Einstiegspunkte:</span><span class="sxs-lookup"><span data-stu-id="6efb4-133">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="6efb4-134">`static Task Main()` führt dazu, dass der Compiler das Äquivalent zu `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();` ausgibt</span><span class="sxs-lookup"><span data-stu-id="6efb4-134">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="6efb4-135">`static Task Main(string[])` führt dazu, dass der Compiler das Äquivalent zu `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();` ausgibt</span><span class="sxs-lookup"><span data-stu-id="6efb4-135">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="6efb4-136">`static Task<int> Main()` führt dazu, dass der Compiler das Äquivalent zu `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();` ausgibt</span><span class="sxs-lookup"><span data-stu-id="6efb4-136">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="6efb4-137">`static Task<int> Main(string[])` führt dazu, dass der Compiler das Äquivalent zu `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();` ausgibt</span><span class="sxs-lookup"><span data-stu-id="6efb4-137">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="6efb4-138">Wäre im Beispiel der Modifizierer `async` auf die Methode `Main` angewendet worden, hätte der Compiler denselben Code generiert.</span><span class="sxs-lookup"><span data-stu-id="6efb4-138">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="6efb4-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6efb4-139">See also</span></span>
<span data-ttu-id="6efb4-140">[C# Programming Guide (C#-Programmierhandbuch)](../../programming-guide/index.md)
[C# Reference (C#-Referenz)](../index.md)
[Main() and Command-Line Arguments (Main() und Befehlszeilenargumente)](index.md)
[How to: Display Command Line Arguments (Vorgehensweise: Anzeigen von Befehlszeilenargumenten)](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
[How to: Access Command-Line Arguments Using foreach (Vorgehensweise: Zugreifen auf Befehlszeilenargumente mithilfe von foreach)](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)</span><span class="sxs-lookup"><span data-stu-id="6efb4-140">[C# Programming Guide](../../programming-guide/index.md)
[C# Reference](../index.md)
[Main() and Command-Line Arguments](index.md)
[How to: Display Command Line Arguments](../../programming-guide/main-and-command-args/how-to-display-command-line-arguments.md)
[How to: Access Command-Line Arguments Using foreach](../../programming-guide/main-and-command-args/how-to-access-command-line-arguments-using-foreach.md)</span></span>

