---
title: Mid-Anweisung
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
ms.openlocfilehash: 90b805df902dcdfebe85421583dd54e9af04bec9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602264"
---
# <a name="mid-statement"></a><span data-ttu-id="81f7b-102">Mid-Anweisung</span><span class="sxs-lookup"><span data-stu-id="81f7b-102">Mid Statement</span></span>
<span data-ttu-id="81f7b-103">Ersetzt eine angegebene Anzahl von Zeichen in einem `String` -Variable mit Zeichen aus einer anderen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="81f7b-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81f7b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="81f7b-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="81f7b-105">Teile</span><span class="sxs-lookup"><span data-stu-id="81f7b-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="81f7b-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="81f7b-106">Required.</span></span> <span data-ttu-id="81f7b-107">Name des der `String` Variable zu ändern.</span><span class="sxs-lookup"><span data-stu-id="81f7b-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="81f7b-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="81f7b-108">Required.</span></span> <span data-ttu-id="81f7b-109">`Integer` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="81f7b-109">`Integer` expression.</span></span> <span data-ttu-id="81f7b-110">Die Zeichenposition in `Target` , in dem die Ersetzung von Text beginnt.</span><span class="sxs-lookup"><span data-stu-id="81f7b-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="81f7b-111">`Start` verwendet einen einsbasierten Index.</span><span class="sxs-lookup"><span data-stu-id="81f7b-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="81f7b-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="81f7b-112">Optional.</span></span> <span data-ttu-id="81f7b-113">`Integer` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="81f7b-113">`Integer` expression.</span></span> <span data-ttu-id="81f7b-114">Anzahl der zu ersetzenden Zeichen.</span><span class="sxs-lookup"><span data-stu-id="81f7b-114">Number of characters to replace.</span></span> <span data-ttu-id="81f7b-115">Wenn nicht angegeben, alle `String` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="81f7b-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="81f7b-116">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="81f7b-116">Required.</span></span> <span data-ttu-id="81f7b-117">`String` Ausdruck, der Teil des ersetzt `Target`.</span><span class="sxs-lookup"><span data-stu-id="81f7b-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="81f7b-118">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="81f7b-118">Exceptions</span></span>  
  
|<span data-ttu-id="81f7b-119">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="81f7b-119">Exception type</span></span>|<span data-ttu-id="81f7b-120">Bedingung</span><span class="sxs-lookup"><span data-stu-id="81f7b-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="81f7b-121">`Start` < = 0 oder `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="81f7b-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81f7b-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81f7b-122">Remarks</span></span>  
 <span data-ttu-id="81f7b-123">Die Anzahl der Zeichen ersetzt ist immer kleiner oder gleich der Anzahl der Zeichen in `Target`.</span><span class="sxs-lookup"><span data-stu-id="81f7b-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="81f7b-124">Visual Basic verfügt über eine <xref:Microsoft.VisualBasic.Strings.Mid%2A> Funktion und eine `Mid` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="81f7b-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="81f7b-125">Diese Elemente, die beide auf eine angegebene Anzahl von Zeichen in eine Zeichenfolge funktionieren, aber die `Mid` Funktion gibt die Zeichen, während die `Mid` Anweisung ersetzt die Zeichen.</span><span class="sxs-lookup"><span data-stu-id="81f7b-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="81f7b-126">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="81f7b-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81f7b-127">Die `MidB` -Anweisung aus früheren Versionen von Visual Basic ersetzt eine Teilzeichenfolge in Bytes anstatt Zeichen.</span><span class="sxs-lookup"><span data-stu-id="81f7b-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="81f7b-128">Es dient in erster Linie für das Konvertieren von Zeichenfolgen in Doppelbyte-Zeichensatz (Character Set, DBCS) Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="81f7b-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="81f7b-129">Alle Visual Basic-Zeichenfolgen werden in Unicode und `MidB` wird nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="81f7b-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="81f7b-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="81f7b-130">Example</span></span>  
 <span data-ttu-id="81f7b-131">Dieses Beispiel verwendet die `Mid` Anweisung, um eine angegebene Anzahl von Zeichen in einer Zeichenfolgenvariablen durch Zeichen aus einer anderen Zeichenfolge zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="81f7b-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="81f7b-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="81f7b-132">Requirements</span></span>  
 <span data-ttu-id="81f7b-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="81f7b-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="81f7b-134">**Modul:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="81f7b-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="81f7b-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81f7b-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81f7b-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81f7b-136">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [<span data-ttu-id="81f7b-137">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="81f7b-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="81f7b-138">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="81f7b-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
