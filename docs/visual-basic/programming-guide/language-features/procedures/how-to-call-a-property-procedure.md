---
title: 'Vorgehensweise: Aufrufen einer Eigenschaftenprozedur'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 0b35751136937d4cee5b3ca9669b43d3fbdf71a1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071950"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a><span data-ttu-id="1c5ed-102">Gewusst wie: Aufrufen einer Eigenschaftenprozedur (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1c5ed-102">How to: Call a Property Procedure (Visual Basic)</span></span>

<span data-ttu-id="1c5ed-103">Sie rufen eine Eigenschaften Prozedur auf, indem Sie einen Wert in der Eigenschaft speichern oder den Wert abrufen.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-103">You call a property procedure by storing a value in the property or retrieving its value.</span></span> <span data-ttu-id="1c5ed-104">Sie greifen auf eine Eigenschaft genauso zu, wie Sie auf eine Variable zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-104">You access a property the same way you access a variable.</span></span>  
  
 <span data-ttu-id="1c5ed-105">Die-Prozedur der Eigenschaft `Set` speichert einen Wert, und `Get` die Prozedur ruft den Wert ab.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-105">The property's `Set` procedure stores a value, and its `Get` procedure retrieves the value.</span></span> <span data-ttu-id="1c5ed-106">Diese Prozeduren werden jedoch nicht explizit anhand ihres Namens aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-106">However, you do not explicitly call these procedures by name.</span></span> <span data-ttu-id="1c5ed-107">Sie verwenden die-Eigenschaft in einer Zuweisungsanweisung oder einem Ausdruck, genauso wie Sie den Wert einer Variablen speichern oder abrufen.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-107">You use the property in an assignment statement or an expression, just as you would store or retrieve the value of a variable.</span></span> <span data-ttu-id="1c5ed-108">Visual Basic führt die Aufrufe der Prozeduren der Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-108">Visual Basic makes the calls to the property's procedures.</span></span>  
  
### <a name="to-call-a-propertys-get-procedure"></a><span data-ttu-id="1c5ed-109">So wenden Sie die Get-Prozedur einer Eigenschaft an</span><span class="sxs-lookup"><span data-stu-id="1c5ed-109">To call a property's Get procedure</span></span>  
  
1. <span data-ttu-id="1c5ed-110">Verwenden Sie den Eigenschaftsnamen in einem Ausdruck auf die gleiche Weise wie einen Variablennamen.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-110">Use the property name in an expression the same way you would use a variable name.</span></span> <span data-ttu-id="1c5ed-111">Sie können eine Eigenschaft überall dort verwenden, wo Sie eine Variable oder eine Konstante verwenden können.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-111">You can use a property anywhere you can use a variable or a constant.</span></span>  
  
     <span data-ttu-id="1c5ed-112">- oder -</span><span class="sxs-lookup"><span data-stu-id="1c5ed-112">-or-</span></span>  
  
     <span data-ttu-id="1c5ed-113">Verwenden Sie den Eigenschaftsnamen nach dem Gleichheits `=` Zeichen () in einer Zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-113">Use the property name following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="1c5ed-114">Im folgenden Beispiel wird der Wert der- <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> Eigenschaft gelesen, wobei die Prozedur implizit aufgerufen wird `Get` .</span><span class="sxs-lookup"><span data-stu-id="1c5ed-114">The following example reads the value of the <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> property, implicitly calling its `Get` procedure.</span></span>  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. <span data-ttu-id="1c5ed-115">Wenn die Eigenschaft Argumente annimmt, befolgen Sie den Eigenschaftsnamen mit Klammern, um die Argumentliste einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-115">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="1c5ed-116">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-116">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="1c5ed-117">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-117">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="1c5ed-118">Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die-Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-118">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="1c5ed-119">Der Wert der Eigenschaft nimmt an dem Ausdruck genau so ein, wie eine Variable oder Konstante, oder er wird in der Variablen oder der Eigenschaft auf der linken Seite der Zuweisungsanweisung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-119">The value of the property participates in the expression just as a variable or constant would, or it is stored in the variable or property on the left side of the assignment statement.</span></span>  
  
### <a name="to-call-a-propertys-set-procedure"></a><span data-ttu-id="1c5ed-120">So wenden Sie die Set-Prozedur einer Eigenschaft an</span><span class="sxs-lookup"><span data-stu-id="1c5ed-120">To call a property's Set procedure</span></span>  
  
1. <span data-ttu-id="1c5ed-121">Verwenden Sie den Eigenschaftsnamen auf der linken Seite einer Zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-121">Use the property name on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="1c5ed-122">Im folgenden Beispiel wird der Wert der- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> Eigenschaft festgelegt, der implizit die-Prozedur aufruft `Set` .</span><span class="sxs-lookup"><span data-stu-id="1c5ed-122">The following example sets the value of the <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> property, implicitly calling the `Set` procedure.</span></span>  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. <span data-ttu-id="1c5ed-123">Wenn die Eigenschaft Argumente annimmt, befolgen Sie den Eigenschaftsnamen mit Klammern, um die Argumentliste einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-123">If the property takes arguments, follow the property name with parentheses to enclose the argument list.</span></span> <span data-ttu-id="1c5ed-124">Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-124">If there are no arguments, you can optionally omit the parentheses.</span></span>  
  
3. <span data-ttu-id="1c5ed-125">Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern, getrennt durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-125">Place the arguments in the argument list within the parentheses, separated by commas.</span></span> <span data-ttu-id="1c5ed-126">Stellen Sie sicher, dass Sie die Argumente in derselben Reihenfolge bereitstellen, in der die-Eigenschaft die entsprechenden Parameter definiert.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-126">Be sure you supply the arguments in the same order that the property defines the corresponding parameters.</span></span>  
  
 <span data-ttu-id="1c5ed-127">Der auf der rechten Seite der Zuweisungsanweisung generierte Wert wird in der-Eigenschaft gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1c5ed-127">The value generated on the right side of the assignment statement is stored in the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c5ed-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1c5ed-128">See also</span></span>

- [<span data-ttu-id="1c5ed-129">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="1c5ed-129">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="1c5ed-130">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="1c5ed-130">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="1c5ed-131">Property Statement</span><span class="sxs-lookup"><span data-stu-id="1c5ed-131">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="1c5ed-132">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c5ed-132">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="1c5ed-133">Vorgehensweise: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1c5ed-133">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="1c5ed-134">Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="1c5ed-134">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="1c5ed-135">Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c5ed-135">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="1c5ed-136">Vorgehensweise: Ablegen eines Werts in eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1c5ed-136">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="1c5ed-137">Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1c5ed-137">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
- [<span data-ttu-id="1c5ed-138">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1c5ed-138">Get Statement</span></span>](../../../language-reference/statements/get-statement.md)
- [<span data-ttu-id="1c5ed-139">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1c5ed-139">Set Statement</span></span>](../../../language-reference/statements/set-statement.md)
