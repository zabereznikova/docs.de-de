---
title: DirectCast-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b81abea364e328b831ee98c3b847161c3f7dd3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="2b182-102">DirectCast-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b182-102">DirectCast Operator (Visual Basic)</span></span>
<span data-ttu-id="2b182-103">Führt einen Typkonvertierungsvorgang basierend auf vererbungs- oder implementierungseinschränkung an.</span><span class="sxs-lookup"><span data-stu-id="2b182-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b182-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b182-104">Remarks</span></span>  
 <span data-ttu-id="2b182-105">`DirectCast`verwendet nicht das Visual Basic-Laufzeit Hilfsroutinen für die Konvertierung, damit er in einem gewissen bereitstellen kann eine Systemleistung als bessere `CType` beim Konvertieren in und aus Datentyp `Object`.</span><span class="sxs-lookup"><span data-stu-id="2b182-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="2b182-106">Verwenden Sie die `DirectCast` Schlüsselwort ähnlich wie bei Verwendung der [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) und [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="2b182-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md) keyword.</span></span> <span data-ttu-id="2b182-107">Sie geben einen Ausdruck als erstes Argument und einen Typ als zweites Argument umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="2b182-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="2b182-108">`DirectCast`erfordert eine vererbungs- oder implementierungseinschränkung Beziehung zwischen den Datentypen der beiden Argumente.</span><span class="sxs-lookup"><span data-stu-id="2b182-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="2b182-109">Dies bedeutet, dass ein Typ den anderen implementieren oder davon erben muss.</span><span class="sxs-lookup"><span data-stu-id="2b182-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="2b182-110">Fehler und Ausfälle</span><span class="sxs-lookup"><span data-stu-id="2b182-110">Errors and Failures</span></span>  
 <span data-ttu-id="2b182-111">`DirectCast`generiert einen Compilerfehler, wenn er erkennt, dass keine Vererbung oder Implementierung Beziehung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2b182-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="2b182-112">Der Mangel an einen Compilerfehler gewährleistet jedoch keine erfolgreiche Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="2b182-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="2b182-113">Wenn die gewünschte Konvertierung einschränkend ist, kann sie zur Laufzeit fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="2b182-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="2b182-114">In diesem Fall löst die Laufzeit eine <xref:System.InvalidCastException> Fehler.</span><span class="sxs-lookup"><span data-stu-id="2b182-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="2b182-115">Konvertierungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="2b182-115">Conversion Keywords</span></span>  
 <span data-ttu-id="2b182-116">Ein Vergleich der Schlüsselwörter für die typkonvertierung lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="2b182-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="2b182-117">Stichwort</span><span class="sxs-lookup"><span data-stu-id="2b182-117">Keyword</span></span>|<span data-ttu-id="2b182-118">Datentypen</span><span class="sxs-lookup"><span data-stu-id="2b182-118">Data types</span></span>|<span data-ttu-id="2b182-119">Arguments-Beziehung</span><span class="sxs-lookup"><span data-stu-id="2b182-119">Argument relationship</span></span>|<span data-ttu-id="2b182-120">Laufzeitfehler</span><span class="sxs-lookup"><span data-stu-id="2b182-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="2b182-121">CType-Funktion</span><span class="sxs-lookup"><span data-stu-id="2b182-121">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="2b182-122">Alle Datentypen</span><span class="sxs-lookup"><span data-stu-id="2b182-122">Any data types</span></span>|<span data-ttu-id="2b182-123">Zwischen den beiden Datentypen muss eine erweiternde oder einschränkende Konvertierung definiert sein</span><span class="sxs-lookup"><span data-stu-id="2b182-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="2b182-124">Löst aus<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="2b182-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="2b182-125">Alle Datentypen</span><span class="sxs-lookup"><span data-stu-id="2b182-125">Any data types</span></span>|<span data-ttu-id="2b182-126">Einen müssen anderen Typ zu implementieren oder davon erben</span><span class="sxs-lookup"><span data-stu-id="2b182-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="2b182-127">Löst aus<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="2b182-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="2b182-128">TryCast-Operator</span><span class="sxs-lookup"><span data-stu-id="2b182-128">TryCast Operator</span></span>](../../../visual-basic/language-reference/operators/trycast-operator.md)|<span data-ttu-id="2b182-129">Nur Verweistypen</span><span class="sxs-lookup"><span data-stu-id="2b182-129">Reference types only</span></span>|<span data-ttu-id="2b182-130">Einen müssen anderen Typ zu implementieren oder davon erben</span><span class="sxs-lookup"><span data-stu-id="2b182-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="2b182-131">Gibt [nichts](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="2b182-131">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2b182-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b182-132">Example</span></span>  
 <span data-ttu-id="2b182-133">Das folgende Beispiel zeigt zwei Verwendungen von `DirectCast`, eines, die zur Laufzeit und eine, die nicht erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2b182-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](../../../visual-basic/language-reference/codesnippet/VisualBasic/directcast-operator_1.vb)]  
  
 <span data-ttu-id="2b182-134">Im vorherigen Beispiel der Laufzeittyp des `q` ist `Double`.</span><span class="sxs-lookup"><span data-stu-id="2b182-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="2b182-135">`CType`ist erfolgreich, da `Double` konvertiert werden kann, um `Integer`.</span><span class="sxs-lookup"><span data-stu-id="2b182-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="2b182-136">Allerdings die erste `DirectCast` zur Laufzeit ein Fehler auftritt, da der Laufzeittyp des `Double` verfügt über keine vererbungsbeziehung mit `Integer`, auch wenn eine Konvertierung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2b182-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="2b182-137">Die zweite `DirectCast` ist erfolgreich, da er vom Typ konvertiert <xref:System.Windows.Forms.Form> Eingabe <xref:System.Windows.Forms.Control>, von dem <xref:System.Windows.Forms.Form> erbt.</span><span class="sxs-lookup"><span data-stu-id="2b182-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b182-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b182-138">See Also</span></span>  
 <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="2b182-139">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="2b182-139">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="2b182-140">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="2b182-140">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
