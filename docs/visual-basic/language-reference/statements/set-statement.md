---
title: Set-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: c6bb924a3c41e1c586f66c9473a94d1971ee262f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973768"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="03949-102">Set-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="03949-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="03949-103">Deklariert eine `Set` Eigenschaftenprozedur, mit einer Eigenschaft einen Wert zuweisen.</span><span class="sxs-lookup"><span data-stu-id="03949-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03949-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03949-104">Syntax</span></span>  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="03949-105">Teile</span><span class="sxs-lookup"><span data-stu-id="03949-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="03949-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="03949-106">Optional.</span></span> <span data-ttu-id="03949-107">Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="03949-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="03949-108">Optional Klicken Sie auf höchstens die `Get` und `Set` Anweisungen in dieser Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="03949-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="03949-109">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="03949-109">Can be one of the following:</span></span>  
  
-   [<span data-ttu-id="03949-110">Protected</span><span class="sxs-lookup"><span data-stu-id="03949-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [<span data-ttu-id="03949-111">Friend</span><span class="sxs-lookup"><span data-stu-id="03949-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [<span data-ttu-id="03949-112">Private</span><span class="sxs-lookup"><span data-stu-id="03949-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 <span data-ttu-id="03949-113">Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="03949-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="03949-114">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03949-114">Required.</span></span> <span data-ttu-id="03949-115">Parameter, der den neuen Wert für die Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="03949-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="03949-116">Erforderlich, wenn `Option Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="03949-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="03949-117">Typ der `value` Parameter.</span><span class="sxs-lookup"><span data-stu-id="03949-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="03949-118">Der angegebene Datentyp muss den Datentyp der Eigenschaft identisch sein, in denen dies `Set` -Anweisung deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="03949-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="03949-119">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="03949-119">Optional.</span></span> <span data-ttu-id="03949-120">Eine oder mehrere Anweisungen, die beim Ausführen der `Set` -Eigenschaftenprozedur aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="03949-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="03949-121">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="03949-121">Required.</span></span> <span data-ttu-id="03949-122">Beendet die Definition der `Set` Eigenschaftenprozedur.</span><span class="sxs-lookup"><span data-stu-id="03949-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03949-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="03949-123">Remarks</span></span>  
 <span data-ttu-id="03949-124">Jede Eigenschaft müssen einen `Set` Eigenschaftenprozedur, wenn die Eigenschaft markiert ist `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="03949-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="03949-125">Die `Set` Verfahren dient zum Festlegen des Werts der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="03949-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="03949-126">Visual Basic automatisch ruft einer Eigenschaft des `Set` Prozedur, wenn eine zuweisungsanweisung einen Wert in der Eigenschaft gespeichert werden bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="03949-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="03949-127">Visual Basic übergibt einen Parameter für die `Set` Prozedur während der eigenschaftenzuweisungen.</span><span class="sxs-lookup"><span data-stu-id="03949-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="03949-128">Wenn Sie keine Parameter für angeben `Set`, die integrierte Entwicklungsumgebung (IDE) verwendet einen impliziten Parameter mit dem Namen `value`.</span><span class="sxs-lookup"><span data-stu-id="03949-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="03949-129">Der Parameter enthält den Wert der Eigenschaft zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="03949-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="03949-130">In der Regel diesen Wert in einer privaten lokalen Variable speichern und zurückgeben immer die `Get` Prozedur aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="03949-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="03949-131">Der Hauptteil der Deklaration der Eigenschaft darf nur der Eigenschaft des `Get` und `Set` Prozeduren zwischen der [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) und `End Property` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="03949-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="03949-132">Es kann nicht als diese Prozeduren gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="03949-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="03949-133">Insbesondere kann nicht der aktuelle Eigenschaftswert speichern.</span><span class="sxs-lookup"><span data-stu-id="03949-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="03949-134">Sie müssen diesen Wert außerhalb der Eigenschaft speichern, da Wenn Sie es in einer der Eigenschaftenprozeduren speichern, die andere Eigenschaftenprozedur nicht darauf zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="03949-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="03949-135">Der übliche Ansatz ist zum Speichern des Werts in einem [Private](../../../visual-basic/language-reference/modifiers/private.md) Variable, die auf derselben Ebene wie die Eigenschaft deklariert.</span><span class="sxs-lookup"><span data-stu-id="03949-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="03949-136">Definieren Sie eine `Set` -Prozedur in der Eigenschaft, die auf die es angewendet.</span><span class="sxs-lookup"><span data-stu-id="03949-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="03949-137">Die `Set` Prozedur standardmäßig auf die Zugriffsebene der enthaltenden Eigenschaft auf, es sei denn, Sie verwenden `accessmodifier` in die `Set` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="03949-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="03949-138">Regeln</span><span class="sxs-lookup"><span data-stu-id="03949-138">Rules</span></span>  
  
-   <span data-ttu-id="03949-139">**Gemischte Zugriffsebenen.**</span><span class="sxs-lookup"><span data-stu-id="03949-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="03949-140">Wenn Sie eine Eigenschaft mit Lese-/ Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene angeben, entweder die `Get` oder `Set` Prozedur, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="03949-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="03949-141">Wenn Sie dies tun, muss die Zugriffsebene der Prozedur restriktiver ist als die Zugriffsebene der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="03949-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="03949-142">Z. B., wenn die Eigenschaft deklariert ist `Friend`, Sie können deklarieren, die `Set` Prozedur `Private`, aber nicht `Public`.</span><span class="sxs-lookup"><span data-stu-id="03949-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="03949-143">Wenn Sie definieren eine `WriteOnly` -Eigenschaft, die `Set` Prozedur darstellt, die gesamte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="03949-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="03949-144">Sie können nicht deklarieren eine andere Zugriffsebene für `Set`, da hierdurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="03949-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="03949-145">Verhalten</span><span class="sxs-lookup"><span data-stu-id="03949-145">Behavior</span></span>  
  
-   <span data-ttu-id="03949-146">**Zurückgeben einer Eigenschaftenprozedur.**</span><span class="sxs-lookup"><span data-stu-id="03949-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="03949-147">Wenn die `Set` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgeführt, nach der Anweisung, die den zu speichernde Wert bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="03949-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="03949-148">`Set` Property-Prozeduren können entweder Zurückgeben der [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) oder [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md).</span><span class="sxs-lookup"><span data-stu-id="03949-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="03949-149">Die `Exit Property` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung einer Eigenschaftenprozedur.</span><span class="sxs-lookup"><span data-stu-id="03949-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="03949-150">Eine beliebige Anzahl von `Exit Property` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Property` und `Return` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="03949-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03949-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03949-151">Example</span></span>  
 <span data-ttu-id="03949-152">Im folgenden Beispiel wird die `Set` Anweisung, um den Wert einer Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="03949-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="03949-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03949-153">See also</span></span>
- [<span data-ttu-id="03949-154">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="03949-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="03949-155">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="03949-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="03949-156">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="03949-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="03949-157">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="03949-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
