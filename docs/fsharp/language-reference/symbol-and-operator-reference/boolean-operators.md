---
title: Boolesche Operatoren (F#)
description: Erfahren Sie, bis die booleschen Operatoren, die in der Programmiersprache F# verfügbar sind.
ms.date: 05/16/2016
ms.openlocfilehash: faa181090efa7c4064a30b42d83afa4888e98b82
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "45638479"
---
# <a name="boolean-operators"></a><span data-ttu-id="3fca6-103">Boolesche Operatoren</span><span class="sxs-lookup"><span data-stu-id="3fca6-103">Boolean Operators</span></span>

<span data-ttu-id="3fca6-104">Dieses Thema beschreibt die Unterstützung für boolesche Operatoren in der Sprache F#.</span><span class="sxs-lookup"><span data-stu-id="3fca6-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="3fca6-105">Zusammenfassung der booleschen Operatoren</span><span class="sxs-lookup"><span data-stu-id="3fca6-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="3fca6-106">Die folgende Tabelle enthält die booleschen Operatoren, die in F# verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3fca6-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="3fca6-107">Ist der einzige Typ, der von diesen unterstützt die `bool` Typ.</span><span class="sxs-lookup"><span data-stu-id="3fca6-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="3fca6-108">Operator</span><span class="sxs-lookup"><span data-stu-id="3fca6-108">Operator</span></span>|<span data-ttu-id="3fca6-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3fca6-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="3fca6-110">Boolesche negation</span><span class="sxs-lookup"><span data-stu-id="3fca6-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="3fca6-111">Boolesche OR</span><span class="sxs-lookup"><span data-stu-id="3fca6-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="3fca6-112">Boolesche AND</span><span class="sxs-lookup"><span data-stu-id="3fca6-112">Boolean AND</span></span>|

<span data-ttu-id="3fca6-113">Führen Sie die boolesche AND und OR-Operatoren *kurzschlussauswertung*, d. h. sie den Ausdruck auf der rechten Seite des Operators auszuwerten, nur, wenn es um das Gesamtergebnis des Ausdrucks zu bestimmen, die erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3fca6-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="3fca6-114">Der zweite Ausdruck, der die `&&` Operator wird nur ausgewertet, wenn der erste Ausdruck ergibt `true`; der zweite Ausdruck, der die `||` Operator wird nur ausgewertet, wenn der erste Ausdruck ergibt `false`.</span><span class="sxs-lookup"><span data-stu-id="3fca6-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3fca6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fca6-115">See also</span></span>

- [<span data-ttu-id="3fca6-116">Bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="3fca6-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="3fca6-117">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="3fca6-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="3fca6-118">Symbol- und Operatorenreferenz</span><span class="sxs-lookup"><span data-stu-id="3fca6-118">Symbol and Operator Reference</span></span>](index.md)
