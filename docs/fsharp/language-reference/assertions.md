---
title: Assertionen
description: Erfahren Sie, wie Sie mit der Ausdruck "assert" als eine Debugfunktion zum Testen von Ausdrücken in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: b8b7e9662143b432d650f87515d4af31cced4149
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630024"
---
# <a name="assertions"></a><span data-ttu-id="86316-103">Assertionen</span><span class="sxs-lookup"><span data-stu-id="86316-103">Assertions</span></span>

<span data-ttu-id="86316-104">Der `assert` Ausdruck ist ein Debugfeature, das Sie zum Testen eines Ausdrucks verwenden können.</span><span class="sxs-lookup"><span data-stu-id="86316-104">The `assert` expression is a debugging feature that you can use to test an expression.</span></span> <span data-ttu-id="86316-105">Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.</span><span class="sxs-lookup"><span data-stu-id="86316-105">Upon failure in Debug mode, an assertion generates a system error dialog box.</span></span>

## <a name="syntax"></a><span data-ttu-id="86316-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="86316-106">Syntax</span></span>

```fsharp
assert condition
```

## <a name="remarks"></a><span data-ttu-id="86316-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86316-107">Remarks</span></span>

<span data-ttu-id="86316-108">Der `assert` Ausdruck weist den `bool -> unit`Typ auf.</span><span class="sxs-lookup"><span data-stu-id="86316-108">The `assert` expression has type `bool -> unit`.</span></span>

<span data-ttu-id="86316-109">In der vorherigen Syntax stellt *Condition* einen booleschen Ausdruck dar, der getestet werden soll.</span><span class="sxs-lookup"><span data-stu-id="86316-109">In the previous syntax, *condition* represents a Boolean expression that is to be tested.</span></span> <span data-ttu-id="86316-110">Wenn der Ausdruck als `true`ausgewertet wird, wird die Ausführung nicht beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="86316-110">If the expression evaluates to `true`, execution continues unaffected.</span></span> <span data-ttu-id="86316-111">Wenn ausgewertet `false`wird, wird ein Systemfehler Dialogfeld generiert.</span><span class="sxs-lookup"><span data-stu-id="86316-111">If it evaluates to `false`, a system error dialog box is generated.</span></span> <span data-ttu-id="86316-112">Das Fehler Dialogfeld enthält eine Beschriftung, die die **Zeichen folgen**-Assertionen enthält.</span><span class="sxs-lookup"><span data-stu-id="86316-112">The error dialog box has a caption that contains the string **Assertion Failed**.</span></span> <span data-ttu-id="86316-113">Das Dialogfeld enthält eine Stapel Überwachung, die angibt, wo der Fehler bei der Übersetzung aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="86316-113">The dialog box contains a stack trace that indicates where the assertion failure occurred.</span></span>

<span data-ttu-id="86316-114">Die Überprüfung der Überprüfung ist nur aktiviert, wenn Sie im Debugmodus kompilieren. Das heißt, wenn die Konstante `DEBUG` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="86316-114">Assertion checking is enabled only when you compile in Debug mode; that is, if the constant `DEBUG` is defined.</span></span> <span data-ttu-id="86316-115">Im Projekt System ist die `DEBUG` Konstante standardmäßig in der Debugkonfiguration definiert, jedoch nicht in der Releasekonfiguration.</span><span class="sxs-lookup"><span data-stu-id="86316-115">In the project system, by default, the `DEBUG` constant is defined in the Debug configuration but not in the Release configuration.</span></span>

<span data-ttu-id="86316-116">Der Fehler bei der Fehlerbehebung kann nicht mithilfe F# der Ausnahmebehandlung abgefangen werden.</span><span class="sxs-lookup"><span data-stu-id="86316-116">The assertion failure error cannot be caught by using F# exception handling.</span></span>

> [!NOTE]
> <span data-ttu-id="86316-117">Die `assert` -Funktion wird <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>in aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="86316-117">The `assert` function resolves to <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.</span></span>

## <a name="example"></a><span data-ttu-id="86316-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="86316-118">Example</span></span>

<span data-ttu-id="86316-119">Im folgenden Codebeispiel wird die Verwendung des `assert` -Ausdrucks veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="86316-119">The following code example illustrates the use of the `assert` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a><span data-ttu-id="86316-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86316-120">See also</span></span>

- [<span data-ttu-id="86316-121">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="86316-121">F# Language Reference</span></span>](index.md)
