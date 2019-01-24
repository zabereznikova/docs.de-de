---
title: Eigenschaftenprozeduren (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: e61cf907ac2c5c04aa86c03a73bda7fcfcb8122d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54710481"
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="527dd-102">Eigenschaftenprozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="527dd-102">Property Procedures (Visual Basic)</span></span>
<span data-ttu-id="527dd-103">Eine Eigenschaftenprozedur ist eine Reihe von Visual Basic-Anweisungen, die eine benutzerdefinierte Eigenschaft in einem Modul, Klasse oder Struktur zu ändern.</span><span class="sxs-lookup"><span data-stu-id="527dd-103">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="527dd-104">-Eigenschaftenprozeduren werden, auch bekannt als *Eigenschaftenaccessoren*.</span><span class="sxs-lookup"><span data-stu-id="527dd-104">Property procedures are also known as *property accessors*.</span></span>  
  
 <span data-ttu-id="527dd-105">Visual Basic bietet für die folgenden Verfahren für die Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="527dd-105">Visual Basic provides for the following property procedures:</span></span>  
  
-   <span data-ttu-id="527dd-106">Ein `Get` Prozedur gibt den Wert einer Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="527dd-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="527dd-107">Wird aufgerufen, wenn Sie die Eigenschaft in einem Ausdruck zugreifen.</span><span class="sxs-lookup"><span data-stu-id="527dd-107">It is called when you access the property in an expression.</span></span>  
  
-   <span data-ttu-id="527dd-108">Ein `Set` Prozedur setzt eine Eigenschaft auf einen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="527dd-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="527dd-109">Wird aufgerufen, wenn Sie die Eigenschaft einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="527dd-109">It is called when you assign a value to the property.</span></span>  
  
 <span data-ttu-id="527dd-110">Sie Eigenschaftenprozeduren in der Regel paarweise mit definieren die `Get` und `Set` -Anweisungen, aber Sie können auch einzeln definiert, wenn die Eigenschaft schreibgeschützt ist ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) oder nur Schreibzugriff ([festlegen Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md)).</span><span class="sxs-lookup"><span data-stu-id="527dd-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>  
  
 <span data-ttu-id="527dd-111">Können Sie weglassen der `Get` und `Set` Verfahren, wenn Sie eine automatisch implementierte Eigenschaft zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="527dd-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="527dd-112">Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](./auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="527dd-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="527dd-113">Sie können Eigenschaften in Klassen, Strukturen und Module definieren.</span><span class="sxs-lookup"><span data-stu-id="527dd-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="527dd-114">Eigenschaften sind `Public` standardmäßig die bedeutet, dass Sie von überall aus aufrufen können in Ihrer Anwendung, die Container der Eigenschaft zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="527dd-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>  
  
 <span data-ttu-id="527dd-115">Einen Vergleich von Eigenschaften und Variablen finden Sie unter [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="527dd-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md).</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="527dd-116">Deklarationssyntax</span><span class="sxs-lookup"><span data-stu-id="527dd-116">Declaration Syntax</span></span>  
 <span data-ttu-id="527dd-117">Eine Eigenschaft selbst wird durch einen Codeblock eingefasst definiert die [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) und `End Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="527dd-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="527dd-118">Innerhalb dieses Blocks an, die für jede Eigenschaftenprozedur als interner Block einer deklarationsanweisung angegeben eingefasst wird angezeigt (`Get` oder `Set`) und den entsprechenden `End` Deklaration.</span><span class="sxs-lookup"><span data-stu-id="527dd-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>  
  
 <span data-ttu-id="527dd-119">Die Syntax zum Deklarieren einer Eigenschaft und die zugehörigen Prozeduren ist wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="527dd-119">The syntax for declaring a property and its procedures is as follows:</span></span>  
  
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
  
 <span data-ttu-id="527dd-120">Die `Modifiers` festlegbaren Zugriffsebene und Informationen zu überladen, überschreiben, freigeben und shadowing, sowie, ob die Eigenschaft schreibgeschützt oder lesegeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="527dd-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="527dd-121">Die `AccessLevel` auf die `Get` oder `Set` Prozedur kann jeder Ebene, die restriktiver ist als die Zugriffsebene für die Eigenschaft selbst angegeben sein.</span><span class="sxs-lookup"><span data-stu-id="527dd-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="527dd-122">Weitere Informationen finden Sie unter [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="527dd-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="527dd-123">Datentyp</span><span class="sxs-lookup"><span data-stu-id="527dd-123">Data Type</span></span>  
 <span data-ttu-id="527dd-124">Der Datentyp einer Eigenschaft und der Dienstprinzipal Zugriff auf werden definiert, der `Property` -Anweisung nicht in der Eigenschaftenprozeduren.</span><span class="sxs-lookup"><span data-stu-id="527dd-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="527dd-125">Eine Eigenschaft kann nur einen Datentyp verfügen.</span><span class="sxs-lookup"><span data-stu-id="527dd-125">A property can have only one data type.</span></span> <span data-ttu-id="527dd-126">Angenommen, Sie eine Eigenschaft zum Speichern von definieren können kein `Decimal` Wert aber Abrufen einer `Double` Wert.</span><span class="sxs-lookup"><span data-stu-id="527dd-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>  
  
### <a name="access-level"></a><span data-ttu-id="527dd-127">Zugriffsebene</span><span class="sxs-lookup"><span data-stu-id="527dd-127">Access Level</span></span>  
 <span data-ttu-id="527dd-128">Allerdings können Sie definieren einen Dienstprinzipal Zugriff auf für eine Eigenschaft und die Zugriffsebene in einer der Eigenschaftenprozeduren weiter einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="527dd-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="527dd-129">Beispielsweise können Sie definieren eine `Public` Eigenschaft, und klicken Sie dann definieren Sie eine `Private Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="527dd-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="527dd-130">Die `Get` Prozedur bleibt `Public`.</span><span class="sxs-lookup"><span data-stu-id="527dd-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="527dd-131">Sie können die Zugriffsebene in eine der Prozeduren für eine Eigenschaft ändern können, und Sie nur es restriktiver ist als die Zugriffsebene des dienstprinzipals.</span><span class="sxs-lookup"><span data-stu-id="527dd-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="527dd-132">Weitere Informationen finden Sie unter [Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="527dd-132">For more information, see [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md).</span></span>  
  
## <a name="parameter-declaration"></a><span data-ttu-id="527dd-133">Parameterdeklaration</span><span class="sxs-lookup"><span data-stu-id="527dd-133">Parameter Declaration</span></span>  
 <span data-ttu-id="527dd-134">Jeder Parameter deklariert die gleiche Weise für [Sub-Prozeduren](./sub-procedures.md), außer dass muss der Übergabemechanismus sein `ByVal`.</span><span class="sxs-lookup"><span data-stu-id="527dd-134">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>  
  
 <span data-ttu-id="527dd-135">Die Syntax für jeden Parameter in der Liste der Parameter lautet wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="527dd-135">The syntax for each parameter in the parameter list is as follows:</span></span>  
  
 `[Optional] ByVal [ParamArray] parametername As datatype`  
  
 <span data-ttu-id="527dd-136">Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="527dd-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="527dd-137">Die Syntax zum Angeben der Standardwert ist wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="527dd-137">The syntax for specifying a default value is as follows:</span></span>  
  
 `Optional ByVal parametername As datatype = defaultvalue`  
  
## <a name="property-value"></a><span data-ttu-id="527dd-138">Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="527dd-138">Property Value</span></span>  
 <span data-ttu-id="527dd-139">In einem `Get` Verfahren der Rückgabewert dem aufrufenden Ausdruck als Wert der Eigenschaft angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="527dd-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>  
  
 <span data-ttu-id="527dd-140">In einem `Set` Verfahren wird der neue Eigenschaftswert auf den Parameter übergeben die `Set` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="527dd-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="527dd-141">Wenn Sie einen Parameter explizit deklarieren, müssen Sie es mit dem gleichen Datentyp wie die Eigenschaft deklarieren.</span><span class="sxs-lookup"><span data-stu-id="527dd-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="527dd-142">Wenn Sie keinen Parameter deklarieren, verwendet der Compiler die impliziten Parameter `Value` zur Darstellung des neuen Wert der Eigenschaft zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="527dd-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="527dd-143">Die Syntax aufrufen</span><span class="sxs-lookup"><span data-stu-id="527dd-143">Calling Syntax</span></span>  
 <span data-ttu-id="527dd-144">Sie aufrufen eine Eigenschaftenprozedur implizit durch einen Verweis auf die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="527dd-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="527dd-145">Sie verwenden den Namen der Eigenschaft, die gleiche Weise, die Sie verwenden den Namen einer Variablen mit dem Unterschied, dass Sie Werte für alle Argumente angeben müssen, die nicht optional sind, und müssen Sie die Argumentliste in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="527dd-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="527dd-146">Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="527dd-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="527dd-147">Die Syntax für einen impliziten Aufruf einer `Set` Verfahren lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="527dd-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>  
  
 `propertyname[(argumentlist)] = expression`  
  
 <span data-ttu-id="527dd-148">Die Syntax für einen impliziten Aufruf einer `Get` Verfahren lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="527dd-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>  
  
 `lvalue = propertyname[(argumentlist)]`  
  
 `Do While (propertyname[(argumentlist)] > expression)`  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="527dd-149">Abbildung der Deklaration und Aufruf</span><span class="sxs-lookup"><span data-stu-id="527dd-149">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="527dd-150">Die folgende Eigenschaft speichert einen vollständigen Namen als zwei enthaltenen Namen, der Vorname und Nachname.</span><span class="sxs-lookup"><span data-stu-id="527dd-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="527dd-151">Wenn der aufrufende Code liest `fullName`, `Get` Prozedur kombiniert die beiden zugehörigen Namen und gibt den vollständigen Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="527dd-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="527dd-152">Wenn der aufrufende Code einen neuen vollständigen Namen, weist der `Set` Prozedur versucht, die in zwei enthaltenen Namen aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="527dd-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="527dd-153">Wenn sie ein Leerzeichen nicht gefunden wird, es alle als den ersten Namen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="527dd-153">If it does not find a space, it stores it all as the first name.</span></span>  
  
 [!code-vb[VbVbcnProcedures#8](./codesnippet/VisualBasic/property-procedures_1.vb)]  
  
 <span data-ttu-id="527dd-154">Das folgende Beispiel zeigt die typischen Aufrufe an die Eigenschaftenprozeduren von `fullName`.</span><span class="sxs-lookup"><span data-stu-id="527dd-154">The following example shows typical calls to the property procedures of `fullName`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#9](./codesnippet/VisualBasic/property-procedures_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="527dd-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="527dd-155">See also</span></span>
- [<span data-ttu-id="527dd-156">Verfahren</span><span class="sxs-lookup"><span data-stu-id="527dd-156">Procedures</span></span>](./index.md)
- [<span data-ttu-id="527dd-157">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="527dd-157">Function Procedures</span></span>](./function-procedures.md)
- [<span data-ttu-id="527dd-158">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="527dd-158">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="527dd-159">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="527dd-159">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="527dd-160">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="527dd-160">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="527dd-161">Vorgehensweise: Erstellen Sie eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="527dd-161">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="527dd-162">Vorgehensweise: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="527dd-162">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="527dd-163">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="527dd-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="527dd-164">Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="527dd-164">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="527dd-165">Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="527dd-165">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
