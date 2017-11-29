---
title: Boolesche Operatoren (F#)
description: "Erfahren Sie, bis die booleschen Operatoren, die in der Programmiersprache f# verfügbar sind."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: f79370b8-4bc2-4704-b514-d392c80942bd
ms.openlocfilehash: 63588f2e371bf2c0f15de0b8a26a46be82f832c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="boolean-operators"></a><span data-ttu-id="b1351-104">Boolesche Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1351-104">Boolean Operators</span></span>

<span data-ttu-id="b1351-105">Dieses Thema beschreibt die Unterstützung für boolesche Operatoren in der Programmiersprache f#.</span><span class="sxs-lookup"><span data-stu-id="b1351-105">This topic describes the support for Boolean operators in the F# language.</span></span>


## <a name="summary-of-boolean-operators"></a><span data-ttu-id="b1351-106">Zusammenfassung der booleschen Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1351-106">Summary of Boolean Operators</span></span>
<span data-ttu-id="b1351-107">In der folgenden Tabelle zusammengefasst, die booleschen Operatoren, die in der Programmiersprache f# verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b1351-107">The following table summarizes the Boolean operators that are available in the F# language.</span></span> <span data-ttu-id="b1351-108">Der einzige von diesen Operatoren unterstützte Typ ist der `bool` Typ.</span><span class="sxs-lookup"><span data-stu-id="b1351-108">The only type supported by these operators is the `bool` type.</span></span>

|<span data-ttu-id="b1351-109">Operator</span><span class="sxs-lookup"><span data-stu-id="b1351-109">Operator</span></span>|<span data-ttu-id="b1351-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b1351-110">Description</span></span>|
|--------|-----------|
|`not`|<span data-ttu-id="b1351-111">Boolesche negation</span><span class="sxs-lookup"><span data-stu-id="b1351-111">Boolean negation</span></span>|
|<code>&#124;&#124;</code>|<span data-ttu-id="b1351-112">Boolesche OR</span><span class="sxs-lookup"><span data-stu-id="b1351-112">Boolean OR</span></span>|
|`&&`|<span data-ttu-id="b1351-113">Boolesche AND</span><span class="sxs-lookup"><span data-stu-id="b1351-113">Boolean AND</span></span>|

<span data-ttu-id="b1351-114">Führen Sie die boolesche AND und OR-Operatoren *kurzschlussauswertung*, d. h. sie den Ausdruck auf der rechten Seite des Operators auswerten, nur bei Bedarf das Gesamtergebnis des Ausdrucks bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b1351-114">The Boolean AND and OR operators perform *short-circuit evaluation*, that is, they evaluate the expression on the right of the operator only when it is necessary to determine the overall result of the expression.</span></span> <span data-ttu-id="b1351-115">Der zweite Ausdruck, der die `&&` Operator nur ausgewertet, wenn der erste Ausdruck ergibt `true`; der zweite Ausdruck des der `||` Operator nur ausgewertet, wenn der erste Ausdruck ergibt `false`.</span><span class="sxs-lookup"><span data-stu-id="b1351-115">The second expression of the `&&` operator is evaluated only if the first expression evaluates to `true`; the second expression of the `||` operator is evaluated only if the first expression evaluates to `false`.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1351-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1351-116">See Also</span></span>
[<span data-ttu-id="b1351-117">Bitweise Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1351-117">Bitwise Operators</span></span>](bitwise-operators.md)

[<span data-ttu-id="b1351-118">Arithmetische Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1351-118">Arithmetic Operators</span></span>](arithmetic-operators.md)

[<span data-ttu-id="b1351-119">Symbol- und Operatorenreferenz</span><span class="sxs-lookup"><span data-stu-id="b1351-119">Symbol and Operator Reference</span></span>](index.md)
