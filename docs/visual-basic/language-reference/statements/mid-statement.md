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
ms.openlocfilehash: a653e63ded04616b6b0c6bdfb26a0a673d9299fc
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2018
ms.locfileid: "45589338"
---
# <a name="mid-statement"></a><span data-ttu-id="1212c-102">Mid-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1212c-102">Mid Statement</span></span>
<span data-ttu-id="1212c-103">Ersetzt eine angegebene Anzahl von Zeichen in einem `String` Variable mit dem Zeichen aus einer anderen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1212c-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1212c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1212c-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="1212c-105">Teile</span><span class="sxs-lookup"><span data-stu-id="1212c-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="1212c-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1212c-106">Required.</span></span> <span data-ttu-id="1212c-107">Name des der `String` zu ändernden Variablen.</span><span class="sxs-lookup"><span data-stu-id="1212c-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="1212c-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1212c-108">Required.</span></span> <span data-ttu-id="1212c-109">`Integer` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="1212c-109">`Integer` expression.</span></span> <span data-ttu-id="1212c-110">Die Zeichenposition in `Target` , an dem das Ersetzen des Texts beginnt.</span><span class="sxs-lookup"><span data-stu-id="1212c-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="1212c-111">`Start` verwendet einen einsbasierten Index.</span><span class="sxs-lookup"><span data-stu-id="1212c-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="1212c-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1212c-112">Optional.</span></span> <span data-ttu-id="1212c-113">`Integer` -Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="1212c-113">`Integer` expression.</span></span> <span data-ttu-id="1212c-114">Die Anzahl der zu ersetzenden Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1212c-114">Number of characters to replace.</span></span> <span data-ttu-id="1212c-115">Wenn nicht angegeben, alle `String` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1212c-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="1212c-116">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1212c-116">Required.</span></span> <span data-ttu-id="1212c-117">`String` Ausdruck, der Teil des ersetzt `Target`.</span><span class="sxs-lookup"><span data-stu-id="1212c-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="1212c-118">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="1212c-118">Exceptions</span></span>  
  
|<span data-ttu-id="1212c-119">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="1212c-119">Exception type</span></span>|<span data-ttu-id="1212c-120">Bedingung</span><span class="sxs-lookup"><span data-stu-id="1212c-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="1212c-121">`Start` < = 0 oder `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="1212c-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1212c-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1212c-122">Remarks</span></span>  
 <span data-ttu-id="1212c-123">Die Anzahl der Zeichen ersetzt ist immer kleiner oder gleich der Anzahl der Zeichen in `Target`.</span><span class="sxs-lookup"><span data-stu-id="1212c-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="1212c-124">Visual Basic verfügt über eine <xref:Microsoft.VisualBasic.Strings.Mid%2A> Funktion und ein `Mid` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1212c-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="1212c-125">Diese Elemente beide für eine angegebene Anzahl von Zeichen in eine Zeichenfolge funktionieren, aber die `Mid` Funktionsergebnis ist die Zeichen bei der die `Mid` Anweisung ersetzt die Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1212c-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="1212c-126">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="1212c-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1212c-127">Die `MidB` frühere Versionen von Visual Basic-Anweisung ersetzt eine Teilzeichenfolge in Byte, anstatt in Zeichen.</span><span class="sxs-lookup"><span data-stu-id="1212c-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="1212c-128">Es dient in erster Linie für das Konvertieren von Zeichenfolgen in Doppelbyte-Zeichensatz (DBCS)-Satz Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="1212c-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="1212c-129">Alle Visual Basic-Zeichenfolgen werden in Unicode und `MidB` wird nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1212c-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1212c-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1212c-130">Example</span></span>  
 <span data-ttu-id="1212c-131">Dieses Beispiel verwendet die `Mid` Anweisung, um eine angegebene Anzahl von Zeichen in einer Zeichenfolgenvariablen durch Zeichen aus einer anderen Zeichenfolge ersetzen.</span><span class="sxs-lookup"><span data-stu-id="1212c-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="1212c-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1212c-132">Requirements</span></span>  
 <span data-ttu-id="1212c-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="1212c-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="1212c-134">**Modul:** `Strings`</span><span class="sxs-lookup"><span data-stu-id="1212c-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="1212c-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1212c-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1212c-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1212c-136">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [<span data-ttu-id="1212c-137">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="1212c-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="1212c-138">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1212c-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
