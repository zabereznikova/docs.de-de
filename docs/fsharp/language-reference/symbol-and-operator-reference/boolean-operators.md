---
title: Boolesche Operatoren (F#)
description: Erfahren Sie, bis die booleschen Operatoren, die in der Programmiersprache f# verfügbar sind.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 0b11b5133b02b6f507c7886b2fbaebf30abf46cb
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="boolean-operators"></a><span data-ttu-id="a509c-103">Boolesche Operatoren</span><span class="sxs-lookup"><span data-stu-id="a509c-103">Boolean Operators</span></span>

<span data-ttu-id="a509c-104">Dieses Thema beschreibt die Unterstützung für boolesche Operatoren in der Programmiersprache f#.</span><span class="sxs-lookup"><span data-stu-id="a509c-104">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="a509c-105">Zusammenfassung der booleschen Operatoren</span><span class="sxs-lookup"><span data-stu-id="a509c-105">Summary of Boolean Operators</span></span>
<span data-ttu-id="a509c-106">In der folgenden Tabelle zusammengefasst, die booleschen Operatoren, die in der Programmiersprache f# verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a509c-106">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="a509c-107">Der einzige von diesen Operatoren unterstützte Typ ist der `bool` Typ.</span><span class="sxs-lookup"><span data-stu-id="a509c-107">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="a509c-108">Operator</span><span class="sxs-lookup"><span data-stu-id="a509c-108">Operator</span></span>|<span data-ttu-id="a509c-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a509c-109">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="a509c-110">Boolesche negation</span><span class="sxs-lookup"><span data-stu-id="a509c-110">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="a509c-111">Boolesche OR</span><span class="sxs-lookup"><span data-stu-id="a509c-111">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="a509c-112">Boolesche AND</span><span class="sxs-lookup"><span data-stu-id="a509c-112">Boolean AND</span></span>|

<span data-ttu-id="a509c-113">Führen Sie die boolesche AND und OR-Operatoren *kurzschlussauswertung*, d. h. sie den Ausdruck auf der rechten Seite des Operators auswerten, nur bei Bedarf das Gesamtergebnis des Ausdrucks bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a509c-113">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="a509c-114">Der zweite Ausdruck, der die `&&` Operator nur ausgewertet, wenn der erste Ausdruck ergibt `true`; der zweite Ausdruck des der `||` Operator nur ausgewertet, wenn der erste Ausdruck ergibt `false`.</span><span class="sxs-lookup"><span data-stu-id="a509c-114">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a509c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a509c-115">See Also</span></span>
[<span data-ttu-id="a509c-116">Bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="a509c-116">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="a509c-117">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="a509c-117">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="a509c-118">Symbol- und Operatorenreferenz</span><span class="sxs-lookup"><span data-stu-id="a509c-118">Symbol and Operator Reference</span></span>](index.md)
