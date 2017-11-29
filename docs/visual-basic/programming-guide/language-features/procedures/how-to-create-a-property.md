---
title: 'Gewusst wie: Erstellen einer Eigenschaft (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, properties
- properties [Visual Basic]
ms.assetid: 4d229712-6be8-4c5c-bac5-06995ce9185a
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d140e6a10061f7fabe3d12c6cce5d0c201e103d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-property-visual-basic"></a><span data-ttu-id="5a59e-102">Gewusst wie: Erstellen einer Eigenschaft (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a59e-102">How to: Create a Property (Visual Basic)</span></span>
<span data-ttu-id="5a59e-103">Sie setzen eine Eigenschaftsdefinition zwischen einer `Property` Anweisung und eine `End Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5a59e-103">You enclose a property definition between a `Property` statement and an `End Property` statement.</span></span> <span data-ttu-id="5a59e-104">Innerhalb dieser Definition, die Sie definieren eine `Get` Prozedur, eine `Set` Prozedur oder beides.</span><span class="sxs-lookup"><span data-stu-id="5a59e-104">Within this definition you define a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="5a59e-105">Alle Eigenschaft Code ist in diesen Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="5a59e-105">All the property's code lies within these procedures.</span></span>  
  
 <span data-ttu-id="5a59e-106">Die `Get` Prozedur ruft den Wert der Eigenschaft ab, und die `Set` Prozedur speichert einen Wert.</span><span class="sxs-lookup"><span data-stu-id="5a59e-106">The `Get` procedure retrieves the property's value, and the `Set` procedure stores a value.</span></span> <span data-ttu-id="5a59e-107">Wenn Sie die Eigenschaft Lese-/Schreibzugriff verfügen soll, müssen Sie beide Prozeduren definieren.</span><span class="sxs-lookup"><span data-stu-id="5a59e-107">If you want the property to have read/write access, you must define both procedures.</span></span> <span data-ttu-id="5a59e-108">Für eine schreibgeschützte Eigenschaft, definieren Sie nur `Get`, und für eine WriteOnly-Eigenschaft, definieren Sie nur `Set`.</span><span class="sxs-lookup"><span data-stu-id="5a59e-108">For a read-only property, you define only `Get`, and for a write-only property, you define only `Set`.</span></span>  
  
### <a name="to-create-a-property"></a><span data-ttu-id="5a59e-109">So erstellen Sie eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5a59e-109">To create a property</span></span>  
  
1.  <span data-ttu-id="5a59e-110">Außerhalb einer Eigenschaft oder Prozedur verwendet eine [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md), gefolgt von einem `End Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5a59e-110">Outside any property or procedure, use a [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md), followed by an `End Property` statement.</span></span>  
  
2.  <span data-ttu-id="5a59e-111">Wenn die Eigenschaft Parameter annimmt, führen Sie die `Property` Schlüsselwort mit dem Namen der Prozedur, und klicken Sie dann auf die Parameterliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="5a59e-111">If the property takes parameters, follow the `Property` keyword with the name of the procedure, then the parameter list in parentheses.</span></span>  
  
3.  <span data-ttu-id="5a59e-112">Führen Sie die Klammern mit einer `As` -Klausel, um den Datentyp des Werts der Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="5a59e-112">Follow the parentheses with an `As` clause to specify the data type of the property's value.</span></span> <span data-ttu-id="5a59e-113">Sie müssen den Datentyp auch für eine WriteOnly-Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="5a59e-113">You must specify the data type even for a write-only property.</span></span>  
  
4.  <span data-ttu-id="5a59e-114">Hinzufügen `Get` und `Set` Prozeduren nach Bedarf.</span><span class="sxs-lookup"><span data-stu-id="5a59e-114">Add `Get` and `Set` procedures, as appropriate.</span></span> <span data-ttu-id="5a59e-115">Finden Sie unter den folgenden Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="5a59e-115">See the following directions.</span></span>  
  
### <a name="to-create-a-get-procedure-that-retrieves-a-property-value"></a><span data-ttu-id="5a59e-116">Zum Erstellen einer Get-Prozedur, die einen Eigenschaftswert abruft.</span><span class="sxs-lookup"><span data-stu-id="5a59e-116">To create a Get procedure that retrieves a property value</span></span>  
  
1.  <span data-ttu-id="5a59e-117">Zwischen der `Property` und `End Property` -Anweisungen Schreiben einer [Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md), gefolgt von einer `End Get` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5a59e-117">Between the `Property` and `End Property` statements, write a [Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md), followed by an `End Get` statement.</span></span> <span data-ttu-id="5a59e-118">Sie müssen keine Parameter für definieren die `Get` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="5a59e-118">You do not need to define any parameters for the `Get` procedure.</span></span>  
  
2.  <span data-ttu-id="5a59e-119">Platzieren Sie die codeanweisungen zum Abrufen des Eigenschaftswerts zwischen den `Get` und `End Get` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="5a59e-119">Place the code statements to retrieve the property's value between the `Get` and `End Get` statements.</span></span> <span data-ttu-id="5a59e-120">Dieser Code kann andere Berechnungen und Datenmanipulationen zusätzlich zu generieren und den Wert der Eigenschaft zurückgeben enthalten.</span><span class="sxs-lookup"><span data-stu-id="5a59e-120">This code can include other calculations and data manipulations in addition to generating and returning the property's value.</span></span>  
  
3.  <span data-ttu-id="5a59e-121">Verwenden einer `Return` -Anweisung den Wert der Eigenschaft an den aufrufenden Code zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5a59e-121">Use a `Return` statement to return the property's value to the calling code.</span></span>  
  
 <span data-ttu-id="5a59e-122">Sie schreiben eine `Get` Prozedur für eine Eigenschaft Lese-/ Schreibzugriff und für eine schreibgeschützte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5a59e-122">You must write a `Get` procedure for a read-write property and for a read-only property.</span></span> <span data-ttu-id="5a59e-123">Sie müssen nicht definieren eine `Get` Prozedur für eine WriteOnly-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5a59e-123">You must not define a `Get` procedure for a write-only property.</span></span>  
  
### <a name="to-create-a-set-procedure-that-writes-a-propertys-value"></a><span data-ttu-id="5a59e-124">So erstellen Sie eine Set-Prozedur schreibt, die den Wert einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5a59e-124">To create a Set procedure that writes a property's value</span></span>  
  
1.  <span data-ttu-id="5a59e-125">Zwischen der `Property` und `End Property` -Anweisungen Schreiben einer [Set-Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md), gefolgt von einer `End Set` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="5a59e-125">Between the `Property` and `End Property` statements, write a [Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md), followed by an `End Set` statement.</span></span>  
  
2.  <span data-ttu-id="5a59e-126">In der `Set` -Anweisung, befolgen Sie die `Set` Schlüsselwort in einer Parameterliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="5a59e-126">In the `Set` statement, follow the `Set` keyword with a parameter list in parentheses.</span></span> <span data-ttu-id="5a59e-127">Diese Parameterliste muss mindestens ein Werteparameter für die vom aufrufenden Code übergebene Wert enthalten.</span><span class="sxs-lookup"><span data-stu-id="5a59e-127">This parameter list must include at least a value parameter for the value passed by the calling code.</span></span> <span data-ttu-id="5a59e-128">Der Standardname für diesen Wertparameter lautet `Value`, aber Sie können einen anderen Namen verwenden, falls zutreffend.</span><span class="sxs-lookup"><span data-stu-id="5a59e-128">The default name for this value parameter is `Value`, but you can use a different name if appropriate.</span></span> <span data-ttu-id="5a59e-129">Der Value-Parameter muss den gleichen Datentyp wie die Eigenschaft selbst verfügen.</span><span class="sxs-lookup"><span data-stu-id="5a59e-129">The value parameter must have the same data type as the property itself.</span></span>  
  
3.  <span data-ttu-id="5a59e-130">Platzieren Sie die codeanweisungen zum Speichern eines Werts in der Eigenschaft zwischen den `Set` und `End Set` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="5a59e-130">Place the code statements to store a value in the property between the `Set` and `End Set` statements.</span></span> <span data-ttu-id="5a59e-131">Dieser Code kann andere Berechnungen und Datenmanipulationen zusätzlich zu überprüfen, und speichern den Wert der Eigenschaft enthalten.</span><span class="sxs-lookup"><span data-stu-id="5a59e-131">This code can include other calculations and data manipulations in addition to validating and storing the property's value.</span></span>  
  
4.  <span data-ttu-id="5a59e-132">Verwenden Sie den Value-Parameter, um den Wert des aufrufenden Codes nicht annehmen.</span><span class="sxs-lookup"><span data-stu-id="5a59e-132">Use the value parameter to accept the value supplied by the calling code.</span></span> <span data-ttu-id="5a59e-133">Sie können entweder speichern den Wert direkt in einer zuweisungsanweisung, oder sie in einem Ausdruck verwenden, berechnen Sie den internen Wert gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="5a59e-133">You can either store this value directly in an assignment statement, or use it in an expression to calculate the internal value to be stored.</span></span>  
  
 <span data-ttu-id="5a59e-134">Sie schreiben eine `Set` Prozedur für eine Eigenschaft Lese-/ Schreibzugriff und für eine WriteOnly-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5a59e-134">You must write a `Set` procedure for a read-write property and for a write-only property.</span></span> <span data-ttu-id="5a59e-135">Sie müssen nicht definieren eine `Set` Prozedur für eine schreibgeschützte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5a59e-135">You must not define a `Set` procedure for a read-only property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a59e-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5a59e-136">Example</span></span>  
 <span data-ttu-id="5a59e-137">Das folgende Beispiel erstellt eine Lese-/Schreibzugriff-Eigenschaft, die einen vollständigen Namen als zwei konstituierende Namen, den Vornamen und den Nachnamen des speichert.</span><span class="sxs-lookup"><span data-stu-id="5a59e-137">The following example creates a read/write property that stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="5a59e-138">Wenn der aufrufende Code liest `fullName`die `Get` Prozedur kombiniert die beiden konstituierenden Namen und gibt den vollständigen Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="5a59e-138">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="5a59e-139">Wenn der aufrufende Code einen neuen vollständigen Name weist das `Set` Prozedur versucht, die sie in zwei konstituierende Namen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="5a59e-139">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="5a59e-140">Wenn sie ein Leerzeichen nicht gefunden wird, wird er alle als den Vornamen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5a59e-140">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/how-to-create-a-property_1.vb)]  
  
 <span data-ttu-id="5a59e-141">Das folgende Beispiel zeigt typische Aufrufe der Eigenschaftenprozeduren `fullName`.</span><span class="sxs-lookup"><span data-stu-id="5a59e-141">The following example shows typical calls to the property procedures of `fullName`.</span></span> <span data-ttu-id="5a59e-142">Der erste Aufruf legt den Eigenschaftswert fest, und der zweite Aufruf abgerufen.</span><span class="sxs-lookup"><span data-stu-id="5a59e-142">The first call sets the property value and the second call retrieves it.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/how-to-create-a-property_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5a59e-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a59e-143">See Also</span></span>  
 [<span data-ttu-id="5a59e-144">Verfahren</span><span class="sxs-lookup"><span data-stu-id="5a59e-144">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="5a59e-145">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="5a59e-145">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="5a59e-146">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="5a59e-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="5a59e-147">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a59e-147">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="5a59e-148">Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="5a59e-148">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="5a59e-149">Gewusst wie: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="5a59e-149">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="5a59e-150">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a59e-150">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="5a59e-151">Gewusst wie: Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5a59e-151">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="5a59e-152">Gewusst wie: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5a59e-152">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
