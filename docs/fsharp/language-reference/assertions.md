---
title: Assertionen (F#)
description: Erfahren Sie, wie Sie mit der Ausdruck "assert" als eine Debugfunktion zum Testen von Ausdrücken in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: 85b1e839bfd19bada48b7f1821d15ddd8fa77754
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "48842475"
---
# <a name="assertions"></a><span data-ttu-id="2110e-103">Assertionen</span><span class="sxs-lookup"><span data-stu-id="2110e-103">Assertions</span></span>

<span data-ttu-id="2110e-104">Die `assert` Ausdruck ist eine Debugfunktion, die Sie verwenden können, um einen Ausdruck zu testen.</span><span class="sxs-lookup"><span data-stu-id="2110e-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="2110e-105">Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.</span><span class="sxs-lookup"><span data-stu-id="2110e-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="2110e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2110e-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="2110e-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2110e-107">Remarks</span></span>

<span data-ttu-id="2110e-108">Die `assert` Ausdruck weist Typ `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="2110e-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="2110e-109">In der vorherigen Syntax *Bedingung* stellt einen booleschen Ausdruck, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2110e-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="2110e-110">Wenn der Ausdruck ergibt `true`, Ausführung wird fortgeführt, nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="2110e-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="2110e-111">Ergibt die Auswertung `false`, wird ein Dialogfeld System Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="2110e-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="2110e-112">Das Dialogfeld "Fehler" hat einer Beschriftung, die die Zeichenfolge enthält **Assertionsfehler**.</span><span class="sxs-lookup"><span data-stu-id="2110e-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="2110e-113">Das Dialogfeld enthält eine stapelüberwachung, die angibt, in der Assertionsfehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="2110e-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="2110e-114">Assertionsüberprüfung ist aktiviert, nur beim Kompilieren im Debugmodus befindet. d.h., wenn die Konstante `DEBUG` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="2110e-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="2110e-115">Im Projektsystem, standardmäßig die `DEBUG` Konstante wird definiert, in der Debug-Konfiguration jedoch nicht in der Releasekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="2110e-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="2110e-116">Der Assertionsfehler kann nicht abgefangen werden, mithilfe von F#-Ausnahmebehandlung.</span><span class="sxs-lookup"><span data-stu-id="2110e-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

>[!NOTE]
<span data-ttu-id="2110e-117">Die `assert` Funktion löst in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2110e-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="2110e-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2110e-118">Example</span></span>

<span data-ttu-id="2110e-119">Das folgende Codebeispiel veranschaulicht die Verwendung von der `assert` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="2110e-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="2110e-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2110e-120">See also</span></span>

- [<span data-ttu-id="2110e-121">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="2110e-121">F# Language Reference</span></span>](index.md)
