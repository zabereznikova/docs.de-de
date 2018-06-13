---
title: Main() und Befehlszeilenargumente (C#-Programmierhandbuch)
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
ms.openlocfilehash: 03d6e7185a0a16589fb612724be52ce51e813173
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33332367"
---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="a9ca3-102">Main() und Befehlszeilenargumente (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a9ca3-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="a9ca3-103">Die `Main`-Methode ist der Einstiegspunkt einer C#-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="a9ca3-104">(Bibliotheken und Dienste erfordern keine `Main`-Methode als Einstiegspunkt.) Wenn die Anwendung gestartet wird, ist die `Main`-Methode die erste Methode, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

 <span data-ttu-id="a9ca3-105">In einem C#-Programm kann nur ein Einstiegspunkt vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="a9ca3-106">Wenn Sie mehr als eine Klasse mit einer `Main`-Methode aufweisen, müssen Sie das Programm mit der **/main**-Compileroption kompilieren, um anzugeben, welche `Main`-Methode als Einstiegspunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-106">If you have more than one class that has a `Main` method, you must compile your program with the **/main** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="a9ca3-107">Weitere Informationen hierzu finden Sie unter [/main (C# Compiler Options)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="a9ca3-107">For more information, see [/main (C# Compiler Options)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span></span>

 [!code-csharp[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]

## <a name="overview"></a><span data-ttu-id="a9ca3-108">Übersicht</span><span class="sxs-lookup"><span data-stu-id="a9ca3-108">Overview</span></span>

- <span data-ttu-id="a9ca3-109">Die `Main`-Methode ist der Einstiegspunkt eines ausführbaren Programms. Hier beginnt und endet die Programmsteuerung.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-109">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="a9ca3-110">`Main` wird innerhalb einer Klasse oder Struktur deklariert.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-110">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="a9ca3-111">`Main` muss [statisch](../../../csharp/language-reference/keywords/static.md), aber nicht [öffentlich](../../../csharp/language-reference/keywords/public.md) sein.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-111">`Main` must be [static](../../../csharp/language-reference/keywords/static.md) and it need not be [public](../../../csharp/language-reference/keywords/public.md).</span></span> <span data-ttu-id="a9ca3-112">(Im Beispiel oben erhält es den Standardzugriff [private](../../../csharp/language-reference/keywords/private.md).) Die einschließende Klasse oder Struktur muss nicht statisch sein.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-112">(In the earlier example, it receives the default access of [private](../../../csharp/language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="a9ca3-113">`Main` kann über die Rückgabetypen `void` oder `int` verfügen; seit C# 7.1 sind auch die Rückgabetypen `Task` oder `Task<int>` möglich.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-113">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="a9ca3-114">Wenn – und nur wenn – `Main` einen `Task`- oder `Task<int>`-Wert zurückgibt, darf die Deklaration von `Main` den [`async`](../../language-reference/keywords/async.md)-Modifizierer enthalten.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-114">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="a9ca3-115">Beachten Sie, dass diese insbesondere eine `async void Main`-Methode ausschließt.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-115">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="a9ca3-116">Die `Main`-Methode kann mit oder ohne `string[]`-Parameter deklariert werden, der die Befehlszeilenargumente enthält.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-116">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="a9ca3-117">Bei Verwendung von Visual Studio zum Erstellen von Windows-Anwendungen können Sie den Parameter manuell hinzufügen oder die <xref:System.Environment>-Klasse verwenden, um die Befehlszeilenargumente abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-117">When using Visual Studio to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment> class to obtain the command-line arguments.</span></span> <span data-ttu-id="a9ca3-118">Parameter werden als mit Null indizierte Befehlszeilenargumente gelesen.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-118">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="a9ca3-119">Im Gegensatz zu C und C++ wird der Name des Programms nicht als erstes Befehlszeilenargument behandelt.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-119">Unlike C and C++, the name of the program is not treated as the first command-line argument.</span></span>

<span data-ttu-id="a9ca3-120">Das Hinzufügen der `async`-Rückgabetypen `Task` und `Task<int>` vereinfacht den Programmcode, wenn Konsolenanwendungen asynchrone Vorgänge in `Main` starten und mit `await` darauf warten müssen.</span><span class="sxs-lookup"><span data-stu-id="a9ca3-120">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a9ca3-121">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a9ca3-121">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a9ca3-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9ca3-122">See also</span></span>
[<span data-ttu-id="a9ca3-123">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="a9ca3-123">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
[<span data-ttu-id="a9ca3-124">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a9ca3-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="a9ca3-125">Methoden</span><span class="sxs-lookup"><span data-stu-id="a9ca3-125">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
[<span data-ttu-id="a9ca3-126">Einblicke in ein C#-Programm</span><span class="sxs-lookup"><span data-stu-id="a9ca3-126">Inside a C# Program</span></span>](../../../csharp/programming-guide/inside-a-program/index.md)  
