---
title: 'Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- defaults, properties
- properties [Visual Basic], default
- procedures, defining
- default properties, in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7cfd476def67ccf46e524da7943680f9e34b6a26
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="60e3c-102">Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="60e3c-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="60e3c-103">Ein *Standardeigenschaft* ist eine Klasse oder Struktur-Eigenschaft, die der Code zugreifen kann, ohne dass es.</span><span class="sxs-lookup"><span data-stu-id="60e3c-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="60e3c-104">Beim Aufrufen von Code, den Namen einer Klasse oder Struktur, aber keine Eigenschaft, und der Kontext den Zugriff auf eine Eigenschaft ermöglicht [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] löst den Zugriff auf die Klasse oder Struktur Standardeigenschaft, falls vorhanden.</span><span class="sxs-lookup"><span data-stu-id="60e3c-104">When calling code names a class or structure but not a property, and the context allows access to a property, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="60e3c-105">Eine Klasse oder Struktur kann höchstens eine Standardeigenschaft besitzen.</span><span class="sxs-lookup"><span data-stu-id="60e3c-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="60e3c-106">Sie können allerdings haben mehr als eine Version und eine Standardeigenschaft überladen.</span><span class="sxs-lookup"><span data-stu-id="60e3c-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="60e3c-107">Weitere Informationen finden Sie unter [Standard](../../../../visual-basic/language-reference/modifiers/default.md).</span><span class="sxs-lookup"><span data-stu-id="60e3c-107">For more information, see [Default](../../../../visual-basic/language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="60e3c-108">Deklarieren Sie eine Default-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="60e3c-108">To declare a default property</span></span>  
  
1.  <span data-ttu-id="60e3c-109">Deklarieren Sie die Eigenschaft auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="60e3c-109">Declare the property in the normal way.</span></span> <span data-ttu-id="60e3c-110">Geben Sie die `Shared` oder `Private` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="60e3c-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2.  <span data-ttu-id="60e3c-111">Enthalten die `Default` Schlüsselwort in der Eigenschaftendeklaration.</span><span class="sxs-lookup"><span data-stu-id="60e3c-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3.  <span data-ttu-id="60e3c-112">Geben Sie mindestens einen Parameter für die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="60e3c-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="60e3c-113">Sie können keine Standardeigenschaft definieren, die nicht mindestens ein Argument annimmt.</span><span class="sxs-lookup"><span data-stu-id="60e3c-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     <span data-ttu-id="60e3c-114">[!code-vb[VbVbcnProcedures&17;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="60e3c-114">[!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]</span></span>  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="60e3c-115">Aufrufen eine Standardeigenschaft</span><span class="sxs-lookup"><span data-stu-id="60e3c-115">To call a default property</span></span>  
  
1.  <span data-ttu-id="60e3c-116">Deklarieren Sie eine Variable des enthaltenden Typs Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="60e3c-116">Declare a variable of the containing class or structure type.</span></span>  
  
     <span data-ttu-id="60e3c-117">[!code-vb[VbVbcnProcedures Nr.&16;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="60e3c-117">[!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]</span></span>  
  
2.  <span data-ttu-id="60e3c-118">Verwenden Sie den Variablennamen Allein in einem Ausdruck, der Sie normalerweise den Eigenschaftennamen enthalten würde.</span><span class="sxs-lookup"><span data-stu-id="60e3c-118">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     <span data-ttu-id="60e3c-119">[!code-vb[VbVbcnProcedures&21;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="60e3c-119">[!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]</span></span>  
  
3.  <span data-ttu-id="60e3c-120">Folgen Sie den Variablennamen eine Argumentliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="60e3c-120">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="60e3c-121">Eine Standardeigenschaft muss mindestens ein Argument annehmen.</span><span class="sxs-lookup"><span data-stu-id="60e3c-121">A default property must take at least one argument.</span></span>  
  
     <span data-ttu-id="60e3c-122">[!code-vb[VbVbcnProcedures&20;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="60e3c-122">[!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]</span></span>  
  
4.  <span data-ttu-id="60e3c-123">Um den Standardwert der Eigenschaft abzurufen, verwenden Sie den Variablennamen mit einer Argumentliste, die in einem Ausdruck oder nach dem Gleichheitszeichen (`=`) melden Sie sich eine Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="60e3c-123">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     <span data-ttu-id="60e3c-124">[!code-vb[VbVbcnProcedures&#15;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="60e3c-124">[!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]</span></span>  
  
5.  <span data-ttu-id="60e3c-125">Um den Standardwert der Eigenschaft festzulegen, verwenden Sie den Variablennamen mit einer Argumentliste auf der linken Seite einer Zuweisung-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="60e3c-125">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     <span data-ttu-id="60e3c-126">[!code-vb[VbVbcnProcedures&14;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="60e3c-126">[!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]</span></span>  
  
6.  <span data-ttu-id="60e3c-127">Sie können den Standardnamen für die Eigenschaft zusammen mit dem Variablennamen immer angeben, wie würde für den Zugriff auf eine andere Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="60e3c-127">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     <span data-ttu-id="60e3c-128">[!code-vb[VbVbcnProcedures Nr.&19;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="60e3c-128">[!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="60e3c-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60e3c-129">Example</span></span>  
 <span data-ttu-id="60e3c-130">Das folgende Beispiel deklariert eine Standardeigenschaft für eine Klasse.</span><span class="sxs-lookup"><span data-stu-id="60e3c-130">The following example declares a default property on a class.</span></span>  
  
 <span data-ttu-id="60e3c-131">[!code-vb[VbVbcnProcedures&#12;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="60e3c-131">[!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="60e3c-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="60e3c-132">Example</span></span>  
 <span data-ttu-id="60e3c-133">Im folgenden Beispiel wird veranschaulicht, wie die Standardeigenschaft Aufrufen `myProperty` Klasse `class1`.</span><span class="sxs-lookup"><span data-stu-id="60e3c-133">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="60e3c-134">Die drei zuweisungsanweisungen speichern Sie die Werte in `myProperty`, und die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>Aufruf liest die Werte.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A></span><span class="sxs-lookup"><span data-stu-id="60e3c-134">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 <span data-ttu-id="60e3c-135">[!code-vb[VbVbcnProcedures&#13;](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="60e3c-135">[!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]</span></span>  
  
 <span data-ttu-id="60e3c-136">Die häufigste Verwendung einer Standard-Eigenschaft wird die <xref:Microsoft.VisualBasic.Collection.Item%2A>-Eigenschaft in verschiedenen Auflistungsklassen.</xref:Microsoft.VisualBasic.Collection.Item%2A></span><span class="sxs-lookup"><span data-stu-id="60e3c-136">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="60e3c-137">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="60e3c-137">Robust Programming</span></span>  
 <span data-ttu-id="60e3c-138">Standardeigenschaften können dazu führen, dass eine kleine Reduzierung Code Quellzeichen können, sie jedoch Ihren Code schwieriger zu lesen.</span><span class="sxs-lookup"><span data-stu-id="60e3c-138">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="60e3c-139">Wenn der aufrufende Code nicht mit der Klasse oder Struktur, vertraut ist, wenn einen Verweis auf den Namen der Klasse oder Struktur erstellt kann nicht es sicher sein, ob der Verweis der Klasse oder Struktur selbst oder eine Default-Eigenschaft zugreift.</span><span class="sxs-lookup"><span data-stu-id="60e3c-139">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="60e3c-140">Dies kann zu Compilerfehlern oder feine Laufzeitlogik Fehler führen.</span><span class="sxs-lookup"><span data-stu-id="60e3c-140">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="60e3c-141">Sie können das Fehlerrisiko Standard-Eigenschaft etwas reduzieren, indem Sie immer die [Option Strict-Anweisung](../../../../visual-basic/language-reference/statements/option-strict-statement.md) Compilertyp Überprüfung festlegen `On`.</span><span class="sxs-lookup"><span data-stu-id="60e3c-141">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="60e3c-142">Wenn Sie beabsichtigen, mit eine vordefinierte Klasse oder Struktur im Code müssen Sie bestimmen, ob es sich um eine Standardeigenschaft verfügt, und wenn Ja, wie lautet der Name.</span><span class="sxs-lookup"><span data-stu-id="60e3c-142">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="60e3c-143">Wegen dieser Nachteile sollten Sie keine Standardeigenschaften definieren.</span><span class="sxs-lookup"><span data-stu-id="60e3c-143">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="60e3c-144">Für die Lesbarkeit des Codes sollten Sie auch in Betracht ziehen, immer explizit auf alle Eigenschaften verweisen, auch auf Standardeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="60e3c-144">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60e3c-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="60e3c-145">See Also</span></span>  
 <span data-ttu-id="60e3c-146">[Property-Prozeduren](./property-procedures.md) </span><span class="sxs-lookup"><span data-stu-id="60e3c-146">[Property Procedures](./property-procedures.md) </span></span>  
<span data-ttu-id="60e3c-147"> [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="60e3c-147"> [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md) </span></span>  
<span data-ttu-id="60e3c-148"> [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md) </span><span class="sxs-lookup"><span data-stu-id="60e3c-148"> [Property Statement](../../../../visual-basic/language-reference/statements/property-statement.md) </span></span>  
<span data-ttu-id="60e3c-149"> [Standardwert](../../../../visual-basic/language-reference/modifiers/default.md) </span><span class="sxs-lookup"><span data-stu-id="60e3c-149"> [Default](../../../../visual-basic/language-reference/modifiers/default.md) </span></span>  
<span data-ttu-id="60e3c-150"> [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md) </span><span class="sxs-lookup"><span data-stu-id="60e3c-150"> [Differences Between Properties and Variables in Visual Basic](./differences-between-properties-and-variables.md) </span></span>  
<span data-ttu-id="60e3c-151"> [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="60e3c-151"> [How to: Create a Property](./how-to-create-a-property.md) </span></span>  
<span data-ttu-id="60e3c-152"> [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md) </span><span class="sxs-lookup"><span data-stu-id="60e3c-152"> [How to: Declare a Property with Mixed Access Levels](./how-to-declare-a-property-with-mixed-access-levels.md) </span></span>  
<span data-ttu-id="60e3c-153"> [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md) </span><span class="sxs-lookup"><span data-stu-id="60e3c-153"> [How to: Call a Property Procedure](./how-to-call-a-property-procedure.md) </span></span>  
<span data-ttu-id="60e3c-154"> [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md) </span><span class="sxs-lookup"><span data-stu-id="60e3c-154"> [How to: Put a Value in a Property](./how-to-put-a-value-in-a-property.md) </span></span>  
<span data-ttu-id="60e3c-155"> [Gewusst wie: Abrufen eines Werts aus einer Eigenschaft](./how-to-get-a-value-from-a-property.md)</span><span class="sxs-lookup"><span data-stu-id="60e3c-155"> [How to: Get a Value from a Property](./how-to-get-a-value-from-a-property.md)</span></span>
