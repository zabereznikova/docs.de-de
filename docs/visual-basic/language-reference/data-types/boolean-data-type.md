---
title: Boolean-Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.FALSE
- vb.TRUE
- vb.Boolean
helpviewer_keywords:
- Boolean data type
- Boolean values [Visual Basic], False keyword
- False keyword [Visual Basic]
- True keyword [Visual Basic]
- Boolean values [Visual Basic], True keyword
ms.assetid: 4858e630-4813-4216-a55e-f4d0feb884e4
ms.openlocfilehash: 7b64302d801a08f976de0ec969983c821f7a8471
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841217"
---
# <a name="boolean-data-type-visual-basic"></a><span data-ttu-id="0041f-102">Boolean-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0041f-102">Boolean Data Type (Visual Basic)</span></span>
<span data-ttu-id="0041f-103">Enthält Werte, die nur können `True` oder `False`.</span><span class="sxs-lookup"><span data-stu-id="0041f-103">Holds values that can be only `True` or `False`.</span></span> <span data-ttu-id="0041f-104">Die Schlüsselwörter `True` und `False` entsprechen, die beiden Status `Boolean` Variablen.</span><span class="sxs-lookup"><span data-stu-id="0041f-104">The keywords `True` and `False` correspond to the two states of `Boolean` variables.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0041f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0041f-105">Remarks</span></span>  
 <span data-ttu-id="0041f-106">Verwenden der [Boolean-Datentyp (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) enthält zwei-Status-Werte wie wahr/falsch, Ja/Nein, oder ein/aus.</span><span class="sxs-lookup"><span data-stu-id="0041f-106">Use the [Boolean Data Type (Visual Basic)](../../../visual-basic/language-reference/data-types/boolean-data-type.md) to contain two-state values such as true/false, yes/no, or on/off.</span></span>  
  
 <span data-ttu-id="0041f-107">Der Standardwert von `Boolean` ist `False`.</span><span class="sxs-lookup"><span data-stu-id="0041f-107">The default value of `Boolean` is `False`.</span></span>  
  
 <span data-ttu-id="0041f-108">`Boolean` Werte werden nicht als Zahlen gespeichert, und die gespeicherten Werte sind nicht für das Zahlen entsprechen soll.</span><span class="sxs-lookup"><span data-stu-id="0041f-108">`Boolean` values are not stored as numbers, and the stored values are not intended to be equivalent to numbers.</span></span> <span data-ttu-id="0041f-109">Schreiben Sie Code, der auf den entsprechenden numerischen Werten für basiert `True` und `False`.</span><span class="sxs-lookup"><span data-stu-id="0041f-109">You should never write code that relies on equivalent numeric values for `True` and `False`.</span></span> <span data-ttu-id="0041f-110">Wann immer möglich, beschränken Sie die Verwendung von `Boolean` Variablen, um die logischen Werte, die für die sie entworfen werden.</span><span class="sxs-lookup"><span data-stu-id="0041f-110">Whenever possible, you should restrict usage of `Boolean` variables to the logical values for which they are designed.</span></span>  
  
## <a name="type-conversions"></a><span data-ttu-id="0041f-111">Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="0041f-111">Type Conversions</span></span>  
 <span data-ttu-id="0041f-112">Wenn konvertiert Visual Basic numerischen Typ Datenwerte `Boolean`, wird 0 `False` und alle anderen Werte werden `True`.</span><span class="sxs-lookup"><span data-stu-id="0041f-112">When Visual Basic converts numeric data type values to `Boolean`, 0 becomes `False` and all other values become `True`.</span></span> <span data-ttu-id="0041f-113">Wenn Visual Basic konvertiert `Boolean` Werten in numerische Typen `False` ist 0 und `True` wird – 1.</span><span class="sxs-lookup"><span data-stu-id="0041f-113">When Visual Basic converts `Boolean` values to numeric types, `False` becomes 0 and `True` becomes -1.</span></span>  
  
 <span data-ttu-id="0041f-114">Beim Konvertieren zwischen `Boolean` Werte und numerische Datentypen und Bedenken Sie, dass die .NET Framework-Konvertierungsmethoden nicht immer die gleichen Ergebnisse wie die Schlüsselwörter der Visual Basic-Konvertierung erzeugen.</span><span class="sxs-lookup"><span data-stu-id="0041f-114">When you convert between `Boolean` values and numeric data types, keep in mind that the .NET Framework conversion methods do not always produce the same results as the Visual Basic conversion keywords.</span></span> <span data-ttu-id="0041f-115">Dies ist, da die Visual Basic-Konvertierung Verhalten kompatibel mit früheren Versionen werden beibehalten.</span><span class="sxs-lookup"><span data-stu-id="0041f-115">This is because the Visual Basic conversion retains behavior compatible with previous versions.</span></span> <span data-ttu-id="0041f-116">Weitere Informationen finden Sie unter "Boolescher Typ ist nicht präzise, den numerischen Typ konvertieren" in [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span><span class="sxs-lookup"><span data-stu-id="0041f-116">For more information, see "Boolean Type Does Not Convert to Numeric Type Accurately" in [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="0041f-117">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="0041f-117">Programming Tips</span></span>  
  
-   <span data-ttu-id="0041f-118">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="0041f-118">**Negative Numbers.**</span></span> <span data-ttu-id="0041f-119">`Boolean` ist kein numerischer Typ und einen negativen Wert nicht darstellen kann.</span><span class="sxs-lookup"><span data-stu-id="0041f-119">`Boolean` is not a numeric type and cannot represent a negative value.</span></span> <span data-ttu-id="0041f-120">In jedem Fall sollten Sie nicht verwenden `Boolean` für numerische Werte.</span><span class="sxs-lookup"><span data-stu-id="0041f-120">In any case, you should not use `Boolean` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="0041f-121">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="0041f-121">**Type Characters.**</span></span> <span data-ttu-id="0041f-122">`Boolean` hat kein literal-Typzeichen oder Bezeichner-Typzeichen.</span><span class="sxs-lookup"><span data-stu-id="0041f-122">`Boolean` has no literal type character or identifier type character.</span></span>  
  
-   <span data-ttu-id="0041f-123">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="0041f-123">**Framework Type.**</span></span> <span data-ttu-id="0041f-124">Der entsprechende Typ in .NET Framework ist die <xref:System.Boolean?displayProperty=nameWithType>-Struktur.</span><span class="sxs-lookup"><span data-stu-id="0041f-124">The corresponding type in the .NET Framework is the <xref:System.Boolean?displayProperty=nameWithType> structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0041f-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0041f-125">Example</span></span>  
 <span data-ttu-id="0041f-126">Im folgenden Beispiel `runningVB` ist eine `Boolean` Variable, die eine einfache Ja/Nein-Einstellung speichert.</span><span class="sxs-lookup"><span data-stu-id="0041f-126">In the following example, `runningVB` is a `Boolean` variable, which stores a simple yes/no setting.</span></span>  
  
```  
Dim runningVB As Boolean  
' Check to see if program is running on Visual Basic engine.  
If scriptEngine = "VB" Then  
    runningVB = True  
End If  
```  
  
## <a name="see-also"></a><span data-ttu-id="0041f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0041f-127">See also</span></span>

- <xref:System.Boolean?displayProperty=nameWithType>
- [<span data-ttu-id="0041f-128">Datentypen</span><span class="sxs-lookup"><span data-stu-id="0041f-128">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="0041f-129">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="0041f-129">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="0041f-130">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="0041f-130">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="0041f-131">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="0041f-131">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [<span data-ttu-id="0041f-132">Problembehandlung bei Datentypen</span><span class="sxs-lookup"><span data-stu-id="0041f-132">Troubleshooting Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [<span data-ttu-id="0041f-133">CType-Funktion</span><span class="sxs-lookup"><span data-stu-id="0041f-133">CType Function</span></span>](../../../visual-basic/language-reference/functions/ctype-function.md)
