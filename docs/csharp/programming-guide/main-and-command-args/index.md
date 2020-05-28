---
title: Main() und Befehlszeilenargumente – C#-Programmierhandbuch
ms.date: 08/02/2017
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
ms.openlocfilehash: 723884dd448232777ae2cfeac5bfcf5ea24363b0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007740"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="2c1e0-102">Main() und Befehlszeilenargumente (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="2c1e0-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="2c1e0-103">Die `Main`-Methode ist der Einstiegspunkt einer C#-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="2c1e0-104">(Bibliotheken und Dienste erfordern keine `Main`-Methode als Einstiegspunkt.) Wenn die Anwendung gestartet wird, ist die `Main`-Methode die erste Methode, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

<span data-ttu-id="2c1e0-105">In einem C#-Programm kann nur ein Einstiegspunkt vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="2c1e0-106">Wenn Sie mehr als eine Klasse mit einer `Main`-Methode aufweisen, müssen Sie das Programm mit der `-main`-Compileroption kompilieren, um anzugeben, welche `Main`-Methode als Einstiegspunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-106">If you have more than one class that has a `Main` method, you must compile your program with the `-main` compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="2c1e0-107">Weitere Informationen finden Sie unter [-main (C#-Compileroptionen)](../../language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="2c1e0-107">For more information, see [-main (C# Compiler Options)](../../language-reference/compiler-options/main-compiler-option.md).</span></span>

[!code-csharp[csProgGuideMain#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideMain/CS/Class1.cs#17)]

## <a name="overview"></a><span data-ttu-id="2c1e0-108">Übersicht</span><span class="sxs-lookup"><span data-stu-id="2c1e0-108">Overview</span></span>

- <span data-ttu-id="2c1e0-109">Die `Main`-Methode ist der Einstiegspunkt eines ausführbaren Programms. Hier beginnt und endet die Programmsteuerung.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-109">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="2c1e0-110">`Main` wird innerhalb einer Klasse oder Struktur deklariert.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-110">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="2c1e0-111">`Main` muss [statisch](../../language-reference/keywords/static.md), aber nicht [öffentlich](../../language-reference/keywords/public.md) sein.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-111">`Main` must be [static](../../language-reference/keywords/static.md) and it need not be [public](../../language-reference/keywords/public.md).</span></span> <span data-ttu-id="2c1e0-112">(Im Beispiel oben erhält es den Standardzugriff [private](../../language-reference/keywords/private.md).) Die einschließende Klasse oder Struktur muss nicht statisch sein.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-112">(In the earlier example, it receives the default access of [private](../../language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="2c1e0-113">`Main` kann über die Rückgabetypen `void` oder `int` verfügen; seit C# 7.1 sind auch die Rückgabetypen `Task` oder `Task<int>` möglich.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-113">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="2c1e0-114">Wenn – und nur wenn – `Main` einen `Task`- oder `Task<int>`-Wert zurückgibt, darf die Deklaration von `Main` den [`async`](../../language-reference/keywords/async.md)-Modifizierer enthalten.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-114">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="2c1e0-115">Beachten Sie, dass diese insbesondere eine `async void Main`-Methode ausschließt.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-115">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="2c1e0-116">Die `Main`-Methode kann mit oder ohne `string[]`-Parameter deklariert werden, der die Befehlszeilenargumente enthält.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-116">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="2c1e0-117">Bei Verwendung von Visual Studio zum Erstellen von Windows-Anwendungen können Sie den Parameter manuell hinzufügen oder die <xref:System.Environment.GetCommandLineArgs>-Methode verwenden, um die [Befehlszeilenargumente](command-line-arguments.md) abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-117">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment.GetCommandLineArgs> method to obtain the [command-line arguments](command-line-arguments.md).</span></span> <span data-ttu-id="2c1e0-118">Parameter werden als mit Null indizierte Befehlszeilenargumente gelesen.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-118">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="2c1e0-119">Im Gegensatz zu C und C++ wird der Name des Programms nicht als erstes Befehlszeilenargument im `args`-Array behandelt, es ist jedoch das erste Element der <xref:System.Environment.GetCommandLineArgs>-Methode.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-119">Unlike C and C++, the name of the program is not treated as the first command-line argument in the `args` array, but it is the first element of the <xref:System.Environment.GetCommandLineArgs> method.</span></span>

<span data-ttu-id="2c1e0-120">Im Folgenden erhalten Sie eine Liste gültiger `Main`-Signaturen:</span><span class="sxs-lookup"><span data-stu-id="2c1e0-120">The following is a list of valid `Main` signatures:</span></span>

```csharp
public static void Main() { }
public static int Main() { }
public static void Main(string[] args) { }
public static int Main(string[] args) { }
public static async Task Main() { }
public static async Task<int> Main() { }
public static async Task Main(string[] args) { }
public static async Task<int> Main(string[] args) { }
```

<span data-ttu-id="2c1e0-121">In den vorangehenden Beispielen wird der öffentliche Zugriffsmodifizierer verwendet.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-121">The preceding examples all use the public accessor modifier.</span></span> <span data-ttu-id="2c1e0-122">Dieses Verhalten ist typisch, aber nicht obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-122">That is typical, but not required.</span></span>

<span data-ttu-id="2c1e0-123">Das Hinzufügen der `async`-Rückgabetypen `Task` und `Task<int>` vereinfacht den Programmcode, wenn Konsolenanwendungen asynchrone Vorgänge in `Main` starten und mit `await` darauf warten müssen.</span><span class="sxs-lookup"><span data-stu-id="2c1e0-123">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="2c1e0-124">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="2c1e0-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2c1e0-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2c1e0-125">See also</span></span>

- [<span data-ttu-id="2c1e0-126">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="2c1e0-126">Command-line Building With csc.exe</span></span>](../../language-reference/compiler-options/command-line-building-with-csc-exe.md)
- [<span data-ttu-id="2c1e0-127">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2c1e0-127">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2c1e0-128">Methoden</span><span class="sxs-lookup"><span data-stu-id="2c1e0-128">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="2c1e0-129">Einblicke in ein C#-Programm</span><span class="sxs-lookup"><span data-stu-id="2c1e0-129">Inside a C# Program</span></span>](../inside-a-program/index.md)
