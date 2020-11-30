---
title: Verfassen von benutzerdefinierten Attributen
description: Entwerfen Sie Ihre eigenen benutzerdefinierten Attribute in .NET. Benutzerdefinierte Attribute sind im wesentlichen Klassen, die direkt oder indirekt von System.Attribute abgeleitet werden.
ms.date: 07/17/2018
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- multiple attribute instances
- AttributeTargets enumeration
- attributes [.NET], custom
- AllowMultiple property
- custom attributes
- AttributeUsageAttribute class, custom attributes
- Inherited property
- attribute classes, declaring
ms.assetid: 97216f69-bde8-49fd-ac40-f18c500ef5dc
ms.openlocfilehash: e3c97f28a05f2e5396872fe808cae0d48d5a4824
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727002"
---
# <a name="writing-custom-attributes"></a><span data-ttu-id="eef16-104">Verfassen von benutzerdefinierten Attributen</span><span class="sxs-lookup"><span data-stu-id="eef16-104">Writing Custom Attributes</span></span>

<span data-ttu-id="eef16-105">Zum Entwerfen eigener, benutzerdefinierter Attribute brauchen Sie nicht viele neue Konzepte zu beherrschen.</span><span class="sxs-lookup"><span data-stu-id="eef16-105">To design your own custom attributes, you do not need to master many new concepts.</span></span> <span data-ttu-id="eef16-106">Wenn Sie mit objektorientierter Programmierung vertraut sind und wissen, wie Klassen entworfen werden, haben Sie bereits den größten Teil der Kenntnisse, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="eef16-106">If you are familiar with object-oriented programming and know how to design classes, you already have most of the knowledge needed.</span></span> <span data-ttu-id="eef16-107">Benutzerdefinierte Attribute sind im Wesentlichen traditionelle Klassen, die sich direkt oder indirekt aus <xref:System.Attribute?displayProperty=nameWithType>ableiten.</span><span class="sxs-lookup"><span data-stu-id="eef16-107">Custom attributes are essentially traditional classes that derive directly or indirectly from <xref:System.Attribute?displayProperty=nameWithType>.</span></span> <span data-ttu-id="eef16-108">Genau wie traditionelle Klassen enthalten benutzerdefinierte Attribute Methoden zum Speichern und Abrufen von Daten.</span><span class="sxs-lookup"><span data-stu-id="eef16-108">Just like traditional classes, custom attributes contain methods that store and retrieve data.</span></span>  
  
 <span data-ttu-id="eef16-109">Die wichtigsten Schritte beim ordnungsgemäßen Entwerfen von benutzerdefinierten Attributklassen sind die folgenden:</span><span class="sxs-lookup"><span data-stu-id="eef16-109">The primary steps to properly design custom attribute classes are as follows:</span></span>  
  
- [<span data-ttu-id="eef16-110">Anwenden des AttributeUsage-Attributs</span><span class="sxs-lookup"><span data-stu-id="eef16-110">Applying the AttributeUsageAttribute</span></span>](#applying-the-attributeusageattribute)  
  
- [<span data-ttu-id="eef16-111">Deklarieren der Attributklasse</span><span class="sxs-lookup"><span data-stu-id="eef16-111">Declaring the attribute class</span></span>](#declaring-the-attribute-class)  
  
- [<span data-ttu-id="eef16-112">Deklarieren von Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="eef16-112">Declaring constructors</span></span>](#declaring-constructors)  
  
- [<span data-ttu-id="eef16-113">Deklarieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eef16-113">Declaring properties</span></span>](#declaring-properties)  
  
 <span data-ttu-id="eef16-114">In diesem Abschnitt wird jeder dieser Schritte beschrieben, den Schluss bildet ein [Beispiel für ein benutzerdefiniertes Attribut](#custom-attribute-example).</span><span class="sxs-lookup"><span data-stu-id="eef16-114">This section describes each of these steps and concludes with a [custom attribute example](#custom-attribute-example).</span></span>  
  
## <a name="applying-the-attributeusageattribute"></a><span data-ttu-id="eef16-115">Anwenden des AttributeUsage-Attributs</span><span class="sxs-lookup"><span data-stu-id="eef16-115">Applying the AttributeUsageAttribute</span></span>  

 <span data-ttu-id="eef16-116">Die Deklaration eines benutzerdefinierten Attributs beginnt mit dem <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>, das einige der Hauptmerkmale Ihrer Attributklasse definiert.</span><span class="sxs-lookup"><span data-stu-id="eef16-116">A custom attribute declaration begins with the <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>, which defines some of the key characteristics of your attribute class.</span></span> <span data-ttu-id="eef16-117">Sie können beispielsweise angeben, ob das Attribut von anderen Klassen geerbt werden kann, oder festlegen, auf welche Elemente das Attribut angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="eef16-117">For example, you can specify whether your attribute can be inherited by other classes or specify which elements the attribute can be applied to.</span></span> <span data-ttu-id="eef16-118">Das folgende Codefragment zeigt die Verwendung des <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="eef16-118">The following code fragment demonstrates how to use the <xref:System.AttributeUsageAttribute>.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#5)]
 [!code-csharp[Conceptual.Attributes.Usage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#5)]
 [!code-vb[Conceptual.Attributes.Usage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#5)]  
  
 <span data-ttu-id="eef16-119">Die Klasse <xref:System.AttributeUsageAttribute> weist drei Member auf, die für die Erstellung von benutzerdefinierten Attributen wichtig sind: [AttributeTargets](#attributetargets-member), [Inherited](#inherited-property) und [AllowMultiple](#allowmultiple-property).</span><span class="sxs-lookup"><span data-stu-id="eef16-119">The <xref:System.AttributeUsageAttribute> has three members that are important for the creation of custom attributes: [AttributeTargets](#attributetargets-member), [Inherited](#inherited-property), and [AllowMultiple](#allowmultiple-property).</span></span>  
  
### <a name="attributetargets-member"></a><span data-ttu-id="eef16-120">AttributeTargets-Member</span><span class="sxs-lookup"><span data-stu-id="eef16-120">AttributeTargets Member</span></span>  

 <span data-ttu-id="eef16-121">Im vorherigen Beispiel wird <xref:System.AttributeTargets.All?displayProperty=nameWithType> angegeben, was darauf hinweist, dass dieses Attribut auf alle Programmelemente angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="eef16-121">In the previous example, <xref:System.AttributeTargets.All?displayProperty=nameWithType> is specified, indicating that this attribute can be applied to all program elements.</span></span> <span data-ttu-id="eef16-122">Alternativ können Sie <xref:System.AttributeTargets.Class?displayProperty=nameWithType> angeben und damit festlegen, dass Ihr Attribut nur auf eine Klasse angewendet werden kann, oder Sie können <xref:System.AttributeTargets.Method?displayProperty=nameWithType> angeben, wodurch Sie festlegen, dass Ihr Attribut nur auf eine Methode angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="eef16-122">Alternatively, you can specify <xref:System.AttributeTargets.Class?displayProperty=nameWithType>, indicating that your attribute can be applied only to a class, or <xref:System.AttributeTargets.Method?displayProperty=nameWithType>, indicating that your attribute can be applied only to a method.</span></span> <span data-ttu-id="eef16-123">Alle Programmelemente können in dieser Weise für die Beschreibung durch ein benutzerdefiniertes Attribut gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="eef16-123">All program elements can be marked for description by a custom attribute in this manner.</span></span>  
  
 <span data-ttu-id="eef16-124">Sie können auch mehrere <xref:System.AttributeTargets>-Werte übergeben.</span><span class="sxs-lookup"><span data-stu-id="eef16-124">You can also pass multiple <xref:System.AttributeTargets> values.</span></span> <span data-ttu-id="eef16-125">Das folgende Codefragment gibt an, dass ein benutzerdefiniertes Attribut auf beliebige Klassen oder Methoden angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="eef16-125">The following code fragment specifies that a custom attribute can be applied to any class or method.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#6)]
 [!code-csharp[Conceptual.Attributes.Usage#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#6)]
 [!code-vb[Conceptual.Attributes.Usage#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#6)]  
  
### <a name="inherited-property"></a><span data-ttu-id="eef16-126">Inherited Property</span><span class="sxs-lookup"><span data-stu-id="eef16-126">Inherited Property</span></span>  

 <span data-ttu-id="eef16-127">Die <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType>-Eigenschaft gibt an, ob das Attribut von Klassen geerbt werden kann, die von den Klassen abgeleitet werden, auf die das Attribut angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="eef16-127">The <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property indicates whether your attribute can be inherited by classes that are derived from the classes to which your attribute is applied.</span></span> <span data-ttu-id="eef16-128">Diese Eigenschaft akzeptiert entweder das Flag `true` (den Standardwert) oder das Flag `false`.</span><span class="sxs-lookup"><span data-stu-id="eef16-128">This property takes either a `true` (the default) or `false` flag.</span></span> <span data-ttu-id="eef16-129">Im folgenden Beispiel weist `MyAttribute` für <xref:System.AttributeUsageAttribute.Inherited%2A> den Standardwert `true` auf, während `YourAttribute` einen <xref:System.AttributeUsageAttribute.Inherited%2A>-Wert von `false` hat.</span><span class="sxs-lookup"><span data-stu-id="eef16-129">In the following example, `MyAttribute` has a default <xref:System.AttributeUsageAttribute.Inherited%2A> value of `true`, while `YourAttribute` has an <xref:System.AttributeUsageAttribute.Inherited%2A> value of `false`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#7)]
 [!code-csharp[Conceptual.Attributes.Usage#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#7)]
 [!code-vb[Conceptual.Attributes.Usage#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#7)]  
  
 <span data-ttu-id="eef16-130">Die beiden Attribute werden dann auf eine Methode in der Basisklasse `MyClass`angewendet.</span><span class="sxs-lookup"><span data-stu-id="eef16-130">The two attributes are then applied to a method in the base class `MyClass`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#9)]
 [!code-csharp[Conceptual.Attributes.Usage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#9)]
 [!code-vb[Conceptual.Attributes.Usage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#9)]  
  
 <span data-ttu-id="eef16-131">Schließlich wird die Klasse `YourClass` von der Basisklasse `MyClass`geerbt.</span><span class="sxs-lookup"><span data-stu-id="eef16-131">Finally, the class `YourClass` is inherited from the base class `MyClass`.</span></span> <span data-ttu-id="eef16-132">Die Methode `MyMethod` zeigt `MyAttribute`, aber nicht `YourAttribute`.</span><span class="sxs-lookup"><span data-stu-id="eef16-132">The method `MyMethod` shows `MyAttribute`, but not `YourAttribute`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#10](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#10)]
 [!code-csharp[Conceptual.Attributes.Usage#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#10)]
 [!code-vb[Conceptual.Attributes.Usage#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#10)]  
  
### <a name="allowmultiple-property"></a><span data-ttu-id="eef16-133">AllowMultiple-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="eef16-133">AllowMultiple Property</span></span>  

 <span data-ttu-id="eef16-134">Die <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType>-Eigenschaft gibt an, ob mehrere Instanzen eines Attributs für ein Element vorhanden sein können.</span><span class="sxs-lookup"><span data-stu-id="eef16-134">The <xref:System.AttributeUsageAttribute.AllowMultiple%2A?displayProperty=nameWithType> property indicates whether multiple instances of your attribute can exist on an element.</span></span> <span data-ttu-id="eef16-135">Wenn sie auf `true` festgelegt ist, sind mehrere Instanzen zulässig; bei `false` (dem Standardwert) ist nur eine Instanz erlaubt.</span><span class="sxs-lookup"><span data-stu-id="eef16-135">If set to `true`, multiple instances are allowed; if set to `false` (the default), only one instance is allowed.</span></span>  
  
 <span data-ttu-id="eef16-136">Im folgenden Beispiel weist `MyAttribute` für <xref:System.AttributeUsageAttribute.AllowMultiple%2A> den Standardwert `false` auf, während `YourAttribute` den Wert `true` hat.</span><span class="sxs-lookup"><span data-stu-id="eef16-136">In the following example, `MyAttribute` has a default <xref:System.AttributeUsageAttribute.AllowMultiple%2A> value of `false`, while `YourAttribute` has a value of `true`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#11](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#11)]
 [!code-csharp[Conceptual.Attributes.Usage#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#11)]
 [!code-vb[Conceptual.Attributes.Usage#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#11)]  
  
 <span data-ttu-id="eef16-137">Wenn mehrere Instanzen dieser Attribute angewendet werden, führt `MyAttribute` zu einem Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="eef16-137">When multiple instances of these attributes are applied, `MyAttribute` produces a compiler error.</span></span> <span data-ttu-id="eef16-138">Das folgende Codebeispiel zeigt die gültige Verwendung von `YourAttribute` und die ungültige Verwaltung von `MyAttribute`.</span><span class="sxs-lookup"><span data-stu-id="eef16-138">The following code example shows the valid use of `YourAttribute` and the invalid use of `MyAttribute`.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#13](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#13)]
 [!code-csharp[Conceptual.Attributes.Usage#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#13)]
 [!code-vb[Conceptual.Attributes.Usage#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#13)]  
  
 <span data-ttu-id="eef16-139">Wenn sowohl die <xref:System.AttributeUsageAttribute.AllowMultiple%2A>-Eigenschaft als auch die <xref:System.AttributeUsageAttribute.Inherited%2A>-Eigenschaft auf `true` festgelegt sind, kann eine Klasse, die von einer anderen Klasse geerbt wurde, ein Attribut erben, und zugleich kann in der gleichen untergeordneten Klasse eine weitere Instanz des gleichen Attributs angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="eef16-139">If both the <xref:System.AttributeUsageAttribute.AllowMultiple%2A> property and the <xref:System.AttributeUsageAttribute.Inherited%2A> property are set to `true`, a class that is inherited from another class can inherit an attribute and have another instance of the same attribute applied in the same child class.</span></span> <span data-ttu-id="eef16-140">Wenn <xref:System.AttributeUsageAttribute.AllowMultiple%2A> auf `false` festgelegt ist, werden die Werte aller Attribute in der übergeordneten Klasse durch neue Instanzen der gleichen Attribute in der untergeordneten Klasse überschrieben.</span><span class="sxs-lookup"><span data-stu-id="eef16-140">If <xref:System.AttributeUsageAttribute.AllowMultiple%2A> is set to `false`, the values of any attributes in the parent class will be overwritten by new instances of the same attribute in the child class.</span></span>  
  
## <a name="declaring-the-attribute-class"></a><span data-ttu-id="eef16-141">Deklarieren der Attributklasse</span><span class="sxs-lookup"><span data-stu-id="eef16-141">Declaring the Attribute Class</span></span>  

 <span data-ttu-id="eef16-142">Nach dem Anwenden von <xref:System.AttributeUsageAttribute>können Sie beginnen, die Einzelheiten Ihres Attributs zu definieren.</span><span class="sxs-lookup"><span data-stu-id="eef16-142">After you apply the <xref:System.AttributeUsageAttribute>, you can begin to define the specifics of your attribute.</span></span> <span data-ttu-id="eef16-143">Die Deklaration einer Attributklasse ähnelt der Deklaration einer traditionellen Klasse, wie im folgenden Code zu sehen.</span><span class="sxs-lookup"><span data-stu-id="eef16-143">The declaration of an attribute class looks similar to the declaration of a traditional class, as demonstrated by the following code.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#14](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#14)]
 [!code-csharp[Conceptual.Attributes.Usage#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#14)]
 [!code-vb[Conceptual.Attributes.Usage#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#14)]  
  
 <span data-ttu-id="eef16-144">Diese Attibutdefinition veranschaulicht die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="eef16-144">This attribute definition demonstrates the following points:</span></span>  
  
- <span data-ttu-id="eef16-145">Attributklassen müssen als öffentliche Klassen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="eef16-145">Attribute classes must be declared as public classes.</span></span>  
  
- <span data-ttu-id="eef16-146">Gemäß Konvention endet der Name der Attributklasse mit dem Wort **Attribute**.</span><span class="sxs-lookup"><span data-stu-id="eef16-146">By convention, the name of the attribute class ends with the word **Attribute**.</span></span> <span data-ttu-id="eef16-147">Dies ist zwar nicht erforderlich, die Einhaltung dieser Konvention empfiehlt sich aber aus Gründen der besseren Übersicht.</span><span class="sxs-lookup"><span data-stu-id="eef16-147">While not required, this convention is recommended for readability.</span></span> <span data-ttu-id="eef16-148">Wenn das Attribut angewendet wird, ist die Aufnahme des Wortes „Attribute“ optional.</span><span class="sxs-lookup"><span data-stu-id="eef16-148">When the attribute is applied, the inclusion of the word Attribute is optional.</span></span>  
  
- <span data-ttu-id="eef16-149">Alle Attributklassen müssen direkt oder indirekt von <xref:System.Attribute?displayProperty=nameWithType> erben.</span><span class="sxs-lookup"><span data-stu-id="eef16-149">All attribute classes must inherit directly or indirectly from <xref:System.Attribute?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="eef16-150">In Microsoft Visual Basic müssen alle benutzerdefinierten Attributklassen über das Attribut <xref:System.AttributeUsageAttribute?displayProperty=nameWithType> verfügen.</span><span class="sxs-lookup"><span data-stu-id="eef16-150">In Microsoft Visual Basic, all custom attribute classes must have the <xref:System.AttributeUsageAttribute?displayProperty=nameWithType> attribute.</span></span>  
  
## <a name="declaring-constructors"></a><span data-ttu-id="eef16-151">Deklarieren von Konstruktoren</span><span class="sxs-lookup"><span data-stu-id="eef16-151">Declaring Constructors</span></span>  

 <span data-ttu-id="eef16-152">Attribute werden in der gleichen Weise wie traditionelle Klassen mit Konstruktoren initialisiert.</span><span class="sxs-lookup"><span data-stu-id="eef16-152">Attributes are initialized with constructors in the same way as traditional classes.</span></span> <span data-ttu-id="eef16-153">Das folgende Codefragment stellt ein Beispiel für einen typischen Attributkonstruktor dar.</span><span class="sxs-lookup"><span data-stu-id="eef16-153">The following code fragment illustrates a typical attribute constructor.</span></span> <span data-ttu-id="eef16-154">Dieser öffentliche Konstruktor akzeptiert einen Parameter und legt eine Membervariable auf seinen Wert fest.</span><span class="sxs-lookup"><span data-stu-id="eef16-154">This public constructor takes a parameter and sets a member variable equal to its value.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#15](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#15)]
 [!code-csharp[Conceptual.Attributes.Usage#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#15)]
 [!code-vb[Conceptual.Attributes.Usage#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#15)]  
  
 <span data-ttu-id="eef16-155">Sie können den Konstruktor überladen, um verschiedene Kombinationen von Werten zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="eef16-155">You can overload the constructor to accommodate different combinations of values.</span></span> <span data-ttu-id="eef16-156">Wenn Sie darüber hinaus eine [Eigenschaft](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)) für Ihre benutzerdefinierte Attributklasse definieren, können Sie eine Kombination aus benannten und Positionsparametern zum Initialisieren des Attributs verwenden.</span><span class="sxs-lookup"><span data-stu-id="eef16-156">If you also define a [property](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)) for your custom attribute class, you can use a combination of named and positional parameters when initializing the attribute.</span></span> <span data-ttu-id="eef16-157">Normalerweise definieren Sie alle erforderlichen Parameter als Positionsparameter und alle optionalen Parameter als benannt.</span><span class="sxs-lookup"><span data-stu-id="eef16-157">Typically, you define all required parameters as positional and all optional parameters as named.</span></span> <span data-ttu-id="eef16-158">In diesem Fall kann das Attribut nicht ohne den erforderlichen Parameter initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="eef16-158">In this case, the attribute cannot be initialized without the required parameter.</span></span> <span data-ttu-id="eef16-159">Alle anderen Parameter sind optional.</span><span class="sxs-lookup"><span data-stu-id="eef16-159">All other parameters are optional.</span></span> <span data-ttu-id="eef16-160">Beachten Sie, dass in Visual Basic die Konstruktoren für eine Attributklasse kein ParamArray-Argument verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="eef16-160">Note that in Visual Basic, constructors for an attribute class should not use a ParamArray argument.</span></span>  
  
 <span data-ttu-id="eef16-161">Das folgende Codebeispiel zeigt, wie ein Attribut, das den oben angegebenen Konstruktor verwendet, mithilfe von optionalen und erforderlichen Parametern angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="eef16-161">The following code example shows how an attribute that uses the previous constructor can be applied using optional and required parameters.</span></span> <span data-ttu-id="eef16-162">Es wird angenommen, dass das Attribut einen erforderlichen Booleschen Wert und eine optionale Zeichenfolgeneigenschaft aufweist.</span><span class="sxs-lookup"><span data-stu-id="eef16-162">It assumes that the attribute has one required Boolean value and one optional string property.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#17)]
 [!code-csharp[Conceptual.Attributes.Usage#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#17)]
 [!code-vb[Conceptual.Attributes.Usage#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#17)]  
  
## <a name="declaring-properties"></a><span data-ttu-id="eef16-163">Deklarieren von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eef16-163">Declaring Properties</span></span>  

 <span data-ttu-id="eef16-164">Wenn Sie einen benannten Parameter definieren oder eine einfache Möglichkeit zum Zurückgeben der von Ihrem Attribut gespeicherten Werte bereitstellen möchten, deklarieren Sie eine [Eigenschaft](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="eef16-164">If you want to define a named parameter or provide an easy way to return the values stored by your attribute, declare a [property](/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v=vs.120)).</span></span> <span data-ttu-id="eef16-165">Attributeigenschaften müssen als öffentliche Entitäten mit einer Beschreibung des zurückgegebenen Datentyps deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="eef16-165">Attribute properties should be declared as public entities with a description of the data type that will be returned.</span></span> <span data-ttu-id="eef16-166">Definieren Sie die Variable, die den Wert der Eigenschaft enthalten soll, und ordnen Sie sie den Methoden **get** und **set** zu.</span><span class="sxs-lookup"><span data-stu-id="eef16-166">Define the variable that will hold the value of your property and associate it with the **get** and **set** methods.</span></span> <span data-ttu-id="eef16-167">Das folgende Codebeispiel veranschaulicht, wie eine einfache Eigenschaft in Ihrem Attribut implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="eef16-167">The following code example demonstrates how to implement a simple property in your attribute.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#16](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#16)]
 [!code-csharp[Conceptual.Attributes.Usage#16](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#16)]
 [!code-vb[Conceptual.Attributes.Usage#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#16)]  
  
## <a name="custom-attribute-example"></a><span data-ttu-id="eef16-168">Beispiel für ein benutzerdefiniertes Attribut</span><span class="sxs-lookup"><span data-stu-id="eef16-168">Custom Attribute Example</span></span>  

 <span data-ttu-id="eef16-169">Dieser Abschnitt beinhaltet die Informationen aus den vorhergehenden Abschnitten und zeigt das Entwerfen eines einfachen Attributs, das Informationen über den Autor eines Codeabschnitts dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="eef16-169">This section incorporates the previous information and shows how to design a simple attribute that documents information about the author of a section of code.</span></span> <span data-ttu-id="eef16-170">Das Attribut in diesem Beispiel speichert den Namen und die Qualifikation des Programmierers und gibt an, ob der Code überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="eef16-170">The attribute in this example stores the name and level of the programmer, and whether the code has been reviewed.</span></span> <span data-ttu-id="eef16-171">Es verwendet drei private Variablen zum Speichern der eigentlichen, zu speichernden Werte.</span><span class="sxs-lookup"><span data-stu-id="eef16-171">It uses three private variables to store the actual values to save.</span></span> <span data-ttu-id="eef16-172">Jede Variable wird durch eine öffentliche Eigenschaft dargestellt, die zum Abrufen und Festlegen der Werte verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eef16-172">Each variable is represented by a public property that gets and sets the values.</span></span> <span data-ttu-id="eef16-173">Schließlich wird der Konstruktor mit zwei erforderlichen Parametern definiert.</span><span class="sxs-lookup"><span data-stu-id="eef16-173">Finally, the constructor is defined with two required parameters.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#4)]
 [!code-csharp[Conceptual.Attributes.Usage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#4)]
 [!code-vb[Conceptual.Attributes.Usage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#4)]  
  
 <span data-ttu-id="eef16-174">Sie können das Attribut mit seinem vollständigen Namen `DeveloperAttribute`oder mit seinem abgekürzten Namen `Developer`auf eine der folgenden Weisen anwenden.</span><span class="sxs-lookup"><span data-stu-id="eef16-174">You can apply this attribute using the full name, `DeveloperAttribute`, or using the abbreviated name, `Developer`, in one of the following ways.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#12](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source2.cpp#12)]
 [!code-csharp[Conceptual.Attributes.Usage#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source2.cs#12)]
 [!code-vb[Conceptual.Attributes.Usage#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source2.vb#12)]  
  
 <span data-ttu-id="eef16-175">Im ersten Beispiel wird das Attribut nur mit den erforderlichen benannten Parametern angewendet, während das zweite Beispiel die Anwendung des Attributs mit den erforderlichen und den optionalen Parametern zeigt.</span><span class="sxs-lookup"><span data-stu-id="eef16-175">The first example shows the attribute applied with only the required named parameters, while the second example shows the attribute applied with both the required and optional parameters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eef16-176">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eef16-176">See also</span></span>

- <xref:System.Attribute?displayProperty=nameWithType>
- <xref:System.AttributeUsageAttribute?displayProperty=nameWithType>
- [<span data-ttu-id="eef16-177">Attribute</span><span class="sxs-lookup"><span data-stu-id="eef16-177">Attributes</span></span>](index.md)
