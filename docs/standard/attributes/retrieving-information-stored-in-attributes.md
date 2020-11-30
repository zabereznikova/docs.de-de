---
title: Abrufen von Informationen aus Attributen
description: Hier erfahren Sie mehr über das Abrufen von in Attributen gespeicherten Informationen für eine Attributinstanz, viele Instanzen für denselben Bereich und viele Instanzen für verschiedene Bereiche.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
ms.openlocfilehash: 6ba01fcd23e626354e5f9a2baa914815b61c8332
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701561"
---
# <a name="retrieving-information-stored-in-attributes"></a><span data-ttu-id="0f2e5-103">Abrufen von Informationen aus Attributen</span><span class="sxs-lookup"><span data-stu-id="0f2e5-103">Retrieving Information Stored in Attributes</span></span>

<span data-ttu-id="0f2e5-104">Das Abrufen eines benutzerdefinierten Attributs ist ein einfacher Prozess.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-104">Retrieving a custom attribute is a simple process.</span></span> <span data-ttu-id="0f2e5-105">Zuerst deklarieren Sie eine Instanz des Attributs, das Sie abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-105">First, declare an instance of the attribute you want to retrieve.</span></span> <span data-ttu-id="0f2e5-106">Dann verwenden Sie die <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>-Methode, um das neue Attribut auf den Wert des abzurufenden Attributs zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-106">Then, use the <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> method to initialize the new attribute to the value of the attribute you want to retrieve.</span></span> <span data-ttu-id="0f2e5-107">Sobald das neue Attribut initialisiert wurde, verwenden Sie einfach dessen Eigenschaften, um die Werte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-107">Once the new attribute is initialized, you simply use its properties to get the values.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0f2e5-108">In diesem Thema wird beschrieben, wie Attribute für Code abgerufen werden, der in den Ausführungskontext geladen wird.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-108">This topic describes how to retrieve attributes for code loaded into the execution context.</span></span> <span data-ttu-id="0f2e5-109">Zum Abrufen von Attributen für Code, der in den reflexionsbezogenen Kontext geladen wurde, müssen Sie die <xref:System.Reflection.CustomAttributeData>-Klasse verwenden, wie in [Vorgehensweise: Laden von Assemblys in den reflexionsbezogenen Kontext](../../framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span><span class="sxs-lookup"><span data-stu-id="0f2e5-109">To retrieve attributes for code loaded into the reflection-only context, you must use the <xref:System.Reflection.CustomAttributeData> class, as shown in [How to: Load Assemblies into the Reflection-Only Context](../../framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
 <span data-ttu-id="0f2e5-110">Dieser Abschnitt erläutert die folgenden Möglichkeiten zum Abrufen von Attributen:</span><span class="sxs-lookup"><span data-stu-id="0f2e5-110">This section describes the following ways to retrieve attributes:</span></span>  
  
- [<span data-ttu-id="0f2e5-111">Eine einzelne Instanz eines Attributs abrufen</span><span class="sxs-lookup"><span data-stu-id="0f2e5-111">Retrieving a single instance of an attribute</span></span>](#cpconretrievingsingleinstanceofattribute)  
  
- [<span data-ttu-id="0f2e5-112">Abrufen mehrerer Instanzen eines Attributs in demselben Gültigkeitsbereich angewendet</span><span class="sxs-lookup"><span data-stu-id="0f2e5-112">Retrieving multiple instances of an attribute applied to the same scope</span></span>](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
- [<span data-ttu-id="0f2e5-113">Abrufen mehrerer Instanzen eines Attributs auf unterschiedliche Bereiche angewendet</span><span class="sxs-lookup"><span data-stu-id="0f2e5-113">Retrieving multiple instances of an attribute applied to different scopes</span></span>](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>

## <a name="retrieving-a-single-instance-of-an-attribute"></a><span data-ttu-id="0f2e5-114">Abrufen einer einzelnen Instanz eines Attributs</span><span class="sxs-lookup"><span data-stu-id="0f2e5-114">Retrieving a Single Instance of an Attribute</span></span>  

 <span data-ttu-id="0f2e5-115">Im folgenden Beispiel wird die (im vorherigen Abschnitt beschriebene) `DeveloperAttribute`-Klasse auf die `MainApp`-Klasse auf Klassenebene angewendet.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-115">In the following example, the `DeveloperAttribute` (described in the previous section) is applied to the `MainApp` class on the class level.</span></span> <span data-ttu-id="0f2e5-116">Die `GetAttribute`-Methode verwendet **GetCustomAttribute**, um die in `DeveloperAttribute` gespeicherten Werte auf Klassenebene abzurufen, bevor sie in der Konsole angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-116">The `GetAttribute` method uses **GetCustomAttribute** to retrieve the values stored in `DeveloperAttribute` on the class level before displaying them to the console.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 <span data-ttu-id="0f2e5-117">Dieses Programm zeigt folgenden Text bei der Ausführung an.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-117">This program displays the following text when executed.</span></span>  
  
```console  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 <span data-ttu-id="0f2e5-118">Wenn das Attribut nicht gefunden wird, initialisiert die **GetCustomAttribute**-Methode `MyAttribute` auf einen Nullwert.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-118">If the attribute is not found, the **GetCustomAttribute** method initializes `MyAttribute` to a null value.</span></span> <span data-ttu-id="0f2e5-119">In diesem Beispiel wird `MyAttribute` auf eine solche Instanz geprüft und der Benutzer benachrichtigt, wenn kein Attribut gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-119">This example checks `MyAttribute` for such an instance and notifies the user if no attribute is found.</span></span> <span data-ttu-id="0f2e5-120">Wenn das `DeveloperAttribute` nicht im Klassenbereich gefunden werden, wird die folgende Meldung in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-120">If the `DeveloperAttribute` is not found in the class scope, the following message displays to the console.</span></span>  
  
```console  
The attribute was not found.
```  
  
 <span data-ttu-id="0f2e5-121">In diesem Beispiel wird davon ausgegangen, dass sich die Attributdefinition im aktuellen Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-121">This example assumes that the attribute definition is in the current namespace.</span></span> <span data-ttu-id="0f2e5-122">Denken Sie daran, den Namespace zu importieren, in dem sich die Attributdefinition befindet, wenn diese nicht im aktuellen Namespace ist.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-122">Remember to import the namespace in which the attribute definition resides if it is not in the current namespace.</span></span>  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>

## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a><span data-ttu-id="0f2e5-123">Abrufen mehrerer Instanzen eines Attributs in demselben Gültigkeitsbereich angewendet</span><span class="sxs-lookup"><span data-stu-id="0f2e5-123">Retrieving Multiple Instances of an Attribute Applied to the Same Scope</span></span>  

 <span data-ttu-id="0f2e5-124">Im vorherigen Beispiel werden die zu prüfende Klasse und das zu suchenden spezifische Attribut an <xref:System.Attribute.GetCustomAttribute%2A> übergeben.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-124">In the previous example, the class to inspect and the specific attribute to find are passed to <xref:System.Attribute.GetCustomAttribute%2A>.</span></span> <span data-ttu-id="0f2e5-125">Dieser Code funktioniert gut, wenn nur eine Instanz eines Attributs auf Klassenebene angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-125">That code works well if only one instance of an attribute is applied on the class level.</span></span> <span data-ttu-id="0f2e5-126">Wenn jedoch mehrere Instanzen eines Attributs auf derselben Klassenebene angewendet werden, ruft die **GetCustomAttribute**-Methode nicht alle Informationen ab.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-126">However, if multiple instances of an attribute are applied on the same class level, the **GetCustomAttribute** method does not retrieve all the information.</span></span> <span data-ttu-id="0f2e5-127">In Fällen, in dem mehrere Instanzen des gleichen Attributs in demselben Gültigkeitsbereich angewendet werden, können Sie mithilfe von <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> alle Instanzen eines Attributs in einem Array platzieren.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-127">In cases where multiple instances of the same attribute are applied to the same scope, you can use <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> to place all instances of an attribute into an array.</span></span> <span data-ttu-id="0f2e5-128">Wenn beispielsweise zwei Instanzen von `DeveloperAttribute` auf Klassenebene derselben Klasse angewendet werden, kann die `GetAttribute`-Methode zum Anzeigen der in beiden Attributen gefundenen Informationen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-128">For example, if two instances of `DeveloperAttribute` are applied on the class level of the same class, the `GetAttribute` method can be modified to display the information found in both attributes.</span></span> <span data-ttu-id="0f2e5-129">Beim Anwenden mehrerer Attribute auf derselben Ebene müssen Sie beachten, dass das Attribut mit der **AllowMultiple**-Eigenschaft definiert wird, die in der <xref:System.AttributeUsageAttribute> auf **true** gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-129">Remember, to apply multiple attributes on the same level, the attribute must be defined with the **AllowMultiple** property set to **true** in the <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="0f2e5-130">Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit der **GetCustomAttributes**-Methode ein Array erstellen, das auf alle Instanzen von `DeveloperAttribute` in einer bestimmten Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-130">The following code example shows how to use the **GetCustomAttributes** method to create an array that references all instances of `DeveloperAttribute` in any given class.</span></span> <span data-ttu-id="0f2e5-131">Die Werte aller Attribute werden anschließend in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-131">The values of all attributes are then displayed to the console.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 <span data-ttu-id="0f2e5-132">Wenn keine Attribute gefunden werden, gibt dieser Code eine Warnung an den Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-132">If no attributes are found, this code alerts the user.</span></span> <span data-ttu-id="0f2e5-133">Andernfalls werden die in beiden Instanzen von `DeveloperAttribute` enthaltenen Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-133">Otherwise, the information contained in both instances of `DeveloperAttribute` is displayed.</span></span>  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>

## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a><span data-ttu-id="0f2e5-134">Abrufen mehrerer Instanzen eines Attributs auf unterschiedliche Bereiche angewendet</span><span class="sxs-lookup"><span data-stu-id="0f2e5-134">Retrieving Multiple Instances of an Attribute Applied to Different Scopes</span></span>  

 <span data-ttu-id="0f2e5-135">Die Methoden <xref:System.Attribute.GetCustomAttributes%2A> und <xref:System.Attribute.GetCustomAttribute%2A> durchsuchen nicht eine ganze Klasse, um Instanzen eines Attributs in dieser Klasse zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-135">The <xref:System.Attribute.GetCustomAttributes%2A> and <xref:System.Attribute.GetCustomAttribute%2A> methods do not search an entire class and return all instances of an attribute in that class.</span></span> <span data-ttu-id="0f2e5-136">Stattdessen suchen sie nur nach einer bestimmten Methode oder einem bestimmten Element zu einem gegebenen Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-136">Rather, they search only one specified method or member at a time.</span></span> <span data-ttu-id="0f2e5-137">Angenommen, Sie haben eine Klasse, für die das gleiche Attribut auf jedes Element angewendet wurde. Um nun die Werte in den Attributen abzurufen, die auf diese Elemente angewendet wurden, müssen Sie jede Methode oder jedes Element einzeln für **GetCustomAttributes** und  **GetCustomAttribute** bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-137">If you have a class with the same attribute applied to every member and you want to retrieve the values in all the attributes applied to those members, you must supply every method or member individually to **GetCustomAttributes** and **GetCustomAttribute**.</span></span>  
  
 <span data-ttu-id="0f2e5-138">Im folgenden Codebeispiel wird eine Klasse als Parameter akzeptiert und nach dem `DeveloperAttribute` (zuvor definiert) auf Klassenebene und in jeder einzelnen Methode dieser Klasse gesucht.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-138">The following code example takes a class as a parameter and searches for the `DeveloperAttribute` (defined previously) on the class level and on every individual method of that class.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 <span data-ttu-id="0f2e5-139">Wenn auf Methoden- oder Klassenebene keine Instanzen von `DeveloperAttribute` gefunden werden, benachrichtigt die `GetAttribute`-Methode den Benutzer, dass keine Attribute gefunden wurden, und zeigt den Namen der Methode oder Klasse an, die das Attribut nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-139">If no instances of the `DeveloperAttribute` are found on the method level or class level, the `GetAttribute` method notifies the user that no attributes were found and displays the name of the method or class that does not contain the attribute.</span></span> <span data-ttu-id="0f2e5-140">Wenn ein Attribut gefunden wird, werden die Felder `Name`, `Level` und `Reviewed` in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-140">If an attribute is found, the `Name`, `Level`, and `Reviewed` fields are displayed to the console.</span></span>  
  
 <span data-ttu-id="0f2e5-141">Sie können die Elemente der <xref:System.Type>-Klasse verwenden, um die einzelnen Methoden und Elemente der übergebenen Klasse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-141">You can use the members of the <xref:System.Type> class to get the individual methods and members in the passed class.</span></span> <span data-ttu-id="0f2e5-142">In diesem Beispiel wird zuerst das **Type**-Objekt abgefragt, um Attributinformationen für die Klassenebene abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-142">This example first queries the **Type** object to get attribute information for the class level.</span></span> <span data-ttu-id="0f2e5-143">Als Nächstes wird <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> verwendet, um Instanzen aller Methoden in einem Array von <xref:System.Reflection.MemberInfo?displayProperty=nameWithType>-Objekten zu platzieren, um Attributinformationen für die Methodenebene abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-143">Next, it uses <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> to place instances of all methods into an array of <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> objects to retrieve attribute information for the method level.</span></span> <span data-ttu-id="0f2e5-144">Sie können mithilfe der <xref:System.Type.GetProperties%2A?displayProperty=nameWithType>-Methode nach Attributen auf Eigenschaftenebene oder mithilfe von <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> nach Attributen auf Konstruktorebene suchen.</span><span class="sxs-lookup"><span data-stu-id="0f2e5-144">You can also use the <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> method to check for attributes on the property level or <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> to check for attributes on the constructor level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f2e5-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f2e5-145">See also</span></span>

- <xref:System.Type?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>
- [<span data-ttu-id="0f2e5-146">Attribute</span><span class="sxs-lookup"><span data-stu-id="0f2e5-146">Attributes</span></span>](index.md)
