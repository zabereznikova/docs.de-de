---
title: Variable &#39; &lt;Variablename&gt; &#39; verbirgt eine Variable in einem einschließenden Block
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 23ec659535b71ee9af189f5c4fec0dec2bb1cd8f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719429"
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a><span data-ttu-id="d2385-102">Variable &#39; &lt;Variablename&gt; &#39; verbirgt eine Variable in einem einschließenden Block</span><span class="sxs-lookup"><span data-stu-id="d2385-102">Variable &#39;&lt;variablename&gt;&#39; hides a variable in an enclosing block</span></span>
<span data-ttu-id="d2385-103">Eine Variable in einem Block eingeschlossen hat den gleichen Namen wie eine andere lokale Variable.</span><span class="sxs-lookup"><span data-stu-id="d2385-103">A variable enclosed in a block has the same name as another local variable.</span></span>  
  
 <span data-ttu-id="d2385-104">**Fehler-ID:** BC30616</span><span class="sxs-lookup"><span data-stu-id="d2385-104">**Error ID:** BC30616</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d2385-105">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d2385-105">To correct this error</span></span>  
  
-   <span data-ttu-id="d2385-106">Benennen Sie die Variable im-Block eingeschlossen, sodass sie nicht identisch mit anderen lokalen Variablen ist.</span><span class="sxs-lookup"><span data-stu-id="d2385-106">Rename the variable in the enclosed block so that it is not the same as any other local variables.</span></span> <span data-ttu-id="d2385-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d2385-107">For example:</span></span>  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   <span data-ttu-id="d2385-108">Eine häufige Ursache für diesen Fehler ist die Verwendung von `Catch e As Exception` innerhalb eines ereignishandlers.</span><span class="sxs-lookup"><span data-stu-id="d2385-108">A common cause for this error is the use of `Catch e As Exception` inside an event handler.</span></span> <span data-ttu-id="d2385-109">Wenn dies der Fall ist, den Namen der `Catch` Blockvariable `ex` statt `e`.</span><span class="sxs-lookup"><span data-stu-id="d2385-109">If this is the case, name the `Catch` block variable `ex` rather than `e`.</span></span>  
  
-   <span data-ttu-id="d2385-110">Eine andere übliche Quelle für diesen Fehler ist ein Zugriffsversuch auf eine lokale Variable deklariert, die innerhalb einer `Try` -block in einem separaten `Catch` Block.</span><span class="sxs-lookup"><span data-stu-id="d2385-110">Another common source of this error is an attempt to access a local variable declared within a `Try` block in a separate `Catch` block.</span></span> <span data-ttu-id="d2385-111">Um dies zu korrigieren, deklarieren Sie die Variable außerhalb der `Try...Catch...Finally` Struktur.</span><span class="sxs-lookup"><span data-stu-id="d2385-111">To correct this, declare the variable outside the `Try...Catch...Finally` structure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2385-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d2385-112">See also</span></span>
- [<span data-ttu-id="d2385-113">Try...Catch...Finally-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d2385-113">Try...Catch...Finally Statement</span></span>](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [<span data-ttu-id="d2385-114">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="d2385-114">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
