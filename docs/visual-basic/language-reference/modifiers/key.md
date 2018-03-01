---
title: Key (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AnonymousKey
helpviewer_keywords:
- anonymous types [Visual Basic], key
- Key [Visual Basic]
- Key keyword [Visual Basic]
ms.assetid: 7697a928-7d14-4430-a72a-c9e96e8d6c11
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 20dbe4e67fb3e415ba0202555ace7fd5afed68d2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="key-visual-basic"></a><span data-ttu-id="dbdff-102">Key (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dbdff-102">Key (Visual Basic)</span></span>
<span data-ttu-id="dbdff-103">Die `Key` Schlüsselwort ermöglicht Ihnen das Verhalten für Eigenschaften von anonymen Typen festlegen.</span><span class="sxs-lookup"><span data-stu-id="dbdff-103">The `Key` keyword enables you to specify behavior for properties of anonymous types.</span></span> <span data-ttu-id="dbdff-104">Nur Eigenschaften bestimmen Sie, wie die Tests der auf Gleichheit zwischen Instanzen eines anonymen Typs oder eine Berechnung des Hashcodewerte Schlüsseleigenschaften teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="dbdff-104">Only properties you designate as key properties participate in tests of equality between anonymous type instances, or calculation of hash code values.</span></span> <span data-ttu-id="dbdff-105">Die Werte von Schlüsseleigenschaften können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dbdff-105">The values of key properties cannot be changed.</span></span>  
  
 <span data-ttu-id="dbdff-106">Eine Eigenschaft eines anonymen Typs wird als Schlüsseleigenschaft gekennzeichnet, indem Sie das Schlüsselwort `Key` vor ihrer Deklaration in der Initialisierungsliste.</span><span class="sxs-lookup"><span data-stu-id="dbdff-106">You designate a property of an anonymous type as a key property by placing the keyword `Key` in front of its declaration in the initialization list.</span></span> <span data-ttu-id="dbdff-107">Im folgenden Beispiel `Airline` und `FlightNo` Schlüsseleigenschaften, sind aber `Gate` nicht.</span><span class="sxs-lookup"><span data-stu-id="dbdff-107">In the following example, `Airline` and `FlightNo` are key properties, but `Gate` is not.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#26](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_1.vb)]  
  
 <span data-ttu-id="dbdff-108">Wenn ein neuer anonymer Typ erstellt wird, erbt direkt von <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="dbdff-108">When a new anonymous type is created, it inherits directly from <xref:System.Object>.</span></span> <span data-ttu-id="dbdff-109">Der Compiler überschreibt drei geerbte Member: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, und <xref:System.Object.ToString%2A>.</span><span class="sxs-lookup"><span data-stu-id="dbdff-109">The compiler overrides three inherited members: <xref:System.Object.Equals%2A>, <xref:System.Object.GetHashCode%2A>, and <xref:System.Object.ToString%2A>.</span></span> <span data-ttu-id="dbdff-110">Die Außerkraftsetzung-Code, der für erzeugt wird <xref:System.Object.Equals%2A> und <xref:System.Object.GetHashCode%2A> Schlüsseleigenschaften basiert.</span><span class="sxs-lookup"><span data-stu-id="dbdff-110">The override code that is produced for <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> is based on key properties.</span></span> <span data-ttu-id="dbdff-111">Wenn keine wichtigsten Eigenschaften vorhanden, geben Sie im sind <xref:System.Object.GetHashCode%2A> und <xref:System.Object.Equals%2A> nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="dbdff-111">If there are no key properties in the type, <xref:System.Object.GetHashCode%2A> and <xref:System.Object.Equals%2A> are not overridden.</span></span>  
  
## <a name="equality"></a><span data-ttu-id="dbdff-112">Gleichheit</span><span class="sxs-lookup"><span data-stu-id="dbdff-112">Equality</span></span>  
 <span data-ttu-id="dbdff-113">Wenn sie Instanzen desselben Typs sind und die Werte ihrer Schlüssel Eigenschaften gleich sind, werden die zwei Instanzen eines anonymen Typs gleich sind.</span><span class="sxs-lookup"><span data-stu-id="dbdff-113">Two anonymous type instances are equal if they are instances of the same type and if the values of their key properties are equal.</span></span> <span data-ttu-id="dbdff-114">In den folgenden Beispielen `flight2` gleich `flight1` aus dem vorherigen Beispiel, da sie Instanzen des gleichen anonymen sind Typ und sie haben übereinstimmende Werte für ihre Schlüsseleigenschaften.</span><span class="sxs-lookup"><span data-stu-id="dbdff-114">In the following examples, `flight2` is equal to `flight1` from the previous example because they are instances of the same anonymous type and they have matching values for their key properties.</span></span> <span data-ttu-id="dbdff-115">Allerdings `flight3` stimmt nicht mit `flight1` da sie einen anderen Wert für eine Schlüsseleigenschaft verfügt `FlightNo`.</span><span class="sxs-lookup"><span data-stu-id="dbdff-115">However, `flight3` is not equal to `flight1` because it has a different value for a key property, `FlightNo`.</span></span> <span data-ttu-id="dbdff-116">Instanz `flight4` ist nicht vom selben Typ wie `flight1` , da sie andere Eigenschaften als Schlüsseleigenschaften festlegen.</span><span class="sxs-lookup"><span data-stu-id="dbdff-116">Instance `flight4` is not the same type as `flight1` because they designate different properties as key properties.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#27](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_2.vb)]  
  
 <span data-ttu-id="dbdff-117">Wenn zwei Instanzen mit nur nicht schlüsselbezogene Eigenschaften Name, Typ, Reihenfolge und Wert identisch deklariert werden sind die beiden Instanzen ungleich.</span><span class="sxs-lookup"><span data-stu-id="dbdff-117">If two instances are declared with only non-key properties, identical in name, type, order, and value, the two instances are not equal.</span></span> <span data-ttu-id="dbdff-118">Eine Instanz ohne Schlüsseleigenschaften ist ungleich sich selbst.</span><span class="sxs-lookup"><span data-stu-id="dbdff-118">An instance without key properties is equal only to itself.</span></span>  
  
 <span data-ttu-id="dbdff-119">Weitere Informationen zu den Bedingungen, unter dem sind zwei Instanzen eines anonymen Typs Instanzen desselben anonymen Typs, finden Sie unter [anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span><span class="sxs-lookup"><span data-stu-id="dbdff-119">For more information about the conditions under which two anonymous type instances are instances of the same anonymous type, see [Anonymous Types](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).</span></span>  
  
## <a name="hash-code-calculation"></a><span data-ttu-id="dbdff-120">Berechnung des Hashs Code</span><span class="sxs-lookup"><span data-stu-id="dbdff-120">Hash Code Calculation</span></span>  
 <span data-ttu-id="dbdff-121">Wie <xref:System.Object.Equals%2A>, Hash-Funktion, die in definierten <xref:System.Object.GetHashCode%2A> für ein anonymer Typ auf den Schlüsseleigenschaften des Typs basiert.</span><span class="sxs-lookup"><span data-stu-id="dbdff-121">Like <xref:System.Object.Equals%2A>, the hash function that is defined in <xref:System.Object.GetHashCode%2A> for an anonymous type is based on the key properties of the type.</span></span> <span data-ttu-id="dbdff-122">Die folgenden Beispiele zeigen die Interaktion zwischen Schlüsseleigenschaften und Hash Codewerte.</span><span class="sxs-lookup"><span data-stu-id="dbdff-122">The following examples show the interaction between key properties and hash code values.</span></span>  
  
 <span data-ttu-id="dbdff-123">Instanzen eines anonymen Typs, die die gleichen Werte für alle Schlüsseleigenschaften verfügen haben den gleichen Code Hashwert an, auch wenn nicht schlüsselbezogene Eigenschaften nicht übereinstimmende Werte verfügen.</span><span class="sxs-lookup"><span data-stu-id="dbdff-123">Instances of an anonymous type that have the same values for all key properties have the same hash code value, even if non-key properties do not have matching values.</span></span> <span data-ttu-id="dbdff-124">Die folgende Anweisung gibt `True`.</span><span class="sxs-lookup"><span data-stu-id="dbdff-124">The following statement returns `True`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#37](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_3.vb)]  
  
 <span data-ttu-id="dbdff-125">Instanzen eines anonymen Typs, die unterschiedliche Werte für eine oder mehrere wichtige Eigenschaften verfügen über anderen Hash Codewerte verfügen.</span><span class="sxs-lookup"><span data-stu-id="dbdff-125">Instances of an anonymous type that have different values for one or more key properties have different hash code values.</span></span> <span data-ttu-id="dbdff-126">Die folgende Anweisung gibt `False`.</span><span class="sxs-lookup"><span data-stu-id="dbdff-126">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#38](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_4.vb)]  
  
 <span data-ttu-id="dbdff-127">Instanzen von anonymen Typen, die andere Eigenschaften festlegen, wie Schlüsseleigenschaften keine Instanzen desselben Typs sind.</span><span class="sxs-lookup"><span data-stu-id="dbdff-127">Instances of anonymous types that designate different properties as key properties are not instances of the same type.</span></span> <span data-ttu-id="dbdff-128">Sie verfügen über anderen Hashcodewerte, selbst wenn die Namen und Werte aller Eigenschaften identisch sind.</span><span class="sxs-lookup"><span data-stu-id="dbdff-128">They have different hash code values even when the names and values of all properties are the same.</span></span> <span data-ttu-id="dbdff-129">Die folgende Anweisung gibt `False`.</span><span class="sxs-lookup"><span data-stu-id="dbdff-129">The following statement returns `False`.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#39](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_5.vb)]  
  
## <a name="read-only-values"></a><span data-ttu-id="dbdff-130">Schreibgeschützte Werte</span><span class="sxs-lookup"><span data-stu-id="dbdff-130">Read-Only Values</span></span>  
 <span data-ttu-id="dbdff-131">Die Werte von Schlüsseleigenschaften können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dbdff-131">The values of key properties cannot be changed.</span></span> <span data-ttu-id="dbdff-132">Beispielsweise ist in `flight1` in den vorherigen Beispielen die `Airline` und `FlightNo` Felder sind schreibgeschützt, aber `Gate` kann geändert werden.</span><span class="sxs-lookup"><span data-stu-id="dbdff-132">For example, in `flight1` in the earlier examples, the `Airline` and `FlightNo` fields are read-only, but `Gate` can be changed.</span></span>  
  
 [!code-vb[VbVbalrAnonymousTypes#28](../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/key_6.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="dbdff-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dbdff-133">See Also</span></span>  
 [<span data-ttu-id="dbdff-134">Definition von anonymen Typen</span><span class="sxs-lookup"><span data-stu-id="dbdff-134">Anonymous Type Definition</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-type-definition.md)  
 [<span data-ttu-id="dbdff-135">Gewusst wie: Ableiten von Eigenschaftennamen und Typen in Deklarationen von anonymen Typen</span><span class="sxs-lookup"><span data-stu-id="dbdff-135">How to: Infer Property Names and Types in Anonymous Type Declarations</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/how-to-infer-property-names-and-types-in-anonymous-type-declarations.md)  
 [<span data-ttu-id="dbdff-136">Anonyme Typen</span><span class="sxs-lookup"><span data-stu-id="dbdff-136">Anonymous Types</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
