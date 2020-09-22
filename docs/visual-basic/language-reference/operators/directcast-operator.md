---
title: DirectCast-Operator
ms.date: 07/20/2015
f1_keywords:
- vb.directCast
- directCast
helpviewer_keywords:
- DirectCast keyword [Visual Basic]
ms.assetid: 63e5a1d0-4d9e-4732-bf8f-e90c0c8784b8
ms.openlocfilehash: 7b070b8eba240440821f7984a9336c2ecaf61706
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867081"
---
# <a name="directcast-operator-visual-basic"></a><span data-ttu-id="c5cc3-102">DirectCast-Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c5cc3-102">DirectCast Operator (Visual Basic)</span></span>

<span data-ttu-id="c5cc3-103">Führt eine Typkonvertierungs Operation auf der Grundlage von Vererbung oder Implementierung ein.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-103">Introduces a type conversion operation based on inheritance or implementation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c5cc3-104">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c5cc3-104">Remarks</span></span>  

 <span data-ttu-id="c5cc3-105">`DirectCast` verwendet nicht die Routinen für die Visual Basic-Lauf Zeit Hilfsprogramme für die Konvertierung, sodass eine etwas bessere Leistung erzielt werden kann als `CType` beim Konvertieren von Datentypen in und aus dem-Datentyp `Object` .</span><span class="sxs-lookup"><span data-stu-id="c5cc3-105">`DirectCast` does not use the Visual Basic run-time helper routines for conversion, so it can provide somewhat better performance than `CType` when converting to and from data type `Object`.</span></span>  
  
 <span data-ttu-id="c5cc3-106">Sie verwenden das `DirectCast` Schlüsselwort ähnlich der Verwendung der [CType-Funktion](../functions/ctype-function.md) und des [TryCast-Operator](trycast-operator.md) Schlüsselworts.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-106">You use the `DirectCast` keyword similar to the way you use the [CType Function](../functions/ctype-function.md) and the [TryCast Operator](trycast-operator.md) keyword.</span></span> <span data-ttu-id="c5cc3-107">Sie geben einen Ausdruck als erstes Argument und einen Typ an, in den es als zweites Argument konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-107">You supply an expression as the first argument and a type to convert it to as the second argument.</span></span> <span data-ttu-id="c5cc3-108">`DirectCast` erfordert eine Vererbungs-oder Implementierungs Beziehung zwischen den Datentypen der beiden Argumente.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-108">`DirectCast` requires an inheritance or implementation relationship between the data types of the two arguments.</span></span> <span data-ttu-id="c5cc3-109">Dies bedeutet, dass ein Typ von einem Typ erben oder ihn implementieren muss.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-109">This means that one type must inherit from or implement the other.</span></span>  
  
## <a name="errors-and-failures"></a><span data-ttu-id="c5cc3-110">Fehler und Fehler</span><span class="sxs-lookup"><span data-stu-id="c5cc3-110">Errors and Failures</span></span>  

 <span data-ttu-id="c5cc3-111">`DirectCast` generiert einen Compilerfehler, wenn erkannt wird, dass keine Vererbungs-oder Implementierungs Beziehung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-111">`DirectCast` generates a compiler error if it detects that no inheritance or implementation relationship exists.</span></span> <span data-ttu-id="c5cc3-112">Das Fehlen eines Compilerfehlers garantiert jedoch nicht die erfolgreiche Konvertierung.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-112">But the lack of a compiler error does not guarantee a successful conversion.</span></span> <span data-ttu-id="c5cc3-113">Wenn die gewünschte Konvertierung einschränkend ist, kann Sie zur Laufzeit fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-113">If the desired conversion is narrowing, it could fail at run time.</span></span> <span data-ttu-id="c5cc3-114">Wenn dies der Fall ist, löst die Laufzeit einen <xref:System.InvalidCastException> Fehler aus.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-114">If this happens, the runtime throws an <xref:System.InvalidCastException> error.</span></span>  
  
## <a name="conversion-keywords"></a><span data-ttu-id="c5cc3-115">Konvertierungsschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c5cc3-115">Conversion Keywords</span></span>  

 <span data-ttu-id="c5cc3-116">Ein Vergleich der Schlüsselwörter für die Typkonvertierung lautet wie folgt.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-116">A comparison of the type conversion keywords is as follows.</span></span>  
  
|<span data-ttu-id="c5cc3-117">Stichwort</span><span class="sxs-lookup"><span data-stu-id="c5cc3-117">Keyword</span></span>|<span data-ttu-id="c5cc3-118">Datentypen</span><span class="sxs-lookup"><span data-stu-id="c5cc3-118">Data types</span></span>|<span data-ttu-id="c5cc3-119">Argument Beziehung</span><span class="sxs-lookup"><span data-stu-id="c5cc3-119">Argument relationship</span></span>|<span data-ttu-id="c5cc3-120">Laufzeitfehler</span><span class="sxs-lookup"><span data-stu-id="c5cc3-120">Run-time failure</span></span>|  
|---|---|---|---|  
|[<span data-ttu-id="c5cc3-121">CType Function</span><span class="sxs-lookup"><span data-stu-id="c5cc3-121">CType Function</span></span>](../functions/ctype-function.md)|<span data-ttu-id="c5cc3-122">Beliebige Datentypen</span><span class="sxs-lookup"><span data-stu-id="c5cc3-122">Any data types</span></span>|<span data-ttu-id="c5cc3-123">Zwischen den beiden Datentypen muss eine erweiternde oder einschränkende Konvertierung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-123">Widening or narrowing conversion must be defined between the two data types</span></span>|<span data-ttu-id="c5cc3-124">KEH <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="c5cc3-124">Throws <xref:System.InvalidCastException></span></span>|  
|`DirectCast`|<span data-ttu-id="c5cc3-125">Beliebige Datentypen</span><span class="sxs-lookup"><span data-stu-id="c5cc3-125">Any data types</span></span>|<span data-ttu-id="c5cc3-126">Ein Typ muss von einem anderen Typ erben oder ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-126">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="c5cc3-127">KEH <xref:System.InvalidCastException></span><span class="sxs-lookup"><span data-stu-id="c5cc3-127">Throws <xref:System.InvalidCastException></span></span>|  
|[<span data-ttu-id="c5cc3-128">TryCast-Operator</span><span class="sxs-lookup"><span data-stu-id="c5cc3-128">TryCast Operator</span></span>](trycast-operator.md)|<span data-ttu-id="c5cc3-129">Nur Verweis Typen</span><span class="sxs-lookup"><span data-stu-id="c5cc3-129">Reference types only</span></span>|<span data-ttu-id="c5cc3-130">Ein Typ muss von einem anderen Typ erben oder ihn implementieren.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-130">One type must inherit from or implement the other type</span></span>|<span data-ttu-id="c5cc3-131">Gibt [nichts](../nothing.md) zurück.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-131">Returns [Nothing](../nothing.md)</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c5cc3-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c5cc3-132">Example</span></span>  

 <span data-ttu-id="c5cc3-133">Im folgenden Beispiel werden zwei Verwendungsmöglichkeiten von veranschaulicht `DirectCast` : eine, die zur Laufzeit fehlschlägt, und eine, die erfolgreich ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-133">The following example demonstrates two uses of `DirectCast`, one that fails at run time and one that succeeds.</span></span>  
  
 [!code-vb[VbVbalrKeywords#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#1)]  
  
 <span data-ttu-id="c5cc3-134">Im vorherigen Beispiel ist der Lauf Zeittyp von `q` `Double` .</span><span class="sxs-lookup"><span data-stu-id="c5cc3-134">In the preceding example, the run-time type of `q` is `Double`.</span></span> <span data-ttu-id="c5cc3-135">`CType` ist erfolgreich `Double` , da in konvertiert werden kann `Integer` .</span><span class="sxs-lookup"><span data-stu-id="c5cc3-135">`CType` succeeds because `Double` can be converted to `Integer`.</span></span> <span data-ttu-id="c5cc3-136">Allerdings schlägt der erste `DirectCast` zur Laufzeit fehl, da der Lauf Zeittyp von `Double` keine Vererbungs Beziehung mit aufweist `Integer` , obwohl eine Konvertierung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-136">However, the first `DirectCast` fails at run time because the run-time type of `Double` has no inheritance relationship with `Integer`, even though a conversion exists.</span></span> <span data-ttu-id="c5cc3-137">Die zweite `DirectCast` ist erfolgreich, da Sie vom Typ <xref:System.Windows.Forms.Form> in den Typ konvertiert <xref:System.Windows.Forms.Control> , von dem <xref:System.Windows.Forms.Form> erbt.</span><span class="sxs-lookup"><span data-stu-id="c5cc3-137">The second `DirectCast` succeeds because it converts from type <xref:System.Windows.Forms.Form> to type <xref:System.Windows.Forms.Control>, from which <xref:System.Windows.Forms.Form> inherits.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5cc3-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5cc3-138">See also</span></span>

- <xref:System.Convert.ChangeType%2A?displayProperty=nameWithType>
- [<span data-ttu-id="c5cc3-139">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="c5cc3-139">Widening and Narrowing Conversions</span></span>](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [<span data-ttu-id="c5cc3-140">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="c5cc3-140">Implicit and Explicit Conversions</span></span>](../../programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
