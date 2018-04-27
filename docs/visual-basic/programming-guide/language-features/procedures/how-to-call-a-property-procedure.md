---
title: 'Gewusst wie: Aufrufen einer Eigenschaftenprozedur (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38b3704328916a487f94879ea0096ae923f19082
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="bdc47-102">Gewusst wie: Aufrufen einer Eigenschaftenprozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bdc47-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="bdc47-103">Zum Aufrufen einer Eigenschaftenprozedur zum Speichern eines Werts in der Eigenschaft oder der Wert abgerufen.</span><span class="sxs-lookup"><span data-stu-id="bdc47-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="bdc47-104">Eine Eigenschaft die gleiche Weise, die Sie Zugriff auf eine Variable zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="bdc47-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="bdc47-105">Der Eigenschaft `Set` Prozedur speichert einen Wert ein, und die zugehörige `Get` Prozedur ruft den Wert ab.</span><span class="sxs-lookup"><span data-stu-id="bdc47-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="bdc47-106">Allerdings sind Sie nicht explizit diese Prozeduren anhand des Namens aufrufen.</span><span class="sxs-lookup"><span data-stu-id="bdc47-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="bdc47-107">Verwenden Sie die Eigenschaft in einer zuweisungsanweisung oder einen Ausdruck, wie würden Sie speichern oder des Werts einer Variablen abrufen.</span><span class="sxs-lookup"><span data-stu-id="bdc47-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="bdc47-108">Visual Basic ermöglicht die Aufrufe an die Eigenschaftenprozeduren.</span><span class="sxs-lookup"><span data-stu-id="bdc47-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="bdc47-109">Aufrufen einer Eigenschaftenprozedur Get</span><span class="sxs-lookup"><span data-stu-id="bdc47-109">To call a property's Get procedure</span></span>  
  
1.  <span data-ttu-id="bdc47-110">Verwenden Sie den Namen der Eigenschaft in einem Ausdruck die gleiche Weise wie ein Variablenname.</span><span class="sxs-lookup"><span data-stu-id="bdc47-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="bdc47-111">Sie können eine Eigenschaft an einer beliebigen Stelle können Sie eine Variable oder eine Konstante.</span><span class="sxs-lookup"><span data-stu-id="bdc47-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="bdc47-112">- oder - </span><span class="sxs-lookup"><span data-stu-id="bdc47-112">-or-</span></span>  
  
     <span data-ttu-id="bdc47-113">Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung signieren.</span><span class="sxs-lookup"><span data-stu-id="bdc47-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="bdc47-114">Das folgende Beispiel liest den Wert der <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> Eigenschaft implizit Aufrufen seiner `Get` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="bdc47-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-call-a-property-procedure_1.vb)]  
  
2.  <span data-ttu-id="bdc47-115">Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="bdc47-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="bdc47-116">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="bdc47-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="bdc47-117">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="bdc47-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="bdc47-118">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="bdc47-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="bdc47-119">Der Wert der Eigenschaft beteiligt ist, in dem Ausdruck ebenso wie eine Variable oder Konstante oder befindet sich in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="bdc47-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="bdc47-120">Rufen Sie eine Eigenschaft auf die Prozedur festzulegen.</span><span class="sxs-lookup"><span data-stu-id="bdc47-120">To call a property's Set procedure</span></span>  
  
1.  <span data-ttu-id="bdc47-121">Verwenden Sie den Namen der Eigenschaft, auf der linken Seite einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="bdc47-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="bdc47-122">Im folgenden Beispiel wird den Wert von der <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> Eigenschaft implizit Aufrufen der `Set` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="bdc47-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](./codesnippet/VisualBasic/how-to-call-a-property-procedure_2.vb)]  
  
2.  <span data-ttu-id="bdc47-123">Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen.</span><span class="sxs-lookup"><span data-stu-id="bdc47-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="bdc47-124">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="bdc47-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3.  <span data-ttu-id="bdc47-125">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="bdc47-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="bdc47-126">Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="bdc47-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="bdc47-127">Der Wert, der auf der rechten Seite der Zuweisung generiert wird in der Eigenschaft gespeichert.</span><span class="sxs-lookup"><span data-stu-id="bdc47-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdc47-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdc47-128">See Also</span></span>  
 [<span data-ttu-id="bdc47-129">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="bdc47-129">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="bdc47-130">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="bdc47-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="bdc47-131">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bdc47-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="bdc47-132">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdc47-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="bdc47-133">Gewusst wie: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bdc47-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="bdc47-134">Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="bdc47-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="bdc47-135">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bdc47-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="bdc47-136">Gewusst wie: Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bdc47-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="bdc47-137">Gewusst wie: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bdc47-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)  
 [<span data-ttu-id="bdc47-138">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bdc47-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="bdc47-139">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="bdc47-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
