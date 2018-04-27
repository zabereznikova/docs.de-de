---
title: Eigenschaftenprozeduren (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- Set statement [Visual Basic], Property procedures
- Visual Basic code, procedures
- return values [Visual Basic], Property procedures
- syntax [Visual Basic], Property procedures
- procedures [Visual Basic], property
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], custom
- property procedures
- Get statement [Visual Basic], property procedures
ms.assetid: 46a98379-e1a2-45dd-a48c-b51213f5ab07
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0d9df6f381c89263aa16315fb06a2b3b0d645bbf
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="2d4c4-102">Eigenschaftenprozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d4c4-102">Property Procedures (Visual Basic)</span></span>
<span data-ttu-id="2d4c4-103">Eine Eigenschaftenprozedur ist eine Reihe von Visual Basic-Anweisungen, die eine benutzerdefinierte Eigenschaft für ein Modul, eine Klasse oder eine Struktur zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-103">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="2d4c4-104">-Eigenschaftenprozeduren werden auch bekannt als *Eigenschaftenaccessoren*.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-104">Property procedures are also known as *property accessors*.</span></span>  
  
 <span data-ttu-id="2d4c4-105">Visual Basic bietet die folgenden Eigenschaftenprozeduren:</span><span class="sxs-lookup"><span data-stu-id="2d4c4-105">Visual Basic provides for the following property procedures:</span></span>  
  
-   <span data-ttu-id="2d4c4-106">Ein `Get` Prozedur gibt den Wert einer Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="2d4c4-107">Sie wird aufgerufen, wenn Sie Zugriff auf die Eigenschaft in einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-107">It is called when you access the property in an expression.</span></span>  
  
-   <span data-ttu-id="2d4c4-108">Ein `Set` Prozedur wird eine Eigenschaft auf einen Wert, z. B. einen Objektverweis.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="2d4c4-109">Sie wird aufgerufen, wenn Sie die Eigenschaft einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-109">It is called when you assign a value to the property.</span></span>  
  
 <span data-ttu-id="2d4c4-110">Sie definieren Eigenschaftenprozeduren in der Regel paarweise mit der `Get` und `Set` -Anweisungen, aber Sie können auch einzeln definiert, wenn die Eigenschaft schreibgeschützt ist ([Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md)) oder lesegeschützt ([festlegen Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="2d4c4-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>  
  
 <span data-ttu-id="2d4c4-111">Sie lassen die `Get` und `Set` Verfahren, wenn Sie eine automatisch implementierte Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="2d4c4-112">Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](./auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2d4c4-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="2d4c4-113">Sie können Eigenschaften in Klassen, Strukturen und Module definieren.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="2d4c4-114">Eigenschaften sind `Public` standardmäßig, d. h. können von überall aus Anrufen in Ihrer Anwendung, die die Eigenschaft Container zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>  
  
 <span data-ttu-id="2d4c4-115">Einen Vergleich von Eigenschaften und Variablen, finden Sie unter [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="2d4c4-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md).</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="2d4c4-116">Deklarationssyntax</span><span class="sxs-lookup"><span data-stu-id="2d4c4-116">Declaration Syntax</span></span>  
 <span data-ttu-id="2d4c4-117">Eine Eigenschaft selbst wird durch einen Codeblock eingefasst definiert die [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md) und die `End Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="2d4c4-118">Innerhalb dieses Blocks erscheint jede-Eigenschaftenprozedur als interner Block, die in einer deklarationsanweisung eingeschlossen (`Get` oder `Set`) und die entsprechenden `End` Deklaration.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>  
  
 <span data-ttu-id="2d4c4-119">Die Syntax zum Deklarieren einer Eigenschaft und die zugehörigen Prozeduren lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2d4c4-119">The syntax for declaring a property and its procedures is as follows:</span></span>  
  
```  
[Default] [Modifiers] Property PropertyName[(ParameterList)] [As DataType]  
    [AccessLevel] Get  
        ' Statements of the Get procedure.  
        ' The following statement returns an expression as the property's value.  
        Return Expression  
    End Get  
    [AccessLevel] Set[(ByVal NewValue As DataType)]  
        ' Statements of the Set procedure.  
        ' The following statement assigns newvalue as the property's value.  
        LValue = NewValue  
    End Set  
End Property  
- or -  
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]  
```  
  
 <span data-ttu-id="2d4c4-120">Die `Modifiers` festlegbaren Zugriffsebene und Informationen zum Überladen, überschreiben, freigeben und shadowing, sowie, ob die Eigenschaft schreibgeschützt oder lesegeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="2d4c4-121">Die `AccessLevel` auf die `Get` oder `Set` Prozedur kann auf jeder Ebene, die restriktiver ist als die Zugriffsebene für die Eigenschaft selbst angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="2d4c4-122">Weitere Informationen finden Sie unter [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="2d4c4-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="2d4c4-123">Datentyp</span><span class="sxs-lookup"><span data-stu-id="2d4c4-123">Data Type</span></span>  
 <span data-ttu-id="2d4c4-124">Datentyp für eine Eigenschaft und die Zugriffsebene für Dienstprinzipalname werden definiert, der `Property` -Anweisung nicht in den Eigenschaftenprozeduren.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="2d4c4-125">Eine Eigenschaft kann nur einen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-125">A property can have only one data type.</span></span> <span data-ttu-id="2d4c4-126">Sie können nicht angenommen, eine Eigenschaft zum Speichern von definieren eine `Decimal` Wert aber abrufen eine `Double` Wert.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>  
  
### <a name="access-level"></a><span data-ttu-id="2d4c4-127">Zugriffsebene</span><span class="sxs-lookup"><span data-stu-id="2d4c4-127">Access Level</span></span>  
 <span data-ttu-id="2d4c4-128">Allerdings können Sie definieren eine principal Zugriffsebene für eine Eigenschaft und die Zugriffsebene in einer der Eigenschaftenprozeduren weiter einschränken.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="2d4c4-129">Beispielsweise können Sie definieren eine `Public` Eigenschaft definieren und anschließend eine `Private Set` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="2d4c4-130">Die `Get` Prozedur bleibt `Public`.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="2d4c4-131">Sie können die Zugriffsebene in nur einem der Verfahren für eine Eigenschaft ändern können, und Sie nur diese restriktiver als die Zugriffsebene für Dienstprinzipalname.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="2d4c4-132">Weitere Informationen finden Sie unter [wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="2d4c4-132">For more information, see [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="2d4c4-133">Parameterdeklaration</span><span class="sxs-lookup"><span data-stu-id="2d4c4-133">Parameter Declaration</span></span>  
 <span data-ttu-id="2d4c4-134">Deklarieren Sie jeden Parameter genauso wie Sie für [Sub-Prozeduren](./sub-procedures.md), außer dass der Übergabemechanismus Transportservers `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-134">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>  
  
 <span data-ttu-id="2d4c4-135">Die Syntax für jeden Parameter in der Parameterliste lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2d4c4-135">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 <span data-ttu-id="2d4c4-136">Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="2d4c4-137">Die Syntax zum Angeben der Standardwert lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2d4c4-137">The syntax for specifying a default value is as follows:</span></span>  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a><span data-ttu-id="2d4c4-138">Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="2d4c4-138">Property Value</span></span>  
 <span data-ttu-id="2d4c4-139">In einer `Get` Prozedur, den Rückgabewert mit dem aufrufenden Ausdruck wie den Wert der Eigenschaft angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>  
  
 <span data-ttu-id="2d4c4-140">In einem `Set` Prozedur, der neue Eigenschaftswert wird auf den Parameter übergeben der `Set` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="2d4c4-141">Wenn Sie einen Parameter explizit deklarieren, müssen Sie es mit dem gleichen Datentyp wie die Eigenschaft deklarieren.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="2d4c4-142">Wenn Sie kein Parameter deklariert, verwendet der Compiler impliziten Parameter `Value` zur Darstellung der neue Wert der Eigenschaft zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="2d4c4-143">Aufrufen der Syntax</span><span class="sxs-lookup"><span data-stu-id="2d4c4-143">Calling Syntax</span></span>  
 <span data-ttu-id="2d4c4-144">Sie aufrufen eine Eigenschaftenprozedur implizit durch einen Verweis auf die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="2d4c4-145">Sie verwenden den Namen der Eigenschaft, die gleiche Weise wie den Namen einer Variablen mit dem Unterschied, dass Sie Werte für alle Argumente angeben müssen, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="2d4c4-146">Wenn keine Argumente übergeben werden, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="2d4c4-147">Die Syntax für einen impliziten Aufruf einer `Set` Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2d4c4-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>  
  
 `propertyname[(argumentlist)] = expression`  
  
 <span data-ttu-id="2d4c4-148">Die Syntax für einen impliziten Aufruf einer `Get` Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="2d4c4-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="2d4c4-149">Abbildung der Deklaration und Aufruf</span><span class="sxs-lookup"><span data-stu-id="2d4c4-149">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="2d4c4-150">Die folgende Eigenschaft speichert einen vollständigen Namen als zwei konstituierende Namen, den Vornamen und den Nachnamen an.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="2d4c4-151">Wenn der aufrufende Code liest `fullName`die `Get` Prozedur kombiniert die beiden konstituierenden Namen und gibt den vollständigen Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="2d4c4-152">Wenn der aufrufende Code einen neuen vollständigen Name weist das `Set` Prozedur versucht, die sie in zwei konstituierende Namen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="2d4c4-153">Wenn sie ein Leerzeichen nicht gefunden wird, wird er alle als den Vornamen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-153">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 <span data-ttu-id="2d4c4-154">Das folgende Beispiel zeigt typische Aufrufe der Eigenschaftenprozeduren `fullName`.</span><span class="sxs-lookup"><span data-stu-id="2d4c4-154">The following example shows typical calls to the property procedures of `fullName`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="2d4c4-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d4c4-155">See Also</span></span>  
 [<span data-ttu-id="2d4c4-156">Verfahren</span><span class="sxs-lookup"><span data-stu-id="2d4c4-156">Procedures</span></span>](./index.md)  
 [<span data-ttu-id="2d4c4-157">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="2d4c4-157">Function Procedures</span></span>](./function-procedures.md)  
 [<span data-ttu-id="2d4c4-158">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="2d4c4-158">Operator Procedures</span></span>](./operator-procedures.md)  
 [<span data-ttu-id="2d4c4-159">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="2d4c4-159">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="2d4c4-160">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2d4c4-160">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="2d4c4-161">Gewusst wie: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2d4c4-161">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="2d4c4-162">Gewusst wie: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="2d4c4-162">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="2d4c4-163">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2d4c4-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)  
 [<span data-ttu-id="2d4c4-164">Gewusst wie: Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2d4c4-164">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="2d4c4-165">Gewusst wie: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="2d4c4-165">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
