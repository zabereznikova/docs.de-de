---
title: 'Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: de5719527216411c7bd156f2cc0d369442eaee20
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56964772"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="d687d-102">Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d687d-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="d687d-103">Sie rufen den Wert einer Eigenschaft, indem Sie den Eigenschaftennamen in einen Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="d687d-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="d687d-104">Des Eigenschaftenwert `Get` Prozedur ruft den Wert ab, aber Sie rufen sie nicht explizit anhand des Namens.</span><span class="sxs-lookup"><span data-stu-id="d687d-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="d687d-105">Verwenden Sie die Eigenschaft, genauso wie Sie eine Variable.</span><span class="sxs-lookup"><span data-stu-id="d687d-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="d687d-106">Visual Basic ermöglicht, die Aufrufe an die Prozeduren der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d687d-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="d687d-107">Zum Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d687d-107">To retrieve a value from a property</span></span>  
  
1.  <span data-ttu-id="d687d-108">Verwenden Sie die Namen der Eigenschaft in einem Ausdruck die gleiche Weise, die Sie einen Variablennamen verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="d687d-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="d687d-109">Sie können eine Eigenschaft an einer beliebigen Stelle können Sie eine Variable oder eine Konstante.</span><span class="sxs-lookup"><span data-stu-id="d687d-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="d687d-110">- oder - </span><span class="sxs-lookup"><span data-stu-id="d687d-110">-or-</span></span>  
  
     <span data-ttu-id="d687d-111">Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung anmelden.</span><span class="sxs-lookup"><span data-stu-id="d687d-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="d687d-112">Das folgende Beispiel liest den Wert der Visual Basic `Now` implizit aufrufen-Eigenschaft der `Get` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="d687d-112">The following example reads the value of the Visual Basic `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2.  <span data-ttu-id="d687d-113">Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="d687d-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="d687d-114">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="d687d-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="d687d-115">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="d687d-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="d687d-116">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft über die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="d687d-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="d687d-117">Der Wert der Eigenschaft ist Teil des Ausdrucks wie eine Variable oder Konstante würde, oder es befindet sich in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="d687d-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d687d-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d687d-118">See also</span></span>
- [<span data-ttu-id="d687d-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="d687d-119">Procedures</span></span>](./index.md)
- [<span data-ttu-id="d687d-120">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="d687d-120">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="d687d-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="d687d-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d687d-122">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d687d-122">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="d687d-123">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d687d-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="d687d-124">Vorgehensweise: Erstellen Sie eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d687d-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="d687d-125">Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="d687d-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="d687d-126">Vorgehensweise: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="d687d-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="d687d-127">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d687d-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="d687d-128">Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d687d-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
