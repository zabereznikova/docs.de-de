---
title: Lambdaausdrücke sind nicht gültig ist, im ersten Ausdruck einer &#39;Select Case&#39; Anweisung
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: c492615850ec089fe35c1ae4eaba90a741e30f42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588920"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a><span data-ttu-id="d82b6-102">Lambdaausdrücke sind nicht gültig ist, im ersten Ausdruck einer &#39;Select Case&#39; Anweisung</span><span class="sxs-lookup"><span data-stu-id="d82b6-102">Lambda expressions are not valid in the first expression of a &#39;Select Case&#39; statement</span></span>
<span data-ttu-id="d82b6-103">Sie können einen Lambda-Ausdruck keine für den Testausdruck in einer `Select Case` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d82b6-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="d82b6-104">Definitionen der Lambda-Ausdruck zurückgeben, Funktionen und der Testausdruck eine `Select Case` -Anweisung muss ein elementarer Datentyp sein.</span><span class="sxs-lookup"><span data-stu-id="d82b6-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="d82b6-105">Der folgende Code verursacht diesen Fehler:</span><span class="sxs-lookup"><span data-stu-id="d82b6-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="d82b6-106">**Fehler-ID:** BC36635</span><span class="sxs-lookup"><span data-stu-id="d82b6-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d82b6-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d82b6-107">To correct this error</span></span>  
  
-   <span data-ttu-id="d82b6-108">Überprüfen Sie den Code, um festzustellen, ob eine andere bedingte Konstruktion für Sie geeignet wäre, z. B. eine `If...Then...Else` -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="d82b6-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
-   <span data-ttu-id="d82b6-109">Sie können haben die Funktion aufrufen gedacht, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="d82b6-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="d82b6-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d82b6-110">See Also</span></span>  
 [<span data-ttu-id="d82b6-111">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="d82b6-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="d82b6-112">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d82b6-112">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="d82b6-113">Select...Case-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d82b6-113">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
