---
title: 'Vorgehensweise: Aufrufen einer Eigenschaftenprozedur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 1f8871c2cc5126110fa849d42eed3d8edb3a03f5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602571"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="d4a86-102">Vorgehensweise: Aufrufen einer Eigenschaftenprozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4a86-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="d4a86-103">Sie aufrufen eine Eigenschaftenprozedur zum Speichern eines Werts in der Eigenschaft oder der Wert abgerufen.</span><span class="sxs-lookup"><span data-stu-id="d4a86-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="d4a86-104">Sie Zugriff auf eine Eigenschaft die gleiche Weise, die Sie eine Variable zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d4a86-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="d4a86-105">Des Eigenschaftenwert `Set` Prozedur speichert einen Wert ein, und die zugehörige `Get` Prozedur ruft den Wert ab.</span><span class="sxs-lookup"><span data-stu-id="d4a86-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="d4a86-106">Allerdings sind Sie nicht explizit dazu anhand des Namens aufrufen.</span><span class="sxs-lookup"><span data-stu-id="d4a86-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="d4a86-107">Verwenden Sie die Eigenschaft in einer zuweisungsanweisung oder einem Ausdruck, wie würden Sie speichern oder des Werts einer Variablen abrufen.</span><span class="sxs-lookup"><span data-stu-id="d4a86-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="d4a86-108">Visual Basic ermöglicht, die Aufrufe an die Prozeduren der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d4a86-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="d4a86-109">Zum Aufrufen einer Eigenschaft Get-Prozedur</span><span class="sxs-lookup"><span data-stu-id="d4a86-109">To call a property's Get procedure</span></span>  
  
1.  <span data-ttu-id="d4a86-110">Verwenden Sie die Namen der Eigenschaft in einem Ausdruck die gleiche Weise, die Sie einen Variablennamen verwenden würden.</span><span class="sxs-lookup"><span data-stu-id="d4a86-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="d4a86-111">Sie können eine Eigenschaft an einer beliebigen Stelle können Sie eine Variable oder eine Konstante.</span><span class="sxs-lookup"><span data-stu-id="d4a86-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="d4a86-112">- oder - </span><span class="sxs-lookup"><span data-stu-id="d4a86-112">-or-</span></span>  
  
     <span data-ttu-id="d4a86-113">Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung anmelden.</span><span class="sxs-lookup"><span data-stu-id="d4a86-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="d4a86-114">Das folgende Beispiel liest den Wert des der <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> implizit aufrufen-Eigenschaft der `Get` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="d4a86-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  <span data-ttu-id="d4a86-115">Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="d4a86-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="d4a86-116">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="d4a86-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="d4a86-117">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="d4a86-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="d4a86-118">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft über die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="d4a86-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="d4a86-119">Der Wert der Eigenschaft ist Teil des Ausdrucks wie eine Variable oder Konstante würde, oder es befindet sich in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="d4a86-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="d4a86-120">Um eine Eigenschaft Aufrufen der Prozedur festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d4a86-120">To call a property's Set procedure</span></span>  
  
1.  <span data-ttu-id="d4a86-121">Verwenden Sie den Eigenschaftennamen, auf der linken Seite einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="d4a86-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="d4a86-122">Im folgenden Beispiel wird den Wert des der <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> implizit aufrufen-Eigenschaft der `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="d4a86-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  <span data-ttu-id="d4a86-123">Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="d4a86-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="d4a86-124">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="d4a86-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="d4a86-125">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="d4a86-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="d4a86-126">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft über die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="d4a86-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="d4a86-127">Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Eigenschaft gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d4a86-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4a86-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4a86-128">See also</span></span>
- [<span data-ttu-id="d4a86-129">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="d4a86-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="d4a86-130">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="d4a86-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="d4a86-131">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d4a86-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="d4a86-132">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4a86-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="d4a86-133">Vorgehensweise: Erstellen Sie eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d4a86-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="d4a86-134">Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="d4a86-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="d4a86-135">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d4a86-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="d4a86-136">Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d4a86-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="d4a86-137">Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="d4a86-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="d4a86-138">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d4a86-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="d4a86-139">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="d4a86-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
