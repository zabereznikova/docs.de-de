---
title: Einschränken des Zugriffsmethodenzugriffs – C#-Programmierhandbuch
description: Die Zugriffsmethoden „Get“ und „Set“ einer Eigenschaft in C# haben standardmäßig die gleiche Sichtbarkeit oder Zugriffsebene wie die Eigenschaft, zu der sie gehören. Sie können den Zugriff einschränken.
ms.date: 07/20/2015
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accessibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
ms.openlocfilehash: be7be4fc67a9a6f62a71f8473d6daa1fac49e842
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91199028"
---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a><span data-ttu-id="d353c-104">Einschränken des Accessorzugriffs (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d353c-104">Restricting Accessor Accessibility (C# Programming Guide)</span></span>

<span data-ttu-id="d353c-105">Die [Get](../../language-reference/keywords/get.md)- und [Set](../../language-reference/keywords/set.md)-Teile einer Eigenschaft oder eines Indexers werden *Zugriffsmethoden* oder Accessoren genannt.</span><span class="sxs-lookup"><span data-stu-id="d353c-105">The [get](../../language-reference/keywords/get.md) and [set](../../language-reference/keywords/set.md) portions of a property or indexer are called *accessors*.</span></span> <span data-ttu-id="d353c-106">Standardmäßig weisen diese Zugriffsmethoden dieselbe Sichtbarkeit oder Zugriffsebene auf: nämlich die der Eigenschaft oder des Indexers, zu dem sie gehören.</span><span class="sxs-lookup"><span data-stu-id="d353c-106">By default these accessors have the same visibility or access level of the property or indexer to which they belong.</span></span> <span data-ttu-id="d353c-107">Weitere Informationen finden Sie unter [Zugriffsebenen](../../language-reference/keywords/accessibility-levels.md).</span><span class="sxs-lookup"><span data-stu-id="d353c-107">For more information, see [accessibility levels](../../language-reference/keywords/accessibility-levels.md).</span></span> <span data-ttu-id="d353c-108">Allerdings ist es manchmal sinnvoll, den Zugriff auf eine der beiden Zugriffsmethoden einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="d353c-108">However, it is sometimes useful to restrict access to one of these accessors.</span></span> <span data-ttu-id="d353c-109">Dies bedeutet in der Regel, dass der Zugriff auf den `set`-Accessor eingeschränkt wird, während der `get`-Accessor öffentlich zugänglich bleibt.</span><span class="sxs-lookup"><span data-stu-id="d353c-109">Typically, this involves restricting the accessibility of the `set` accessor, while keeping the `get` accessor publicly accessible.</span></span> <span data-ttu-id="d353c-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d353c-110">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#6)]  
  
 <span data-ttu-id="d353c-111">In diesem Beispiel definiert die Eigenschaft `Name` einen `get`- und einen `set`-Accessor.</span><span class="sxs-lookup"><span data-stu-id="d353c-111">In this example, a property called `Name` defines a `get` and `set` accessor.</span></span> <span data-ttu-id="d353c-112">Der `get`-Accessor erhält die Zugriffsebene der Eigenschaft selbst, in diesem Fall `public`. Der `set`-Accessor wird jedoch explizit durch Anwenden des [Protected](../../language-reference/keywords/protected.md)-Zugriffsmodifizierers auf den Accessor selbst eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="d353c-112">The `get` accessor receives the accessibility level of the property itself, `public` in this case, while the `set` accessor is explicitly restricted by applying the [protected](../../language-reference/keywords/protected.md) access modifier to the accessor itself.</span></span>  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a><span data-ttu-id="d353c-113">Einschränkungen für Zugriffsmodifizierer für Accessoren</span><span class="sxs-lookup"><span data-stu-id="d353c-113">Restrictions on Access Modifiers on Accessors</span></span>  

 <span data-ttu-id="d353c-114">Bei der Verwendung von Accessormodifizierern auf Eigenschaften oder Indexer muss Folgendes beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="d353c-114">Using the accessor modifiers on properties or indexers is subject to these conditions:</span></span>  
  
- <span data-ttu-id="d353c-115">Accessormodifizierer können nicht bei einer Schnittstelle oder einer expliziten [Schnittstellen](../../language-reference/keywords/interface.md)-Member-Implementierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d353c-115">You cannot use accessor modifiers on an interface or an explicit [interface](../../language-reference/keywords/interface.md) member implementation.</span></span>  
  
- <span data-ttu-id="d353c-116">Accessormodifizierer können nur verwendet werden, wenn die Eigenschaft oder der Indexer sowohl einen `set`- als auch einen `get`-Accessor besitzt.</span><span class="sxs-lookup"><span data-stu-id="d353c-116">You can use accessor modifiers only if the property or indexer has both `set` and `get` accessors.</span></span> <span data-ttu-id="d353c-117">In diesem Fall ist der Modifizierer nur für einen der beiden Accessoren zulässig.</span><span class="sxs-lookup"><span data-stu-id="d353c-117">In this case, the modifier is permitted on only one of the two accessors.</span></span>  
  
- <span data-ttu-id="d353c-118">Besitzt die Eigenschaft oder der Indexer einen [Override](../../language-reference/keywords/override.md)-Modifizierer, muss der Accessormodifizierer mit dem eventuell vorhandenen Accessor des überschriebenen Accessors übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d353c-118">If the property or indexer has an [override](../../language-reference/keywords/override.md) modifier, the accessor modifier must match the accessor of the overridden accessor, if any.</span></span>  
  
- <span data-ttu-id="d353c-119">Die Zugriffsebene des Accessors muss restriktiver sein als die Zugriffsebene der Eigenschaft oder des Indexers selbst.</span><span class="sxs-lookup"><span data-stu-id="d353c-119">The accessibility level on the accessor must be more restrictive than the accessibility level on the property or indexer itself.</span></span>  
  
## <a name="access-modifiers-on-overriding-accessors"></a><span data-ttu-id="d353c-120">Zugriffsmodifizierer für Override-Accessoren</span><span class="sxs-lookup"><span data-stu-id="d353c-120">Access Modifiers on Overriding Accessors</span></span>  

 <span data-ttu-id="d353c-121">Beim Überschreiben einer Eigenschaft oder eines Indexers müssen die überschriebenen Accessoren für den überschreibenden Code zugänglich sein.</span><span class="sxs-lookup"><span data-stu-id="d353c-121">When you override a property or indexer, the overridden accessors must be accessible to the overriding code.</span></span> <span data-ttu-id="d353c-122">Außerdem müssen der Zugriff der Eigenschaft/des Indexers als auch der Accessoren mit der entsprechenden überschriebenen Eigenschaft/dem Indexer und den Accessoren übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="d353c-122">Also, the accessibility of both the property/indexer and its accessors must match the corresponding overridden property/indexer and its accessors.</span></span> <span data-ttu-id="d353c-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d353c-123">For example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#7)]  
  
## <a name="implementing-interfaces"></a><span data-ttu-id="d353c-124">Implementieren von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d353c-124">Implementing Interfaces</span></span>  

 <span data-ttu-id="d353c-125">Bei der Verwendung eines Accessors zur Implementierung einer Schnittstelle darf der Accessor keinen Zugriffsmodifizierer besitzen.</span><span class="sxs-lookup"><span data-stu-id="d353c-125">When you use an accessor to implement an interface, the accessor may not have an access modifier.</span></span> <span data-ttu-id="d353c-126">Wird jedoch zur Implementierung der Schnittstelle nur ein Accessor verwendet, z.B. `get`, kann der andere Accessor einen Zugriffsmodifizierer besitzen. Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d353c-126">However, if you implement the interface using one accessor, such as `get`, the other accessor can have an access modifier, as in the following example:</span></span>  
  
 [!code-csharp[csProgGuideIndexers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#8)]  
  
## <a name="accessor-accessibility-domain"></a><span data-ttu-id="d353c-127">Zugriffsdomäne des Accessors</span><span class="sxs-lookup"><span data-stu-id="d353c-127">Accessor Accessibility Domain</span></span>  

 <span data-ttu-id="d353c-128">Bei Verwendung eines Zugriffsmodifizierers für den Accessor wird die [Zugriffsdomäne](../../language-reference/keywords/accessibility-domain.md) des Accessors durch diesen Modifizierer bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d353c-128">If you use an access modifier on the accessor, the [accessibility domain](../../language-reference/keywords/accessibility-domain.md) of the accessor is determined by this modifier.</span></span>  
  
 <span data-ttu-id="d353c-129">Andernfalls wird die Zugriffsdomäne des Accessors durch die Zugriffsebene der Eigenschaft oder des Indexers bestimmt.</span><span class="sxs-lookup"><span data-stu-id="d353c-129">If you did not use an access modifier on the accessor, the accessibility domain of the accessor is determined by the accessibility level of the property or indexer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d353c-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d353c-130">Example</span></span>  

 <span data-ttu-id="d353c-131">Das folgende Beispiel enthält drei Klassen: `BaseClass`, `DerivedClass` und `MainClass`.</span><span class="sxs-lookup"><span data-stu-id="d353c-131">The following example contains three classes, `BaseClass`, `DerivedClass`, and `MainClass`.</span></span> <span data-ttu-id="d353c-132">Für `BaseClass` gibt es zwei Eigenschaften, `Name` und `Id` für beide Klassen.</span><span class="sxs-lookup"><span data-stu-id="d353c-132">There are two properties on the `BaseClass`, `Name` and `Id` on both classes.</span></span> <span data-ttu-id="d353c-133">Das Beispiel veranschaulicht, wie die Eigenschaft `Id` in `DerivedClass` durch die Eigenschaft `Id` in `BaseClass` ausgeblendet werden kann, wenn ein restriktiver Zugriffsmodifizierer, wie z.B. [protected](../../language-reference/keywords/protected.md) oder [private](../../language-reference/keywords/private.md), verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d353c-133">The example demonstrates how the property `Id` on `DerivedClass` can be hidden by the property `Id` on `BaseClass` when you use a restrictive access modifier such as [protected](../../language-reference/keywords/protected.md) or [private](../../language-reference/keywords/private.md).</span></span> <span data-ttu-id="d353c-134">Daher wird beim Zuweisen von Werten zu dieser Eigenschaft stattdessen die Eigenschaft für die Klasse `BaseClass` aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="d353c-134">Therefore, when you assign values to this property, the property on the `BaseClass` class is called instead.</span></span> <span data-ttu-id="d353c-135">Wird der Zugriffsmodifizierer durch [public](../../language-reference/keywords/public.md) ersetzt, kann auf die Eigenschaft zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="d353c-135">Replacing the access modifier by [public](../../language-reference/keywords/public.md) will make the property accessible.</span></span>  
  
 <span data-ttu-id="d353c-136">Das Beispiel zeigt auch, dass die Verwendung eines restriktiven Zugriffsmodifizierers, wie z.B. `private` oder `protected`, auf den `set`-Accessor der Eigenschaft `Name` in `DerivedClass` den Zugriff auf den Accessor verhindert. Mit dem Zuweisen zu dem Accessor wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="d353c-136">The example also demonstrates that a restrictive access modifier, such as `private` or `protected`, on the `set` accessor of the `Name` property in `DerivedClass` prevents access to the accessor and generates an error when you assign to it.</span></span>  
  
 [!code-csharp[csProgGuideIndexers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#5)]  
  
## <a name="comments"></a><span data-ttu-id="d353c-137">Kommentare</span><span class="sxs-lookup"><span data-stu-id="d353c-137">Comments</span></span>  

 <span data-ttu-id="d353c-138">Beachten Sie, dass beim Ersetzen der Deklaration `new private string Id` durch `new public string Id` Folgendes ausgegeben wird:</span><span class="sxs-lookup"><span data-stu-id="d353c-138">Notice that if you replace the declaration `new private string Id` by `new public string Id`, you get the output:</span></span>  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a><span data-ttu-id="d353c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d353c-139">See also</span></span>

- [<span data-ttu-id="d353c-140">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d353c-140">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d353c-141">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="d353c-141">Properties</span></span>](./properties.md)
- [<span data-ttu-id="d353c-142">Indexer</span><span class="sxs-lookup"><span data-stu-id="d353c-142">Indexers</span></span>](../indexers/index.md)
- [<span data-ttu-id="d353c-143">Zugriffsmodifizierer</span><span class="sxs-lookup"><span data-stu-id="d353c-143">Access Modifiers</span></span>](./access-modifiers.md)
