---
title: 'Ausnahmen: Die raise-Funktion'
description: Erfahren Sie, F# wie die ' Raise '-Funktion verwendet wird, um anzugeben, dass ein Fehler oder eine Ausnahme Bedingung aufgetreten ist.
ms.date: 05/16/2016
ms.openlocfilehash: e0cc8da8310203c537b8081af8a225671bd8c6a3
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630291"
---
# <a name="exceptions-the-raise-function"></a><span data-ttu-id="20af2-103">Ausnahmen: Die raise-Funktion</span><span class="sxs-lookup"><span data-stu-id="20af2-103">Exceptions: the raise Function</span></span>

<span data-ttu-id="20af2-104">Die `raise` -Funktion wird verwendet, um anzugeben, dass ein Fehler oder eine Ausnahme Bedingung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="20af2-104">The `raise` function is used to indicate that an error or exceptional condition has occurred.</span></span> <span data-ttu-id="20af2-105">Informationen über den Fehler werden in einem Ausnahme Objekt aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="20af2-105">Information about the error is captured in an exception object.</span></span>

## <a name="syntax"></a><span data-ttu-id="20af2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="20af2-106">Syntax</span></span>

```fsharp
raise (expression)
```

## <a name="remarks"></a><span data-ttu-id="20af2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20af2-107">Remarks</span></span>

<span data-ttu-id="20af2-108">Die `raise` -Funktion generiert ein Exception-Objekt und initiiert einen Stapel Entwicklungsprozess.</span><span class="sxs-lookup"><span data-stu-id="20af2-108">The `raise` function generates an exception object and initiates a stack unwinding process.</span></span> <span data-ttu-id="20af2-109">Der Stapel Entwicklungsprozess wird vom Common Language Runtime (CLR) verwaltet, sodass das Verhalten dieses Prozesses mit dem Verhalten in jeder anderen .NET-Sprache identisch ist.</span><span class="sxs-lookup"><span data-stu-id="20af2-109">The stack unwinding process is managed by the common language runtime (CLR), so the behavior of this process is the same as it is in any other .NET language.</span></span> <span data-ttu-id="20af2-110">Der Stapel Entwicklungsprozess ist eine Suche nach einem Ausnahmehandler, der mit der generierten Ausnahme übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="20af2-110">The stack unwinding process is a search for an exception handler that matches the generated exception.</span></span> <span data-ttu-id="20af2-111">Die Suche beginnt im aktuellen `try...with` Ausdruck, sofern vorhanden.</span><span class="sxs-lookup"><span data-stu-id="20af2-111">The search starts in the current `try...with` expression, if there is one.</span></span> <span data-ttu-id="20af2-112">Jedes Muster im Block `with` wird in der richtigen Reihenfolge geprüft.</span><span class="sxs-lookup"><span data-stu-id="20af2-112">Each pattern in the `with` block is checked, in order.</span></span> <span data-ttu-id="20af2-113">Wenn ein übereinstimmender Ausnahmehandler gefunden wird, gilt die Ausnahme als behandelt. Andernfalls wird der Stapel entsperrt und `with` blockiert, bis ein übereinstimmender Handler gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="20af2-113">When a matching exception handler is found, the exception is considered handled; otherwise, the stack is unwound and `with` blocks up the call chain are checked until a matching handler is found.</span></span> <span data-ttu-id="20af2-114">Alle `finally` Blöcke, die in der-Aufrufkette gefunden werden, werden auch nacheinander ausgeführt, wenn der Stapel entlädt.</span><span class="sxs-lookup"><span data-stu-id="20af2-114">Any `finally` blocks that are encountered in the call chain are also executed in sequence as the stack unwinds.</span></span>

<span data-ttu-id="20af2-115">Die `raise` -Funktion `throw` entspricht in C# oder C++.</span><span class="sxs-lookup"><span data-stu-id="20af2-115">The `raise` function is the equivalent of `throw` in C# or C++.</span></span> <span data-ttu-id="20af2-116">Verwenden `reraise` Sie in einem catch-Handler, um dieselbe Ausnahme in der Aufrufkette weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="20af2-116">Use `reraise` in a catch handler to propagate the same exception up the call chain.</span></span>

<span data-ttu-id="20af2-117">Die folgenden Codebeispiele veranschaulichen die Verwendung `raise` der-Funktion, um eine Ausnahme zu generieren.</span><span class="sxs-lookup"><span data-stu-id="20af2-117">The following code examples illustrate the use of the `raise` function to generate an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5801.fs)]

<span data-ttu-id="20af2-118">Die `raise` -Funktion kann auch verwendet werden, um .NET-Ausnahmen zu verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="20af2-118">The `raise` function can also be used to raise .NET exceptions, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5802.fs)]

## <a name="see-also"></a><span data-ttu-id="20af2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20af2-119">See also</span></span>

- [<span data-ttu-id="20af2-120">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="20af2-120">Exception Handling</span></span>](index.md)
- [<span data-ttu-id="20af2-121">Ausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="20af2-121">Exception Types</span></span>](exception-types.md)
- [<span data-ttu-id="20af2-122">Ausnahmen: Der `try...with` Ausdruck</span><span class="sxs-lookup"><span data-stu-id="20af2-122">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)
- [<span data-ttu-id="20af2-123">Ausnahmen: Der `try...finally` Ausdruck</span><span class="sxs-lookup"><span data-stu-id="20af2-123">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)
- [<span data-ttu-id="20af2-124">Ausnahmen: Die `failwith` -Funktion</span><span class="sxs-lookup"><span data-stu-id="20af2-124">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)
- [<span data-ttu-id="20af2-125">Ausnahmen: Die `invalidArg` -Funktion</span><span class="sxs-lookup"><span data-stu-id="20af2-125">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)
