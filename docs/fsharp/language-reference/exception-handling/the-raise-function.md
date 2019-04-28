---
title: 'Ausnahmen: Die raise-Funktion'
description: Erfahren Sie, wie die F# "raise"-Funktion wird verwendet, um anzugeben, dass ein Fehler oder Ausnahmebedingung aufgetreten ist.
ms.date: 05/16/2016
ms.openlocfilehash: 87773ead7773c62a325c7e7ff105c729e10dd69c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772670"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="53a6f-103">Ausnahmen: Die raise-Funktion</span><span class="sxs-lookup"><span data-stu-id="53a6f-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="53a6f-104">Die `raise` Funktion wird verwendet, um anzugeben, dass ein Fehler oder Ausnahmebedingung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="53a6f-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="53a6f-105">Informationen zu dem Fehler wird in einem Ausnahmeobjekt erfasst.</span><span class="sxs-lookup"><span data-stu-id="53a6f-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="53a6f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="53a6f-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="53a6f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53a6f-107">Remarks</span></span>

<span data-ttu-id="53a6f-108">Die `raise` Funktion generiert ein Exception-Objekt und eine stapelentladung Prozess initiiert.</span><span class="sxs-lookup"><span data-stu-id="53a6f-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="53a6f-109">Des Entladens Stapel wird durch die common Language Runtime (CLR), verwaltet, sodass das Verhalten dieses Prozesses identisch ist, da es in einer beliebigen anderen .NET-Sprache ist.</span><span class="sxs-lookup"><span data-stu-id="53a6f-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="53a6f-110">Der Stapel entladen Prozess ist eine Suche nach einem Ausnahmehandler, der die generierte Ausnahme entspricht.</span><span class="sxs-lookup"><span data-stu-id="53a6f-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="53a6f-111">Die Suche beginnt in der aktuellen `try...with` Ausdruck, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="53a6f-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="53a6f-112">Jedes Muster in den `with` Block aktiviert ist, in der Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="53a6f-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="53a6f-113">Wenn ein passender Ausnahmehandler gefunden wird, wird die Ausnahme als behandelt. Andernfalls wird der Stapel entladen und `with` -Blöcke in der Aufrufkette werden überprüft, bis ein entsprechender Handler gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="53a6f-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="53a6f-114">Alle `finally` zunehmender Abarbeitung des Stapels werden ebenfalls blockiert, die in der Aufrufkette gefunden werden nacheinander ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="53a6f-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="53a6f-115">Die `raise` Funktion entspricht der `throw` in c# oder C++.</span><span class="sxs-lookup"><span data-stu-id="53a6f-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="53a6f-116">Verwendung `reraise` in einem Catch-Handler die gleiche Ausnahme der Aufrufkette weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="53a6f-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="53a6f-117">Die folgenden Codebeispiele veranschaulichen die Verwendung der `raise` Funktion eine Ausnahme generiert.</span><span class="sxs-lookup"><span data-stu-id="53a6f-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="53a6f-118">Die `raise` Funktion kann auch zum Auslösen von Ausnahmen .NET verwendet werden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="53a6f-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="53a6f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53a6f-119">See also</span></span>

- [<span data-ttu-id="53a6f-120">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="53a6f-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="53a6f-121">Ausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="53a6f-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="53a6f-122">Ausnahmen: Die `try...with` Ausdruck</span><span class="sxs-lookup"><span data-stu-id="53a6f-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="53a6f-123">Ausnahmen: Die `try...finally` Ausdruck</span><span class="sxs-lookup"><span data-stu-id="53a6f-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="53a6f-124">Ausnahmen: Die `failwith` Funktion</span><span class="sxs-lookup"><span data-stu-id="53a6f-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="53a6f-125">Ausnahmen: Die `invalidArg` Funktion</span><span class="sxs-lookup"><span data-stu-id="53a6f-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)