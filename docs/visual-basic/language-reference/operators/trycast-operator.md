---
title: TryCast-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords: TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6be11b49eb3b9d98e3bf147e9b1026d4ffc860c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="trycast-operator-visual-basic"></a><span data-ttu-id="bf3d5-102">TryCast-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bf3d5-102">TryCast Operator (Visual Basic)</span></span>
<span data-ttu-id="bf3d5-103">Führt einen Typkonvertierungsvorgang, der keine Ausnahme auslöst.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-103">Introduces a type conversion operation that does not throw an exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf3d5-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf3d5-104">Remarks</span></span>  
 <span data-ttu-id="bf3d5-105">Wenn eine versuchte Konvertierung ein Fehler auftritt, `CType` und `DirectCast` sowohl Auslösen einer <xref:System.InvalidCastException> Fehler.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-105">If an attempted conversion fails, `CType` and `DirectCast` both throw an <xref:System.InvalidCastException> error.</span></span> <span data-ttu-id="bf3d5-106">Dies kann die Leistung der Anwendung beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-106">This can adversely affect the performance of your application.</span></span> <span data-ttu-id="bf3d5-107">`TryCast`Gibt [nichts](../../../visual-basic/language-reference/nothing.md), sodass anstatt auf eine mögliche Ausnahme behandeln Sie nur das zurückgegebene Ergebnis mit testen müssen `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-107">`TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md), so that instead of having to handle a possible exception, you need only test the returned result against `Nothing`.</span></span>  
  
 <span data-ttu-id="bf3d5-108">Verwenden Sie die `TryCast` Schlüsselwort die gleiche Weise, die Sie verwenden die [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) und [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-108">You use the `TryCast` keyword the same way you use the [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) and the [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) keyword.</span></span> <span data-ttu-id="bf3d5-109">Sie geben einen Ausdruck als erstes Argument und einen Typ als zweites Argument umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-109">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="bf3d5-110">`TryCast`kann nur für Verweistypen, z. B. Klassen und Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-110">`TryCast` operates only on reference types, such as classes and interfaces.</span></span> <span data-ttu-id="bf3d5-111">Voraussetzung hierfür ist eine Beziehung vererbungs- oder implementierungsbeziehung zwischen den beiden Typen.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-111">It requires an inheritance or implementation relationship between the two types.</span></span> <span data-ttu-id="bf3d5-112">Dies bedeutet, dass ein Typ den anderen implementieren oder davon erben muss.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-112">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="bf3d5-113">Fehler und Ausfälle</span><span class="sxs-lookup"><span data-stu-id="bf3d5-113">Errors and Failures</span></span>  
 <span data-ttu-id="bf3d5-114">`TryCast`generiert einen Compilerfehler, wenn er erkennt, dass keine Vererbung oder Implementierung Beziehung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-114">`TryCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="bf3d5-115">Der Mangel an einen Compilerfehler gewährleistet jedoch keine erfolgreiche Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-115">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="bf3d5-116">Wenn die gewünschte Konvertierung einschränkend ist, kann sie zur Laufzeit fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-116">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="bf3d5-117">In diesem Fall `TryCast` gibt [nichts](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="bf3d5-117">If this happens, `TryCast` returns [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="bf3d5-118">Konvertierungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bf3d5-118">Conversion Keywords</span></span>  
 <span data-ttu-id="bf3d5-119">Ein Vergleich der Schlüsselwörter für die typkonvertierung lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-119">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="bf3d5-120">Stichwort</span><span class="sxs-lookup"><span data-stu-id="bf3d5-120">Keyword</span></span>|<span data-ttu-id="bf3d5-121">Datentypen</span><span class="sxs-lookup"><span data-stu-id="bf3d5-121">Data types</span></span>|<span data-ttu-id="bf3d5-122">Arguments-Beziehung</span><span class="sxs-lookup"><span data-stu-id="bf3d5-122">Argument relationship</span></span>|<span data-ttu-id="bf3d5-123">Laufzeitfehler</span><span class="sxs-lookup"><span data-stu-id="bf3d5-123">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="bf3d5-124">CType-Funktion</span><span class="sxs-lookup"><span data-stu-id="bf3d5-124">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)|<span data-ttu-id="bf3d5-125">Alle Datentypen</span><span class="sxs-lookup"><span data-stu-id="bf3d5-125">Any data types</span></span>|<span data-ttu-id="bf3d5-126">Zwischen den beiden Datentypen muss eine erweiternde oder einschränkende Konvertierung definiert sein</span><span class="sxs-lookup"><span data-stu-id="bf3d5-126">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="bf3d5-127">Löst aus<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="bf3d5-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="bf3d5-128">DirectCast-Operator</span><span class="sxs-lookup"><span data-stu-id="bf3d5-128">DirectCast Operator</span></span>](../../../visual-basic/language-reference/operators/directcast-operator.md)|<span data-ttu-id="bf3d5-129">Alle Datentypen</span><span class="sxs-lookup"><span data-stu-id="bf3d5-129">Any data types</span></span>|<span data-ttu-id="bf3d5-130">Einen müssen anderen Typ zu implementieren oder davon erben</span><span class="sxs-lookup"><span data-stu-id="bf3d5-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="bf3d5-131">Löst aus<xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="bf3d5-131">Throws <xref:System.InvalidCastException></span></span>|  
|`TryCast`|<span data-ttu-id="bf3d5-132">Nur Verweistypen</span><span class="sxs-lookup"><span data-stu-id="bf3d5-132">Reference types only</span></span>|<span data-ttu-id="bf3d5-133">Einen müssen anderen Typ zu implementieren oder davon erben</span><span class="sxs-lookup"><span data-stu-id="bf3d5-133">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="bf3d5-134">Gibt [nichts](../../../visual-basic/language-reference/nothing.md)</span><span class="sxs-lookup"><span data-stu-id="bf3d5-134">Returns [Nothing](../../../visual-basic/language-reference/nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bf3d5-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf3d5-135">Example</span></span>  
 <span data-ttu-id="bf3d5-136">Das folgende Beispiel veranschaulicht die Verwendung von `TryCast`.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-136">The following example shows how to use `TryCast`.</span></span>  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="bf3d5-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf3d5-137">See Also</span></span>  
 [<span data-ttu-id="bf3d5-138">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="bf3d5-138">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="bf3d5-139">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="bf3d5-139">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
