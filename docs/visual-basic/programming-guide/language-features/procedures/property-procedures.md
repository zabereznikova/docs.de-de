---
title: Eigenschaftenprozeduren
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
ms.openlocfilehash: a4b8ac3e27348764f537ee9502ce1fbb165bb3ef
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352564"
---
# <a name="property-procedures-visual-basic"></a><span data-ttu-id="3663d-102">Eigenschaftenprozeduren (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3663d-102">Property Procedures (Visual Basic)</span></span>

<span data-ttu-id="3663d-103">Eine Eigenschaften Prozedur ist eine Reihe von Visual Basic-Anweisungen, die eine benutzerdefinierte Eigenschaft für ein Modul, eine Klasse oder eine Struktur bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="3663d-103">A property procedure is a series of Visual Basic statements that manipulate a custom property on a module, class, or structure.</span></span> <span data-ttu-id="3663d-104">Eigenschaften Prozeduren werden auch als *Eigenschaftenaccessoren*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3663d-104">Property procedures are also known as *property accessors*.</span></span>

<span data-ttu-id="3663d-105">Visual Basic bietet die folgenden Eigenschaften Prozeduren:</span><span class="sxs-lookup"><span data-stu-id="3663d-105">Visual Basic provides for the following property procedures:</span></span>

- <span data-ttu-id="3663d-106">Eine `Get` Prozedur gibt den Wert einer Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="3663d-106">A `Get` procedure returns the value of a property.</span></span> <span data-ttu-id="3663d-107">Sie wird aufgerufen, wenn Sie in einem Ausdruck auf die-Eigenschaft zugreifen.</span><span class="sxs-lookup"><span data-stu-id="3663d-107">It is called when you access the property in an expression.</span></span>
- <span data-ttu-id="3663d-108">Eine `Set` Prozedur legt eine Eigenschaft auf einen Wert fest, einschließlich eines Objekt Verweises.</span><span class="sxs-lookup"><span data-stu-id="3663d-108">A `Set` procedure sets a property to a value, including an object reference.</span></span> <span data-ttu-id="3663d-109">Sie wird aufgerufen, wenn Sie der-Eigenschaft einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="3663d-109">It is called when you assign a value to the property.</span></span>

<span data-ttu-id="3663d-110">In der Regel definieren Sie Eigenschafts Prozeduren in Paaren, indem Sie die Anweisungen `Get` und `Set` verwenden. Sie können jedoch jede Prozedur allein definieren, wenn die Eigenschaft schreibgeschützt ([Get-Anweisung](../../../../visual-basic/language-reference/statements/get-statement.md)) oder schreibgeschützt ([Set-Anweisung](../../../../visual-basic/language-reference/statements/set-statement.md)) ist.</span><span class="sxs-lookup"><span data-stu-id="3663d-110">You usually define property procedures in pairs, using the `Get` and `Set` statements, but you can define either procedure alone if the property is read-only ([Get Statement](../../../../visual-basic/language-reference/statements/get-statement.md)) or write-only ([Set Statement](../../../../visual-basic/language-reference/statements/set-statement.md)).</span></span>

<span data-ttu-id="3663d-111">Wenn Sie eine automatisch implementierte Eigenschaft verwenden, können Sie die `Get` und `Set` Verfahren weglassen.</span><span class="sxs-lookup"><span data-stu-id="3663d-111">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="3663d-112">Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](./auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="3663d-112">For more information, see [Auto-Implemented Properties](./auto-implemented-properties.md).</span></span>

<span data-ttu-id="3663d-113">Sie können Eigenschaften in Klassen, Strukturen und Modulen definieren.</span><span class="sxs-lookup"><span data-stu-id="3663d-113">You can define properties in classes, structures, and modules.</span></span> <span data-ttu-id="3663d-114">Eigenschaften werden standardmäßig `Public`. Dies bedeutet, dass Sie Sie von überall in Ihrer Anwendung aus aufrufen können, die auf den Container der Eigenschaft zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="3663d-114">Properties are `Public` by default, which means you can call them from anywhere in your application that can access the property's container.</span></span>

<span data-ttu-id="3663d-115">Einen Vergleich von Eigenschaften und Variablen finden Sie [unter Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](differences-between-properties-and-variables.md).</span><span class="sxs-lookup"><span data-stu-id="3663d-115">For a comparison of properties and variables, see [Differences Between Properties and Variables in Visual Basic](differences-between-properties-and-variables.md).</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="3663d-116">Deklarations Syntax</span><span class="sxs-lookup"><span data-stu-id="3663d-116">Declaration syntax</span></span>

<span data-ttu-id="3663d-117">Eine Eigenschaft selbst wird durch einen Codeblock definiert, der in der- [Eigenschafts Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md) und der `End Property`-Anweisung eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3663d-117">A property itself is defined by a block of code enclosed within the [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="3663d-118">Innerhalb dieses Blocks wird jede Eigenschaften Prozedur als interner Block angezeigt, der in einer Deklarations Anweisung (`Get` oder `Set`) und der entsprechenden `End` Deklaration eingeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="3663d-118">Inside this block, each property procedure appears as an internal block enclosed within a declaration statement (`Get` or `Set`) and the matching `End` declaration.</span></span>

<span data-ttu-id="3663d-119">Die Syntax zum Deklarieren einer Eigenschaft und ihrer Prozeduren lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3663d-119">The syntax for declaring a property and its procedures is as follows:</span></span>

```vb
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
' - or -
[Default] [Modifiers] Property PropertyName [(ParameterList)] [As DataType]
```

<span data-ttu-id="3663d-120">Der `Modifiers` kann die Zugriffsebene und Informationen zu überladen, überschreiben, freigeben und shadoading angeben, und ob die Eigenschaft schreibgeschützt oder schreibgeschützt ist.</span><span class="sxs-lookup"><span data-stu-id="3663d-120">The `Modifiers` can specify access level and information regarding overloading, overriding, sharing, and shadowing, as well as whether the property is read-only or write-only.</span></span> <span data-ttu-id="3663d-121">Die `AccessLevel` auf der `Get`-oder `Set`-Prozedur kann eine beliebige Ebene sein, die restriktiver ist als die für die Eigenschaft selbst angegebene Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="3663d-121">The `AccessLevel` on the `Get` or `Set` procedure can be any level that is more restrictive than the access level specified for the property itself.</span></span> <span data-ttu-id="3663d-122">Weitere Informationen finden Sie unter [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md).</span><span class="sxs-lookup"><span data-stu-id="3663d-122">For more information, see [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="3663d-123">Datentyp</span><span class="sxs-lookup"><span data-stu-id="3663d-123">Data Type</span></span>

<span data-ttu-id="3663d-124">Der Datentyp der Eigenschaft und die Prinzipal Zugriffsebene werden in der `Property`-Anweisung definiert, nicht in den-Eigenschaften Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="3663d-124">A property's data type and principal access level are defined in the `Property` statement, not in the property procedures.</span></span> <span data-ttu-id="3663d-125">Eine Eigenschaft kann nur einen Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="3663d-125">A property can have only one data type.</span></span> <span data-ttu-id="3663d-126">Beispielsweise können Sie keine Eigenschaft zum Speichern eines `Decimal` Werts definieren, sondern einen `Double` Wert abrufen.</span><span class="sxs-lookup"><span data-stu-id="3663d-126">For example, you cannot define a property to store a `Decimal` value but retrieve a `Double` value.</span></span>

### <a name="access-level"></a><span data-ttu-id="3663d-127">Zugriffsebene</span><span class="sxs-lookup"><span data-stu-id="3663d-127">Access Level</span></span>

<span data-ttu-id="3663d-128">Sie können jedoch eine Prinzipal Zugriffsebene für eine Eigenschaft definieren und die Zugriffsebene in einer der Eigenschaften Prozeduren weiter einschränken.</span><span class="sxs-lookup"><span data-stu-id="3663d-128">However, you can define a principal access level for a property and further restrict the access level in one of its property procedures.</span></span> <span data-ttu-id="3663d-129">Sie können z. b. eine `Public`-Eigenschaft definieren und dann eine `Private Set` Prozedur definieren.</span><span class="sxs-lookup"><span data-stu-id="3663d-129">For example, you can define a `Public` property and then define a `Private Set` procedure.</span></span> <span data-ttu-id="3663d-130">Die Prozedur `Get` bleibt `Public`.</span><span class="sxs-lookup"><span data-stu-id="3663d-130">The `Get` procedure remains `Public`.</span></span> <span data-ttu-id="3663d-131">Sie können die Zugriffsebene nur in einer der Prozeduren einer Eigenschaft ändern, und Sie können Sie nur restriktiver machen als die Prinzipal Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="3663d-131">You can change the access level in only one of a property's procedures, and you can only make it more restrictive than the principal access level.</span></span> <span data-ttu-id="3663d-132">Weitere Informationen finden Sie unter Gewusst [wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](how-to-declare-a-property-with-mixed-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="3663d-132">For more information, see [How to: Declare a Property with Mixed Access Levels](how-to-declare-a-property-with-mixed-access-levels.md).</span></span>

## <a name="parameter-declaration"></a><span data-ttu-id="3663d-133">Parameter Deklaration</span><span class="sxs-lookup"><span data-stu-id="3663d-133">Parameter declaration</span></span>

<span data-ttu-id="3663d-134">Sie deklarieren jeden Parameter auf dieselbe Weise wie bei [unter Prozeduren](sub-procedures.md), mit der Ausnahme, dass der Übergabe Mechanismus `ByVal`werden muss.</span><span class="sxs-lookup"><span data-stu-id="3663d-134">You declare each parameter the same way you do for [Sub Procedures](sub-procedures.md), except that the passing mechanism must be `ByVal`.</span></span>

<span data-ttu-id="3663d-135">Die Syntax für jeden Parameter in der Parameterliste lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3663d-135">The syntax for each parameter in the parameter list is as follows:</span></span>

```vb
[Optional] ByVal [ParamArray] parametername As datatype
```

<span data-ttu-id="3663d-136">Wenn der Parameter optional ist, müssen Sie auch einen Standardwert als Teil der Deklaration angeben.</span><span class="sxs-lookup"><span data-stu-id="3663d-136">If the parameter is optional, you must also supply a default value as part of its declaration.</span></span> <span data-ttu-id="3663d-137">Die Syntax zum Angeben eines Standardwerts lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3663d-137">The syntax for specifying a default value is as follows:</span></span>

```vb
Optional ByVal parametername As datatype = defaultvalue
```

## <a name="property-value"></a><span data-ttu-id="3663d-138">Eigenschaftswert</span><span class="sxs-lookup"><span data-stu-id="3663d-138">Property value</span></span>

<span data-ttu-id="3663d-139">In einer `Get` Prozedur wird der Rückgabewert für den aufrufenden Ausdruck als Wert der-Eigenschaft bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3663d-139">In a `Get` procedure, the return value is supplied to the calling expression as the value of the property.</span></span>

<span data-ttu-id="3663d-140">In einer `Set` Prozedur wird der neue Eigenschafts Wert an den-Parameter der `Set`-Anweisung übergeben.</span><span class="sxs-lookup"><span data-stu-id="3663d-140">In a `Set` procedure, the new property value is passed to the parameter of the `Set` statement.</span></span> <span data-ttu-id="3663d-141">Wenn Sie explizit einen Parameter deklarieren, müssen Sie ihn mit dem gleichen Datentyp wie die-Eigenschaft deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3663d-141">If you explicitly declare a parameter, you must declare it with the same data type as the property.</span></span> <span data-ttu-id="3663d-142">Wenn Sie keinen Parameter deklarieren, verwendet der Compiler den impliziten Parameter `Value`, um den neuen Wert darzustellen, der der Eigenschaft zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="3663d-142">If you do not declare a parameter, the compiler uses the implicit parameter `Value` to represent the new value to be assigned to the property.</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="3663d-143">Aufruf Syntax</span><span class="sxs-lookup"><span data-stu-id="3663d-143">Calling syntax</span></span>

<span data-ttu-id="3663d-144">Sie rufen eine Eigenschaften Prozedur implizit auf, indem Sie einen Verweis auf die-Eigenschaft erstellen.</span><span class="sxs-lookup"><span data-stu-id="3663d-144">You invoke a property procedure implicitly by making reference to the property.</span></span> <span data-ttu-id="3663d-145">Sie verwenden den Namen der Eigenschaft auf die gleiche Weise wie den Namen einer Variablen, mit dem Unterschied, dass Sie Werte für alle nicht optionalen Argumente angeben müssen, und Sie müssen die Argumentliste in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="3663d-145">You use the name of the property the same way you would use the name of a variable, except that you must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="3663d-146">Wenn keine Argumente angegeben werden, können Sie die Klammern optional weglassen.</span><span class="sxs-lookup"><span data-stu-id="3663d-146">If no arguments are supplied, you can optionally omit the parentheses.</span></span>

<span data-ttu-id="3663d-147">Die Syntax für einen impliziten aufrufsvorgang einer `Set` Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3663d-147">The syntax for an implicit call to a `Set` procedure is as follows:</span></span>

```vb
propertyname[(argumentlist)] = expression
```

<span data-ttu-id="3663d-148">Die Syntax für einen impliziten aufrufsvorgang einer `Get` Prozedur lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3663d-148">The syntax for an implicit call to a `Get` procedure is as follows:</span></span>

```vb
lvalue = propertyname[(argumentlist)]
Do While (propertyname[(argumentlist)] > expression)
```

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="3663d-149">Abbildung der Deklaration und des Aufruf</span><span class="sxs-lookup"><span data-stu-id="3663d-149">Illustration of declaration and call</span></span>

<span data-ttu-id="3663d-150">Die folgende Eigenschaft speichert einen vollständigen Namen als zwei konstituierende Namen, den Vornamen und den Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="3663d-150">The following property stores a full name as two constituent names, the first name and the last name.</span></span> <span data-ttu-id="3663d-151">Wenn der aufrufenden Code `fullName`liest, werden die beiden konstituierenden Namen in der `Get` Prozedur kombiniert, und der vollständige Name wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3663d-151">When the calling code reads `fullName`, the `Get` procedure combines the two constituent names and returns the full name.</span></span> <span data-ttu-id="3663d-152">Wenn der Aufruf Code einen neuen vollständigen Namen zuweist, versucht die `Set` Prozedur, Sie in zwei Bestandteile zu zerlegen.</span><span class="sxs-lookup"><span data-stu-id="3663d-152">When the calling code assigns a new full name, the `Set` procedure attempts to break it into two constituent names.</span></span> <span data-ttu-id="3663d-153">Wenn kein Leerzeichen gefunden wird, wird alles als Vorname gespeichert.</span><span class="sxs-lookup"><span data-stu-id="3663d-153">If it does not find a space, it stores it all as the first name.</span></span>

[!code-vb[VbVbcnProcedures#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#8)]

<span data-ttu-id="3663d-154">Das folgende Beispiel zeigt typische Aufrufe der-Eigenschaften Prozeduren `fullName`:</span><span class="sxs-lookup"><span data-stu-id="3663d-154">The following example shows typical calls to the property procedures of `fullName`:</span></span>

[!code-vb[VbVbcnProcedures#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#9)]

## <a name="see-also"></a><span data-ttu-id="3663d-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3663d-155">See also</span></span>

- [<span data-ttu-id="3663d-156">Verfahren</span><span class="sxs-lookup"><span data-stu-id="3663d-156">Procedures</span></span>](index.md)
- [<span data-ttu-id="3663d-157">Function-Prozeduren</span><span class="sxs-lookup"><span data-stu-id="3663d-157">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="3663d-158">Operatorprozeduren</span><span class="sxs-lookup"><span data-stu-id="3663d-158">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="3663d-159">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="3663d-159">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="3663d-160">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3663d-160">Differences Between Properties and Variables in Visual Basic</span></span>](differences-between-properties-and-variables.md)
- [<span data-ttu-id="3663d-161">Gewusst wie: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3663d-161">How to: Create a Property</span></span>](how-to-create-a-property.md)
- [<span data-ttu-id="3663d-162">Gewusst wie: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="3663d-162">How to: Call a Property Procedure</span></span>](how-to-call-a-property-procedure.md)
- [<span data-ttu-id="3663d-163">Vorgehensweise: Deklarieren und Abrufen einer Standard Eigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="3663d-163">How to: Declare and Call a Default Property in Visual Basic</span></span>](how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="3663d-164">Gewusst wie: Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3663d-164">How to: Put a Value in a Property</span></span>](how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="3663d-165">Gewusst wie: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="3663d-165">How to: Get a Value from a Property</span></span>](how-to-get-a-value-from-a-property.md)
