---
title: "Lambdaausdrücke sind nicht gültig ist, im ersten Ausdruck einer &#39; Wählen Sie die Groß-/Kleinschreibung &#39; Anweisung"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords: BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e91401d6891d4e38014bb716a337560885cf73a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a><span data-ttu-id="9a30c-102">Lambdaausdrücke sind nicht gültig ist, im ersten Ausdruck einer &#39; Wählen Sie die Groß-/Kleinschreibung &#39; Anweisung</span><span class="sxs-lookup"><span data-stu-id="9a30c-102">Lambda expressions are not valid in the first expression of a &#39;Select Case&#39; statement</span></span>
<span data-ttu-id="9a30c-103">Sie können einen Lambda-Ausdruck keine für den Testausdruck in einer `Select Case` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9a30c-103">You cannot use a lambda expression for the test expression in a `Select Case` statement.</span></span> <span data-ttu-id="9a30c-104">Definitionen der Lambda-Ausdruck zurückgeben, Funktionen und der Testausdruck eine `Select Case` -Anweisung muss ein elementarer Datentyp sein.</span><span class="sxs-lookup"><span data-stu-id="9a30c-104">Lambda expression definitions return functions, and the test expression of a `Select Case` statement must be an elementary data type.</span></span>  
  
 <span data-ttu-id="9a30c-105">Der folgende Code verursacht diesen Fehler:</span><span class="sxs-lookup"><span data-stu-id="9a30c-105">The following code causes this error:</span></span>  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 <span data-ttu-id="9a30c-106">**Fehler-ID:** BC36635</span><span class="sxs-lookup"><span data-stu-id="9a30c-106">**Error ID:** BC36635</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9a30c-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9a30c-107">To correct this error</span></span>  
  
-   <span data-ttu-id="9a30c-108">Überprüfen Sie den Code, um festzustellen, ob eine andere bedingte Konstruktion für Sie geeignet wäre, z. B. eine `If...Then...Else` -Anweisung.</span><span class="sxs-lookup"><span data-stu-id="9a30c-108">Examine your code to determine whether a different conditional construction, such as an `If...Then...Else` statement, would work for you.</span></span>  
  
-   <span data-ttu-id="9a30c-109">Sie können haben die Funktion aufrufen gedacht, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="9a30c-109">You may have intended to call the function, as shown in the following code:</span></span>  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a><span data-ttu-id="9a30c-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a30c-110">See Also</span></span>  
 [<span data-ttu-id="9a30c-111">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="9a30c-111">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [<span data-ttu-id="9a30c-112">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9a30c-112">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [<span data-ttu-id="9a30c-113">Select...Case-Anweisung</span><span class="sxs-lookup"><span data-stu-id="9a30c-113">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
