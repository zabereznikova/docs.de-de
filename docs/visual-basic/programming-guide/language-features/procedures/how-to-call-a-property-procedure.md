---
title: 'Gewusst wie: Aufrufen einer Eigenschaftenprozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 52e6c62ffb81c480ccc1abf06f04eb780218dbf1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340551"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="32bc8-102">Gewusst wie: Aufrufen einer Eigenschaftenprozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="32bc8-102">How to: Call a Property Procedure (Visual Basic)</span></span>
<span data-ttu-id="32bc8-103">Sie rufen eine Eigenschaften Prozedur auf, indem Sie einen Wert in der Eigenschaft speichern oder den Wert abrufen.</span><span class="sxs-lookup"><span data-stu-id="32bc8-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="32bc8-104">Sie greifen auf eine Eigenschaft genauso zu, wie Sie auf eine Variable zugreifen.</span><span class="sxs-lookup"><span data-stu-id="32bc8-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="32bc8-105">Die `Set` Prozedur der Eigenschaft speichert einen Wert, und die `Get` Prozedur ruft den Wert ab.</span><span class="sxs-lookup"><span data-stu-id="32bc8-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="32bc8-106">Diese Prozeduren werden jedoch nicht explizit anhand ihres Namens aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="32bc8-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="32bc8-107">Sie verwenden die-Eigenschaft in einer Zuweisungsanweisung oder einem Ausdruck, genauso wie Sie den Wert einer Variablen speichern oder abrufen.</span><span class="sxs-lookup"><span data-stu-id="32bc8-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="32bc8-108">Visual Basic führt die Aufrufe der Prozeduren der Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="32bc8-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="32bc8-109">So wenden Sie die Get-Prozedur einer Eigenschaft an</span><span class="sxs-lookup"><span data-stu-id="32bc8-109">To call a property's Get procedure</span></span>  
  
1. <span data-ttu-id="32bc8-110">Verwenden Sie den Eigenschaftsnamen in einem Ausdruck auf die gleiche Weise wie einen Variablennamen.</span><span class="sxs-lookup"><span data-stu-id="32bc8-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="32bc8-111">Sie können eine Eigenschaft überall dort verwenden, wo Sie eine Variable oder eine Konstante verwenden können.</span><span class="sxs-lookup"><span data-stu-id="32bc8-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="32bc8-112">\- oder -</span><span class="sxs-lookup"><span data-stu-id="32bc8-112">-or-</span></span>  
  
     <span data-ttu-id="32bc8-113">Verwenden Sie den Eigenschaftsnamen nach dem Gleichheitszeichen (`=`) in einer Zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="32bc8-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="32bc8-114">Im folgenden Beispiel wird der Wert der <xref:Microsoft.VisualBasic.DateAndTime.Now%2A>-Eigenschaft gelesen, wobei die `Get` Prozedur implizit aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="32bc8-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="32bc8-115">Wenn die Eigenschaft Argumente annimmt, befolgen Sie den Eigenschaftsnamen mit Klammern, um die Argumentliste einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="32bc8-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="32bc8-116">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="32bc8-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="32bc8-117">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="32bc8-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="32bc8-118">Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die-Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="32bc8-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="32bc8-119">Der Wert der Eigenschaft nimmt an dem Ausdruck genau so ein, wie eine Variable oder Konstante, oder er wird in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="32bc8-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="32bc8-120">So wenden Sie die Set-Prozedur einer Eigenschaft an</span><span class="sxs-lookup"><span data-stu-id="32bc8-120">To call a property's Set procedure</span></span>  
  
1. <span data-ttu-id="32bc8-121">Verwenden Sie den Eigenschaftsnamen auf der linken Seite einer Zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="32bc8-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="32bc8-122">Im folgenden Beispiel wird der Wert der <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>-Eigenschaft festgelegt, wobei der `Set` Prozedur implizit aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="32bc8-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="32bc8-123">Wenn die Eigenschaft Argumente annimmt, befolgen Sie den Eigenschaftsnamen mit Klammern, um die Argumentliste einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="32bc8-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="32bc8-124">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="32bc8-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="32bc8-125">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="32bc8-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="32bc8-126">Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die-Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="32bc8-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="32bc8-127">Der auf der rechten Seite der Zuweisungsanweisung generierte Wert wird in der-Eigenschaft gespeichert.</span><span class="sxs-lookup"><span data-stu-id="32bc8-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32bc8-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32bc8-128">See also</span></span>

- [<span data-ttu-id="32bc8-129">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="32bc8-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="32bc8-130">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="32bc8-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="32bc8-131">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="32bc8-131">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="32bc8-132">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32bc8-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="32bc8-133">Gewusst wie: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="32bc8-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="32bc8-134">Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="32bc8-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="32bc8-135">Vorgehensweise: Deklarieren und Abrufen einer Standard Eigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="32bc8-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="32bc8-136">Gewusst wie: Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="32bc8-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="32bc8-137">Gewusst wie: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="32bc8-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="32bc8-138">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="32bc8-138">Get Statement</span></span>](../../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="32bc8-139">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="32bc8-139">Set Statement</span></span>](../../../../visual-basic/language-reference/statements/set-statement.md)
