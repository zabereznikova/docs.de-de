---
title: Der Typ von '<variablename>' kann nicht abgeleitet werden, weil die Schleifenbegrenzungen und die step-Klausel nicht in denselben Typ konvertiert werden
ms.date: 07/20/2015
f1_keywords:
- bc30982
- vbc30982
helpviewer_keywords:
- BC30982
ms.assetid: 741e85d9-a747-42ad-a1e1-a3f1928aaff5
ms.openlocfilehash: e90e881546c12df2c8b19ff03a4d4c7304c4596c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58815874"
---
# <a name="type-of-variablename-cannot-be-inferred-because-the-loop-bounds-and-the-step-variable-do-not-widen-to-the-same-type"></a><span data-ttu-id="9b3c5-102">Geben Sie der "\<Variablenname >' kann nicht abgeleitet werden, weil die schleifenbegrenzungen und die Step-Klausel nicht in denselben Typ konvertiert werden</span><span class="sxs-lookup"><span data-stu-id="9b3c5-102">Type of '\<variablename>' cannot be inferred because the loop bounds and the step variable do not widen to the same type</span></span>
<span data-ttu-id="9b3c5-103">Sie geschrieben haben eine `For...Next` Schleife, in denen der Compiler nicht werden, einen Datentyp für die Schleifensteuerungsvariable abgeleitet kann da die folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="9b3c5-103">You have written a `For...Next` loop in which the compiler cannot infer a data type for the loop control variable because the following conditions are true:</span></span>  
  
-   <span data-ttu-id="9b3c5-104">Der Datentyp der Schleifensteuerungsvariablen wird nicht mit einer `As` -Klausel angegeben.</span><span class="sxs-lookup"><span data-stu-id="9b3c5-104">The data type of the loop control variable is not specified with an `As` clause.</span></span>  
  
-   <span data-ttu-id="9b3c5-105">Die Schleifenbegrenzungen und die step-Variable enthalten mindestens zwei Datentypen.</span><span class="sxs-lookup"><span data-stu-id="9b3c5-105">The loop bounds and step variable contain at least two data types.</span></span>  
  
-   <span data-ttu-id="9b3c5-106">Keine standardkonvertierungen vorhanden sein, zwischen den Datentypen.</span><span class="sxs-lookup"><span data-stu-id="9b3c5-106">No standard conversions exist between the data types.</span></span>  
  
 <span data-ttu-id="9b3c5-107">Aus diesem Grund kann nicht der Compiler den Datentyp, der eine Schleifensteuerungsvariable ableiten.</span><span class="sxs-lookup"><span data-stu-id="9b3c5-107">Therefore, the compiler cannot infer the data type of a loop's control variable.</span></span>  
  
 <span data-ttu-id="9b3c5-108">Im folgenden Beispiel die Schritt-Variable ist ein Zeichen, und die schleifenbegrenzungen sind sowohl ganze Zahlen.</span><span class="sxs-lookup"><span data-stu-id="9b3c5-108">In the following example, the step variable is a character and the loop bounds are both integers.</span></span> <span data-ttu-id="9b3c5-109">Da es keine standardkonvertierung zwischen Zeichen und ganze Zahlen ist, wird dieser Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="9b3c5-109">Because there is no standard conversion between characters and integers, this error is reported.</span></span>  
  
```vb  
Dim stepVar = "1"c  
Dim m = 0  
Dim n = 20  
  
' Not valid.  
' For i = 1 To 10 Step stepVar  
    ' Loop processing  
' Next  
```  
  
 <span data-ttu-id="9b3c5-110">**Fehler-ID:** BC30982</span><span class="sxs-lookup"><span data-stu-id="9b3c5-110">**Error ID:** BC30982</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9b3c5-111">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9b3c5-111">To correct this error</span></span>  
  
-   <span data-ttu-id="9b3c5-112">Ändern Sie die Typen von die schleifenbegrenzungen und Schritt nach Bedarf, sodass mindestens eine von ihnen ein Typ ist, dem die anderen erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="9b3c5-112">Change the types of the loop bounds and step variable as necessary so that at least one of them is a type that the others widen to.</span></span> <span data-ttu-id="9b3c5-113">Ändern Sie im vorherigen Beispiel ist den Typ des `stepVar` zu `Integer`.</span><span class="sxs-lookup"><span data-stu-id="9b3c5-113">In the preceding example, change the type of `stepVar` to `Integer`.</span></span>  
  
    ```  
    Dim stepVar = 1  
    ```  
  
     <span data-ttu-id="9b3c5-114">– oder –</span><span class="sxs-lookup"><span data-stu-id="9b3c5-114">—or—</span></span>  
  
    ```  
    Dim stepVar As Integer = 1  
    ```  
  
-   <span data-ttu-id="9b3c5-115">Verwenden Sie explizite Konvertierungsfunktionen, um die schleifenbegrenzungen und Schritt in die entsprechenden Typen konvertieren.</span><span class="sxs-lookup"><span data-stu-id="9b3c5-115">Use explicit conversion functions to convert the loop bounds and step variable to the appropriate types.</span></span> <span data-ttu-id="9b3c5-116">Im vorherigen Beispiel, gelten die `Val` -Funktion `stepVar`.</span><span class="sxs-lookup"><span data-stu-id="9b3c5-116">In the preceding example, apply the `Val` function to `stepVar`.</span></span>  
  
    ```  
    For i = 1 To 10 Step Val(stepVar)  
        ' Loop processing  
    Next  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9b3c5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b3c5-117">See also</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="9b3c5-118">For...Next-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9b3c5-118">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="9b3c5-119">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="9b3c5-119">Implicit and Explicit Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [<span data-ttu-id="9b3c5-120">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="9b3c5-120">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="9b3c5-121">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9b3c5-121">Option Infer Statement</span></span>](../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [<span data-ttu-id="9b3c5-122">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="9b3c5-122">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="9b3c5-123">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="9b3c5-123">Widening and Narrowing Conversions</span></span>](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
