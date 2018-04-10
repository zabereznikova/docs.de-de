---
title: Ausnahmebehandlung (F#)
description: Grundlagen der Ausnahmebehandlung in F# erläutert werden, und enthält Links zu Ausnahmebehandlung Ausdrücke und Funktionen.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: ad475c4a-d94e-47d9-b27b-3ff000b65f8e
ms.openlocfilehash: b61af66e0a70fdf9b86df37418c0284957d1f99e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="exception-handling"></a><span data-ttu-id="590eb-104">Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="590eb-104">Exception Handling</span></span>

<span data-ttu-id="590eb-105">Dieser Abschnitt enthält Informationen über die Unterstützung für die Ausnahmebehandlung in der Sprache F#.</span><span class="sxs-lookup"><span data-stu-id="590eb-105">This section contains information about exception handling support in the F# language.</span></span>


## <a name="exception-handling-basics"></a><span data-ttu-id="590eb-106">Grundlagen der Ausnahmebehandlung</span><span class="sxs-lookup"><span data-stu-id="590eb-106">Exception Handling Basics</span></span>
<span data-ttu-id="590eb-107">Die Ausnahmebehandlung ist die Standardmethode zum Behandeln von Fehlerbedingungen in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="590eb-107">Exception handling is the standard way of handling error conditions in the .NET Framework.</span></span> <span data-ttu-id="590eb-108">Daher muss jede .NET-Sprache diesen Mechanismus unterstützen, einschließlich F#.</span><span class="sxs-lookup"><span data-stu-id="590eb-108">Thus, any .NET language must support this mechanism, including F#.</span></span> <span data-ttu-id="590eb-109">Eine *Ausnahme* ist ein Objekt, das Information über einen Fehler kapselt.</span><span class="sxs-lookup"><span data-stu-id="590eb-109">An *exception* is an object that encapsulates information about an error.</span></span> <span data-ttu-id="590eb-110">Wenn Fehler auftreten, werden Ausnahmen ausgelöst, und die reguläre Ausführung wird beendet.</span><span class="sxs-lookup"><span data-stu-id="590eb-110">When errors occur, exceptions are raised and regular execution stops.</span></span> <span data-ttu-id="590eb-111">Stattdessen sucht die Laufzeit nach einem passenden Handler für die Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="590eb-111">Instead, the runtime searches for an appropriate handler for the exception.</span></span> <span data-ttu-id="590eb-112">Die Suche beginnt in der aktuellen Funktion und wird im Stapel in den höheren Ebenen der Aufrufer fortgesetzt, bis ein entsprechender Handler gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="590eb-112">The search starts in the current function, and proceeds up the stack through the layers of callers until a matching handler is found.</span></span> <span data-ttu-id="590eb-113">Anschließend wird der Handler ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="590eb-113">Then the handler is executed.</span></span>

<span data-ttu-id="590eb-114">Zudem führt die Laufzeit beliebigen Code in `finally`-Blöcken aus, wenn der Stapel entladen wird, um sicherzustellen, dass Objekte ordnungsgemäß während des Endladungsprozesses bereinigt werden.</span><span class="sxs-lookup"><span data-stu-id="590eb-114">In addition, as the stack is unwound, the runtime executes any code in `finally` blocks, to guarantee that objects are cleaned up correctly during the unwinding process.</span></span>


## <a name="related-topics"></a><span data-ttu-id="590eb-115">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="590eb-115">Related Topics</span></span>

|<span data-ttu-id="590eb-116">Titel</span><span class="sxs-lookup"><span data-stu-id="590eb-116">Title</span></span>|<span data-ttu-id="590eb-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="590eb-117">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="590eb-118">Ausnahmetypen</span><span class="sxs-lookup"><span data-stu-id="590eb-118">Exception Types</span></span>](exception-types.md)|<span data-ttu-id="590eb-119">Beschreibt, wie ein Ausnahmetyp deklariert wird</span><span class="sxs-lookup"><span data-stu-id="590eb-119">Describes how to declare an exception type.</span></span>|
|[<span data-ttu-id="590eb-120">Ausnahmen: Der `try...with`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="590eb-120">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)|<span data-ttu-id="590eb-121">Beschreibt das Sprachkonstrukt, das Ausnahmebehandlung unterstützt</span><span class="sxs-lookup"><span data-stu-id="590eb-121">Describes the language construct that supports exception handling.</span></span>|
|[<span data-ttu-id="590eb-122">Ausnahmen: Der `try...finally`-Ausdruck</span><span class="sxs-lookup"><span data-stu-id="590eb-122">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)|<span data-ttu-id="590eb-123">Beschreibt das Sprachkonstrukt, mit dem Sie Bereinigungscode auszuführen können, während der Stapel entladen wird, wenn eine Ausnahme ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="590eb-123">Describes the language construct that enables you to execute clean-up code as the stack unwinds when an exception is thrown.</span></span>|
|[<span data-ttu-id="590eb-124">Ausnahmen: Die `raise`-Funktion</span><span class="sxs-lookup"><span data-stu-id="590eb-124">Exceptions: the `raise` Function</span></span>](the-raise-Function.md)|<span data-ttu-id="590eb-125">Beschreibt, wie ein Ausnahmeobjekt ausgelöst wird</span><span class="sxs-lookup"><span data-stu-id="590eb-125">Describes how to throw an exception object.</span></span>|
|[<span data-ttu-id="590eb-126">Ausnahmen: Die `failwith`-Funktion</span><span class="sxs-lookup"><span data-stu-id="590eb-126">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)|<span data-ttu-id="590eb-127">Beschreibt, wie eine allgemeine F#-Ausnahme generiert wird</span><span class="sxs-lookup"><span data-stu-id="590eb-127">Describes how to generate a general F# exception.</span></span>|
|[<span data-ttu-id="590eb-128">Ausnahmen: Die `invalidArg`-Funktion</span><span class="sxs-lookup"><span data-stu-id="590eb-128">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)|<span data-ttu-id="590eb-129">Beschreibt, wie eine ungültige Argumentausnahme generiert wird</span><span class="sxs-lookup"><span data-stu-id="590eb-129">Describes how to generate an invalid argument exception.</span></span>|
