---
title: 'Gewusst wie: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 9f97669e8d18e7fc633cb0e691d973a611a8cea0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648407"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a><span data-ttu-id="20436-102">Gewusst wie: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20436-102">How to: Get a Value from a Property (Visual Basic)</span></span>
<span data-ttu-id="20436-103">Rufen Sie den Wert einer Eigenschaft den Namen der Eigenschaft in einen Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="20436-103">You retrieve a property's value by including the property name in an expression.</span></span>  
  
 <span data-ttu-id="20436-104">Der Eigenschaft `Get` Prozedur ruft den Wert ab, aber Sie rufen sie nicht explizit nach Namen.</span><span class="sxs-lookup"><span data-stu-id="20436-104">The property's `Get` procedure retrieves the value, but you do not explicitly call it by name.</span></span> <span data-ttu-id="20436-105">Sie können die Eigenschaft verwenden, wie Sie eine Variable verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="20436-105">You use the property just as you would use a variable.</span></span> <span data-ttu-id="20436-106">Visual Basic ermöglicht die Aufrufe an die Eigenschaftenprozeduren.</span><span class="sxs-lookup"><span data-stu-id="20436-106">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-retrieve-a-value-from-a-property"></a><span data-ttu-id="20436-107">Zum Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="20436-107">To retrieve a value from a property</span></span>  
  
1.  <span data-ttu-id="20436-108">Verwenden Sie den Namen der Eigenschaft in einem Ausdruck die gleiche Weise wie ein Variablenname.</span><span class="sxs-lookup"><span data-stu-id="20436-108">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="20436-109">Sie können eine Eigenschaft an einer beliebigen Stelle können Sie eine Variable oder eine Konstante.</span><span class="sxs-lookup"><span data-stu-id="20436-109">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="20436-110">- oder - </span><span class="sxs-lookup"><span data-stu-id="20436-110">-or-</span></span>  
  
     <span data-ttu-id="20436-111">Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung signieren.</span><span class="sxs-lookup"><span data-stu-id="20436-111">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="20436-112">Das folgende Beispiel liest den Wert der Visual Basic `Now` Eigenschaft implizit Aufrufen seiner `Get` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="20436-112">The following example reads the value of the Visual Basic `Now` property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  <span data-ttu-id="20436-113">Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="20436-113">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="20436-114">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="20436-114">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="20436-115">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="20436-115">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="20436-116">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="20436-116">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="20436-117">Der Wert der Eigenschaft beteiligt ist, in dem Ausdruck ebenso wie eine Variable oder Konstante oder befindet sich in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="20436-117">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20436-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20436-118">See Also</span></span>  
 [<span data-ttu-id="20436-119">Verfahren</span><span class="sxs-lookup"><span data-stu-id="20436-119">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="20436-120">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="20436-120">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="20436-121">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="20436-121">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="20436-122">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="20436-122">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="20436-123">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20436-123">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="20436-124">Gewusst wie: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="20436-124">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="20436-125">Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="20436-125">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="20436-126">Gewusst wie: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="20436-126">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="20436-127">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="20436-127">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="20436-128">Gewusst wie: Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="20436-128">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
