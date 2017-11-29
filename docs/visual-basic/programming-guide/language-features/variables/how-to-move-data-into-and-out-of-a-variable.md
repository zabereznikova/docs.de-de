---
title: 'Gewusst wie: Verschieben von Daten in und aus einer Variablen (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- variables [Visual Basic], retrieving values
- variables [Visual Basic], storing data
ms.assetid: 93744f46-bf78-4fa0-9640-1de01bc38d9a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fefb1979e35cd7b5fa1917f8f1a57af575e51234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-move-data-into-and-out-of-a-variable-visual-basic"></a><span data-ttu-id="33d0a-102">Gewusst wie: Verschieben von Daten in und aus einer Variablen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="33d0a-102">How to: Move Data Into and Out of a Variable (Visual Basic)</span></span>
<span data-ttu-id="33d0a-103">Sie können einen Wert in einer Variablen speichern, indem Sie den Variablennamen auf der linken Seite einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="33d0a-103">You store a value in a variable by putting the variable name on the left side of an assignment statement.</span></span>  
  
## <a name="putting-data-in-a-variable"></a><span data-ttu-id="33d0a-104">Einfügen von Daten in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="33d0a-104">Putting Data in a Variable</span></span>  
  
#### <a name="to-store-a-value-in-a-variable"></a><span data-ttu-id="33d0a-105">Zum Speichern eines Werts in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="33d0a-105">To store a value in a variable</span></span>  
  
-   <span data-ttu-id="33d0a-106">Verwenden Sie den Variablennamen an, auf der linken Seite einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="33d0a-106">Use the variable name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="33d0a-107">Im folgenden Beispiel wird den Wert der Variablen `alpha`.</span><span class="sxs-lookup"><span data-stu-id="33d0a-107">The following example sets the value of the variable `alpha`.</span></span>  
  
    ```  
    alpha = (beta * 6.27) / (gamma + 2.1)  
    ```  
  
     <span data-ttu-id="33d0a-108">Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="33d0a-108">The value generated on the right side of the assignment statement is stored in the variable.</span></span>  
  
## <a name="getting-data-from-a-variable"></a><span data-ttu-id="33d0a-109">Abrufen von Daten aus einer Variablen</span><span class="sxs-lookup"><span data-stu-id="33d0a-109">Getting Data from a Variable</span></span>  
 <span data-ttu-id="33d0a-110">Rufen Sie die Werte einer Variable den Variablennamen in einen Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="33d0a-110">You retrieve a variable's value by including the variable name in an expression.</span></span>  
  
#### <a name="to-retrieve-a-value-from-a-variable"></a><span data-ttu-id="33d0a-111">Zum Abrufen eines Werts aus einer Variablen</span><span class="sxs-lookup"><span data-stu-id="33d0a-111">To retrieve a value from a variable</span></span>  
  
-   <span data-ttu-id="33d0a-112">Verwenden Sie den Variablennamen in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="33d0a-112">Use the variable name in an expression.</span></span> <span data-ttu-id="33d0a-113">Sie können eine Variable an einer beliebigen Stelle können Sie eine Konstante oder ein Literal außer in einem Ausdruck, der den Wert einer Konstante definiert.</span><span class="sxs-lookup"><span data-stu-id="33d0a-113">You can use a variable anywhere you can use a constant or a literal, except in an expression that defines the value of a constant.</span></span>  
  
     <span data-ttu-id="33d0a-114">- oder - </span><span class="sxs-lookup"><span data-stu-id="33d0a-114">-or-</span></span>  
  
-   <span data-ttu-id="33d0a-115">Verwenden Sie den Variablennamen, die nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung signieren.</span><span class="sxs-lookup"><span data-stu-id="33d0a-115">Use the variable name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="33d0a-116">Das folgende Beispiel liest den Wert der Variablen `startValue` und verwendet dann den Wert der Variablen `counter` in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="33d0a-116">The following example reads the value of the variable `startValue` and then uses the value of the variable `counter` in an expression.</span></span>  
  
    ```  
    counter = startValue  
    cellValue = (counter + 5) ^ 2  
    ```  
  
     <span data-ttu-id="33d0a-117">Der Wert der Variablen teilnimmt im Ausdruck, ebenso wie eine Konstante ist, und klicken Sie dann in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="33d0a-117">The value of the variable participates in the expression just as a constant would, and then it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33d0a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33d0a-118">See Also</span></span>  
 [<span data-ttu-id="33d0a-119">Variablen</span><span class="sxs-lookup"><span data-stu-id="33d0a-119">Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [<span data-ttu-id="33d0a-120">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="33d0a-120">Variable Declaration</span></span>](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [<span data-ttu-id="33d0a-121">Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="33d0a-121">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
