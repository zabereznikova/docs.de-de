---
title: Main()-Rückgabewerte – C#-Programmierhandbuch
description: Erfahren Sie mehr über Main()-Rückgabewerte. Hier finden Sie Codebeispiele, vom Compiler generierten Code und zusätzliche verfügbare Ressourcen.
ms.date: 08/02/2017
helpviewer_keywords:
- Main method [C#], return values
ms.assetid: c2f5a1d8-1676-4bea-bc7e-44a97e72d5bc
ms.openlocfilehash: c7521f6aef79825a8cc20d5455588a2d684b9ccb
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609602"
---
# <a name="main-return-values-c-programming-guide"></a><span data-ttu-id="47981-104">Main()-Rückgabewerte (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="47981-104">Main() return values (C# Programming Guide)</span></span>

<span data-ttu-id="47981-105">Die Methode `Main` kann `void` zurückgeben:</span><span class="sxs-lookup"><span data-stu-id="47981-105">The `Main` method can return `void`:</span></span>

 [!code-csharp[csProgGuideMain#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#12)]

<span data-ttu-id="47981-106">Zudem kann `int` zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="47981-106">It can also return an `int`:</span></span>

 [!code-csharp[csProgGuideMain#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#13)]

<span data-ttu-id="47981-107">Wenn der Rückgabewert von `Main` nicht verwendet wird, ermöglicht die Rückgabe von `void` einen etwas einfacheren Code.</span><span class="sxs-lookup"><span data-stu-id="47981-107">If the return value from `Main` is not used, returning `void` allows for slightly simpler code.</span></span> <span data-ttu-id="47981-108">Die Rückgabe einer Ganzzahl ermöglicht es dem Programm jedoch, Statusinformationen an andere Programme oder Skripts zu übermitteln, die die ausführbare Datei aufrufen.</span><span class="sxs-lookup"><span data-stu-id="47981-108">However, returning an integer enables the program to communicate status information to other programs or scripts that invoke the executable file.</span></span> <span data-ttu-id="47981-109">Der Rückgabewert von `Main` wird als Exitcode für den Prozess behandelt.</span><span class="sxs-lookup"><span data-stu-id="47981-109">The return value from `Main` is treated as the exit code for the process.</span></span> <span data-ttu-id="47981-110">Wenn `void` von `Main` zurückgegeben wird, entspricht der Exitcode implizit `0`.</span><span class="sxs-lookup"><span data-stu-id="47981-110">If `void` is returned from `Main`, the exit code will be implicitly `0`.</span></span> <span data-ttu-id="47981-111">Im folgenden Beispiel wird gezeigt, wie auf den Rückgabewert von `Main` zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="47981-111">The following example shows how the return value from `Main` can be accessed.</span></span>

## <a name="example"></a><span data-ttu-id="47981-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="47981-112">Example</span></span>

<span data-ttu-id="47981-113">In diesem Beispiel werden Befehlszeilentools von [.NET Core](../../../core/introduction.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="47981-113">This example uses [.NET Core](../../../core/introduction.md) command-line tools.</span></span> <span data-ttu-id="47981-114">Wenn Sie noch nicht mit den Befehlszeilentools von .NET Core vertraut sind, finden Sie weitere Informationen in diesem [Artikel zu den ersten Schritten](../../../core/tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="47981-114">If you are unfamiliar with .NET Core command-line tools, you can learn about them in this [get-started article](../../../core/tutorials/with-visual-studio-code.md).</span></span>

<span data-ttu-id="47981-115">Ändern Sie die Methode `Main` in *program.cs* folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="47981-115">Modify the `Main` method in *program.cs* as follows:</span></span>

 [!code-csharp[csProgGuideMain#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class3.cs#14)]

<span data-ttu-id="47981-116">Wenn ein Programm in Windows ausgeführt wird, wird jeder Wert, der von der Funktion `Main` zurückgegeben wurde, in einer Umgebungsvariable gespeichert.</span><span class="sxs-lookup"><span data-stu-id="47981-116">When a program is executed in Windows, any value returned from the `Main` function is stored in an environment variable.</span></span> <span data-ttu-id="47981-117">Diese Umgebungsvariable kann abgerufen werden, indem `ERRORLEVEL` aus einer Batchdatei oder `$LastExitCode` aus PowerShell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="47981-117">This environment variable can be retrieved using `ERRORLEVEL` from a batch file, or `$LastExitCode` from PowerShell.</span></span>

<span data-ttu-id="47981-118">Sie können die Anwendung mithilfe des [dotnet CLI](../../../core/tools/dotnet.md)-Befehls `dotnet build` erstellen.</span><span class="sxs-lookup"><span data-stu-id="47981-118">You can build the application using the [dotnet CLI](../../../core/tools/dotnet.md) `dotnet build` command.</span></span>

<span data-ttu-id="47981-119">Als Nächstes erstellen Sie ein PowerShell-Skript, das die Anwendung ausführt und die Ergebnisse anzeigt.</span><span class="sxs-lookup"><span data-stu-id="47981-119">Next, create a PowerShell script to run the application and display the result.</span></span> <span data-ttu-id="47981-120">Fügen Sie folgenden Code in eine Textdatei ein und speichern Sie diese als `test.ps1` in dem Ordner, der das Projekt enthält.</span><span class="sxs-lookup"><span data-stu-id="47981-120">Paste the following code into a text file and save it as `test.ps1` in the folder that contains the project.</span></span> <span data-ttu-id="47981-121">Führen Sie das PowerShell-Skript aus, indem Sie `test.ps1` in die PowerShell-Eingabeaufforderung eingeben.</span><span class="sxs-lookup"><span data-stu-id="47981-121">Run the PowerShell script by typing `test.ps1` at the PowerShell prompt.</span></span>

<span data-ttu-id="47981-122">Da der Code null zurückgibt, wird die Batchdatei als erfolgreich gemeldet.</span><span class="sxs-lookup"><span data-stu-id="47981-122">Because the code returns zero, the batch file will report success.</span></span> <span data-ttu-id="47981-123">Wenn Sie jedoch die Datei „MainReturnValTest.cs“ ändern, damit sie einen Wert ungleich null (0) zurückgibt, und das Programm anschließend neu kompilieren, wird eine nachfolgende Ausführung des PowerShell-Skripts einen Fehler melden.</span><span class="sxs-lookup"><span data-stu-id="47981-123">However, if you change MainReturnValTest.cs to return a non-zero value and then recompile the program, subsequent execution of the PowerShell script will report failure.</span></span>

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

## <a name="sample-output"></a><span data-ttu-id="47981-124">Beispielausgabe:</span><span class="sxs-lookup"><span data-stu-id="47981-124">Sample output</span></span>

```txt
Execution succeeded
Return value = 0
```

## <a name="async-main-return-values"></a><span data-ttu-id="47981-125">Asynchrone Hauptrückgabewerte</span><span class="sxs-lookup"><span data-stu-id="47981-125">Async Main return values</span></span>

<span data-ttu-id="47981-126">Asynchrone Hauptrückgabewerte verschieben die Codebausteine, die zum Abrufen von asynchronen Methoden benötigt werden, nach `Main` zu dem Code, der vom Compiler generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="47981-126">Async Main return values move the boilerplate code necessary for calling asynchronous methods in `Main` to code generated by the compiler.</span></span> <span data-ttu-id="47981-127">Bisher mussten Sie dieses Konstrukt schreiben, um asynchronen Code abzurufen und prüfen, ob Ihr Programm ausgeführt wurde, bevor der asynchrone Vorgang abgeschlossen ist:</span><span class="sxs-lookup"><span data-stu-id="47981-127">Previously, you would need to write this construct to call asynchronous code and ensure your program ran until the asynchronous operation completed:</span></span>

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

<span data-ttu-id="47981-128">Dies kann nun durch Folgendes ersetzt werden:</span><span class="sxs-lookup"><span data-stu-id="47981-128">Now, this can be replaced by:</span></span>

[!code-csharp[AsyncMain](../../../../samples/snippets/csharp/main-arguments/program.cs#AsyncMain)]

<span data-ttu-id="47981-129">Der Vorteil der neuen Syntax ist, dass der Compiler immer den richtigen Code generiert.</span><span class="sxs-lookup"><span data-stu-id="47981-129">The advantage of the new syntax is that the compiler always generates the correct code.</span></span>

## <a name="compiler-generated-code"></a><span data-ttu-id="47981-130">Vom Compiler generierter Code</span><span class="sxs-lookup"><span data-stu-id="47981-130">Compiler-generated code</span></span>

<span data-ttu-id="47981-131">Wenn der Einstiegspunkt der Anwendung `Task` oder `Task<int>` zurückgibt, generiert der Compiler einen neuen Eingangspunkt, der die Eingangspunktmethode abruft, die im Anwendungscode deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="47981-131">When the application entry point returns a `Task` or `Task<int>`, the compiler generates a new entry point that calls the entry point method declared in the application code.</span></span> <span data-ttu-id="47981-132">Unter der Annahme, dass dieser Einstiegspunkt als `$GeneratedMain` bezeichnet wird, generiert der Compiler den folgenden Code für diese Einstiegspunkte:</span><span class="sxs-lookup"><span data-stu-id="47981-132">Assuming that this entry point is called `$GeneratedMain`, the compiler generates the following code for these entry points:</span></span>

- <span data-ttu-id="47981-133">`static Task Main()` führt dazu, dass der Compiler das Äquivalent zu `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();` ausgibt</span><span class="sxs-lookup"><span data-stu-id="47981-133">`static Task Main()` results in the compiler emitting the equivalent of `private static void $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="47981-134">`static Task Main(string[])` führt dazu, dass der Compiler das Äquivalent zu `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();` ausgibt</span><span class="sxs-lookup"><span data-stu-id="47981-134">`static Task Main(string[])` results in the compiler emitting the equivalent of `private static void $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="47981-135">`static Task<int> Main()` führt dazu, dass der Compiler das Äquivalent zu `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();` ausgibt</span><span class="sxs-lookup"><span data-stu-id="47981-135">`static Task<int> Main()` results in the compiler emitting the equivalent of `private static int $GeneratedMain() => Main().GetAwaiter().GetResult();`</span></span>
- <span data-ttu-id="47981-136">`static Task<int> Main(string[])` führt dazu, dass der Compiler das Äquivalent zu `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();` ausgibt</span><span class="sxs-lookup"><span data-stu-id="47981-136">`static Task<int> Main(string[])` results in the compiler emitting the equivalent of `private static int $GeneratedMain(string[] args) => Main(args).GetAwaiter().GetResult();`</span></span>

> [!NOTE]
><span data-ttu-id="47981-137">Wäre im Beispiel der Modifizierer `async` auf die Methode `Main` angewendet worden, hätte der Compiler denselben Code generiert.</span><span class="sxs-lookup"><span data-stu-id="47981-137">If the examples used `async` modifier on the `Main` method, the compiler would generate the same code.</span></span>

## <a name="see-also"></a><span data-ttu-id="47981-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47981-138">See also</span></span>

- [<span data-ttu-id="47981-139">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="47981-139">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="47981-140">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="47981-140">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="47981-141">Main() und Befehlszeilenargumente</span><span class="sxs-lookup"><span data-stu-id="47981-141">Main() and Command-Line Arguments</span></span>](index.md)
- [<span data-ttu-id="47981-142">Vorgehensweise: Anzeigen von Befehlszeilenargumenten</span><span class="sxs-lookup"><span data-stu-id="47981-142">How to display command line arguments</span></span>](./how-to-display-command-line-arguments.md)
