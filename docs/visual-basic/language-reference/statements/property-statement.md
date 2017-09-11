---
title: Property-Anweisung | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
dev_langs:
- VB
helpviewer_keywords:
- Property statement
- default modifier
- property procedures, Property statements
- Property keyword
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
caps.latest.revision: 41
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
ms.sourcegitcommit: 14abadaf548e228244a1ff7ca72fa3896ef4eb5d
ms.openlocfilehash: dbd779b4b6a1dd167e8581066b0fbe034cd2d8f2
ms.contentlocale: de-de
ms.lasthandoff: 05/23/2017

---
# <a name="property-statement"></a><span data-ttu-id="4dc85-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="4dc85-102">Property Statement</span></span>
<span data-ttu-id="4dc85-103">Deklariert den Namen einer Eigenschaft sowie die Eigenschaftenprozeduren zum Speichern und Abrufen des Werts der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4dc85-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dc85-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4dc85-104">Syntax</span></span>  
  
```  
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
  
## <a name="parts"></a><span data-ttu-id="4dc85-105">Teile</span><span class="sxs-lookup"><span data-stu-id="4dc85-105">Parts</span></span>  
  
-   `attributelist`  
  
     <span data-ttu-id="4dc85-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-106">Optional.</span></span> <span data-ttu-id="4dc85-107">Liste der Attribute, die für diese Eigenschaft gelten oder `Get` oder `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4dc85-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="4dc85-108">Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="4dc85-108">See [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md).</span></span>  
  
-   `Default`  
  
     <span data-ttu-id="4dc85-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-109">Optional.</span></span> <span data-ttu-id="4dc85-110">Gibt an, dass diese Eigenschaft ist die Standardeigenschaft für die Klasse oder Struktur, in der sie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4dc85-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="4dc85-111">Standardeigenschaften können müssen Parameter akzeptieren und festgelegt und ohne den Eigenschaftsnamen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4dc85-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="4dc85-112">Wenn Sie die Eigenschaft als deklarieren `Default`, können keine `Private` für die Eigenschaft noch für eine ihrer Eigenschaftenprozeduren.</span><span class="sxs-lookup"><span data-stu-id="4dc85-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>  
  
-   `accessmodifier`  
  
     <span data-ttu-id="4dc85-113">Optional Klicken Sie auf die `Property` -Anweisung und für höchstens eine der der `Get` und `Set` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="4dc85-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="4dc85-114">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="4dc85-114">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="4dc85-115">Public</span><span class="sxs-lookup"><span data-stu-id="4dc85-115">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [<span data-ttu-id="4dc85-116">Protected</span><span class="sxs-lookup"><span data-stu-id="4dc85-116">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [<span data-ttu-id="4dc85-117">Friend</span><span class="sxs-lookup"><span data-stu-id="4dc85-117">Friend</span></span>](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [<span data-ttu-id="4dc85-118">Private</span><span class="sxs-lookup"><span data-stu-id="4dc85-118">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     <span data-ttu-id="4dc85-119">Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4dc85-119">See [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
-   `propertymodifiers`  
  
     <span data-ttu-id="4dc85-120">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-120">Optional.</span></span> <span data-ttu-id="4dc85-121">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="4dc85-121">Can be one of the following:</span></span>  
  
    -   [<span data-ttu-id="4dc85-122">Overloads</span><span class="sxs-lookup"><span data-stu-id="4dc85-122">Overloads</span></span>](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [<span data-ttu-id="4dc85-123">Overrides</span><span class="sxs-lookup"><span data-stu-id="4dc85-123">Overrides</span></span>](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [<span data-ttu-id="4dc85-124">Overridable</span><span class="sxs-lookup"><span data-stu-id="4dc85-124">Overridable</span></span>](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [<span data-ttu-id="4dc85-125">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="4dc85-125">NotOverridable</span></span>](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [<span data-ttu-id="4dc85-126">MustOverride</span><span class="sxs-lookup"><span data-stu-id="4dc85-126">MustOverride</span></span>](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     <span data-ttu-id="4dc85-127">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-127">Optional.</span></span> <span data-ttu-id="4dc85-128">Finden Sie unter [freigegebenen](../../../visual-basic/language-reference/modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="4dc85-128">See [Shared](../../../visual-basic/language-reference/modifiers/shared.md).</span></span>  
  
-   `Shadows`  
  
     <span data-ttu-id="4dc85-129">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-129">Optional.</span></span> <span data-ttu-id="4dc85-130">Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="4dc85-130">See [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).</span></span>  
  
-   `ReadOnly`  
  
     <span data-ttu-id="4dc85-131">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-131">Optional.</span></span> <span data-ttu-id="4dc85-132">Finden Sie unter [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="4dc85-132">See [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
-   `WriteOnly`  
  
     <span data-ttu-id="4dc85-133">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-133">Optional.</span></span> <span data-ttu-id="4dc85-134">Finden Sie unter [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span><span class="sxs-lookup"><span data-stu-id="4dc85-134">See [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).</span></span>  
  
-   `Iterator`  
  
     <span data-ttu-id="4dc85-135">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-135">Optional.</span></span> <span data-ttu-id="4dc85-136">Finden Sie unter [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="4dc85-136">See [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).</span></span>  
  
-   `name`  
  
     <span data-ttu-id="4dc85-137">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4dc85-137">Required.</span></span> <span data-ttu-id="4dc85-138">Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4dc85-138">Name of the property.</span></span> <span data-ttu-id="4dc85-139">Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="4dc85-139">See [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
-   `parameterlist`  
  
     <span data-ttu-id="4dc85-140">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-140">Optional.</span></span> <span data-ttu-id="4dc85-141">Liste der Namen lokaler Variablen, die die Parameter dieser Eigenschaft und mögliche zusätzliche Parameter der darstellen der `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4dc85-141">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="4dc85-142">Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="4dc85-142">See [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).</span></span>  
  
-   `returntype`  
  
     <span data-ttu-id="4dc85-143">Erforderlich, wenn `Option``Strict` ist `On`.</span><span class="sxs-lookup"><span data-stu-id="4dc85-143">Required if `Option``Strict` is `On`.</span></span> <span data-ttu-id="4dc85-144">Der Datentyp des von dieser Eigenschaft zurückgegebenen Werts.</span><span class="sxs-lookup"><span data-stu-id="4dc85-144">Data type of the value returned by this property.</span></span>  
  
-   `Implements`  
  
     <span data-ttu-id="4dc85-145">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-145">Optional.</span></span> <span data-ttu-id="4dc85-146">Gibt an, dass diese Eigenschaft implementiert eine oder mehrere Eigenschaften, die jeweils in einer Schnittstelle implementiert, die von dieser Eigenschaft enthaltenden Klasse oder Struktur definiert.</span><span class="sxs-lookup"><span data-stu-id="4dc85-146">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="4dc85-147">Finden Sie unter [Anweisung implementiert](../../../visual-basic/language-reference/statements/implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="4dc85-147">See [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).</span></span>  
  
-   `implementslist`  
  
     <span data-ttu-id="4dc85-148">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4dc85-148">Required if `Implements` is supplied.</span></span> <span data-ttu-id="4dc85-149">Liste der implementierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="4dc85-149">List of properties being implemented.</span></span>  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     <span data-ttu-id="4dc85-150">Jede `implementedproperty` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="4dc85-150">Each `implementedproperty` has the following syntax and parts:</span></span>  
  
     `interface.definedname`  
  
    |<span data-ttu-id="4dc85-151">Segment</span><span class="sxs-lookup"><span data-stu-id="4dc85-151">Part</span></span>|<span data-ttu-id="4dc85-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4dc85-152">Description</span></span>|  
    |---|---|  
    |`interface`|<span data-ttu-id="4dc85-153">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4dc85-153">Required.</span></span> <span data-ttu-id="4dc85-154">Name der Schnittstelle implementiert, die von dieser Eigenschaft der enthaltenden Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="4dc85-154">Name of an interface implemented by this property's containing class or structure.</span></span>|  
    |`definedname`|<span data-ttu-id="4dc85-155">Erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4dc85-155">Required.</span></span> <span data-ttu-id="4dc85-156">Name, mit dem die Eigenschaft, in definiert ist `interface`.</span><span class="sxs-lookup"><span data-stu-id="4dc85-156">Name by which the property is defined in `interface`.</span></span>|  
  
-   `Get`  
  
     <span data-ttu-id="4dc85-157">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-157">Optional.</span></span> <span data-ttu-id="4dc85-158">Erforderlich, wenn die Eigenschaft markiert ist `WriteOnly`.</span><span class="sxs-lookup"><span data-stu-id="4dc85-158">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="4dc85-159">Startet eine `Get` Property-Prozedur, die verwendet wird, um den Wert der Eigenschaft zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="4dc85-159">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  
  
-   `statements`  
  
     <span data-ttu-id="4dc85-160">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-160">Optional.</span></span> <span data-ttu-id="4dc85-161">Block von Anweisungen für die Ausführung innerhalb der `Get` oder `Set` Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4dc85-161">Block of statements to run within the `Get` or `Set` procedure.</span></span>  
  
-   `End Get`  
  
     <span data-ttu-id="4dc85-162">Beendet die `Get` Property-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="4dc85-162">Terminates the `Get` property procedure.</span></span>  
  
-   `Set`  
  
     <span data-ttu-id="4dc85-163">Optional.</span><span class="sxs-lookup"><span data-stu-id="4dc85-163">Optional.</span></span> <span data-ttu-id="4dc85-164">Erforderlich, wenn die Eigenschaft markiert ist `ReadOnly`.</span><span class="sxs-lookup"><span data-stu-id="4dc85-164">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="4dc85-165">Startet eine `Set` Property-Prozedur, die zum Speichern des Werts der Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4dc85-165">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  
  
-   `End Set`  
  
     <span data-ttu-id="4dc85-166">Beendet die `Set` Property-Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="4dc85-166">Terminates the `Set` property procedure.</span></span>  
  
-   `End Property`  
  
     <span data-ttu-id="4dc85-167">Beendet die Definition dieser Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4dc85-167">Terminates the definition of this property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4dc85-168">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4dc85-168">Remarks</span></span>  
 <span data-ttu-id="4dc85-169">Die `Property` -Anweisung führt die Deklaration einer Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="4dc85-169">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="4dc85-170">Eine Eigenschaft haben eine `Get` Verfahren (schreibgeschützt), eine `Set` -Prozedur (lesegeschützt) oder beide (Lese-/ Schreibzugriff).</span><span class="sxs-lookup"><span data-stu-id="4dc85-170">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="4dc85-171">Sie lassen die `Get` und `Set` Verfahren, wenn Sie eine automatisch implementierte Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dc85-171">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="4dc85-172">Weitere Informationen finden Sie unter [automatisch implementierte Eigenschaften](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="4dc85-172">For more information, see [Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>  
  
 <span data-ttu-id="4dc85-173">Sie können `Property` nur auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="4dc85-173">You can use `Property` only at class level.</span></span> <span data-ttu-id="4dc85-174">Dies bedeutet, dass die *Deklarationskontext* für eine Eigenschaft eine Klasse, Struktur, Modul oder Schnittstelle sein muss und darf keine Quelldatei, Namespace, Prozedur oder Block.</span><span class="sxs-lookup"><span data-stu-id="4dc85-174">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="4dc85-175">Weitere Informationen finden Sie unter [Deklarationskontexte und Zugriffsebenen standardmäßig](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="4dc85-175">For more information, see [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).</span></span>  
  
 <span data-ttu-id="4dc85-176">Standardmäßig verwenden die Eigenschaften öffentlicher Zugriff.</span><span class="sxs-lookup"><span data-stu-id="4dc85-176">By default, properties use public access.</span></span> <span data-ttu-id="4dc85-177">Sie können die Zugriffsebene einer Eigenschaft mit einem Zugriffsmodifizierer anpassen, auf die `Property` -Anweisung, und Sie können optional auch anpassen, eine ihrer Eigenschaftenprozeduren auf eine restriktivere Zugriffsebene festlegen.</span><span class="sxs-lookup"><span data-stu-id="4dc85-177">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>  
  
 <span data-ttu-id="4dc85-178">Visual Basic übergibt einen Parameter an die `Set` Prozedur während der Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="4dc85-178">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="4dc85-179">Wenn Sie keine Parameter für bieten `Set`, die integrierte Entwicklungsumgebung (IDE) verwendet einen impliziten Parameter mit dem Namen `value`.</span><span class="sxs-lookup"><span data-stu-id="4dc85-179">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="4dc85-180">Dieser Parameter enthält den Wert der Eigenschaft zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="4dc85-180">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="4dc85-181">In der Regel speichern Sie diesen Wert in einer privaten lokalen Variablen und gibt es immer die `Get` Prozedur aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4dc85-181">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>  
  
## <a name="rules"></a><span data-ttu-id="4dc85-182">Regeln</span><span class="sxs-lookup"><span data-stu-id="4dc85-182">Rules</span></span>  
  
-   <span data-ttu-id="4dc85-183">**Gemischte Zugriffsebenen.**</span><span class="sxs-lookup"><span data-stu-id="4dc85-183">**Mixed Access Levels.**</span></span> <span data-ttu-id="4dc85-184">Wenn Sie eine Eigenschaft mit Lese-/ Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene angeben, entweder für die `Get` oder `Set` Verfahren, aber nicht beide.</span><span class="sxs-lookup"><span data-stu-id="4dc85-184">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="4dc85-185">Wenn Sie dies tun, muss die Zugriffsebene der Prozedur restriktiver als die Zugriffsebene der Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="4dc85-185">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="4dc85-186">Beispielsweise, wenn die Eigenschaft deklariert wird `Friend`, können Sie deklarieren die `Set` Prozedur `Private`, aber nicht `Public`.</span><span class="sxs-lookup"><span data-stu-id="4dc85-186">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>  
  
     <span data-ttu-id="4dc85-187">Definieren einer `ReadOnly` oder `WriteOnly` -Eigenschaft, die Eigenschaftenprozedur (`Get` oder `Set`bzw.) alle der Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="4dc85-187">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="4dc85-188">Sie können nicht für eine Prozedur, eine andere Zugriffsebene deklarieren, da hierdurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4dc85-188">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>  
  
-   <span data-ttu-id="4dc85-189">**Der Rückgabetyp.**</span><span class="sxs-lookup"><span data-stu-id="4dc85-189">**Return Type.**</span></span> <span data-ttu-id="4dc85-190">Die `Property` -Anweisung kann den Datentyp des zurückgegebenen Werts deklarieren.</span><span class="sxs-lookup"><span data-stu-id="4dc85-190">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="4dc85-191">Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="4dc85-191">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>  
  
     <span data-ttu-id="4dc85-192">Wenn Sie keinen angeben `returntype`, gibt die Eigenschaft `Object`.</span><span class="sxs-lookup"><span data-stu-id="4dc85-192">If you do not specify `returntype`, the property returns `Object`.</span></span>  
  
-   <span data-ttu-id="4dc85-193">**-Implementierung.**</span><span class="sxs-lookup"><span data-stu-id="4dc85-193">**Implementation.**</span></span> <span data-ttu-id="4dc85-194">Wenn diese Eigenschaft verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur benötigen eine `Implements` -Anweisung unmittelbar nach seiner `Class` oder `Structure` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4dc85-194">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="4dc85-195">Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`.</span><span class="sxs-lookup"><span data-stu-id="4dc85-195">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="4dc85-196">Allerdings den Namen, mit dem eine Schnittstelle definiert, die `Property` (in `definedname`) muss nicht identisch mit dem Namen dieser Eigenschaft werden (in `name`).</span><span class="sxs-lookup"><span data-stu-id="4dc85-196">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>  
  
## <a name="behavior"></a><span data-ttu-id="4dc85-197">Verhalten</span><span class="sxs-lookup"><span data-stu-id="4dc85-197">Behavior</span></span>  
  
-   <span data-ttu-id="4dc85-198">**Zurückgeben einer Eigenschaftenprozedur.**</span><span class="sxs-lookup"><span data-stu-id="4dc85-198">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="4dc85-199">Wenn die `Get` oder `Set` -Prozedur zum aufrufenden Code zurückkehrt, die Ausführung wird fortgesetzt, mit der Anweisung nach der Anweisung, die sie aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="4dc85-199">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>  
  
     <span data-ttu-id="4dc85-200">Die `Exit Property` und `Return` -Anweisung führen zur unmittelbare Beendigung einer Eigenschaftenprozedur.</span><span class="sxs-lookup"><span data-stu-id="4dc85-200">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="4dc85-201">Eine beliebige Anzahl von `Exit Property` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie kombinieren können `Exit Property` und `Return` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="4dc85-201">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>  
  
-   <span data-ttu-id="4dc85-202">**Der Rückgabewert.**</span><span class="sxs-lookup"><span data-stu-id="4dc85-202">**Return Value.**</span></span> <span data-ttu-id="4dc85-203">Zum Zurückgeben eines Werts aus einer `Get` Verfahren, Sie können entweder den Wert der Eigenschaftenname zuweisen oder ihn in eine `Return` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4dc85-203">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="4dc85-204">Das folgende Beispiel weist den Rückgabewert dem Eigenschaftennamen `quoteForTheDay` und verwendet dann die `Exit Property` -Anweisung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4dc85-204">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>  
  
     <span data-ttu-id="4dc85-205">[!code-vb[VbVbalrStatements&#27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4dc85-205">[!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span></span>  
  
     <span data-ttu-id="4dc85-206">[!code-vb[VbVbalrStatements&#28;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="4dc85-206">[!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]</span></span>  
  
     <span data-ttu-id="4dc85-207">Bei Verwendung von `Exit Property` ohne Zuweisen eines Werts zur `name`der `Get` Prozedur gibt den Standardwert für den Datentyp der Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="4dc85-207">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>  
  
     <span data-ttu-id="4dc85-208">Die `Return` Anweisung zur gleichen Zeit weist der `Get` Prozedur zurück und beendet die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4dc85-208">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="4dc85-209">Das folgende Beispiel zeigt dies.</span><span class="sxs-lookup"><span data-stu-id="4dc85-209">The following example shows this.</span></span>  
  
     <span data-ttu-id="4dc85-210">[!code-vb[VbVbalrStatements&#27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="4dc85-210">[!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]</span></span>  
  
     <span data-ttu-id="4dc85-211">[!code-vb[VbVbalrStatements&#29;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="4dc85-211">[!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4dc85-212">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4dc85-212">Example</span></span>  
 <span data-ttu-id="4dc85-213">Im folgende Beispiel wird eine Eigenschaft in einer Klasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="4dc85-213">The following example declares a property in a class.</span></span>  
  
 <span data-ttu-id="4dc85-214">[!code-vb[VbVbalrStatements&51;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="4dc85-214">[!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc85-215">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4dc85-215">See Also</span></span>  
 <span data-ttu-id="4dc85-216">[Automatisch implementierte Eigenschaften](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md) </span><span class="sxs-lookup"><span data-stu-id="4dc85-216">[Auto-Implemented Properties](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md) </span></span>  
<span data-ttu-id="4dc85-217"> [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span><span class="sxs-lookup"><span data-stu-id="4dc85-217"> [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) </span></span>  
<span data-ttu-id="4dc85-218"> [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4dc85-218"> [Get Statement](../../../visual-basic/language-reference/statements/get-statement.md) </span></span>  
<span data-ttu-id="4dc85-219"> [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md) </span><span class="sxs-lookup"><span data-stu-id="4dc85-219"> [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md) </span></span>  
<span data-ttu-id="4dc85-220"> [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md) </span><span class="sxs-lookup"><span data-stu-id="4dc85-220"> [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md) </span></span>  
<span data-ttu-id="4dc85-221"> [Default](../../../visual-basic/language-reference/modifiers/default.md)</span><span class="sxs-lookup"><span data-stu-id="4dc85-221"> [Default](../../../visual-basic/language-reference/modifiers/default.md)</span></span>

