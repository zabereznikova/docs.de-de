---
title: Set-Anweisung
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
ms.openlocfilehash: 75ad6d87f1785fea13a282d953f117c9c234e203
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349568"
---
# <a name="set-statement-visual-basic"></a><span data-ttu-id="64207-102">Set-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="64207-102">Set Statement (Visual Basic)</span></span>
<span data-ttu-id="64207-103">Deklariert eine `Set`-Eigenschaften Prozedur, mit der einer Eigenschaft ein Wert zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="64207-103">Declares a `Set` property procedure used to assign a value to a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64207-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="64207-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a><span data-ttu-id="64207-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="64207-105">Parts</span></span>  
 `attributelist`  
 <span data-ttu-id="64207-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="64207-106">Optional.</span></span> <span data-ttu-id="64207-107">Siehe [Attribut Liste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="64207-107">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
 `accessmodifier`  
 <span data-ttu-id="64207-108">Optional für höchstens eine der `Get`-und `Set` Anweisungen in dieser Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="64207-108">Optional on at most one of the `Get` and `Set` statements in this property.</span></span> <span data-ttu-id="64207-109">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="64207-109">Can be one of the following:</span></span>  
  
- [<span data-ttu-id="64207-110">Protected</span><span class="sxs-lookup"><span data-stu-id="64207-110">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
- [<span data-ttu-id="64207-111">Friend</span><span class="sxs-lookup"><span data-stu-id="64207-111">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
- [<span data-ttu-id="64207-112">Private</span><span class="sxs-lookup"><span data-stu-id="64207-112">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
- `Protected Friend`  
  
 <span data-ttu-id="64207-113">Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="64207-113">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
 `value`  
 <span data-ttu-id="64207-114">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="64207-114">Required.</span></span> <span data-ttu-id="64207-115">-Parameter, der den neuen Wert für die Eigenschaft enthält.</span><span class="sxs-lookup"><span data-stu-id="64207-115">Parameter containing the new value for the property.</span></span>  
  
 `datatype`  
 <span data-ttu-id="64207-116">Erforderlich, wenn `Option Strict` `On`ist.</span><span class="sxs-lookup"><span data-stu-id="64207-116">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="64207-117">Der Datentyp des `value`-Parameters.</span><span class="sxs-lookup"><span data-stu-id="64207-117">Data type of the `value` parameter.</span></span> <span data-ttu-id="64207-118">Der angegebene Datentyp muss mit dem Datentyp der Eigenschaft übereinstimmen, in der diese `Set` Anweisung deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="64207-118">The data type specified must be the same as the data type of the property where this `Set` statement is declared.</span></span>  
  
 `statements`  
 <span data-ttu-id="64207-119">Optional.</span><span class="sxs-lookup"><span data-stu-id="64207-119">Optional.</span></span> <span data-ttu-id="64207-120">Eine oder mehrere-Anweisungen, die ausgeführt werden, wenn die `Set`-Eigenschaften Prozedur aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="64207-120">One or more statements that run when the `Set` property procedure is called.</span></span>  
  
 `End Set`  
 <span data-ttu-id="64207-121">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="64207-121">Required.</span></span> <span data-ttu-id="64207-122">Beendet die Definition der `Set`-Eigenschaften Prozedur.</span><span class="sxs-lookup"><span data-stu-id="64207-122">Terminates the definition of the `Set` property procedure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64207-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64207-123">Remarks</span></span>  
 <span data-ttu-id="64207-124">Jede Eigenschaft muss über eine `Set`-Eigenschaften Prozedur verfügen, es sei denn, die Eigenschaft ist `ReadOnly`markiert.</span><span class="sxs-lookup"><span data-stu-id="64207-124">Every property must have a `Set` property procedure unless the property is marked `ReadOnly`.</span></span> <span data-ttu-id="64207-125">Die `Set` Prozedur wird verwendet, um den Wert der-Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="64207-125">The `Set` procedure is used to set the value of the property.</span></span>  
  
 <span data-ttu-id="64207-126">Visual Basic automatisch die `Set` Prozedur einer Eigenschaft aufruft, wenn eine Zuweisungsanweisung einen Wert bereitstellt, der in der-Eigenschaft gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="64207-126">Visual Basic automatically calls a property's `Set` procedure when an assignment statement provides a value to be stored in the property.</span></span>  
  
 <span data-ttu-id="64207-127">Visual Basic übergibt einen Parameter an die `Set` Prozedur während der Eigenschaften Zuweisungen.</span><span class="sxs-lookup"><span data-stu-id="64207-127">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="64207-128">Wenn Sie keinen Parameter für `Set`bereitstellen, verwendet die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) einen impliziten Parameter mit dem Namen `value`.</span><span class="sxs-lookup"><span data-stu-id="64207-128">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="64207-129">Der-Parameter enthält den Wert, der der-Eigenschaft zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="64207-129">The parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="64207-130">In der Regel speichern Sie diesen Wert in einer privaten lokalen Variable und geben ihn zurück, wenn die `Get` Prozedur aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="64207-130">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
 <span data-ttu-id="64207-131">Der Text der Eigenschafts Deklaration darf nur die `Get`-und `Set` Prozeduren der Eigenschaft zwischen der [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md) und der `End Property`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="64207-131">The body of the property declaration can contain only the property's `Get` and `Set` procedures between the [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md) and the `End Property` statement.</span></span> <span data-ttu-id="64207-132">Es kann nichts anderes als diese Prozeduren speichern.</span><span class="sxs-lookup"><span data-stu-id="64207-132">It cannot store anything other than those procedures.</span></span> <span data-ttu-id="64207-133">Insbesondere kann der aktuelle Wert der Eigenschaft nicht gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="64207-133">In particular, it cannot store the property's current value.</span></span> <span data-ttu-id="64207-134">Sie müssen diesen Wert außerhalb der-Eigenschaft speichern, denn wenn Sie ihn in einer der Eigenschaften Prozeduren speichern, kann die andere Eigenschaften Prozedur nicht darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="64207-134">You must store this value outside the property, because if you store it inside either of the property procedures, the other property procedure cannot access it.</span></span> <span data-ttu-id="64207-135">Die übliche Vorgehensweise besteht darin, den Wert in einer [privaten](../../../visual-basic/language-reference/modifiers/private.md) Variable zu speichern, die auf derselben Ebene wie die-Eigenschaft deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="64207-135">The usual approach is to store the value in a [Private](../../../visual-basic/language-reference/modifiers/private.md) variable declared at the same level as the property.</span></span> <span data-ttu-id="64207-136">Sie müssen eine `Set` Prozedur innerhalb der Eigenschaft definieren, auf die Sie angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="64207-136">You must define a `Set` procedure inside the property to which it applies.</span></span>  
  
 <span data-ttu-id="64207-137">Die `Set` Prozedur verwendet standardmäßig die Zugriffsebene der enthaltenden Eigenschaft, es sei denn, Sie verwenden `accessmodifier` in der `Set`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="64207-137">The `Set` procedure defaults to the access level of its containing property unless you use `accessmodifier` in the `Set` statement.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="64207-138">Regeln</span><span class="sxs-lookup"><span data-stu-id="64207-138">Rules</span></span>  
  
- <span data-ttu-id="64207-139">**Gemischte Zugriffsebenen.**</span><span class="sxs-lookup"><span data-stu-id="64207-139">**Mixed Access Levels.**</span></span> <span data-ttu-id="64207-140">Wenn Sie eine Eigenschaft mit Lese-/Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene für die `Get` oder die `Set` Prozedur angeben, jedoch nicht für beide.</span><span class="sxs-lookup"><span data-stu-id="64207-140">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="64207-141">Wenn Sie dies tun, muss die Prozedur Zugriffsebene restriktiver sein als die Zugriffsebene der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="64207-141">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="64207-142">Wenn die Eigenschaft beispielsweise als `Friend`deklariert ist, können Sie die `Set` Prozedur `Private`deklarieren, jedoch nicht `Public`.</span><span class="sxs-lookup"><span data-stu-id="64207-142">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="64207-143">Wenn Sie eine `WriteOnly`-Eigenschaft definieren, stellt die `Set` Prozedur die gesamte-Eigenschaft dar.</span><span class="sxs-lookup"><span data-stu-id="64207-143">If you are defining a `WriteOnly` property, the `Set` procedure represents the entire property.</span></span> <span data-ttu-id="64207-144">Sie können für `Set`keine andere Zugriffsebene deklarieren, da dadurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="64207-144">You cannot declare a different access level for `Set`, because that would set two access levels for the property.</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="64207-145">Verhalten</span><span class="sxs-lookup"><span data-stu-id="64207-145">Behavior</span></span>  
  
- <span data-ttu-id="64207-146">**Zurückgeben von einer Eigenschaften Prozedur.**</span><span class="sxs-lookup"><span data-stu-id="64207-146">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="64207-147">Wenn die `Set` Prozedur an den aufrufenden Code zurückgegeben wird, wird die Ausführung nach der Anweisung fortgesetzt, die den zu speichernden Wert bereitgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="64207-147">When the `Set` procedure returns to the calling code, execution continues following the statement that provided the value to be stored.</span></span>  
  
     <span data-ttu-id="64207-148">`Set`-Eigenschaften Prozeduren können entweder mithilfe der [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md) oder der [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="64207-148">`Set` property procedures can return using either the [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) or the [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md).</span></span>  
  
     <span data-ttu-id="64207-149">Die Anweisungen `Exit Property` und `Return` führen zu einem sofortigen Beenden einer Eigenschaften Prozedur.</span><span class="sxs-lookup"><span data-stu-id="64207-149">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="64207-150">Eine beliebige Anzahl von `Exit Property`-und `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können `Exit Property`-und `Return`-Anweisungen mischen.</span><span class="sxs-lookup"><span data-stu-id="64207-150">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64207-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="64207-151">Example</span></span>  
 <span data-ttu-id="64207-152">Im folgenden Beispiel wird die `Set`-Anweisung verwendet, um den Wert einer Eigenschaft festzulegen.</span><span class="sxs-lookup"><span data-stu-id="64207-152">The following example uses the `Set` statement to set the value of a property.</span></span>  
  
 [!code-vb[VbVbalrStatements#55](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#55)]  
  
## <a name="see-also"></a><span data-ttu-id="64207-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64207-153">See also</span></span>

- [<span data-ttu-id="64207-154">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="64207-154">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)
- [<span data-ttu-id="64207-155">Property-Anweisung</span><span class="sxs-lookup"><span data-stu-id="64207-155">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="64207-156">Sub-Anweisung</span><span class="sxs-lookup"><span data-stu-id="64207-156">Sub Statement</span></span>](../../../visual-basic/language-reference/statements/sub-statement.md)
- [<span data-ttu-id="64207-157">Eigenschaftenprozeduren</span><span class="sxs-lookup"><span data-stu-id="64207-157">Property Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
