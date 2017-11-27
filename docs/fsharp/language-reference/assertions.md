---
title: Assertionen (F#)
description: "Erfahren Sie, wie den Ausdruck \"assert\" als eine Debugfunktion für das Testen von Ausdrücken in der Programmiersprache f# verwendet."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 2badaad7-f086-47e7-99c1-91f35117da83
ms.openlocfilehash: 56891769602afaa765ebfe7e7822a179c7a22968
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="assertions"></a><span data-ttu-id="b06fc-104">Assertionen</span><span class="sxs-lookup"><span data-stu-id="b06fc-104">Assertions</span></span>

<span data-ttu-id="b06fc-105">Die `assert` Ausdruck ist eine Debugfunktion, die Sie verwenden können, um einen Ausdruck zu testen.</span><span class="sxs-lookup"><span data-stu-id="b06fc-105">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="b06fc-106">Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.</span><span class="sxs-lookup"><span data-stu-id="b06fc-106">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="b06fc-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b06fc-107">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="b06fc-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b06fc-108">Remarks</span></span>

<span data-ttu-id="b06fc-109">Die `assert` Ausdruck weist den Typ `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="b06fc-109">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="b06fc-110">In der vorherigen Syntax *Bedingung* stellt einen booleschen Ausdruck, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="b06fc-110">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="b06fc-111">Wenn der ausgewertete Ausdruck `true`, Ausführung wird fortgeführt, hat keine Auswirkung.</span><span class="sxs-lookup"><span data-stu-id="b06fc-111">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="b06fc-112">Ergibt die Auswertung `false`, wird ein Systemfehlerdialogfeld generiert.</span><span class="sxs-lookup"><span data-stu-id="b06fc-112">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="b06fc-113">Das Dialogfeld "Fehler" hat einer Beschriftung, die die Zeichenfolge enthält **"Assertionsfehler"**.</span><span class="sxs-lookup"><span data-stu-id="b06fc-113">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="b06fc-114">Das Dialogfeld enthält eine stapelüberwachung, die angibt, in der Assertionsfehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="b06fc-114">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="b06fc-115">Assertionsüberprüfung ist nur aktiviert, wenn Sie im Debugmodus kompiliert; d. h., wenn die Konstante `DEBUG` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="b06fc-115">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="b06fc-116">Im Projektsystem wird standardmäßig die `DEBUG` Konstante ist, aber nicht in der Releasekonfiguration in der Debugkonfiguration automatisch definiert.</span><span class="sxs-lookup"><span data-stu-id="b06fc-116">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="b06fc-117">Der Assertionsfehler kann nicht mit der f#-Ausnahmebehandlung abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="b06fc-117">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="b06fc-118">Die `assert` Funktion löst in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b06fc-118">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="b06fc-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b06fc-119">Example</span></span>

<span data-ttu-id="b06fc-120">Das folgende Codebeispiel veranschaulicht die Verwendung von der `assert` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b06fc-120">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]
    
## <a name="see-also"></a><span data-ttu-id="b06fc-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b06fc-121">See Also</span></span>

[<span data-ttu-id="b06fc-122">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="b06fc-122">F# Language Reference</span></span>](index.md)
