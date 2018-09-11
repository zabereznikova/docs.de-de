---
title: Boolesche Operatoren (F#)
description: Erfahren Sie, bis die booleschen Operatoren, die in der Programmiersprache f# verfügbar sind.
ms.date: 05/16/2016
ms.openlocfilehash: faa181090efa7c4064a30b42d83afa4888e98b82
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44272318"
---
# <a name="boolean-operators"></a><span data-ttu-id="e9778-103">Boolesche Operatoren</span><span class="sxs-lookup"><span data-stu-id="e9778-103">Boolean Operators</span></span>

<span data-ttu-id="e9778-104">Dieses Thema beschreibt die Unterstützung für boolesche Operatoren in der Sprache f#.</span><span class="sxs-lookup"><span data-stu-id="e9778-104">This topic describes the support for Boolean operators in the F# language.</span></span>

## <a name="summary-of-boolean-operators"></a><span data-ttu-id="e9778-105">Zusammenfassung der booleschen Operatoren</span><span class="sxs-lookup"><span data-stu-id="e9778-105">Summary of Boolean Operators</span></span>

<span data-ttu-id="e9778-106">Die folgende Tabelle enthält die booleschen Operatoren, die in f# verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="e9778-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="e9778-107">Ist der einzige Typ, der von diesen unterstützt die `bool` Typ.</span><span class="sxs-lookup"><span data-stu-id="e9778-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="e9778-108">Operator</span><span class="sxs-lookup"><span data-stu-id="e9778-108">Operator</span></span>|<span data-ttu-id="e9778-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9778-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="e9778-110">Boolesche negation</span><span class="sxs-lookup"><span data-stu-id="e9778-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="e9778-111">Boolesche OR</span><span class="sxs-lookup"><span data-stu-id="e9778-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="e9778-112">Boolesche AND</span><span class="sxs-lookup"><span data-stu-id="e9778-112">Boolean AND</span></span>|

<span data-ttu-id="e9778-113">Führen Sie die boolesche AND und OR-Operatoren *kurzschlussauswertung*, d. h. sie den Ausdruck auf der rechten Seite des Operators auszuwerten, nur, wenn es um das Gesamtergebnis des Ausdrucks zu bestimmen, die erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e9778-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="e9778-114">Der zweite Ausdruck, der die `&&` Operator wird nur ausgewertet, wenn der erste Ausdruck ergibt `true`; der zweite Ausdruck, der die `||` Operator wird nur ausgewertet, wenn der erste Ausdruck ergibt `false`.</span><span class="sxs-lookup"><span data-stu-id="e9778-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="e9778-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9778-115">See also</span></span>

- [<span data-ttu-id="e9778-116">Bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="e9778-116">Bitwise Operators</span></span>](bitwise-operators.md)
- [<span data-ttu-id="e9778-117">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="e9778-117">Arithmetic Operators</span></span>](arithmetic-operators.md)
- [<span data-ttu-id="e9778-118">Symbol- und Operatorenreferenz</span><span class="sxs-lookup"><span data-stu-id="e9778-118">Symbol and Operator Reference</span></span>](index.md)
