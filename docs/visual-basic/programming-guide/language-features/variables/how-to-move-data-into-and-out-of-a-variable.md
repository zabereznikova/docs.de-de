---
title: 'Vorgehensweise: Verschieben von Daten in und aus einer Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
ms.openlocfilehash: 9b34173ebb3226fa00610c124c7b680e18d80de9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717943"
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="c0e7b-102">Vorgehensweise: Verschieben von Daten in und aus einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0e7b-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>
<span data-ttu-id="c0e7b-103">Sie können einen Wert in einer Variablen speichern, indem Sie den Namen den Variablen auf der linken Seite einer zuweisungsanweisung einfügen.</span><span class="sxs-lookup"><span data-stu-id="c0e7b-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>  
  
## <a name="putting-data-in-a-variable"></a><span data-ttu-id="c0e7b-104">Einfügen von Daten in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="c0e7b-104">Putting Data in a Variable</span></span>  
  
#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="c0e7b-105">Einen Wert in einer Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c0e7b-105">To store a value in a variable</span></span>  
  
-   <span data-ttu-id="c0e7b-106">Verwenden Sie den Namen den Variablen auf der linken Seite einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="c0e7b-106">Use the variable name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="c0e7b-107">Im folgenden Beispiel wird den Wert der Variablen `alpha`.</span><span class="sxs-lookup"><span data-stu-id="c0e7b-107">The following example sets the value of the variable `alpha`.</span></span>  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     <span data-ttu-id="c0e7b-108">Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c0e7b-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>  
  
## <a name="getting-data-from-a-variable"></a><span data-ttu-id="c0e7b-109">Abrufen von Daten aus einer Variablen</span><span class="sxs-lookup"><span data-stu-id="c0e7b-109">Getting Data from a Variable</span></span>  
 <span data-ttu-id="c0e7b-110">Sie rufen den Wert einer Variable, indem Sie den Namen den Variablen in einen Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="c0e7b-110">You retrieve a variable's value by including the variable name in an expression.</span></span>  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="c0e7b-111">Zum Abrufen eines Werts aus einer Variablen</span><span class="sxs-lookup"><span data-stu-id="c0e7b-111">To retrieve a value from a variable</span></span>  
  
-   <span data-ttu-id="c0e7b-112">Verwenden Sie den Namen den Variablen in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c0e7b-112">Use the variable name in an expression.</span></span> <span data-ttu-id="c0e7b-113">Sie können eine Variable an einer beliebigen Stelle können Sie eine Konstante oder ein Literal ist, außer in einem Ausdruck, der den Wert einer Konstante definiert.</span><span class="sxs-lookup"><span data-stu-id="c0e7b-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>  
  
     <span data-ttu-id="c0e7b-114">- oder - </span><span class="sxs-lookup"><span data-stu-id="c0e7b-114">-or-</span></span>  
  
-   <span data-ttu-id="c0e7b-115">Verwenden Sie den Namen den Variablen nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung anmelden.</span><span class="sxs-lookup"><span data-stu-id="c0e7b-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="c0e7b-116">Das folgende Beispiel liest den Wert der Variablen `startValue` und verwendet dann den Wert der Variablen `counter` in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c0e7b-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     <span data-ttu-id="c0e7b-117">Der Wert der Variablen ist Teil des Ausdrucks wie würden eine Konstante, und wird dann in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="c0e7b-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0e7b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0e7b-118">See also</span></span>
- [<span data-ttu-id="c0e7b-119">Variablen</span><span class="sxs-lookup"><span data-stu-id="c0e7b-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [<span data-ttu-id="c0e7b-120">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="c0e7b-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="c0e7b-121">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="c0e7b-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
