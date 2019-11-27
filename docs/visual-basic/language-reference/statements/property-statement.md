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
ms.openlocfilehash: 80bce2442d96ecb9c548a88c8e5ee44c6258473b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346754"
---
# <a name="property-statement"></a><span data-ttu-id="0f802-102">Property Statement</span><span class="sxs-lookup"><span data-stu-id="0f802-102">Property Statement</span></span>

<span data-ttu-id="0f802-103">Deklariert den Namen einer Eigenschaft sowie die Eigenschaften Prozeduren, die zum Speichern und Abrufen des Werts der Eigenschaft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0f802-103">Declares the name of a property, and the property procedures used to store and retrieve the value of the property.</span></span>

## <a name="syntax"></a><span data-ttu-id="0f802-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f802-104">Syntax</span></span>

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

## <a name="parts"></a><span data-ttu-id="0f802-105">-Komponenten</span><span class="sxs-lookup"><span data-stu-id="0f802-105">Parts</span></span>

- `attributelist`

  <span data-ttu-id="0f802-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-106">Optional.</span></span> <span data-ttu-id="0f802-107">Liste der Attribute, die für diese Eigenschaft oder `Get` oder `Set` Prozedur gelten.</span><span class="sxs-lookup"><span data-stu-id="0f802-107">List of attributes that apply to this property or `Get` or `Set` procedure.</span></span> <span data-ttu-id="0f802-108">Siehe [Attribut Liste](attribute-list.md).</span><span class="sxs-lookup"><span data-stu-id="0f802-108">See [Attribute List](attribute-list.md).</span></span>

- `Default`

  <span data-ttu-id="0f802-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-109">Optional.</span></span> <span data-ttu-id="0f802-110">Gibt an, dass diese Eigenschaft die Standard Eigenschaft für die Klasse oder Struktur ist, in der Sie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="0f802-110">Specifies that this property is the default property for the class or structure on which it is defined.</span></span> <span data-ttu-id="0f802-111">Standardeigenschaften müssen Parameter akzeptieren und können ohne Angabe des Eigenschaften namensfest gelegt und abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0f802-111">Default properties must accept parameters and can be set and retrieved without specifying the property name.</span></span> <span data-ttu-id="0f802-112">Wenn Sie die Eigenschaft als `Default`deklarieren, können Sie `Private` nicht für die Eigenschaft oder für eine der Eigenschaften Prozeduren verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f802-112">If you declare the property as `Default`, you cannot use `Private` on the property or on either of its property procedures.</span></span>

- `accessmodifier`

  <span data-ttu-id="0f802-113">Optional für die `Property`-Anweisung und für höchstens eine der Anweisungen `Get` und `Set`.</span><span class="sxs-lookup"><span data-stu-id="0f802-113">Optional on the `Property` statement and on at most one of the `Get` and `Set` statements.</span></span> <span data-ttu-id="0f802-114">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="0f802-114">Can be one of the following:</span></span>

  - [<span data-ttu-id="0f802-115">Public</span><span class="sxs-lookup"><span data-stu-id="0f802-115">Public</span></span>](../modifiers/public.md)

  - [<span data-ttu-id="0f802-116">Protected</span><span class="sxs-lookup"><span data-stu-id="0f802-116">Protected</span></span>](../modifiers/protected.md)

  - [<span data-ttu-id="0f802-117">Friend</span><span class="sxs-lookup"><span data-stu-id="0f802-117">Friend</span></span>](../modifiers/friend.md)

  - [<span data-ttu-id="0f802-118">Private</span><span class="sxs-lookup"><span data-stu-id="0f802-118">Private</span></span>](../modifiers/private.md)

  - [<span data-ttu-id="0f802-119">Protected Friend</span><span class="sxs-lookup"><span data-stu-id="0f802-119">Protected Friend</span></span>](../modifiers/protected-friend.md)

  - [<span data-ttu-id="0f802-120">Private Protected</span><span class="sxs-lookup"><span data-stu-id="0f802-120">Private Protected</span></span>](../modifiers/private-protected.md)

  <span data-ttu-id="0f802-121">Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0f802-121">See [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).</span></span>

- `propertymodifiers`

  <span data-ttu-id="0f802-122">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-122">Optional.</span></span> <span data-ttu-id="0f802-123">Einer der folgenden Werte ist möglich:</span><span class="sxs-lookup"><span data-stu-id="0f802-123">Can be one of the following:</span></span>

  - [<span data-ttu-id="0f802-124">Overloads</span><span class="sxs-lookup"><span data-stu-id="0f802-124">Overloads</span></span>](../modifiers/overloads.md)

  - [<span data-ttu-id="0f802-125">Overrides</span><span class="sxs-lookup"><span data-stu-id="0f802-125">Overrides</span></span>](../modifiers/overrides.md)

  - [<span data-ttu-id="0f802-126">Overrides</span><span class="sxs-lookup"><span data-stu-id="0f802-126">Overridable</span></span>](../modifiers/overridable.md)

  - [<span data-ttu-id="0f802-127">NotOverridable</span><span class="sxs-lookup"><span data-stu-id="0f802-127">NotOverridable</span></span>](../modifiers/notoverridable.md)

  - [<span data-ttu-id="0f802-128">MustOverride</span><span class="sxs-lookup"><span data-stu-id="0f802-128">MustOverride</span></span>](../modifiers/mustoverride.md)

  - `MustOverride Overrides`

  - `NotOverridable Overrides`

- `Shared`

  <span data-ttu-id="0f802-129">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-129">Optional.</span></span> <span data-ttu-id="0f802-130">Siehe [Shared](../modifiers/shared.md).</span><span class="sxs-lookup"><span data-stu-id="0f802-130">See [Shared](../modifiers/shared.md).</span></span>

- `Shadows`

  <span data-ttu-id="0f802-131">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-131">Optional.</span></span> <span data-ttu-id="0f802-132">Siehe [Shadows](../modifiers/shadows.md).</span><span class="sxs-lookup"><span data-stu-id="0f802-132">See [Shadows](../modifiers/shadows.md).</span></span>

- `ReadOnly`

  <span data-ttu-id="0f802-133">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-133">Optional.</span></span> <span data-ttu-id="0f802-134">Siehe [nur](../modifiers/readonly.md)lesen.</span><span class="sxs-lookup"><span data-stu-id="0f802-134">See [ReadOnly](../modifiers/readonly.md).</span></span>

- `WriteOnly`

  <span data-ttu-id="0f802-135">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-135">Optional.</span></span> <span data-ttu-id="0f802-136">Siehe [nur](../modifiers/writeonly.md)schreiben.</span><span class="sxs-lookup"><span data-stu-id="0f802-136">See [WriteOnly](../modifiers/writeonly.md).</span></span>

- `Iterator`

  <span data-ttu-id="0f802-137">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-137">Optional.</span></span> <span data-ttu-id="0f802-138">Siehe [Iterator](../modifiers/iterator.md).</span><span class="sxs-lookup"><span data-stu-id="0f802-138">See [Iterator](../modifiers/iterator.md).</span></span>

- `name`

  <span data-ttu-id="0f802-139">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0f802-139">Required.</span></span> <span data-ttu-id="0f802-140">Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0f802-140">Name of the property.</span></span> <span data-ttu-id="0f802-141">Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="0f802-141">See [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>

- `parameterlist`

  <span data-ttu-id="0f802-142">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-142">Optional.</span></span> <span data-ttu-id="0f802-143">Liste der Namen der lokalen Variablen, die die Parameter dieser Eigenschaft darstellen, sowie mögliche zusätzliche Parameter der `Set` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0f802-143">List of local variable names representing the parameters of this property, and possible additional parameters of the `Set` procedure.</span></span> <span data-ttu-id="0f802-144">Siehe [Parameter Liste](parameter-list.md).</span><span class="sxs-lookup"><span data-stu-id="0f802-144">See [Parameter List](parameter-list.md).</span></span>

- `returntype`

  <span data-ttu-id="0f802-145">Erforderlich, wenn `Option Strict` `On`ist.</span><span class="sxs-lookup"><span data-stu-id="0f802-145">Required if `Option Strict` is `On`.</span></span> <span data-ttu-id="0f802-146">Datentyp des Werts, der von dieser Eigenschaft zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0f802-146">Data type of the value returned by this property.</span></span>

- `Implements`

  <span data-ttu-id="0f802-147">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-147">Optional.</span></span> <span data-ttu-id="0f802-148">Gibt an, dass diese Eigenschaft eine oder mehrere Eigenschaften implementiert, von denen jede in einer Schnittstelle definiert ist, die von der enthaltenden Klasse oder Struktur dieser Eigenschaft implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="0f802-148">Indicates that this property implements one or more properties, each one defined in an interface implemented by this property's containing class or structure.</span></span> <span data-ttu-id="0f802-149">Siehe [implementierende Anweisung](implements-statement.md).</span><span class="sxs-lookup"><span data-stu-id="0f802-149">See [Implements Statement](implements-statement.md).</span></span>

- `implementslist`

  <span data-ttu-id="0f802-150">Erforderlich, wenn `Implements` angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0f802-150">Required if `Implements` is supplied.</span></span> <span data-ttu-id="0f802-151">Liste der implementierten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="0f802-151">List of properties being implemented.</span></span>

  `implementedproperty [ , implementedproperty ... ]`

  <span data-ttu-id="0f802-152">Jede `implementedproperty` weist folgende Syntax und Bestandteile auf:</span><span class="sxs-lookup"><span data-stu-id="0f802-152">Each `implementedproperty` has the following syntax and parts:</span></span>

  `interface.definedname`

  |<span data-ttu-id="0f802-153">-Komponente</span><span class="sxs-lookup"><span data-stu-id="0f802-153">Part</span></span>|<span data-ttu-id="0f802-154">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f802-154">Description</span></span>|
  |---|---|
  |`interface`|<span data-ttu-id="0f802-155">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0f802-155">Required.</span></span> <span data-ttu-id="0f802-156">Der Name einer Schnittstelle, die von der enthaltenden Klasse oder Struktur dieser Eigenschaft implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="0f802-156">Name of an interface implemented by this property's containing class or structure.</span></span>|
  |`definedname`|<span data-ttu-id="0f802-157">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="0f802-157">Required.</span></span> <span data-ttu-id="0f802-158">Der Name, mit dem die Eigenschaft in `interface`definiert wird.</span><span class="sxs-lookup"><span data-stu-id="0f802-158">Name by which the property is defined in `interface`.</span></span>|

- `Get`

  <span data-ttu-id="0f802-159">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-159">Optional.</span></span> <span data-ttu-id="0f802-160">Erforderlich, wenn die Eigenschaft als `ReadOnly`gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="0f802-160">Required if the property is marked `ReadOnly`.</span></span> <span data-ttu-id="0f802-161">Startet eine `Get`-Eigenschaften Prozedur, die verwendet wird, um den Wert der-Eigenschaft zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="0f802-161">Starts a `Get` property procedure that is used to return the value of the property.</span></span>  <span data-ttu-id="0f802-162">Die `Get`-Anweisung wird nicht mit [automatisch implementierten Eigenschaften](../../programming-guide/language-features/procedures/auto-implemented-properties.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="0f802-162">The `Get` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `statements`

  <span data-ttu-id="0f802-163">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-163">Optional.</span></span> <span data-ttu-id="0f802-164">Block von Anweisungen, die innerhalb des `Get` oder `Set` Prozedur ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0f802-164">Block of statements to run within the `Get` or `Set` procedure.</span></span>

- `End Get`

  <span data-ttu-id="0f802-165">Beendet die `Get`-Eigenschaften Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0f802-165">Terminates the `Get` property procedure.</span></span>

- `Set`

  <span data-ttu-id="0f802-166">Optional.</span><span class="sxs-lookup"><span data-stu-id="0f802-166">Optional.</span></span> <span data-ttu-id="0f802-167">Erforderlich, wenn die Eigenschaft als `WriteOnly`gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="0f802-167">Required if the property is marked `WriteOnly`.</span></span> <span data-ttu-id="0f802-168">Startet eine `Set`-Eigenschaften Prozedur, die zum Speichern des Werts der-Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f802-168">Starts a `Set` property procedure that is used to store the value of the property.</span></span>  <span data-ttu-id="0f802-169">Die `Set`-Anweisung wird nicht mit [automatisch implementierten Eigenschaften](../../programming-guide/language-features/procedures/auto-implemented-properties.md)verwendet.</span><span class="sxs-lookup"><span data-stu-id="0f802-169">The `Set` statement is not used with [auto-implemented properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

- `End Set`

  <span data-ttu-id="0f802-170">Beendet die `Set`-Eigenschaften Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0f802-170">Terminates the `Set` property procedure.</span></span>

- `End Property`

  <span data-ttu-id="0f802-171">Beendet die Definition dieser Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0f802-171">Terminates the definition of this property.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f802-172">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f802-172">Remarks</span></span>

<span data-ttu-id="0f802-173">Mit der `Property`-Anweisung wird die Deklaration einer Eigenschaft eingeführt.</span><span class="sxs-lookup"><span data-stu-id="0f802-173">The `Property` statement introduces the declaration of a property.</span></span> <span data-ttu-id="0f802-174">Eine Eigenschaft kann über eine `Get` Prozedur (schreibgeschützt), eine `Set` Prozedur (schreibgeschützt) oder beides (Lese-/Schreibzugriff) verfügen.</span><span class="sxs-lookup"><span data-stu-id="0f802-174">A property can have a `Get` procedure (read only), a `Set` procedure (write only), or both (read-write).</span></span> <span data-ttu-id="0f802-175">Wenn Sie eine automatisch implementierte Eigenschaft verwenden, können Sie die `Get` und `Set` Verfahren weglassen.</span><span class="sxs-lookup"><span data-stu-id="0f802-175">You can omit the `Get` and `Set` procedure when using an auto-implemented property.</span></span> <span data-ttu-id="0f802-176">Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span><span class="sxs-lookup"><span data-stu-id="0f802-176">For more information, see [Auto-Implemented Properties](../../programming-guide/language-features/procedures/auto-implemented-properties.md).</span></span>

<span data-ttu-id="0f802-177">Sie können `Property` nur auf Klassenebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="0f802-177">You can use `Property` only at class level.</span></span> <span data-ttu-id="0f802-178">Dies bedeutet, dass der *Deklarations Kontext* für eine Eigenschaft eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein muss und nicht eine Quelldatei, ein Namespace, eine Prozedur oder ein Block sein kann.</span><span class="sxs-lookup"><span data-stu-id="0f802-178">This means the *declaration context* for a property must be a class, structure, module, or interface, and cannot be a source file, namespace, procedure, or block.</span></span> <span data-ttu-id="0f802-179">Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="0f802-179">For more information, see [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md).</span></span>

<span data-ttu-id="0f802-180">Standardmäßig verwenden Eigenschaften öffentlichen Zugriff.</span><span class="sxs-lookup"><span data-stu-id="0f802-180">By default, properties use public access.</span></span> <span data-ttu-id="0f802-181">Sie können die Zugriffsebene einer Eigenschaft mit einem Zugriffsmodifizierer für die `Property`-Anweisung anpassen, und Sie können optional eine ihrer Eigenschaften Prozeduren auf eine restriktivere Zugriffsebene anpassen.</span><span class="sxs-lookup"><span data-stu-id="0f802-181">You can adjust a property's access level with an access modifier on the `Property` statement, and you can optionally adjust one of its property procedures to a more restrictive access level.</span></span>

<span data-ttu-id="0f802-182">Visual Basic übergibt einen Parameter an die `Set` Prozedur während der Eigenschaften Zuweisungen.</span><span class="sxs-lookup"><span data-stu-id="0f802-182">Visual Basic passes a parameter to the `Set` procedure during property assignments.</span></span> <span data-ttu-id="0f802-183">Wenn Sie keinen Parameter für `Set`bereitstellen, verwendet die integrierte Entwicklungsumgebung (Integrated Development Environment, IDE) einen impliziten Parameter mit dem Namen `value`.</span><span class="sxs-lookup"><span data-stu-id="0f802-183">If you do not supply a parameter for `Set`, the integrated development environment (IDE) uses an implicit parameter named `value`.</span></span> <span data-ttu-id="0f802-184">Dieser Parameter enthält den Wert, der der Eigenschaft zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="0f802-184">This parameter holds the value to be assigned to the property.</span></span> <span data-ttu-id="0f802-185">In der Regel speichern Sie diesen Wert in einer privaten lokalen Variable und geben ihn zurück, wenn die `Get` Prozedur aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0f802-185">You typically store this value in a private local variable and return it whenever the `Get` procedure is called.</span></span>

## <a name="rules"></a><span data-ttu-id="0f802-186">Regeln</span><span class="sxs-lookup"><span data-stu-id="0f802-186">Rules</span></span>

- <span data-ttu-id="0f802-187">**Gemischte Zugriffsebenen.**</span><span class="sxs-lookup"><span data-stu-id="0f802-187">**Mixed Access Levels.**</span></span> <span data-ttu-id="0f802-188">Wenn Sie eine Eigenschaft mit Lese-/Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene für die `Get` oder die `Set` Prozedur angeben, jedoch nicht für beide.</span><span class="sxs-lookup"><span data-stu-id="0f802-188">If you are defining a read-write property, you can optionally specify a different access level for either the `Get` or the `Set` procedure, but not both.</span></span> <span data-ttu-id="0f802-189">Wenn Sie dies tun, muss die Prozedur Zugriffsebene restriktiver sein als die Zugriffsebene der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0f802-189">If you do this, the procedure access level must be more restrictive than the property's access level.</span></span> <span data-ttu-id="0f802-190">Wenn die Eigenschaft beispielsweise als `Friend`deklariert ist, können Sie die `Set` Prozedur `Private`deklarieren, jedoch nicht `Public`.</span><span class="sxs-lookup"><span data-stu-id="0f802-190">For example, if the property is declared `Friend`, you can declare the `Set` procedure `Private`, but not `Public`.</span></span>

  <span data-ttu-id="0f802-191">Wenn Sie eine `ReadOnly`-oder `WriteOnly`-Eigenschaft definieren, stellt die Prozedur (`Get` oder `Set`) der einzelnen Eigenschaft die gesamte-Eigenschaft dar.</span><span class="sxs-lookup"><span data-stu-id="0f802-191">If you are defining a `ReadOnly` or `WriteOnly` property, the single property procedure (`Get` or `Set`, respectively) represents all of the property.</span></span> <span data-ttu-id="0f802-192">Sie können für eine solche Prozedur keine andere Zugriffsebene deklarieren, da dadurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="0f802-192">You cannot declare a different access level for such a procedure, because that would set two access levels for the property.</span></span>

- <span data-ttu-id="0f802-193">**Rückgabetyp.**</span><span class="sxs-lookup"><span data-stu-id="0f802-193">**Return Type.**</span></span> <span data-ttu-id="0f802-194">Die `Property`-Anweisung kann den Datentyp des zurückgegebenen Werts deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0f802-194">The `Property` statement can declare the data type of the value it returns.</span></span> <span data-ttu-id="0f802-195">Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.</span><span class="sxs-lookup"><span data-stu-id="0f802-195">You can specify any data type or the name of an enumeration, structure, class, or interface.</span></span>

  <span data-ttu-id="0f802-196">Wenn Sie `returntype`nicht angeben, gibt die-Eigenschaft `Object`zurück.</span><span class="sxs-lookup"><span data-stu-id="0f802-196">If you do not specify `returntype`, the property returns `Object`.</span></span>

- <span data-ttu-id="0f802-197">**Ausführungs.**</span><span class="sxs-lookup"><span data-stu-id="0f802-197">**Implementation.**</span></span> <span data-ttu-id="0f802-198">Wenn diese Eigenschaft das `Implements`-Schlüsselwort verwendet, muss die enthaltende Klasse oder Struktur direkt nach der `Class`-oder `Structure` Anweisung eine `Implements`-Anweisung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="0f802-198">If this property uses the `Implements` keyword, the containing class or structure must have an `Implements` statement immediately following its `Class` or `Structure` statement.</span></span> <span data-ttu-id="0f802-199">Die `Implements`-Anweisung muss jede in `implementslist`angegebene Schnittstelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="0f802-199">The `Implements` statement must include each interface specified in `implementslist`.</span></span> <span data-ttu-id="0f802-200">Der Name, mit dem eine Schnittstelle die `Property` definiert (in `definedname`), muss jedoch nicht mit dem Namen dieser Eigenschaft (in `name`) identisch sein.</span><span class="sxs-lookup"><span data-stu-id="0f802-200">However, the name by which an interface defines the `Property` (in `definedname`) does not have to be the same as the name of this property (in `name`).</span></span>

## <a name="behavior"></a><span data-ttu-id="0f802-201">Verhalten</span><span class="sxs-lookup"><span data-stu-id="0f802-201">Behavior</span></span>

- <span data-ttu-id="0f802-202">**Zurückgeben von einer Eigenschaften Prozedur.**</span><span class="sxs-lookup"><span data-stu-id="0f802-202">**Returning from a Property Procedure.**</span></span> <span data-ttu-id="0f802-203">Wenn die `Get` oder `Set` Prozedur an den aufrufenden Code zurückgegeben wird, wird die Ausführung mit der Anweisung nach der Anweisung fortgesetzt, die Sie aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="0f802-203">When the `Get` or `Set` procedure returns to the calling code, execution continues with the statement following the statement that invoked it.</span></span>

  <span data-ttu-id="0f802-204">Die Anweisungen `Exit Property` und `Return` führen zu einem sofortigen Beenden einer Eigenschaften Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0f802-204">The `Exit Property` and `Return` statements cause an immediate exit from a property procedure.</span></span> <span data-ttu-id="0f802-205">Eine beliebige Anzahl von `Exit Property`-und `Return` Anweisungen kann an beliebiger Stelle in der Prozedur angezeigt werden, und Sie können `Exit Property`-und `Return`-Anweisungen mischen.</span><span class="sxs-lookup"><span data-stu-id="0f802-205">Any number of `Exit Property` and `Return` statements can appear anywhere in the procedure, and you can mix `Exit Property` and `Return` statements.</span></span>

- <span data-ttu-id="0f802-206">**Rückgabewert.**</span><span class="sxs-lookup"><span data-stu-id="0f802-206">**Return Value.**</span></span> <span data-ttu-id="0f802-207">Um einen Wert aus einer `Get` Prozedur zurückzugeben, können Sie den Wert entweder dem Eigenschaftsnamen zuweisen oder ihn in eine `Return` Anweisung einschließen.</span><span class="sxs-lookup"><span data-stu-id="0f802-207">To return a value from a `Get` procedure, you can either assign the value to the property name or include it in a `Return` statement.</span></span> <span data-ttu-id="0f802-208">Im folgenden Beispiel wird der-Rückgabewert dem Eigenschaftsnamen `quoteForTheDay` zugewiesen und dann die `Exit Property`-Anweisung verwendet, um zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="0f802-208">The following example assigns the return value to the property name `quoteForTheDay` and then uses the `Exit Property` statement to return.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]

  <span data-ttu-id="0f802-209">Wenn Sie `Exit Property` verwenden, ohne `name`einen Wert zuzuweisen, gibt die `Get`-Prozedur den Standardwert für den Datentyp der Eigenschaft zurück.</span><span class="sxs-lookup"><span data-stu-id="0f802-209">If you use `Exit Property` without assigning a value to `name`, the `Get` procedure returns the default value for the property's data type.</span></span>

  <span data-ttu-id="0f802-210">Die Anweisung `Return` gleichzeitig weist den `Get` Prozedur Rückgabewert zu und beendet die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="0f802-210">The `Return` statement at the same time assigns the `Get` procedure return value and exits the procedure.</span></span> <span data-ttu-id="0f802-211">Dies wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0f802-211">The following example shows this.</span></span>

  [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]

  [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]

## <a name="example"></a><span data-ttu-id="0f802-212">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0f802-212">Example</span></span>

<span data-ttu-id="0f802-213">Im folgenden Beispiel wird eine-Eigenschaft in einer-Klasse deklariert.</span><span class="sxs-lookup"><span data-stu-id="0f802-213">The following example declares a property in a class.</span></span>

[!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]

## <a name="see-also"></a><span data-ttu-id="0f802-214">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f802-214">See also</span></span>

- [<span data-ttu-id="0f802-215">Automatisch implementierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="0f802-215">Auto-Implemented Properties</span></span>](../../programming-guide/language-features/procedures/auto-implemented-properties.md)
- [<span data-ttu-id="0f802-216">Objekte und Klassen</span><span class="sxs-lookup"><span data-stu-id="0f802-216">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="0f802-217">Get-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f802-217">Get Statement</span></span>](get-statement.md)
- [<span data-ttu-id="0f802-218">Set-Anweisung</span><span class="sxs-lookup"><span data-stu-id="0f802-218">Set Statement</span></span>](set-statement.md)
- [<span data-ttu-id="0f802-219">Parameterliste</span><span class="sxs-lookup"><span data-stu-id="0f802-219">Parameter List</span></span>](parameter-list.md)
- [<span data-ttu-id="0f802-220">Default</span><span class="sxs-lookup"><span data-stu-id="0f802-220">Default</span></span>](../modifiers/default.md)
