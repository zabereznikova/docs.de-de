---
title: 'Vorgehensweise: Verschieben von Daten in und aus einer Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: 30d1c0ab91724ac556e59b272782513ee8b8067b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818534"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="86355-102">Vorgehensweise: Verschieben von Daten in und aus einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86355-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>
<span data-ttu-id="86355-103">Sie können einen Wert in einer Variablen speichern, indem Sie den Namen den Variablen auf der linken Seite einer zuweisungsanweisung einfügen.</span><span class="sxs-lookup"><span data-stu-id="86355-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>  
  
## <a name="putting-data-in-a-variable"></a><span data-ttu-id="86355-104">Einfügen von Daten in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="86355-104">Putting Data in a Variable</span></span>  
  
#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="86355-105">Einen Wert in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="86355-105">To store a value in a variable</span></span>  
  
-   <span data-ttu-id="86355-106">Verwenden Sie den Namen den Variablen auf der linken Seite einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="86355-106">Use the variable name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="86355-107">Im folgenden Beispiel wird den Wert der Variablen `alpha`.</span><span class="sxs-lookup"><span data-stu-id="86355-107">The following example sets the value of the variable `alpha`.</span></span>  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     <span data-ttu-id="86355-108">Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="86355-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>  
  
## <a name="getting-data-from-a-variable"></a><span data-ttu-id="86355-109">Abrufen von Daten aus einer Variablen</span><span class="sxs-lookup"><span data-stu-id="86355-109">Getting Data from a Variable</span></span>  
 <span data-ttu-id="86355-110">Sie rufen den Wert einer Variable, indem Sie den Namen den Variablen in einen Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="86355-110">You retrieve a variable's value by including the variable name in an expression.</span></span>  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="86355-111">Zum Abrufen eines Werts aus einer Variablen</span><span class="sxs-lookup"><span data-stu-id="86355-111">To retrieve a value from a variable</span></span>  
  
-   <span data-ttu-id="86355-112">Verwenden Sie den Namen den Variablen in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="86355-112">Use the variable name in an expression.</span></span> <span data-ttu-id="86355-113">Sie können eine Variable an einer beliebigen Stelle können Sie eine Konstante oder ein Literal ist, außer in einem Ausdruck, der den Wert einer Konstante definiert.</span><span class="sxs-lookup"><span data-stu-id="86355-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>  
  
     <span data-ttu-id="86355-114">- oder - </span><span class="sxs-lookup"><span data-stu-id="86355-114">-or-</span></span>  
  
-   <span data-ttu-id="86355-115">Verwenden Sie den Namen den Variablen nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung anmelden.</span><span class="sxs-lookup"><span data-stu-id="86355-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="86355-116">Das folgende Beispiel liest den Wert der Variablen `startValue` und verwendet dann den Wert der Variablen `counter` in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="86355-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     <span data-ttu-id="86355-117">Der Wert der Variablen ist Teil des Ausdrucks wie würden eine Konstante, und wird dann in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="86355-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86355-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86355-118">See also</span></span>

- [<span data-ttu-id="86355-119">Variablen</span><span class="sxs-lookup"><span data-stu-id="86355-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="86355-120">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="86355-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="86355-121">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="86355-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
