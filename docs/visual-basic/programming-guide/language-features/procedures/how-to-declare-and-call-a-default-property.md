---
title: 'Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9c4f471eba42e47d6bef45a4d38abc0cbd2d32bc
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="24563-102">Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24563-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="24563-103">Ein *Standardeigenschaft* ist eine Klasse oder Struktur-Eigenschaft, die der Code zugreifen kann, ohne dass es.</span><span class="sxs-lookup"><span data-stu-id="24563-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="24563-104">Beim Aufrufen von Code Namen einer Klasse oder Struktur, nicht jedoch eine Eigenschaft angibt und den Kontext ermöglicht den Zugriff auf eine Eigenschaft, Visual Basic löst den Zugriff auf diese Klasse oder Struktur Standardeigenschaft, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="24563-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="24563-105">Eine Klasse oder Struktur kann höchstens eine Standardeigenschaft haben.</span><span class="sxs-lookup"><span data-stu-id="24563-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="24563-106">Allerdings können Sie eine Standardeigenschaft überladen und haben mehr als eine Version.</span><span class="sxs-lookup"><span data-stu-id="24563-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="24563-107">Weitere Informationen finden Sie unter [Standard](../../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="24563-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="24563-108">Um eine Standardeigenschaft zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="24563-108">To declare a default property</span></span>  
  
1.  <span data-ttu-id="24563-109">Deklarieren Sie die Eigenschaft auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="24563-109">Declare the property in the normal way.</span></span> <span data-ttu-id="24563-110">Geben Sie keine der `Shared` oder `Private` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="24563-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2.  <span data-ttu-id="24563-111">Enthalten die `Default` -Schlüsselwort in der Deklaration der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="24563-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3.  <span data-ttu-id="24563-112">Geben Sie mindestens einen Parameter für die Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="24563-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="24563-113">Sie können keine Standardeigenschaft definieren, die nicht mindestens ein Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="24563-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="24563-114">Aufrufen eine Standardeigenschaft</span><span class="sxs-lookup"><span data-stu-id="24563-114">To call a default property</span></span>  
  
1.  <span data-ttu-id="24563-115">Deklarieren Sie eine Variable den enthaltenden Typ der Klasse oder Struktur an.</span><span class="sxs-lookup"><span data-stu-id="24563-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  <span data-ttu-id="24563-116">Verwenden Sie den Variablennamen Allein in einem Ausdruck, bei denen Sie normalerweise den Namen der Eigenschaft enthalten würde.</span><span class="sxs-lookup"><span data-stu-id="24563-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  <span data-ttu-id="24563-117">Führen Sie den Variablennamen mit einer Argumentliste in Klammern ein.</span><span class="sxs-lookup"><span data-stu-id="24563-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="24563-118">Eine Standardeigenschaft muss mindestens ein Argument annehmen.</span><span class="sxs-lookup"><span data-stu-id="24563-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  <span data-ttu-id="24563-119">Um den Standardwert der Eigenschaft abzurufen, verwenden Sie den Variablennamen ein, mit der eine Argumentliste in einem Ausdruck oder nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung signieren.</span><span class="sxs-lookup"><span data-stu-id="24563-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  <span data-ttu-id="24563-120">Um den Standardwert der Eigenschaft festzulegen, verwenden Sie den Variablennamen ein, mit einer Argumentliste, auf der linken Seite einer zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="24563-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  <span data-ttu-id="24563-121">Sie können den Standardnamen für die Eigenschaft zusammen mit dem Variablennamen immer angeben, ebenso wie Sie vornehmen möchten, für den Zugriff auf eine andere Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="24563-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a><span data-ttu-id="24563-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="24563-122">Example</span></span>  
 <span data-ttu-id="24563-123">Das folgende Beispiel deklariert eine Standardeigenschaft für eine Klasse an.</span><span class="sxs-lookup"><span data-stu-id="24563-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a><span data-ttu-id="24563-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="24563-124">Example</span></span>  
 <span data-ttu-id="24563-125">Im folgenden Beispiel wird veranschaulicht, wie die Standardeigenschaft Aufrufen `myProperty` Klasse `class1`.</span><span class="sxs-lookup"><span data-stu-id="24563-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="24563-126">Die drei zuweisungsanweisungen speichern Sie die Werte in `myProperty`, und die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Aufruf liest die Werte.</span><span class="sxs-lookup"><span data-stu-id="24563-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 <span data-ttu-id="24563-127">Die häufigste Verwendung der Standardeigenschaft ist der <xref:Microsoft.VisualBasic.Collection.Item%2A> -Eigenschaft für verschiedene Auflistungsklassen.</span><span class="sxs-lookup"><span data-stu-id="24563-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="24563-128">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="24563-128">Robust Programming</span></span>  
 <span data-ttu-id="24563-129">Standardeigenschaften können dazu führen, eine kleine Verkleinerung an Code Quellzeichen können, sie jedoch Code schwieriger zu lesen.</span><span class="sxs-lookup"><span data-stu-id="24563-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="24563-130">Wenn der aufrufende Code nicht mit der Klasse oder Struktur vertraut ist, wenn es sich um einen Verweis auf den Namen der Klasse oder Struktur enthält kann nicht bestimmte darauf, ob der Verweis der Klasse oder Struktur selbst oder eine Standardeigenschaft greift auf.</span><span class="sxs-lookup"><span data-stu-id="24563-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="24563-131">Dies kann zu Compilerfehlern oder geringfügige Logikfehler zur Laufzeit führen.</span><span class="sxs-lookup"><span data-stu-id="24563-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="24563-132">Sie können das Risiko von Fehlern der Standard-Eigenschaft etwas reduzieren, indem immer mithilfe der [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) Compilertyp das Einchecken festlegen `On`.</span><span class="sxs-lookup"><span data-stu-id="24563-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="24563-133">Wenn Sie beabsichtigen, eine vordefinierte Klasse oder Struktur in Ihrem Code müssen Sie bestimmen, ob es sich um eine Standardeigenschaft verfügt, und wenn Ja, ist was seinen Namen aus.</span><span class="sxs-lookup"><span data-stu-id="24563-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="24563-134">Aufgrund dieser Nachteile sollten Sie keine Standardeigenschaften definieren.</span><span class="sxs-lookup"><span data-stu-id="24563-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="24563-135">Für die Lesbarkeit des Codes sollten Sie auch sollten Sie immer alle Eigenschaften explizit auf, auch die Standardeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="24563-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24563-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24563-136">See Also</span></span>  
 [<span data-ttu-id="24563-137">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="24563-137">Property Procedures</span></span>](./property-procedures.md)  
 [<span data-ttu-id="24563-138">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="24563-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)  
 [<span data-ttu-id="24563-139">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="24563-139">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [<span data-ttu-id="24563-140">Default</span><span class="sxs-lookup"><span data-stu-id="24563-140">Default</span></span>](../../../../visual-basic/language-reference/modifiers/default.md)  
 [<span data-ttu-id="24563-141">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="24563-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)  
 [<span data-ttu-id="24563-142">Gewusst wie: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="24563-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)  
 [<span data-ttu-id="24563-143">Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="24563-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [<span data-ttu-id="24563-144">Gewusst wie: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="24563-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)  
 [<span data-ttu-id="24563-145">Gewusst wie: Ablegen eines Werts in einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="24563-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)  
 [<span data-ttu-id="24563-146">Gewusst wie: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="24563-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
