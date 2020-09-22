---
title: Get-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Get
helpviewer_keywords:
- Get statement [Visual Basic], syntax
- Get statement [Visual Basic]
- properties [Visual Basic], read-only
- read-only properties
- Get keyword [Visual Basic]
- property procedures [Visual Basic], Get statements
ms.assetid: 56b05cdc-bd64-4dfd-bb12-824eacec6f94
ms.openlocfilehash: 3da6c099b3f43a144484eaddf58605609eb0bbfe
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866196"
---
# <a name="get-statement"></a><span data-ttu-id="28e6b-102">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="28e6b-102">Get Statement</span></span>

<span data-ttu-id="28e6b-103">Deklariert eine- `Get` Eigenschaften Prozedur, mit der der Wert einer Eigenschaft abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="28e6b-103">Declares a `Get` property procedure used to retrieve the value of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28e6b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="28e6b-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Get()  
    [ statements ]  
End Get  
```  
  
## <a name="parts"></a><span data-ttu-id="28e6b-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="28e6b-105">Parts</span></span>  
  
|<span data-ttu-id="28e6b-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="28e6b-106">Term</span></span>|<span data-ttu-id="28e6b-107">Definition</span><span class="sxs-lookup"><span data-stu-id="28e6b-107">Definition</span></span>|  
|---|---|  
|`attributelist`|<span data-ttu-id="28e6b-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="28e6b-108">Optional.</span></span> <span data-ttu-id="28e6b-109">Siehe [Attribut Liste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="28e6b-109">See [Attribute List](attribute-list.md).</span></span>|  
|`accessmodifier`|<span data-ttu-id="28e6b-110">Optional für höchstens eine der `Get` -und- `Set` Anweisungen in dieser Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="28e6b-110">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="28e6b-111">Dabei kann es sich um eine der folgenden Methoden handeln:</span><span class="sxs-lookup"><span data-stu-id="28e6b-111">Can be one of the following:</span></span><br /><br /> <span data-ttu-id="28e6b-112">-   [Gebieten](../modifiers/protected.md)</span><span class="sxs-lookup"><span data-stu-id="28e6b-112">-   [Protected](../modifiers/protected.md)</span></span><br /><span data-ttu-id="28e6b-113">-   [Kollegen](../modifiers/friend.md)</span><span class="sxs-lookup"><span data-stu-id="28e6b-113">-   [Friend](../modifiers/friend.md)</span></span><br /><span data-ttu-id="28e6b-114">-   [Private](../modifiers/private.md)</span><span class="sxs-lookup"><span data-stu-id="28e6b-114">-   [Private](../modifiers/private.md)</span></span><br />-   `Protected Friend`<br /><br /> <span data-ttu-id="28e6b-115">Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="28e6b-115">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>|  
|`statements`|<span data-ttu-id="28e6b-116">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="28e6b-116">Optional.</span></span> <span data-ttu-id="28e6b-117">Eine oder mehrere-Anweisungen, die ausgeführt werden, wenn die- `Get` Eigenschaften Prozedur aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="28e6b-117">One or more statements that run when the `Get` property procedure is called.</span></span>|  
|`End Get`|<span data-ttu-id="28e6b-118">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="28e6b-118">Required.</span></span> <span data-ttu-id="28e6b-119">Beendet die Definition der `Get` Eigenschaften Prozedur.</span><span class="sxs-lookup"><span data-stu-id="28e6b-119">Terminates the definition of the `Get` property procedure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="28e6b-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="28e6b-120">Remarks</span></span>  

 <span data-ttu-id="28e6b-121">Jede Eigenschaft muss über eine `Get` Eigenschaften Prozedur verfügen, es sei denn, die Eigenschaft ist gekennzeichnet `WriteOnly` .</span><span class="sxs-lookup"><span data-stu-id="28e6b-121">Every property must have a `Get` property procedure unless the property is marked `WriteOnly`.</span></span> <span data-ttu-id="28e6b-122">Die `Get` Prozedur wird verwendet, um den aktuellen Wert der Eigenschaft zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="28e6b-122">The `Get` procedure is used to return the current value of the property.</span></span>  
  
 <span data-ttu-id="28e6b-123">Visual Basic automatisch die-Prozedur einer Eigenschaft aufruft, `Get` Wenn ein Ausdruck den Eigenschafts Wert anfordert.</span><span class="sxs-lookup"><span data-stu-id="28e6b-123">Visual Basic automatically calls a property's `Get` procedure when an expression requests the property's value.</span></span>  
  
 <span data-ttu-id="28e6b-124">Der Text der Eigenschafts Deklaration darf nur die- `Get` und- `Set` Prozeduren der Eigenschaft zwischen der- [Eigenschafts Anweisung](property-statement.md) und der- `End Property` Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="28e6b-124">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="28e6b-125">Es kann nichts anderes als diese Prozeduren speichern.</span><span class="sxs-lookup"><span data-stu-id="28e6b-125">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="28e6b-126">Insbesondere kann der aktuelle Wert der Eigenschaft nicht gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="28e6b-126">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="28e6b-127">Sie müssen diesen Wert außerhalb der-Eigenschaft speichern, denn wenn Sie ihn in einer der Eigenschaften Prozeduren speichern, kann die andere Eigenschaften Prozedur nicht darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="28e6b-127">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="28e6b-128">Die übliche Vorgehensweise besteht darin, den Wert in einer [privaten](../modifiers/private.md) Variable zu speichern, die auf derselben Ebene wie die-Eigenschaft deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="28e6b-128">The usual approach is to store the value in a [Private](../modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="28e6b-129">Sie müssen eine `Get` Prozedur innerhalb der Eigenschaft definieren, auf die Sie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="28e6b-129">You must define a `Get` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="28e6b-130">Die `Get` Prozedur verwendet standardmäßig die Zugriffsebene der enthaltenden Eigenschaft, es sei denn, Sie verwenden `accessmodifier` in der- `Get` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="28e6b-130">The `Get` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Get` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="28e6b-131">Regeln</span><span class="sxs-lookup"><span data-stu-id="28e6b-131">Rules</span></span>  
  
- <span data-ttu-id="28e6b-132">**Gemischte Zugriffsebenen.**</span><span class="sxs-lookup"><span data-stu-id="28e6b-132">**Mixed Access Levels.**</span></span> <span data-ttu-id="28e6b-133">Wenn Sie eine Lese-/Schreibeigenschaft definieren, können Sie optional eine andere Zugriffsebene für die- `Get` oder die- `Set` Prozedur angeben, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="28e6b-133">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="28e6b-134">Wenn Sie dies tun, muss die Prozedur Zugriffsebene restriktiver sein als die Zugriffsebene der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="28e6b-134">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="28e6b-135">Wenn beispielsweise die-Eigenschaft deklariert wird `Friend` , können Sie die Prozedur deklarieren `Get` `Private` , jedoch nicht `Public` .</span><span class="sxs-lookup"><span data-stu-id="28e6b-135">For example, if the property is declared `Friend`, you can declare the `Get` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="28e6b-136">Wenn Sie eine Eigenschaft definieren `ReadOnly` , stellt die `Get` Prozedur die gesamte Eigenschaft dar.</span><span class="sxs-lookup"><span data-stu-id="28e6b-136">If you are defining a `ReadOnly` property, the `Get` procedure represents the entire property.</span></span> <span data-ttu-id="28e6b-137">Sie können keine andere Zugriffsebene für deklarieren `Get` , da dadurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="28e6b-137">You cannot declare a different access level for `Get`, because that would set two access levels for the property.</span></span>  
  
- <span data-ttu-id="28e6b-138">**Rückgabetyp.**</span><span class="sxs-lookup"><span data-stu-id="28e6b-138">**Return Type.**</span></span> <span data-ttu-id="28e6b-139">Die [Property-Anweisung](property-statement.md) kann den Datentyp des zurückgegebenen Werts deklarieren.</span><span class="sxs-lookup"><span data-stu-id="28e6b-139">The [Property Statement](property-statement.md) can declare the data type of the value it returns.</span></span> <span data-ttu-id="28e6b-140">Der-Datentyp wird von der `Get` Prozedur automatisch zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28e6b-140">The `Get` procedure automatically returns that data type.</span></span> <span data-ttu-id="28e6b-141">Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="28e6b-141">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="28e6b-142">Wenn die- `Property` Anweisung nicht angibt `returntype` , gibt die Prozedur zurück `Object` .</span><span class="sxs-lookup"><span data-stu-id="28e6b-142">If the `Property` statement does not specify `returntype`, the procedure returns `Object`.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="28e6b-143">Verhalten</span><span class="sxs-lookup"><span data-stu-id="28e6b-143">Behavior</span></span>  
  
- <span data-ttu-id="28e6b-144">**Zurückgeben aus einer Prozedur.**</span><span class="sxs-lookup"><span data-stu-id="28e6b-144">**Returning from a Procedure.**</span></span> <span data-ttu-id="28e6b-145">Wenn die `Get` Prozedur in den aufrufenden Code zurückkehrt, wird die Ausführung innerhalb der Anweisung fortgesetzt, die den Eigenschafts Wert angefordert hat.</span><span class="sxs-lookup"><span data-stu-id="28e6b-145">When the `Get` procedure returns to the calling code, execution continues within the statement that requested the property value.</span></span>  
  
     <span data-ttu-id="28e6b-146">`Get` Eigenschaften Prozeduren können entweder mithilfe der [Return-Anweisung](return-statement.md) oder durch Zuweisen des Rückgabewerts zum Eigenschaftsnamen einen Wert zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="28e6b-146">`Get` property procedures can return a value using either the [Return Statement](return-statement.md) or by assigning the return value to the property name.</span></span> <span data-ttu-id="28e6b-147">Weitere Informationen finden Sie unter "Rückgabewert" in der [Function-Anweisung](function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="28e6b-147">For more information, see "Return Value" in [Function Statement](function-statement.md).</span></span>  
  
     <span data-ttu-id="28e6b-148">Die `Exit Property` -und- `Return` Anweisungen führen zu einem sofortigen Beenden einer Eigenschaften Prozedur.</span><span class="sxs-lookup"><span data-stu-id="28e6b-148">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="28e6b-149">Eine beliebige Anzahl von `Exit Property` -und- `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können die `Exit Property` -und- `Return` Anweisungen</span><span class="sxs-lookup"><span data-stu-id="28e6b-149">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
- <span data-ttu-id="28e6b-150">**Rückgabewert.**</span><span class="sxs-lookup"><span data-stu-id="28e6b-150">**Return Value.**</span></span> <span data-ttu-id="28e6b-151">Um einen Wert aus einer Prozedur zurückzugeben `Get` , können Sie den Wert entweder dem Eigenschaftsnamen zuweisen oder ihn in eine [Return-Anweisung](return-statement.md)einschließen.</span><span class="sxs-lookup"><span data-stu-id="28e6b-151">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a [Return Statement](return-statement.md).</span></span> <span data-ttu-id="28e6b-152">Die `Return` -Anweisung weist gleichzeitig den `Get` Rückgabewert der Prozedur zu und beendet die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="28e6b-152">The `Return` statement simultaneously assigns the `Get` procedure return value and exits the procedure.</span></span>  
  
     <span data-ttu-id="28e6b-153">Wenn Sie verwenden `Exit Property` , ohne dem Eigenschaftsnamen einen Wert zuzuweisen, `Get` gibt die Prozedur den Standardwert für den Datentyp der Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="28e6b-153">If you use `Exit Property` without assigning a value to the property name, the `Get` procedure returns the default value for the property's data type.</span></span> <span data-ttu-id="28e6b-154">Weitere Informationen finden Sie unter "Rückgabewert" in der [Function-Anweisung](function-statement.md).</span><span class="sxs-lookup"><span data-stu-id="28e6b-154">For more information, see "Return Value" in [Function Statement](function-statement.md).</span></span>  
  
     <span data-ttu-id="28e6b-155">Im folgenden Beispiel werden zwei Möglichkeiten veranschaulicht, wie die schreibgeschützte Eigenschaft `quoteForTheDay` den in der privaten Variablen gespeicherten Wert zurückgeben kann `quoteValue` .</span><span class="sxs-lookup"><span data-stu-id="28e6b-155">The following example illustrates two ways the read-only property `quoteForTheDay` can return the value held in the private variable `quoteValue`.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a><span data-ttu-id="28e6b-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="28e6b-156">Example</span></span>  

 <span data-ttu-id="28e6b-157">Im folgenden Beispiel wird die- `Get` Anweisung verwendet, um den Wert einer Eigenschaft zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="28e6b-157">The following example uses the `Get` statement to return the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="28e6b-158">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="28e6b-158">See also</span></span>

- [<span data-ttu-id="28e6b-159">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="28e6b-159">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="28e6b-160">Property Statement</span><span class="sxs-lookup"><span data-stu-id="28e6b-160">Property Statement</span></span>](property-statement.md)
- [<span data-ttu-id="28e6b-161">Exit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="28e6b-161">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="28e6b-162">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="28e6b-162">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="28e6b-163">Exemplarische Vorgehensweise: Definieren von Klassen</span><span class="sxs-lookup"><span data-stu-id="28e6b-163">Walkthrough: Defining Classes</span></span>](../../programming-guide/language-features/objects-and-classes/walkthrough-defining-classes.md)
