---
title: Assertionen
description: Erfahren Sie, wie Sie den Assert-Ausdruck als Debuggingfunktion zum Testen von F# Ausdrücken in der Programmiersprache verwenden.
ms.date: 10/22/2019
ms.openlocfilehash: 430db20e5ca307ba43a72e678a0424e03b0ac381
ms.sourcegitcommit: 9bd1c09128e012b6e34bdcbdf3576379f58f3137
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2019
ms.locfileid: "72799060"
---
# <a name="assertions"></a><span data-ttu-id="fcded-103">Assertionen</span><span class="sxs-lookup"><span data-stu-id="fcded-103">Assertions</span></span>

<span data-ttu-id="fcded-104">Der `assert` Ausdruck ist ein Debugfeature, das Sie zum Testen eines Ausdrucks verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fcded-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="fcded-105">Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.</span><span class="sxs-lookup"><span data-stu-id="fcded-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="fcded-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fcded-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="fcded-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcded-107">Remarks</span></span>

<span data-ttu-id="fcded-108">Der `assert` Ausdruck hat den Typ `bool -> unit`.</span><span class="sxs-lookup"><span data-stu-id="fcded-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="fcded-109">Die `assert`-Funktion wird in <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="fcded-109">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fcded-110">Dies bedeutet, dass das Verhalten identisch mit dem direkten Aufrufen von <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> ist.</span><span class="sxs-lookup"><span data-stu-id="fcded-110">This means its behavior is identical to having called <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> directly.</span></span>

<span data-ttu-id="fcded-111">Die Überprüfung der Überprüfung ist nur aktiviert, wenn Sie im Debugmodus kompilieren. Das heißt, wenn die Konstante `DEBUG` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fcded-111">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="fcded-112">Im Projekt System ist die `DEBUG` Konstante standardmäßig in der Debugkonfiguration, aber nicht in der Releasekonfiguration definiert.</span><span class="sxs-lookup"><span data-stu-id="fcded-112">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="fcded-113">Der Fehler bei der Fehlerbehebung kann nicht mithilfe F# der Ausnahmebehandlung abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="fcded-113">The assertion failure error cannot be caught by using F# exception handling.</span></span>

## <a name="example"></a><span data-ttu-id="fcded-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fcded-114">Example</span></span>

<span data-ttu-id="fcded-115">Im folgenden Codebeispiel wird die Verwendung des `assert` Ausdrucks veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="fcded-115">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="fcded-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcded-116">See also</span></span>

- [<span data-ttu-id="fcded-117">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="fcded-117">F# Language Reference</span></span>](index.md)
