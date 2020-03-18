---
title: AttributeUsage (C#)
ms.date: 04/25/2018
ms.openlocfilehash: a3a82e33d7259ec56ec3e907bc3d4d9f8a01167d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "61668717"
---
# <a name="attributeusage-c"></a><span data-ttu-id="a058a-102">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="a058a-102">AttributeUsage (C#)</span></span>

<span data-ttu-id="a058a-103">Bestimmt, wie eine benutzerdefinierte Attributklasse verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a058a-103">Determines how a custom attribute class can be used.</span></span> <span data-ttu-id="a058a-104">Bei <xref:System.AttributeUsageAttribute> handelt es sich um ein Attribut, das Sie auf benutzerdefinierte Attributdefinitionen anwenden.</span><span class="sxs-lookup"><span data-stu-id="a058a-104"><xref:System.AttributeUsageAttribute> is an attribute you apply to custom attribute definitions.</span></span> <span data-ttu-id="a058a-105">Mithilfe des `AttributeUsage`-Attribut können Sie Folgendes steuern:</span><span class="sxs-lookup"><span data-stu-id="a058a-105">The `AttributeUsage` attribute enables you to control:</span></span>

- <span data-ttu-id="a058a-106">Auf welche Programmelemente das Attribut angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a058a-106">Which program elements attribute may be applied to.</span></span> <span data-ttu-id="a058a-107">Wenn Sie dessen Verwendung nicht einschränken, kann ein Attribut auf jedes der folgenden Programmelemente angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="a058a-107">Unless you restrict its usage, an attribute may be applied to any of the following program elements:</span></span>
  - <span data-ttu-id="a058a-108">Assembly</span><span class="sxs-lookup"><span data-stu-id="a058a-108">assembly</span></span>
  - <span data-ttu-id="a058a-109">module</span><span class="sxs-lookup"><span data-stu-id="a058a-109">module</span></span>
  - <span data-ttu-id="a058a-110">-Feld</span><span class="sxs-lookup"><span data-stu-id="a058a-110">field</span></span>
  - <span data-ttu-id="a058a-111">event</span><span class="sxs-lookup"><span data-stu-id="a058a-111">event</span></span>
  - <span data-ttu-id="a058a-112">Methode</span><span class="sxs-lookup"><span data-stu-id="a058a-112">method</span></span>
  - <span data-ttu-id="a058a-113">Parameter</span><span class="sxs-lookup"><span data-stu-id="a058a-113">param</span></span>
  - <span data-ttu-id="a058a-114">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a058a-114">property</span></span>
  - <span data-ttu-id="a058a-115">return</span><span class="sxs-lookup"><span data-stu-id="a058a-115">return</span></span>
  - <span data-ttu-id="a058a-116">Typ</span><span class="sxs-lookup"><span data-stu-id="a058a-116">type</span></span>
- <span data-ttu-id="a058a-117">Ob ein Attribut mehrfach auf ein einzelnes Programmelement angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a058a-117">Whether an attribute can be applied to a single program element multiple times.</span></span>
- <span data-ttu-id="a058a-118">Ob Attribute von abgeleiteten Klassen geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="a058a-118">Whether attributes are inherited by derived classes.</span></span>

<span data-ttu-id="a058a-119">Die Standardeinstellungen ähneln folgendem Beispiel, wenn Sie explizit angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="a058a-119">The default settings look like the following example when applied explicitly:</span></span>

[!code-csharp[Define a new attribute](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#1)]

<span data-ttu-id="a058a-120">In diesem Beispiel kann die `NewAttribute`-Klasse auf jedes unterstützte Programmelement angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a058a-120">In this example, the `NewAttribute` class can be applied to any supported program element.</span></span> <span data-ttu-id="a058a-121">Es kann jedoch nur einmal auf jede Entität angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a058a-121">But it can be applied only once to each entity.</span></span> <span data-ttu-id="a058a-122">Wenn das Attribut auf eine Basisklasse angewendet wird, wird es an eine abgeleitete Klasse vererbt.</span><span class="sxs-lookup"><span data-stu-id="a058a-122">The attribute is inherited by derived classes when applied to a base class.</span></span>

<span data-ttu-id="a058a-123">Die Argumente <xref:System.AttributeUsageAttribute.AllowMultiple> und <xref:System.AttributeUsageAttribute.Inherited> sind optional, sodass folgender Code die gleiche Wirkung hat:</span><span class="sxs-lookup"><span data-stu-id="a058a-123">The <xref:System.AttributeUsageAttribute.AllowMultiple> and <xref:System.AttributeUsageAttribute.Inherited> arguments are optional, so the following code has the same effect:</span></span>

[!code-csharp[Omit optional attributes](../../../../../samples/snippets/csharp/attributes/NewAttribute.cs#2)]

<span data-ttu-id="a058a-124">Das erste <xref:System.AttributeUsageAttribute>-Argument muss mindestens ein Element der <xref:System.AttributeTargets>-Enumeration sein.</span><span class="sxs-lookup"><span data-stu-id="a058a-124">The first <xref:System.AttributeUsageAttribute> argument must be one or more elements of the <xref:System.AttributeTargets> enumeration.</span></span> <span data-ttu-id="a058a-125">Mehrere Zieltypen können wie im folgenden Beispiel dargestellt mithilfe des OR-Operators verknüpft werden:</span><span class="sxs-lookup"><span data-stu-id="a058a-125">Multiple target types can be linked together with the OR operator, like the following example shows:</span></span>

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#1)]

<span data-ttu-id="a058a-126">Ab C# 7.3 können Attribut auf das Eigenschaften- oder das Unterstützungsfeld einer automatisch implementierten Eigenschaft angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a058a-126">Beginning in C# 7.3, attributes can be applied to either the property or the backing field for an auto-implemented property.</span></span> <span data-ttu-id="a058a-127">Das Attribut wird auf die Eigenschaft angewendet, sofern Sie den `field`-Bezeichner des Attributs nicht angeben.</span><span class="sxs-lookup"><span data-stu-id="a058a-127">The attribute applies to the property, unless you specify the `field` specifier on the attribute.</span></span> <span data-ttu-id="a058a-128">Beides wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="a058a-128">Both are shown in the following example:</span></span>

[!code-csharp[Create an attribute for fields or properties](../../../../../samples/snippets/csharp/attributes/NewPropertyOrFieldAttribute.cs#2)]

<span data-ttu-id="a058a-129">Wenn das <xref:System.AttributeUsageAttribute.AllowMultiple>-Argument auf `true` festgelegt ist, kann das daraus entstehende Attribut wie im folgenden Beispiel dargestellt mehr als einmal auf eine einzelne Entität angewendet werden:</span><span class="sxs-lookup"><span data-stu-id="a058a-129">If the <xref:System.AttributeUsageAttribute.AllowMultiple> argument is `true`, then the resulting attribute can be applied more than once to a single entity, as shown in the following example:</span></span>

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/MultiUseAttribute.cs#1)]

<span data-ttu-id="a058a-130">In diesem Fall kann `MultiUseAttribute` wiederholt angewendet werden, da `AllowMultiple` auf `true` festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="a058a-130">In this case, `MultiUseAttribute` can be applied repeatedly because `AllowMultiple` is set to `true`.</span></span> <span data-ttu-id="a058a-131">Beide gezeigten Formate für das Anwenden von mehreren Attributen sind gültig.</span><span class="sxs-lookup"><span data-stu-id="a058a-131">Both formats shown for applying multiple attributes are valid.</span></span>

<span data-ttu-id="a058a-132">Wenn <xref:System.AttributeUsageAttribute.Inherited> auf `false` festgelegt wurde, wird das Attribut nicht von Klassen geerbt, die von einer Attributklasse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a058a-132">If <xref:System.AttributeUsageAttribute.Inherited> is `false`, then the attribute isn't inherited by classes derived from an attributed class.</span></span> <span data-ttu-id="a058a-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a058a-133">For example:</span></span>

[!code-csharp[Create and use an attribute that can be applied multiple times](../../../../../samples/snippets/csharp/attributes/NonInheritedAttribute.cs#1)]

<span data-ttu-id="a058a-134">In diesem Fall wird `NonInheritedAttribute` nicht durch Vererbung auf `DClass` angewendet.</span><span class="sxs-lookup"><span data-stu-id="a058a-134">In this case `NonInheritedAttribute` isn't applied to `DClass` via inheritance.</span></span>

## <a name="remarks"></a><span data-ttu-id="a058a-135">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a058a-135">Remarks</span></span>

<span data-ttu-id="a058a-136">Das `AttributeUsage`-Attribut ist für die einmalige Nutzung bestimmt. Es kann nicht mehr als einmal auf dieselbe Klasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a058a-136">The `AttributeUsage` attribute is a single-use attribute--it can't be applied more than once to the same class.</span></span> <span data-ttu-id="a058a-137">`AttributeUsage` ist ein Alias für <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="a058a-137">`AttributeUsage` is an alias for <xref:System.AttributeUsageAttribute>.</span></span>

<span data-ttu-id="a058a-138">Weitere Informationen finden Sie unter [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](accessing-attributes-by-using-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="a058a-138">For more information, see [Accessing Attributes by Using Reflection (C#)](accessing-attributes-by-using-reflection.md).</span></span>

## <a name="example"></a><span data-ttu-id="a058a-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a058a-139">Example</span></span>

<span data-ttu-id="a058a-140">In folgendem Beispiel wird die Wirkung der Argumente <xref:System.AttributeUsageAttribute.Inherited> und <xref:System.AttributeUsageAttribute.AllowMultiple> auf das Attribut <xref:System.AttributeUsageAttribute> und die Enumeration benutzerdefinierter Attribute veranschaulicht, die auf eine Klasse angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="a058a-140">The following example demonstrates the effect of the <xref:System.AttributeUsageAttribute.Inherited> and <xref:System.AttributeUsageAttribute.AllowMultiple> arguments to the <xref:System.AttributeUsageAttribute> attribute, and how the custom attributes applied to a class can be enumerated.</span></span>

[!code-csharp[Applying and querying attributes](../../../../../samples/snippets/csharp/attributes/Program.cs#1)]

## <a name="sample-output"></a><span data-ttu-id="a058a-141">Beispielausgabe</span><span class="sxs-lookup"><span data-stu-id="a058a-141">Sample Output</span></span>

```text
Attributes on Base Class:
FirstAttribute
SecondAttribute
Attributes on Derived Class:
ThirdAttribute
ThirdAttribute
SecondAttribute
```

## <a name="see-also"></a><span data-ttu-id="a058a-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a058a-142">See also</span></span>

- <xref:System.Attribute>
- <xref:System.Reflection>
- [<span data-ttu-id="a058a-143">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a058a-143">C# Programming Guide</span></span>](../..//index.md)
- [<span data-ttu-id="a058a-144">Attribute</span><span class="sxs-lookup"><span data-stu-id="a058a-144">Attributes</span></span>](../../../..//standard/attributes/index.md)
- [<span data-ttu-id="a058a-145">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="a058a-145">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="a058a-146">Attribute</span><span class="sxs-lookup"><span data-stu-id="a058a-146">Attributes</span></span>](index.md)
- [<span data-ttu-id="a058a-147">Erstellen benutzerdefinierter Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="a058a-147">Creating Custom Attributes (C#)</span></span>](creating-custom-attributes.md)
- [<span data-ttu-id="a058a-148">Zugriff auf Attribute mit Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="a058a-148">Accessing Attributes by Using Reflection (C#)</span></span>](accessing-attributes-by-using-reflection.md)
