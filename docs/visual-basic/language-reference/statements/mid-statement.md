---
title: Mid-Anweisung
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.MidB
- vb.Mid
helpviewer_keywords:
- substrings [Visual Basic], Mid statement
- strings [Visual Basic], substrings
- Mid statement [Visual Basic]
- strings [Visual Basic], replacing
ms.assetid: 2b82d7a8-9646-4cb0-bec5-80abc98297bf
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61d812ef91acc65728b04efc9aa99e3975e71d0c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mid-statement"></a><span data-ttu-id="6b289-102">Mid-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6b289-102">Mid Statement</span></span>
<span data-ttu-id="6b289-103">Ersetzt eine angegebene Anzahl von Zeichen in einem `String` -Variable mit Zeichen aus einer anderen Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6b289-103">Replaces a specified number of characters in a `String` variable with characters from another string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b289-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6b289-104">Syntax</span></span>  
  
```  
Mid( _  
   ByRef Target As String, _  
   ByVal Start As Integer, _  
   Optional ByVal Length As Integer _  
) = StringExpression  
```  
  
## <a name="parts"></a><span data-ttu-id="6b289-105">Teile</span><span class="sxs-lookup"><span data-stu-id="6b289-105">Parts</span></span>  
 `Target`  
 <span data-ttu-id="6b289-106">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b289-106">Required.</span></span> <span data-ttu-id="6b289-107">Name des der `String` Variable zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6b289-107">Name of the `String` variable to modify.</span></span>  
  
 `Start`  
 <span data-ttu-id="6b289-108">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b289-108">Required.</span></span> <span data-ttu-id="6b289-109">`Integer`Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="6b289-109">`Integer` expression.</span></span> <span data-ttu-id="6b289-110">Die Zeichenposition in `Target` , in dem die Ersetzung von Text beginnt.</span><span class="sxs-lookup"><span data-stu-id="6b289-110">Character position in `Target` where the replacement of text begins.</span></span> <span data-ttu-id="6b289-111">`Start`verwendet einen einsbasierten Index.</span><span class="sxs-lookup"><span data-stu-id="6b289-111">`Start` uses a one-based index.</span></span>  
  
 `Length`  
 <span data-ttu-id="6b289-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="6b289-112">Optional.</span></span> <span data-ttu-id="6b289-113">`Integer`Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="6b289-113">`Integer` expression.</span></span> <span data-ttu-id="6b289-114">Anzahl der zu ersetzenden Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6b289-114">Number of characters to replace.</span></span> <span data-ttu-id="6b289-115">Wenn nicht angegeben, alle `String` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6b289-115">If omitted, all of `String` is used.</span></span>  
  
 `StringExpression`  
 <span data-ttu-id="6b289-116">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6b289-116">Required.</span></span> <span data-ttu-id="6b289-117">`String`Ausdruck, der Teil des ersetzt `Target`.</span><span class="sxs-lookup"><span data-stu-id="6b289-117">`String` expression that replaces part of `Target`.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="6b289-118">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="6b289-118">Exceptions</span></span>  
  
|<span data-ttu-id="6b289-119">Ausnahmetyp</span><span class="sxs-lookup"><span data-stu-id="6b289-119">Exception type</span></span>|<span data-ttu-id="6b289-120">Bedingung</span><span class="sxs-lookup"><span data-stu-id="6b289-120">Condition</span></span>|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<span data-ttu-id="6b289-121">`Start`< = 0 oder `Length` < 0.</span><span class="sxs-lookup"><span data-stu-id="6b289-121">`Start` <= 0 or `Length` < 0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b289-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6b289-122">Remarks</span></span>  
 <span data-ttu-id="6b289-123">Die Anzahl der Zeichen ersetzt ist immer kleiner oder gleich der Anzahl der Zeichen in `Target`.</span><span class="sxs-lookup"><span data-stu-id="6b289-123">The number of characters replaced is always less than or equal to the number of characters in `Target`.</span></span>  
  
 <span data-ttu-id="6b289-124">Visual Basic verfügt über eine <xref:Microsoft.VisualBasic.Strings.Mid%2A> Funktion und eine `Mid` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6b289-124">Visual Basic has a <xref:Microsoft.VisualBasic.Strings.Mid%2A> function and a `Mid` statement.</span></span> <span data-ttu-id="6b289-125">Diese Elemente, die beide auf eine angegebene Anzahl von Zeichen in eine Zeichenfolge funktionieren, aber die `Mid` Funktion gibt die Zeichen, während die `Mid` Anweisung ersetzt die Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6b289-125">These elements both operate on a specified number of characters in a string, but the `Mid` function returns the characters while the `Mid` statement replaces the characters.</span></span> <span data-ttu-id="6b289-126">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span><span class="sxs-lookup"><span data-stu-id="6b289-126">For more information, see <xref:Microsoft.VisualBasic.Strings.Mid%2A>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6b289-127">Die `MidB` -Anweisung aus früheren Versionen von Visual Basic ersetzt eine Teilzeichenfolge in Bytes anstatt Zeichen.</span><span class="sxs-lookup"><span data-stu-id="6b289-127">The `MidB` statement of earlier versions of Visual Basic replaces a substring in bytes, rather than characters.</span></span> <span data-ttu-id="6b289-128">Es dient in erster Linie für das Konvertieren von Zeichenfolgen in Doppelbyte-Zeichensatz (Character Set, DBCS) Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="6b289-128">It is used primarily for converting strings in double-byte character set (DBCS) applications.</span></span> <span data-ttu-id="6b289-129">Alle Visual Basic-Zeichenfolgen werden in Unicode und `MidB` wird nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6b289-129">All Visual Basic strings are in Unicode, and `MidB` is no longer supported.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b289-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6b289-130">Example</span></span>  
 <span data-ttu-id="6b289-131">Dieses Beispiel verwendet die `Mid` Anweisung, um eine angegebene Anzahl von Zeichen in einer Zeichenfolgenvariablen durch Zeichen aus einer anderen Zeichenfolge zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="6b289-131">This example uses the `Mid` statement to replace a specified number of characters in a string variable with characters from another string.</span></span>  
  
 [!code-vb[VbVbalrStrings#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/mid-statement_1.vb)]  
  
## <a name="requirements"></a><span data-ttu-id="6b289-132">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b289-132">Requirements</span></span>  
 <span data-ttu-id="6b289-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span><span class="sxs-lookup"><span data-stu-id="6b289-133">**Namespace:** [Microsoft.VisualBasic](../../../visual-basic/language-reference/runtime-library-members.md)</span></span>  
  
 <span data-ttu-id="6b289-134">**Modul:**`Strings`</span><span class="sxs-lookup"><span data-stu-id="6b289-134">**Module:** `Strings`</span></span>  
  
 <span data-ttu-id="6b289-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b289-135">**Assembly:** [!INCLUDE[vbprvbruntime](~/includes/vbprvbruntime-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b289-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b289-136">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 [<span data-ttu-id="6b289-137">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="6b289-137">Strings</span></span>](../../../visual-basic/programming-guide/language-features/strings/index.md)  
 [<span data-ttu-id="6b289-138">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6b289-138">Introduction to Strings in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
