---
title: Property Statement
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 3f3ced3f0c441518594820f75243c71fb0c3babd
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="property-statement"></a><span data-ttu-id="e5e06-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="e5e06-102">Property Statement</span></span>
<span data-ttu-id="e5e06-103">Deklariert den Namen einer Eigenschaft und den Eigenschaftenprozeduren, die zum Speichern und Abrufen des Werts der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e5e06-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5e06-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5e06-104">Syntax</span></span>  
  
```vb  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]  
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
    [ <attributelist> ] [ accessmodifier ] Get  
        [ statements ]  
    End Get  
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )  
        [ statements ]  
    End Set  
End Property  
- or -  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]   
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
```  
  
## <a name="parts"></a><span data-ttu-id="e5e06-105">Teile</span><span class="sxs-lookup"><span data-stu-id="e5e06-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="e5e06-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-106">Optional.</span></span> <span data-ttu-id="e5e06-107">Liste der Attribute, die für diese Eigenschaft gelten oder `Get` oder `Set` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e5e06-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="e5e06-108">Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="e5e06-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="e5e06-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-109">Optional.</span></span> <span data-ttu-id="e5e06-110">Gibt an, dass diese Eigenschaft ist die Standardeigenschaft für die Klasse oder Struktur, die auf dem sie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="e5e06-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="e5e06-111">Standardeigenschaften können müssen Parameter annehmen und festgelegt und ohne den Namen der Eigenschaft abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e5e06-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="e5e06-112">Wenn Sie die Eigenschaft als deklarieren `Default`, können keine `Private` auf die Eigenschaft oder eine der Eigenschaftenprozeduren.</span><span class="sxs-lookup"><span data-stu-id="e5e06-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="e5e06-113">Optional Klicken Sie auf die `Property` Anweisung und höchstens eines der `Get` und `Set` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e5e06-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="e5e06-114">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="e5e06-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="e5e06-115">Public</span><span class="sxs-lookup"><span data-stu-id="e5e06-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="e5e06-116">Protected</span><span class="sxs-lookup"><span data-stu-id="e5e06-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="e5e06-117">Friend</span><span class="sxs-lookup"><span data-stu-id="e5e06-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="e5e06-118">Private</span><span class="sxs-lookup"><span data-stu-id="e5e06-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [<span data-ttu-id="e5e06-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="e5e06-119">Protected Friend</span></span>](../../language-reference/modifiers/protected-friend.md) 

    - [<span data-ttu-id="e5e06-120">Geschützt privat</span><span class="sxs-lookup"><span data-stu-id="e5e06-120">Private Protected</span></span>](../../language-reference/modifiers/private-protected.md)
  
     <span data-ttu-id="e5e06-121">Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e5e06-121">See [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="e5e06-122">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-122">Optional.</span></span> <span data-ttu-id="e5e06-123">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="e5e06-123">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="e5e06-124">Overloads</span><span class="sxs-lookup"><span data-stu-id="e5e06-124">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="e5e06-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="e5e06-125">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="e5e06-126">Overridable</span><span class="sxs-lookup"><span data-stu-id="e5e06-126">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="e5e06-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="e5e06-127">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="e5e06-128">MustOverride</span><span class="sxs-lookup"><span data-stu-id="e5e06-128">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="e5e06-129">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-129">Optional.</span></span> <span data-ttu-id="e5e06-130">Finden Sie unter [freigegebene](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="e5e06-130">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="e5e06-131">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-131">Optional.</span></span> <span data-ttu-id="e5e06-132">Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="e5e06-132">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="e5e06-133">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-133">Optional.</span></span> <span data-ttu-id="e5e06-134">Finden Sie unter [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="e5e06-134">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="e5e06-135">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-135">Optional.</span></span> <span data-ttu-id="e5e06-136">Finden Sie unter [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="e5e06-136">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="e5e06-137">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-137">Optional.</span></span> <span data-ttu-id="e5e06-138">Finden Sie unter [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="e5e06-138">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="e5e06-139">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5e06-139">Required.</span></span> <span data-ttu-id="e5e06-140">Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e5e06-140">Name of the property.</span></span> <span data-ttu-id="e5e06-141">Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="e5e06-141">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="e5e06-142">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-142">Optional.</span></span> <span data-ttu-id="e5e06-143">Liste der Namen lokaler Variablen darstellt, die Parameter dieser Eigenschaft und mögliche zusätzliche Parameter der `Set` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e5e06-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="e5e06-144">Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="e5e06-144">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="e5e06-145">Erforderlich, wenn `Option``Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="e5e06-145">Required if `Option``Strict` is `On`.</span></span> <span data-ttu-id="e5e06-146">Der Datentyp der von dieser Eigenschaft zurückgegebene Wert.</span><span class="sxs-lookup"><span data-stu-id="e5e06-146">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="e5e06-147">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-147">Optional.</span></span> <span data-ttu-id="e5e06-148">Gibt an, dass diese Eigenschaft implementiert wird, eine oder mehrere Eigenschaften, die jeweils in einer Schnittstelle implementiert, die durch diese Eigenschaft enthaltende Klasse oder Struktur definiert.</span><span class="sxs-lookup"><span data-stu-id="e5e06-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="e5e06-149">Finden Sie unter [Anweisung implementiert](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="e5e06-149">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="e5e06-150">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e5e06-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="e5e06-151">Liste der Eigenschaften, die implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="e5e06-151">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="e5e06-152">Jede `implementedproperty` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="e5e06-152">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="e5e06-153">Segment</span><span class="sxs-lookup"><span data-stu-id="e5e06-153">Part</span></span>|<span data-ttu-id="e5e06-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e5e06-154">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="e5e06-155">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5e06-155">Required.</span></span> <span data-ttu-id="e5e06-156">Name einer Schnittstelle implementiert, die von dieser Eigenschaft der enthaltenden Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="e5e06-156">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="e5e06-157">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e5e06-157">Required.</span></span> <span data-ttu-id="e5e06-158">Mit dem die Eigenschaft, im definiert ist Namen `interface`.</span><span class="sxs-lookup"><span data-stu-id="e5e06-158">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="e5e06-159">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-159">Optional.</span></span> <span data-ttu-id="e5e06-160">Erforderlich, wenn die Eigenschaft gekennzeichnet ist `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="e5e06-160">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="e5e06-161">Startet eine `Get` Eigenschaftenprozedur, der verwendet wird, um den Wert der Eigenschaft zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="e5e06-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="e5e06-162">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-162">Optional.</span></span> <span data-ttu-id="e5e06-163">Block von Anweisungen für die Ausführung innerhalb der `Get` oder `Set` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e5e06-163">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="e5e06-164">Beendet die `Get` -Eigenschaftenprozedur.</span><span class="sxs-lookup"><span data-stu-id="e5e06-164">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="e5e06-165">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e5e06-165">Optional.</span></span> <span data-ttu-id="e5e06-166">Erforderlich, wenn die Eigenschaft gekennzeichnet ist `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="e5e06-166">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="e5e06-167">Startet eine `Set` Eigenschaftenprozedur, die zum Speichern des Werts der Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e5e06-167">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="e5e06-168">Beendet die `Set` -Eigenschaftenprozedur.</span><span class="sxs-lookup"><span data-stu-id="e5e06-168">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="e5e06-169">Beendet die Definition dieser Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e5e06-169">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5e06-170">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e5e06-170">Remarks</span></span>  
 <span data-ttu-id="e5e06-171">Die `Property` -Anweisung führt die Deklaration einer Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e5e06-171">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="e5e06-172">Eine Eigenschaft aufweisen kann eine `Get` Prozedur (schreibgeschützt), eine `Set` Prozedur (lesegeschützt) oder beide (Lese-/ Schreibzugriff).</span><span class="sxs-lookup"><span data-stu-id="e5e06-172">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="e5e06-173">Sie lassen die `Get` und `Set` Verfahren, wenn Sie eine automatisch implementierte Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="e5e06-173">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="e5e06-174">Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="e5e06-174">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="e5e06-175">Sie können `Property` nur auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="e5e06-175">You can use `Property` only at class level.</span></span> <span data-ttu-id="e5e06-176">Dies bedeutet, dass die *Deklarationskontext* für eine Eigenschaft muss eine Klasse, Struktur, Modul oder Schnittstelle, und nicht mit einer Quelldatei, Namespace, Prozedur oder Block.</span><span class="sxs-lookup"><span data-stu-id="e5e06-176">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="e5e06-177">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="e5e06-177">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="e5e06-178">Standardmäßig verwenden Eigenschaften öffentlicher Zugriff.</span><span class="sxs-lookup"><span data-stu-id="e5e06-178">By default, properties use public access.</span></span> <span data-ttu-id="e5e06-179">Sie können die Zugriffsebene für eine Eigenschaft mit einem Zugriffsmodifizierer anpassen, auf die `Property` -Anweisung, und Sie können optional auch anpassen, eine der Eigenschaftenprozeduren auf eine restriktivere Zugriffsebene.</span><span class="sxs-lookup"><span data-stu-id="e5e06-179">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="e5e06-180">Visual Basic übergibt die Parameter für die `Set` Prozedur während der eigenschaftenzuweisungen.</span><span class="sxs-lookup"><span data-stu-id="e5e06-180">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="e5e06-181">Wenn Sie keine Parameter für angeben `Set`, der integrierten Entwicklungsumgebung (IDE) verwendet einen impliziten Parameter mit dem Namen `value`.</span><span class="sxs-lookup"><span data-stu-id="e5e06-181">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="e5e06-182">Dieser Parameter enthält den Wert der Eigenschaft zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e5e06-182">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="e5e06-183">In der Regel speichern den Wert in einer privaten lokalen Variable und gibt es immer die `Get` Prozedur aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="e5e06-183">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="e5e06-184">Regeln</span><span class="sxs-lookup"><span data-stu-id="e5e06-184">Rules</span></span>  
  
-   <span data-ttu-id="e5e06-185">**Gemischte Zugriffsebenen.**</span><span class="sxs-lookup"><span data-stu-id="e5e06-185">**Mixed Access Levels.**</span></span> <span data-ttu-id="e5e06-186">Wenn Sie eine Eigenschaft mit Lese-/ Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene angeben, entweder die `Get` oder `Set` Prozedur, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="e5e06-186">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="e5e06-187">Wenn in diesem Fall muss die Zugriffsebene der Prozedur restriktiver ist als die Zugriffsebene der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e5e06-187">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="e5e06-188">Z. B., wenn die Eigenschaft deklariert wird `Friend`, Sie können deklarieren, die `Set` Prozedur `Private`, aber nicht `Public`.</span><span class="sxs-lookup"><span data-stu-id="e5e06-188">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="e5e06-189">Wenn Sie definieren eine `ReadOnly` oder `WriteOnly` -Eigenschaft, die einzelne Eigenschaftenprozedur (`Get` oder `Set`bzw.) stellt alle von der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="e5e06-189">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="e5e06-190">Eine andere Zugriffsebene für eine solche Prozedur nicht deklariert werden, da hierdurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e5e06-190">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="e5e06-191">**Der Rückgabetyp.**</span><span class="sxs-lookup"><span data-stu-id="e5e06-191">**Return Type.**</span></span> <span data-ttu-id="e5e06-192">Die `Property` -Anweisung kann den Datentyp des zurückgegebenen Werts deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e5e06-192">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="e5e06-193">Sie können einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="e5e06-193">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="e5e06-194">Wenn Sie keinen angeben `returntype`, gibt die Eigenschaft `Object`.</span><span class="sxs-lookup"><span data-stu-id="e5e06-194">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="e5e06-195">**-Implementierung.**</span><span class="sxs-lookup"><span data-stu-id="e5e06-195">**Implementation.**</span></span> <span data-ttu-id="e5e06-196">Wenn diese Eigenschaft verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur benötigen eine `Implements` Anweisung unmittelbar nach seiner `Class` oder `Structure` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e5e06-196">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="e5e06-197">Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="e5e06-197">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="e5e06-198">Jedoch den Namen, die mit dem eine Schnittstelle definiert die `Property` (in `definedname`) muss nicht in den Namen dieser Eigenschaft entsprechen (im `name`).</span><span class="sxs-lookup"><span data-stu-id="e5e06-198">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="e5e06-199">Verhalten</span><span class="sxs-lookup"><span data-stu-id="e5e06-199">Behavior</span></span>  
  
-   <span data-ttu-id="e5e06-200">**Zurückgeben aus einer Eigenschaftenprozedur.**</span><span class="sxs-lookup"><span data-stu-id="e5e06-200">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="e5e06-201">Wenn die `Get` oder `Set` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgeführt, mit der Anweisung nach der Anweisung, die sie aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="e5e06-201">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="e5e06-202">Die `Exit Property` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung einer Eigenschaftenprozedur.</span><span class="sxs-lookup"><span data-stu-id="e5e06-202">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="e5e06-203">Eine beliebige Anzahl von `Exit Property` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Property` und `Return` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="e5e06-203">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="e5e06-204">**Der Rückgabewert.**</span><span class="sxs-lookup"><span data-stu-id="e5e06-204">**Return Value.**</span></span> <span data-ttu-id="e5e06-205">Zurückzugebenden einen Wert aus einer `Get` Prozedur, Sie können entweder weisen den Namen der Eigenschaft den Wert oder fügen Sie ihn in eine `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="e5e06-205">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="e5e06-206">Im folgende Beispiel weist den Rückgabewert des Eigenschaftennamens `quoteForTheDay` und verwendet dann die `Exit Property` -Anweisung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e5e06-206">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     <span data-ttu-id="e5e06-207">Bei Verwendung von `Exit Property` ohne Zuweisen eines Werts zur `name`die `Get` Prozedur gibt den Standardwert für den Datentyp der Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="e5e06-207">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="e5e06-208">Die `Return` Anweisung zur gleichen Zeit weist der `Get` Prozedur zurückgeben, Wert und Beenden der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="e5e06-208">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="e5e06-209">Das folgende Beispiel zeigt dies.</span><span class="sxs-lookup"><span data-stu-id="e5e06-209">The following example shows this.</span></span>  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a><span data-ttu-id="e5e06-210">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5e06-210">Example</span></span>  
 <span data-ttu-id="e5e06-211">Das folgende Beispiel deklariert eine Eigenschaft in einer Klasse.</span><span class="sxs-lookup"><span data-stu-id="e5e06-211">The following example declares a property in a class.</span></span>  
  
 [!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="e5e06-212">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5e06-212">See Also</span></span>  
 [<span data-ttu-id="e5e06-213">Automatisch implementierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e5e06-213">Auto-Implemented Properties</span></span>](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)  
 [<span data-ttu-id="e5e06-214">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="e5e06-214">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [<span data-ttu-id="e5e06-215">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e5e06-215">Get Statement</span></span>](../../../visual-basic/language-reference/statements/get-statement.md)  
 [<span data-ttu-id="e5e06-216">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e5e06-216">Set Statement</span></span>](../../../visual-basic/language-reference/statements/set-statement.md)  
 [<span data-ttu-id="e5e06-217">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="e5e06-217">Parameter List</span></span>](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [<span data-ttu-id="e5e06-218">Default</span><span class="sxs-lookup"><span data-stu-id="e5e06-218">Default</span></span>](../../../visual-basic/language-reference/modifiers/default.md)
