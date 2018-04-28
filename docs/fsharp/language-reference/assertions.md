---
title: Assertionen (F#)
description: Erfahren Sie, wie den Ausdruck "assert" als eine Debugfunktion für das Testen von Ausdrücken in der Programmiersprache f# verwendet.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 195b4a34977a63d92559003b5cd0bb89490a1e7a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="assertions"></a><span data-ttu-id="79955-103">Assertionen</span><span class="sxs-lookup"><span data-stu-id="79955-103">Assertions</span></span>

<span data-ttu-id="79955-104">Die `assert` Ausdruck ist eine Debugfunktion, die Sie verwenden können, um einen Ausdruck zu testen.</span><span class="sxs-lookup"><span data-stu-id="79955-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="79955-105">Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.</span><span class="sxs-lookup"><span data-stu-id="79955-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="79955-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="79955-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="79955-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="79955-107">Remarks</span></span>

<span data-ttu-id="79955-108">Die `assert` Ausdruck weist den Typ `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="79955-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="79955-109">In der vorherigen Syntax *Bedingung* stellt einen booleschen Ausdruck, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="79955-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="79955-110">Wenn der ausgewertete Ausdruck `true`, Ausführung wird fortgeführt, hat keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="79955-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="79955-111">Ergibt die Auswertung `false`, wird ein Systemfehlerdialogfeld generiert.</span><span class="sxs-lookup"><span data-stu-id="79955-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="79955-112">Das Dialogfeld "Fehler" hat einer Beschriftung, die die Zeichenfolge enthält **"Assertionsfehler"**.</span><span class="sxs-lookup"><span data-stu-id="79955-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="79955-113">Das Dialogfeld enthält eine stapelüberwachung, die angibt, in der Assertionsfehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="79955-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="79955-114">Assertionsüberprüfung ist nur aktiviert, wenn Sie im Debugmodus kompiliert; d. h., wenn die Konstante `DEBUG` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="79955-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="79955-115">Im Projektsystem wird standardmäßig die `DEBUG` Konstante ist, aber nicht in der Releasekonfiguration in der Debugkonfiguration automatisch definiert.</span><span class="sxs-lookup"><span data-stu-id="79955-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="79955-116">Der Assertionsfehler kann nicht mit der f#-Ausnahmebehandlung abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="79955-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="79955-117">Die `assert` Funktion löst in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="79955-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="79955-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79955-118">Example</span></span>

<span data-ttu-id="79955-119">Das folgende Codebeispiel veranschaulicht die Verwendung von der `assert` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="79955-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a><span data-ttu-id="79955-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79955-120">See Also</span></span>

[<span data-ttu-id="79955-121">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="79955-121">F# Language Reference</span></span>](index.md)
