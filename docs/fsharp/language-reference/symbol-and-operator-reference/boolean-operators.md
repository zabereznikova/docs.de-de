---
title: Boolesche Operatoren (F#)
description: Erfahren Sie, bis die booleschen Operatoren, die in der Programmiersprache f# verfügbar sind.
ms.date: 05/16/2016
ms.openlocfilehash: f8516ceb531907400f98dc4226d2985d3119e9e9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563427"
---
# <a name="boolean-operators"></a><span data-ttu-id="b0c02-103">Boolesche Operatoren</span><span class="sxs-lookup"><span data-stu-id="b0c02-103">Boolean Operators</span></span>

<span data-ttu-id="b0c02-104">Dieses Thema beschreibt die Unterstützung für boolesche Operatoren in der Programmiersprache f#.</span><span class="sxs-lookup"><span data-stu-id="b0c02-104">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="b0c02-105">Zusammenfassung der booleschen Operatoren</span><span class="sxs-lookup"><span data-stu-id="b0c02-105">Summary of Boolean Operators</span></span>
<span data-ttu-id="b0c02-106">In der folgenden Tabelle zusammengefasst, die booleschen Operatoren, die in der Programmiersprache f# verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b0c02-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="b0c02-107">Der einzige von diesen Operatoren unterstützte Typ ist der `bool` Typ.</span><span class="sxs-lookup"><span data-stu-id="b0c02-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="b0c02-108">Operator</span><span class="sxs-lookup"><span data-stu-id="b0c02-108">Operator</span></span>|<span data-ttu-id="b0c02-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0c02-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="b0c02-110">Boolesche negation</span><span class="sxs-lookup"><span data-stu-id="b0c02-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="b0c02-111">Boolesche OR</span><span class="sxs-lookup"><span data-stu-id="b0c02-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="b0c02-112">Boolesche AND</span><span class="sxs-lookup"><span data-stu-id="b0c02-112">Boolean AND</span></span>|

<span data-ttu-id="b0c02-113">Führen Sie die boolesche AND und OR-Operatoren *kurzschlussauswertung*, d. h. sie den Ausdruck auf der rechten Seite des Operators auswerten, nur bei Bedarf das Gesamtergebnis des Ausdrucks bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b0c02-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="b0c02-114">Der zweite Ausdruck, der die `&&` Operator nur ausgewertet, wenn der erste Ausdruck ergibt `true`; der zweite Ausdruck des der `||` Operator nur ausgewertet, wenn der erste Ausdruck ergibt `false`.</span><span class="sxs-lookup"><span data-stu-id="b0c02-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b0c02-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0c02-115">See Also</span></span>
[<span data-ttu-id="b0c02-116">Bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="b0c02-116">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="b0c02-117">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="b0c02-117">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="b0c02-118">Symbol- und Operatorenreferenz</span><span class="sxs-lookup"><span data-stu-id="b0c02-118">Symbol and Operator Reference</span></span>](index.md)
