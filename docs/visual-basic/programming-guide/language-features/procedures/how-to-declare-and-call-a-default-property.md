---
title: 'Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft'
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
ms.openlocfilehash: 4de5d94a94e764d1fc543ffae41b00a9bb729c94
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388153"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a><span data-ttu-id="dc418-102">Gewusst wie: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dc418-102">How to: Declare and Call a Default Property in Visual Basic</span></span>
<span data-ttu-id="dc418-103">Eine *Standard Eigenschaft* ist eine Klassen-oder Struktur Eigenschaft, auf die der Code zugreifen kann, ohne ihn anzugeben.</span><span class="sxs-lookup"><span data-stu-id="dc418-103">A *default property* is a class or structure property that your code can access without specifying it.</span></span> <span data-ttu-id="dc418-104">Beim Aufrufen von Code wird eine Klasse oder Struktur, aber keine Eigenschaft benannt, und der Kontext ermöglicht den Zugriff auf eine Eigenschaft, Visual Basic den Zugriff auf die Standard Eigenschaft der Klasse oder Struktur, sofern vorhanden, auflöst.</span><span class="sxs-lookup"><span data-stu-id="dc418-104">When calling code names a class or structure but not a property, and the context allows access to a property, Visual Basic resolves the access to that class or structure's default property if one exists.</span></span>  
  
 <span data-ttu-id="dc418-105">Eine Klasse oder Struktur kann höchstens eine Standard Eigenschaft aufweisen.</span><span class="sxs-lookup"><span data-stu-id="dc418-105">A class or structure can have at most one default property.</span></span> <span data-ttu-id="dc418-106">Sie können jedoch eine Standard Eigenschaft überladen und mehr als eine Version davon haben.</span><span class="sxs-lookup"><span data-stu-id="dc418-106">However, you can overload a default property and have more than one version of it.</span></span>  
  
 <span data-ttu-id="dc418-107">Weitere Informationen finden Sie unter [default (Standard](../../../language-reference/modifiers/default.md)).</span><span class="sxs-lookup"><span data-stu-id="dc418-107">For more information, see [Default](../../../language-reference/modifiers/default.md).</span></span>  
  
### <a name="to-declare-a-default-property"></a><span data-ttu-id="dc418-108">So deklarieren Sie eine Standard Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dc418-108">To declare a default property</span></span>  
  
1. <span data-ttu-id="dc418-109">Deklarieren Sie die Eigenschaft auf die übliche Weise.</span><span class="sxs-lookup"><span data-stu-id="dc418-109">Declare the property in the normal way.</span></span> <span data-ttu-id="dc418-110">Geben Sie das `Shared` Schlüsselwort oder nicht an `Private` .</span><span class="sxs-lookup"><span data-stu-id="dc418-110">Do not specify the `Shared` or `Private` keyword.</span></span>  
  
2. <span data-ttu-id="dc418-111">Fügen Sie das- `Default` Schlüsselwort in die Eigenschaften Deklaration ein</span><span class="sxs-lookup"><span data-stu-id="dc418-111">Include the `Default` keyword in the property declaration.</span></span>  
  
3. <span data-ttu-id="dc418-112">Geben Sie mindestens einen Parameter für die Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="dc418-112">Specify at least one parameter for the property.</span></span> <span data-ttu-id="dc418-113">Sie können keine Standard Eigenschaft definieren, die nicht mindestens ein Argument annimmt.</span><span class="sxs-lookup"><span data-stu-id="dc418-113">You cannot define a default property that does not take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a><span data-ttu-id="dc418-114">So wird eine Standard Eigenschaft aufgerufen</span><span class="sxs-lookup"><span data-stu-id="dc418-114">To call a default property</span></span>  
  
1. <span data-ttu-id="dc418-115">Deklarieren Sie eine Variable vom enthaltenden Klassen-oder Strukturtyp.</span><span class="sxs-lookup"><span data-stu-id="dc418-115">Declare a variable of the containing class or structure type.</span></span>  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2. <span data-ttu-id="dc418-116">Verwenden Sie den Variablennamen allein in einem Ausdruck, in dem Sie normalerweise den Eigenschaftsnamen einschließen.</span><span class="sxs-lookup"><span data-stu-id="dc418-116">Use the variable name alone in an expression where you would normally include the property name.</span></span>  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3. <span data-ttu-id="dc418-117">Befolgen Sie den Variablennamen mit einer Argumentliste in Klammern.</span><span class="sxs-lookup"><span data-stu-id="dc418-117">Follow the variable name with an argument list in parentheses.</span></span> <span data-ttu-id="dc418-118">Eine Standard Eigenschaft muss mindestens ein Argument annehmen.</span><span class="sxs-lookup"><span data-stu-id="dc418-118">A default property must take at least one argument.</span></span>  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4. <span data-ttu-id="dc418-119">Um den Standard Eigenschafts Wert abzurufen, verwenden Sie den Variablennamen, mit einer Argumentliste, in einem Ausdruck oder nach dem Gleichheits `=` Zeichen () in einer Zuweisungsanweisung.</span><span class="sxs-lookup"><span data-stu-id="dc418-119">To retrieve the default property value, use the variable name, with an argument list, in an expression or following the equal (`=`) sign in an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5. <span data-ttu-id="dc418-120">Um den Standard Eigenschafts Wert festzulegen, verwenden Sie den Variablennamen auf der linken Seite einer Zuweisungsanweisung mit einer Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="dc418-120">To set the default property value, use the variable name, with an argument list, on the left side of an assignment statement.</span></span>  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6. <span data-ttu-id="dc418-121">Sie können den Standard Eigenschaftsnamen wie für den Zugriff auf jede andere Eigenschaft immer mit dem Variablennamen angeben.</span><span class="sxs-lookup"><span data-stu-id="dc418-121">You can always specify the default property name together with the variable name, just as you would do to access any other property.</span></span>  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a><span data-ttu-id="dc418-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc418-122">Example</span></span>  
 <span data-ttu-id="dc418-123">Im folgenden Beispiel wird eine Default-Eigenschaft für eine-Klasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="dc418-123">The following example declares a default property on a class.</span></span>  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="dc418-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dc418-124">Example</span></span>  
 <span data-ttu-id="dc418-125">Im folgenden Beispiel wird veranschaulicht, wie die Default-Eigenschaft für die-Klasse aufgerufen wird `myProperty` `class1` .</span><span class="sxs-lookup"><span data-stu-id="dc418-125">The following example demonstrates how to call the default property `myProperty` on class `class1`.</span></span> <span data-ttu-id="dc418-126">Die drei Zuweisungs Anweisungen speichern Werte in `myProperty` , und der-Befehl <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> liest die-Werte.</span><span class="sxs-lookup"><span data-stu-id="dc418-126">The three assignment statements store values in `myProperty`, and the <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> call reads the values.</span></span>  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 <span data-ttu-id="dc418-127">Die häufigste Verwendung einer Standard Eigenschaft ist die- <xref:Microsoft.VisualBasic.Collection.Item%2A> Eigenschaft für verschiedene Auflistungs Klassen.</span><span class="sxs-lookup"><span data-stu-id="dc418-127">The most common use of a default property is the <xref:Microsoft.VisualBasic.Collection.Item%2A> property on various collection classes.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="dc418-128">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="dc418-128">Robust Programming</span></span>  
 <span data-ttu-id="dc418-129">Standardeigenschaften können zu einer geringfügigen Reduzierung der Quell Code Zeichen führen, aber Sie können den Code schwieriger lesbar machen.</span><span class="sxs-lookup"><span data-stu-id="dc418-129">Default properties can result in a small reduction in source code-characters, but they can make your code more difficult to read.</span></span> <span data-ttu-id="dc418-130">Wenn der aufrufende Code nicht mit der Klasse oder Struktur vertraut ist, kann er, wenn er einen Verweis auf den Klassen-oder Struktur Namen erstellt, nicht sicher sein, ob dieser Verweis auf die Klasse oder Struktur selbst oder eine Standard Eigenschaft zugreift.</span><span class="sxs-lookup"><span data-stu-id="dc418-130">If the calling code is not familiar with your class or structure, when it makes a reference to the class or structure name it cannot be certain whether that reference accesses the class or structure itself, or a default property.</span></span> <span data-ttu-id="dc418-131">Dies kann zu Compilerfehlern oder geringfügigen Lauf Zeit Logik-Fehlern führen.</span><span class="sxs-lookup"><span data-stu-id="dc418-131">This can lead to compiler errors or subtle run-time logic errors.</span></span>  
  
 <span data-ttu-id="dc418-132">Sie können die Wahrscheinlichkeit von Fehlern bei Standardeigenschaften verringern, indem Sie immer die [Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md) verwenden, um die Compilertypüberprüfung auf festzulegen `On` .</span><span class="sxs-lookup"><span data-stu-id="dc418-132">You can somewhat reduce the chance of default property errors by always using the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) to set compiler type checking to `On`.</span></span>  
  
 <span data-ttu-id="dc418-133">Wenn Sie beabsichtigen, eine vordefinierte Klasse oder Struktur in Ihrem Code zu verwenden, müssen Sie feststellen, ob Sie über eine Default-Eigenschaft verfügt. wenn dies der Fall ist, müssen Sie den Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="dc418-133">If you are planning to use a predefined class or structure in your code, you must determine whether it has a default property, and if so, what its name is.</span></span>  
  
 <span data-ttu-id="dc418-134">Aufgrund dieser Nachteile sollten Sie das Definieren von Standardeigenschaften in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="dc418-134">Because of these disadvantages, you should consider not defining default properties.</span></span> <span data-ttu-id="dc418-135">Zur besseren Lesbarkeit des Codes sollten Sie auch immer eine explizite Verweis auf alle Eigenschaften in Erwägung ziehen. Dies gilt auch für Standardeigenschaften.</span><span class="sxs-lookup"><span data-stu-id="dc418-135">For code readability, you should also consider always referring to all properties explicitly, even default properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc418-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc418-136">See also</span></span>

- [<span data-ttu-id="dc418-137">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="dc418-137">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="dc418-138">Parameter und Argumente von Prozeduren</span><span class="sxs-lookup"><span data-stu-id="dc418-138">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="dc418-139">Property Statement</span><span class="sxs-lookup"><span data-stu-id="dc418-139">Property Statement</span></span>](../../../language-reference/statements/property-statement.md)
- [<span data-ttu-id="dc418-140">Standard</span><span class="sxs-lookup"><span data-stu-id="dc418-140">Default</span></span>](../../../language-reference/modifiers/default.md)
- [<span data-ttu-id="dc418-141">Unterschiede zwischen Eigenschaften und Variablen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dc418-141">Differences Between Properties and Variables in Visual Basic</span></span>](./differences-between-properties-and-variables.md)
- [<span data-ttu-id="dc418-142">Vorgehensweise: Erstellen einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dc418-142">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="dc418-143">Vorgehensweise: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen</span><span class="sxs-lookup"><span data-stu-id="dc418-143">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="dc418-144">Vorgehensweise: Aufrufen einer Eigenschaftenprozedur</span><span class="sxs-lookup"><span data-stu-id="dc418-144">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="dc418-145">Vorgehensweise: Ablegen eines Werts in eine Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dc418-145">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="dc418-146">Vorgehensweise: Abrufen eines Werts aus einer Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="dc418-146">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
