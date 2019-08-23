---
title: Mid-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
ms.openlocfilehash: 212ce1f06a01c39acbce43d8d069dae3526b1b4d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963548"
---
# <a name="mid-statement"></a><span data-ttu-id="23664-102">Mid-Anweisung</span><span class="sxs-lookup"><span data-stu-id="23664-102">Mid Statement</span></span>
<span data-ttu-id="23664-103">Ersetzt eine angegebene Anzahl von Zeichen in einer `String` Variablen durch Zeichen aus einer anderen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="23664-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23664-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23664-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="23664-105">Teile</span><span class="sxs-lookup"><span data-stu-id="23664-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="23664-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="23664-106">Required.</span></span> <span data-ttu-id="23664-107">Der Name der `String` Variablen, die geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="23664-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="23664-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="23664-108">Required.</span></span> <span data-ttu-id="23664-109">`Integer`Begriff.</span><span class="sxs-lookup"><span data-stu-id="23664-109">`Integer` expression.</span></span> <span data-ttu-id="23664-110">Zeichenposition in `Target` , an der die Text Ersetzung beginnt.</span><span class="sxs-lookup"><span data-stu-id="23664-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="23664-111">`Start`verwendet einen 1-basierten Index.</span><span class="sxs-lookup"><span data-stu-id="23664-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="23664-112">Optional.</span><span class="sxs-lookup"><span data-stu-id="23664-112">Optional.</span></span> <span data-ttu-id="23664-113">`Integer`Begriff.</span><span class="sxs-lookup"><span data-stu-id="23664-113">`Integer` expression.</span></span> <span data-ttu-id="23664-114">Anzahl der zu ersetzenden Zeichen.</span><span class="sxs-lookup"><span data-stu-id="23664-114">Number of characters to replace.</span></span> <span data-ttu-id="23664-115">Wenn der `String` Wert weggelassen wird, wird all verwendet.</span><span class="sxs-lookup"><span data-stu-id="23664-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="23664-116">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="23664-116">Required.</span></span> <span data-ttu-id="23664-117">`String`Ausdruck, der einen Teil `Target`von ersetzt.</span><span class="sxs-lookup"><span data-stu-id="23664-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="23664-118">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="23664-118">Exceptions</span></span>  
  
|<span data-ttu-id="23664-119">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="23664-119">Exception type</span></span>|<span data-ttu-id="23664-120">Bedingung</span><span class="sxs-lookup"><span data-stu-id="23664-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="23664-121">`Start`< = 0 oder `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="23664-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23664-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="23664-122">Remarks</span></span>  
 <span data-ttu-id="23664-123">Die Anzahl der ersetzten Zeichen ist immer kleiner oder gleich der Anzahl von Zeichen in `Target`.</span><span class="sxs-lookup"><span data-stu-id="23664-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="23664-124">Visual Basic verfügt über <xref:Microsoft.VisualBasic.Strings.Mid%2A> eine-Funktion `Mid` und eine-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="23664-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="23664-125">Diese Elemente funktionieren beide mit einer angegebenen Anzahl von Zeichen in einer Zeichenfolge, aber `Mid` die-Funktion gibt die Zeichen `Mid` zurück, während die-Anweisung die Zeichen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="23664-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="23664-126">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="23664-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="23664-127">Die `MidB` -Anweisung früherer Versionen von Visual Basic ersetzt eine Teil Zeichenfolge in Bytes und nicht als Zeichen.</span><span class="sxs-lookup"><span data-stu-id="23664-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="23664-128">Es wird hauptsächlich zum Umrechnen von Zeichen folgen in DBCS-Anwendungen (Double-Byte Character Set) verwendet.</span><span class="sxs-lookup"><span data-stu-id="23664-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="23664-129">Alle Visual Basic Zeichenfolgen sind in Unicode `MidB` und werden nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="23664-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="23664-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23664-130">Example</span></span>  
 <span data-ttu-id="23664-131">In diesem Beispiel wird `Mid` die-Anweisung verwendet, um eine angegebene Anzahl von Zeichen in einer Zeichen folgen Variablen durch Zeichen aus einer anderen Zeichenfolge zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="23664-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#5)]  
  
## <a name="requirements"></a><span data-ttu-id="23664-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23664-132">Requirements</span></span>  
 <span data-ttu-id="23664-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="23664-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="23664-134">**Modul:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="23664-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="23664-135">**Stadtverordneten** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span><span class="sxs-lookup"><span data-stu-id="23664-135">**Assembly:** Visual Basic Runtime Library (in Microsoft.VisualBasic.dll)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23664-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23664-136">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- [<span data-ttu-id="23664-137">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="23664-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)
- [<span data-ttu-id="23664-138">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="23664-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
