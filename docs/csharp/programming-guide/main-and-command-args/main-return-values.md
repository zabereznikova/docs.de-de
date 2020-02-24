---
title: Main()-Rückgabewerte – C#-Programmierhandbuch
ms.date: 08/02/2017
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: eaa78c33613093bb0e108870669392d07d346a95
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/20/2020
ms.locfileid: "77504003"
---
# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="2c2cf-102">Main()-Rückgabewerte (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2c2cf-102">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="2c2cf-103">Die Methode `Main` kann `void` zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="2c2cf-103">The `Main` method can return `void`:</span></span>

 [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

<span data-ttu-id="2c2cf-104">Zudem kann `int` zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="2c2cf-104">It can also return an `int`:</span></span>

 [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

<span data-ttu-id="2c2cf-105">Wenn der Rückgabewert von `Main` nicht verwendet wird, ermöglicht die Rückgabe von `void` einen etwas einfacheren Code.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-105">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="2c2cf-106">Die Rückgabe einer Ganzzahl ermöglicht es dem Programm jedoch, Statusinformationen an andere Programme oder Skripts zu übermitteln, die die ausführbare Datei aufrufen.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-106">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="2c2cf-107">Der Rückgabewert von `Main` wird als Exitcode für den Prozess behandelt.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-107">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="2c2cf-108">Wenn `void` aus `Main` zurückgegeben wird, ist der Exitcode implizit `0`.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-108">If `void` is returned from `Main` the exit code will be implicitly `0`.</span></span> <span data-ttu-id="2c2cf-109">Im folgenden Beispiel wird gezeigt, wie auf den Rückgabewert von `Main` zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-109">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="2c2cf-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2c2cf-110">Example</span></span>

<span data-ttu-id="2c2cf-111">Dieses Beispiel verwendet [.NET Core](../../../core/index.md) -Befehlszeilentools.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-111">This example uses [.NET Core](../../../core/index.md) command line tools.</span></span> <span data-ttu-id="2c2cf-112">Wenn Sie mit den .NET Core-Befehlszeilentools nicht vertraut sind, finden Sie weitere Informationen darüber in diesem [Artikel zu den ersten Schritten](../../../core/tutorials/cli-create-console-app.md).</span><span class="sxs-lookup"><span data-stu-id="2c2cf-112">If you are unfamiliar with .NET Core command line tools, you can learn about them in this [Get started topic](../../../core/tutorials/cli-create-console-app.md).</span></span>

<span data-ttu-id="2c2cf-113">Ändern Sie die Methode `Main` in *program.cs* folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="2c2cf-113">Modify the `Main` method in *program.cs* as follows:</span></span>

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

<span data-ttu-id="2c2cf-114">Wenn ein Programm in Windows ausgeführt wird, wird jeder Wert, der von der Funktion `Main` zurückgegeben wurde, in einer Umgebungsvariable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-114">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="2c2cf-115">Diese Umgebungsvariable kann abgerufen werden, indem `ERRORLEVEL` aus einer Batchdatei oder `$LastExitCode` aus PowerShell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-115">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from powershell.</span></span>

<span data-ttu-id="2c2cf-116">Sie können die Anwendung mithilfe des [dotnet CLI](../../../core/tools/dotnet.md)-Befehls `dotnet build` erstellen.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-116">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="2c2cf-117">Als nächstes erstellen Sie ein PowerShell-Skript, das die Anwendung ausführt und die Ergebnisse anzeigt.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-117">Next, create a Powershell script to run the application and display the result.</span></span> <span data-ttu-id="2c2cf-118">Fügen Sie folgenden Code in eine Textdatei ein und speichern Sie diese als `test.ps1` in dem Ordner, der das Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-118">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="2c2cf-119">Führen Sie das PowerShell-Skript aus, indem Sie `test.ps1` in die PowerShell-Eingabeaufforderung eingeben.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-119">Run the powershell script by typing `test.ps1` at the powershell prompt.</span></span>

<span data-ttu-id="2c2cf-120">Da der Code null zurückgibt, wird die Batchdatei als erfolgreich gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-120">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="2c2cf-121">Wenn Sie jedoch „MainReturnValTest.cs“ ändern, damit sie einen Wert ungleich null zurückgibt, und anschließend das Programm erneut kompilieren, wird eine nachfolgende Ausführung des PowerShell-Skripts einen Fehler melden.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-121">However, if you change MainReturnValTest.cs to return a non-zero value and then re-compile the program, subsequent execution of the powershell script will report failure.</span></span>

```dotnetcli
dotnet run
```

```powershell
if ($LastExitCode -eq 0) {
    Write-Host "Execution succeeded"
} else
{
    Write-Host "Execution Failed"
}
Write-Host "Return value = " $LastExitCode
```

## <a name="sample-output"></a><span data-ttu-id="2c2cf-122">Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="2c2cf-122">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="2c2cf-123">Asynchrone Hauptrückgabewerte</span><span class="sxs-lookup"><span data-stu-id="2c2cf-123">Async Main return values</span></span>

<span data-ttu-id="2c2cf-124">Asynchrone Hauptrückgabewerte verschieben die Codebausteine, die zum Abrufen von asynchronen Methoden benötigt werden, nach `Main` zu dem Code, der vom Compiler generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-124">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="2c2cf-125">Bisher mussten Sie dieses Konstrukt schreiben, um asynchronen Code abzurufen und prüfen, ob Ihr Programm ausgeführt wurde, bevor der asynchrone Vorgang abgeschlossen ist:</span><span class="sxs-lookup"><span data-stu-id="2c2cf-125">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

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

<span data-ttu-id="2c2cf-126">Dies kann nun durch Folgendes ersetzt werden:</span><span class="sxs-lookup"><span data-stu-id="2c2cf-126">Now, this can be replaced by:</span></span>

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

<span data-ttu-id="2c2cf-127">Der Vorteil der neuen Syntax ist, dass der Compiler immer den richtigen Code generiert.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-127">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="2c2cf-128">Vom Compiler generierter Code</span><span class="sxs-lookup"><span data-stu-id="2c2cf-128">Compiler generated code</span></span>

<span data-ttu-id="2c2cf-129">Wenn der Einstiegspunkt der Anwendung `Task` oder `Task<int>` zurückgibt, generiert der Compiler einen neuen Eingangspunkt, der die Eingangspunktmethode abruft, die im Anwendungscode deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-129">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="2c2cf-130">Unter der Annahme, dass dieser Einstiegspunkt als `$GeneratedMain` bezeichnet wird, generiert der Compiler den folgenden Code für diese Einstiegspunkte:</span><span class="sxs-lookup"><span data-stu-id="2c2cf-130">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="2c2cf-131">`static Task Main()` führt dazu, dass der Compiler das Äquivalent zu `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();` ausgibt</span><span class="sxs-lookup"><span data-stu-id="2c2cf-131">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="2c2cf-132">`static Task Main(string[])` führt dazu, dass der Compiler das Äquivalent zu `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();` ausgibt</span><span class="sxs-lookup"><span data-stu-id="2c2cf-132">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="2c2cf-133">`static Task<int> Main()` führt dazu, dass der Compiler das Äquivalent zu `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();` ausgibt</span><span class="sxs-lookup"><span data-stu-id="2c2cf-133">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="2c2cf-134">`static Task<int> Main(string[])` führt dazu, dass der Compiler das Äquivalent zu `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();` ausgibt</span><span class="sxs-lookup"><span data-stu-id="2c2cf-134">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="2c2cf-135">Wäre im Beispiel der Modifizierer `async` auf die Methode `Main` angewendet worden, hätte der Compiler denselben Code generiert.</span><span class="sxs-lookup"><span data-stu-id="2c2cf-135">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c2cf-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c2cf-136">See also</span></span>

- [<span data-ttu-id="2c2cf-137">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2c2cf-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2c2cf-138">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="2c2cf-138">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2c2cf-139">Main() und Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="2c2cf-139">Main() and Command-Line Arguments</span></span>](index.md)
- [<span data-ttu-id="2c2cf-140">Vorgehensweise: Anzeigen von Befehlszeilenargumenten</span><span class="sxs-lookup"><span data-stu-id="2c2cf-140">How to display command line arguments</span></span>](./how-to-display-command-line-arguments.md)
