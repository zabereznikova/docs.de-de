---
title: 'Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: 9ca9a0ccdac3ac13429928233a0c09d58427ce74
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61665766"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="a6ebf-102">Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a6ebf-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="a6ebf-103">Ein *Standardeigenschaft* ist eine Klasse oder Struktur-Eigenschaft, die Ihren Code zugreifen können, ohne ihn.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="a6ebf-104">Beim Aufrufen von Code Namen einer Klasse oder Struktur, aber keine Eigenschaft, und der Kontext ermöglicht den Zugriff auf eine Eigenschaft, Visual Basic löst den Zugriff auf diese Klasse oder Struktur Standardeigenschaft, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="a6ebf-105">Eine Klasse oder Struktur kann höchstens eine Standardeigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="a6ebf-106">Allerdings können Sie eine Standardeigenschaft überladen und haben mehr als eine Version des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="a6ebf-107">Weitere Informationen finden Sie unter [Standard](../../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="a6ebf-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="a6ebf-108">Um eine Standardeigenschaft zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-108">To declare a default property</span></span>  
  
1. <span data-ttu-id="a6ebf-109">Deklarieren Sie die Eigenschaft, auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-109">Declare the property in the normal way.</span></span> <span data-ttu-id="a6ebf-110">Geben Sie nicht die `Shared` oder `Private` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2. <span data-ttu-id="a6ebf-111">Enthalten die `Default` -Schlüsselwort in der Deklaration der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3. <span data-ttu-id="a6ebf-112">Geben Sie mindestens einen Parameter für die Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="a6ebf-113">Sie können keine Standardeigenschaft definieren, die nicht mindestens ein Argument übernimmt.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="a6ebf-114">Zum Aufrufen einer Standardeigenschaft</span><span class="sxs-lookup"><span data-stu-id="a6ebf-114">To call a default property</span></span>  
  
1. <span data-ttu-id="a6ebf-115">Deklarieren Sie eine Variable die enthaltende Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. <span data-ttu-id="a6ebf-116">Verwenden Sie den Variablennamen in einem Ausdruck allein, müssten Sie normalerweise den Eigenschaftennamen einfügen.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="a6ebf-117">Führen Sie den Variablennamen mit einer Argumentliste in Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="a6ebf-118">Eine Standardeigenschaft muss mindestens ein Argument übernehmen.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. <span data-ttu-id="a6ebf-119">Um den Standardwert der Eigenschaft abzurufen, verwenden Sie den Variablennamen ein, mit einer Argumentliste, die in einem Ausdruck oder nach den Gleichheitsoperator (`=`) in einer zuweisungsanweisung anmelden.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. <span data-ttu-id="a6ebf-120">Um den Standardwert der Eigenschaft festzulegen, verwenden Sie den Variablennamen ein, mit einer Argumentliste, auf der linken Seite einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. <span data-ttu-id="a6ebf-121">Sie können den Standardnamen für die Eigenschaft zusammen mit dem Variablennamen immer angeben, wie Sie vornehmen möchten, für den Zugriff auf eine andere Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="a6ebf-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6ebf-122">Example</span></span>  
 <span data-ttu-id="a6ebf-123">Das folgende Beispiel deklariert eine Standardeigenschaft für eine Klasse an.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="a6ebf-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6ebf-124">Example</span></span>  
 <span data-ttu-id="a6ebf-125">Im folgende Beispiel wird veranschaulicht, wie die Standardeigenschaft Aufrufen `myProperty` Klasse `class1`.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="a6ebf-126">Die drei zuweisungsanweisungen speichern Sie die Werte in `myProperty`, und die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Aufruf liest die Werte.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 <span data-ttu-id="a6ebf-127">Die häufigste Verwendung von eine Standardeigenschaft ist der <xref:Microsoft.VisualBasic.Collection.Item%2A> Eigenschaft in verschiedenen Auflistungsklassen.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="a6ebf-128">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="a6ebf-128">Robust Programming</span></span>  
 <span data-ttu-id="a6ebf-129">Standardeigenschaften können dazu führen, eine kleine Reduzierung in Code-Zeichen, aber leisten können Ihren Code schwieriger zu lesen.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="a6ebf-130">Wenn der aufrufende Code nicht vertraut sind, mit der Klasse oder Struktur ist, wenn es sich um einen Verweis auf den Namen der Klasse oder Struktur ist es bestimmte nicht möglich, ob der Verweis der Klasse oder Struktur selbst oder an eine Standardeigenschaft greift auf.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="a6ebf-131">Dies kann zu Compilerfehlern oder geringfügige Laufzeitlogik-Fehler führen.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="a6ebf-132">Sie können etwas reduziert die Wahrscheinlichkeit Eigenschaftenfehler standardmäßig immer mit der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) Festlegen der Compiler die typüberprüfung zu `On`.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="a6ebf-133">Wenn Sie beabsichtigen, mit einer vordefinierten Klasse oder Struktur in Ihrem Code müssen Sie bestimmen, ob es sich um eine Standardeigenschaft verfügt, und wenn Ja, ist wie der Name.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="a6ebf-134">Wegen der genannten Nachteile sollten Sie keine Standardeigenschaften definieren.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="a6ebf-135">Sie sollten für die Lesbarkeit des Codes berücksichtigen Sie auch immer explizit verweisen, die allen Eigenschaften, auch die Standardeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a6ebf-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6ebf-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6ebf-136">See also</span></span>

- [<span data-ttu-id="a6ebf-137">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="a6ebf-137">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="a6ebf-138">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="a6ebf-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="a6ebf-139">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a6ebf-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="a6ebf-140">Default</span><span class="sxs-lookup"><span data-stu-id="a6ebf-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)
- [<span data-ttu-id="a6ebf-141">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a6ebf-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="a6ebf-142">Vorgehensweise: Erstellen Sie eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a6ebf-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="a6ebf-143">Vorgehensweise: Deklarieren Sie eine Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="a6ebf-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="a6ebf-144">Vorgehensweise: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="a6ebf-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="a6ebf-145">Vorgehensweise: Das Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a6ebf-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="a6ebf-146">Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a6ebf-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
