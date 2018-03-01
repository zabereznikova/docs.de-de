---
title: Typ des &#39; &lt;Variablename&gt;&#39; kann nicht abgeleitet werden, weil die schleifenbegrenzungen und die Step-Variable nicht auf den gleichen Typ erweitert werden
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 022e29e38a93d2880bbfa250e65a8b95b39ff140
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="type-of-39ltvariablenamegt39-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="58e87-102">Typ des &#39; &lt;Variablename&gt;&#39; kann nicht abgeleitet werden, weil die schleifenbegrenzungen und die Step-Variable nicht auf den gleichen Typ erweitert werden</span><span class="sxs-lookup"><span data-stu-id="58e87-102">Type of &#39;&lt;variablename&gt;&#39; cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>
<span data-ttu-id="58e87-103">Sie selbst geschrieben haben eine `For...Next` Schleife, in denen der Compiler keinen Datentyp für die Loop-Steuerelementvariable ableiten, da die folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="58e87-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>  
  
-   <span data-ttu-id="58e87-104">Der Datentyp der Schleifensteuerungsvariablen wird nicht mit einer `As` -Klausel angegeben.</span><span class="sxs-lookup"><span data-stu-id="58e87-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>  
  
-   <span data-ttu-id="58e87-105">Die Schleifenbegrenzungen und die step-Variable enthalten mindestens zwei Datentypen.</span><span class="sxs-lookup"><span data-stu-id="58e87-105">The loop bounds and step variable contain at least two data types.</span></span>  
  
-   <span data-ttu-id="58e87-106">Keine standardmäßigen Konvertierungen werden zwischen den Datentypen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="58e87-106">No standard conversions exist between the data types.</span></span>  
  
 <span data-ttu-id="58e87-107">Aus diesem Grund kann nicht der Compiler den Datentyp, der eine Schleifensteuerungsvariable ableiten.</span><span class="sxs-lookup"><span data-stu-id="58e87-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>  
  
 <span data-ttu-id="58e87-108">Im folgenden Beispiel die Step-Variable ist ein Zeichen, und die schleifenbegrenzungen sind beide ganze Zahlen.</span><span class="sxs-lookup"><span data-stu-id="58e87-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="58e87-109">Da es sich keine standardkonvertierung zwischen Zeichen mit und ganze Zahlen, wird dieser Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="58e87-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 <span data-ttu-id="58e87-110">**Fehler-ID:** BC30982</span><span class="sxs-lookup"><span data-stu-id="58e87-110">**Error ID:** BC30982</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="58e87-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="58e87-111">To correct this error</span></span>  
  
-   <span data-ttu-id="58e87-112">Ändern Sie die Typen von die schleifenbegrenzungen und die Step-Variable nach Bedarf, sodass mindestens einer dieser Anweisungstypen ein Typ, dem die anderen ist, erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="58e87-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="58e87-113">Ändern Sie den Typ der im vorherigen Beispiel `stepVar` auf `Integer`.</span><span class="sxs-lookup"><span data-stu-id="58e87-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     <span data-ttu-id="58e87-114">– oder –</span><span class="sxs-lookup"><span data-stu-id="58e87-114">—or—</span></span>  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   <span data-ttu-id="58e87-115">Verwenden Sie explizite Konvertierungsfunktionen, um die schleifenbegrenzungen und die Step-Variable auf die entsprechenden Typen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="58e87-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="58e87-116">Im vorherigen Beispiel gelten die `Val` -Funktion `stepVar`.</span><span class="sxs-lookup"><span data-stu-id="58e87-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="58e87-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58e87-117">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [<span data-ttu-id="58e87-118">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="58e87-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [<span data-ttu-id="58e87-119">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="58e87-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="58e87-120">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="58e87-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [<span data-ttu-id="58e87-121">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="58e87-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [<span data-ttu-id="58e87-122">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="58e87-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="58e87-123">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="58e87-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
