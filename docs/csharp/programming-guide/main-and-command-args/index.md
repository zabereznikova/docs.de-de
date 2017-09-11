---
title: Main() und Befehlszeilenargumente (C#-Programmierhandbuch)
ms.date: 2017-08-02
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- CS5001
- main_CSharpKeyword
- Main
dev_langs:
- CSharp
helpviewer_keywords:
- Main method [C#]
- C# language, command-line arguments
- arguments [C#], command-line
- command line [C#], arguments
- command-line arguments [C#], Main method
ms.assetid: 73a17231-cf96-44ea-aa8a-54807c6fb1f4
caps.latest.revision: 30
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
ms.openlocfilehash: 51408654abd0dcd2f7159438b507c44bd579bfd9
ms.contentlocale: de-de
ms.lasthandoff: 08/03/2017

---
# <a name="main-and-command-line-arguments-c-programming-guide"></a><span data-ttu-id="ee19d-102">Main() und Befehlszeilenargumente (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ee19d-102">Main() and command-line arguments (C# Programming Guide)</span></span>

<span data-ttu-id="ee19d-103">Die `Main`-Methode ist der Einstiegspunkt einer C#-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ee19d-103">The `Main` method is the entry point of a C# application.</span></span> <span data-ttu-id="ee19d-104">(Bibliotheken und Dienste erfordern keine `Main`-Methode als Einstiegspunkt.) Wenn die Anwendung gestartet wird, ist die `Main`-Methode die erste Methode, die aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ee19d-104">(Libraries and services do not require a `Main` method as an entry point.) When the application is started, the `Main` method is the first method that is invoked.</span></span>

 <span data-ttu-id="ee19d-105">In einem C#-Programm kann nur ein Einstiegspunkt vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="ee19d-105">There can only be one entry point in a C# program.</span></span> <span data-ttu-id="ee19d-106">Wenn Sie mehr als eine Klasse mit einer `Main`-Methode aufweisen, müssen Sie das Programm mit der **/main**-Compileroption kompilieren, um anzugeben, welche `Main`-Methode als Einstiegspunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee19d-106">If you have more than one class that has a `Main` method, you must compile your program with the **/main** compiler option to specify which `Main` method to use as the entry point.</span></span> <span data-ttu-id="ee19d-107">Weitere Informationen hierzu finden Sie unter [/main (C# Compiler Options)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="ee19d-107">For more information, see [/main (C# Compiler Options)](../../../csharp/language-reference/compiler-options/main-compiler-option.md).</span></span>

 <span data-ttu-id="ee19d-108">[!code-cs[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ee19d-108">[!code-cs[csProgGuideMain#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/main-and-command-line-arguments_1.cs)]</span></span>

## <a name="overview"></a><span data-ttu-id="ee19d-109">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ee19d-109">Overview</span></span>

- <span data-ttu-id="ee19d-110">Die `Main`-Methode ist der Einstiegspunkt eines ausführbaren Programms. Hier beginnt und endet die Programmsteuerung.</span><span class="sxs-lookup"><span data-stu-id="ee19d-110">The `Main` method is the entry point of an executable program; it is where the program control starts and ends.</span></span>
- <span data-ttu-id="ee19d-111">`Main` wird innerhalb einer Klasse oder Struktur deklariert.</span><span class="sxs-lookup"><span data-stu-id="ee19d-111">`Main` is declared inside a class or struct.</span></span> <span data-ttu-id="ee19d-112">`Main` muss [statisch](../../../csharp/language-reference/keywords/static.md), aber nicht [öffentlich](../../../csharp/language-reference/keywords/public.md) sein.</span><span class="sxs-lookup"><span data-stu-id="ee19d-112">`Main` must be [static](../../../csharp/language-reference/keywords/static.md) and it need not be [public](../../../csharp/language-reference/keywords/public.md).</span></span> <span data-ttu-id="ee19d-113">(Im Beispiel oben erhält es den Standardzugriff [private](../../../csharp/language-reference/keywords/private.md).) Die einschließende Klasse oder Struktur muss nicht statisch sein.</span><span class="sxs-lookup"><span data-stu-id="ee19d-113">(In the earlier example, it receives the default access of [private](../../../csharp/language-reference/keywords/private.md).) The enclosing class or struct is not required to be static.</span></span>
- <span data-ttu-id="ee19d-114">`Main` kann über die Rückgabetypen `void` oder `int` verfügen; seit C# 7.1 sind auch die Rückgabetypen `Task` oder `Task<int>` möglich.</span><span class="sxs-lookup"><span data-stu-id="ee19d-114">`Main` can either have a `void`, `int`, or, starting with C# 7.1, `Task`, or `Task<int>` return type.</span></span>
- <span data-ttu-id="ee19d-115">Wenn – und nur wenn – `Main` einen `Task`- oder `Task<int>`-Wert zurückgibt, darf die Deklaration von `Main` den [`async`](../../language-reference/keywords/async.md)-Modifizierer enthalten.</span><span class="sxs-lookup"><span data-stu-id="ee19d-115">If and only if `Main` returns a `Task` or `Task<int>`, the declaration of `Main` may include the [`async`](../../language-reference/keywords/async.md) modifier.</span></span> <span data-ttu-id="ee19d-116">Beachten Sie, dass diese insbesondere eine `async void Main`-Methode ausschließt.</span><span class="sxs-lookup"><span data-stu-id="ee19d-116">Note that this specifically excludes an `async void Main` method.</span></span>
- <span data-ttu-id="ee19d-117">Die `Main`-Methode kann mit oder ohne `string[]`-Parameter deklariert werden, der die Befehlszeilenargumente enthält.</span><span class="sxs-lookup"><span data-stu-id="ee19d-117">The `Main` method can be declared with or without a `string[]` parameter that contains command-line arguments.</span></span> <span data-ttu-id="ee19d-118">Bei Verwendung von [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] zum Erstellen von Windows-Anwendungen können Sie den Parameter manuell hinzufügen oder die <xref:System.Environment>-Klasse verwenden, um die Befehlszeilenargumente abzurufen.</span><span class="sxs-lookup"><span data-stu-id="ee19d-118">When using [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] to create Windows applications, you can add the parameter manually or else use the <xref:System.Environment> class to obtain the command-line arguments.</span></span> <span data-ttu-id="ee19d-119">Parameter werden als mit Null indizierte Befehlszeilenargumente gelesen.</span><span class="sxs-lookup"><span data-stu-id="ee19d-119">Parameters are read as zero-indexed command-line arguments.</span></span> <span data-ttu-id="ee19d-120">Im Gegensatz zu C und C++ wird der Name des Programms nicht als erstes Befehlszeilenargument behandelt.</span><span class="sxs-lookup"><span data-stu-id="ee19d-120">Unlike C and C++, the name of the program is not treated as the first command-line argument.</span></span>

<span data-ttu-id="ee19d-121">Das Hinzufügen der `async`-Rückgabetypen `Task` und `Task<int>` vereinfacht den Programmcode, wenn Konsolenanwendungen asynchrone Vorgänge in `Main` starten und mit `await` darauf warten müssen.</span><span class="sxs-lookup"><span data-stu-id="ee19d-121">The addition of `async` and `Task`, `Task<int>` return types simplifies program code when console applications need to start and `await` asynchronous operations in `Main`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="ee19d-122">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ee19d-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ee19d-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee19d-123">See also</span></span>
<span data-ttu-id="ee19d-124">[Erstellen über die Befehlszeile mit „csc.exe“](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
[Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md)
[In einem C#-Programm](../../../csharp/programming-guide/inside-a-program/index.md)</span><span class="sxs-lookup"><span data-stu-id="ee19d-124">[Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
[C# Programming Guide](../../../csharp/programming-guide/index.md)
[Methods](../../../csharp/programming-guide/classes-and-structs/methods.md)
[Inside a C# Program](../../../csharp/programming-guide/inside-a-program/index.md)</span></span>

