---
title: Variable &#39; &lt;Variablename&gt; &#39; verbirgt eine Variable in einem einschließenden Block
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 58e09caeb477d6b1df7f3be17e0a8ee05be3551e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595091"
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="8b435-102">Variable &#39; &lt;Variablename&gt; &#39; verbirgt eine Variable in einem einschließenden Block</span><span class="sxs-lookup"><span data-stu-id="8b435-102">Variable &#39;&lt;variablename&gt;&#39; hides a variable in an enclosing block</span></span>
<span data-ttu-id="8b435-103">Eine Variable in einem Block eingeschlossen hat den gleichen Namen wie eine andere lokale Variable.</span><span class="sxs-lookup"><span data-stu-id="8b435-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="8b435-104">**Fehler-ID:** BC30616</span><span class="sxs-lookup"><span data-stu-id="8b435-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8b435-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8b435-105">To correct this error</span></span>  
  
-   <span data-ttu-id="8b435-106">Benennen Sie die Variable in der eingeschlossenen Block, damit er nicht mit der lokalen Variablen identisch ist.</span><span class="sxs-lookup"><span data-stu-id="8b435-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="8b435-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8b435-107">For example:</span></span>  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   <span data-ttu-id="8b435-108">Eine häufige Ursache für diesen Fehler ist die Verwendung von `Catch e As Exception` innerhalb eines ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="8b435-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="8b435-109">Wenn dies der Fall ist, benennen Sie die `Catch` Blockvariable `ex` statt `e`.</span><span class="sxs-lookup"><span data-stu-id="8b435-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
-   <span data-ttu-id="8b435-110">Eine andere übliche Quelle für diesen Fehler ist der Versuch, eine lokale Variable deklariert den Zugriff auf eine `Try` blockieren in einer separaten `Catch` Block.</span><span class="sxs-lookup"><span data-stu-id="8b435-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="8b435-111">Um dies zu korrigieren, deklarieren Sie die Variable außerhalb der `Try...Catch...Finally` Struktur.</span><span class="sxs-lookup"><span data-stu-id="8b435-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b435-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b435-112">See Also</span></span>  
 [<span data-ttu-id="8b435-113">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8b435-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [<span data-ttu-id="8b435-114">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="8b435-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
