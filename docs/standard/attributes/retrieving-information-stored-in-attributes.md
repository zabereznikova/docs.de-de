---
title: Abrufen von Informationen aus Attributen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d3fd9a5a49d65b37d2cdb5107e9c516a6df5847
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-information-stored-in-attributes"></a><span data-ttu-id="ba476-102">Abrufen von Informationen aus Attributen</span><span class="sxs-lookup"><span data-stu-id="ba476-102">Retrieving Information Stored in Attributes</span></span>
<span data-ttu-id="ba476-103">Das Abrufen eines benutzerdefinierten Attributs ist ein einfacher Vorgang.</span><span class="sxs-lookup"><span data-stu-id="ba476-103">Retrieving a custom attribute is a simple process.</span></span> <span data-ttu-id="ba476-104">Deklarieren Sie zuerst eine Instanz des Attributs ein, die Sie abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="ba476-104">First, declare an instance of the attribute you want to retrieve.</span></span> <span data-ttu-id="ba476-105">Verwenden Sie dann die <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> Methode, um das neue Attribut auf den Wert des Attributs initialisieren Sie abrufen möchten.</span><span class="sxs-lookup"><span data-stu-id="ba476-105">Then, use the <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> method to initialize the new attribute to the value of the attribute you want to retrieve.</span></span> <span data-ttu-id="ba476-106">Sobald das neue Attribut initialisiert wurde, verwenden Sie einfach die Eigenschaften zum Abrufen der Werte an.</span><span class="sxs-lookup"><span data-stu-id="ba476-106">Once the new attribute is initialized, you simply use its properties to get the values.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ba476-107">In diesem Thema wird beschrieben, wie zum Abrufen der Attribute für Code, der in den Ausführungskontext geladen wird.</span><span class="sxs-lookup"><span data-stu-id="ba476-107">This topic describes how to retrieve attributes for code loaded into the execution context.</span></span> <span data-ttu-id="ba476-108">Attribute für Code in den ReflectionOnly Kontext geladen abzurufen, verwenden Sie die <xref:System.Reflection.CustomAttributeData> Klasse, entsprechend [wie: Laden von Assemblys in den Reflection-Kontext](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span><span class="sxs-lookup"><span data-stu-id="ba476-108">To retrieve attributes for code loaded into the reflection-only context, you must use the <xref:System.Reflection.CustomAttributeData> class, as shown in [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
 <span data-ttu-id="ba476-109">In diesem Abschnitt werden die folgenden Möglichkeiten zum Abrufen von Attribute beschrieben:</span><span class="sxs-lookup"><span data-stu-id="ba476-109">This section describes the following ways to retrieve attributes:</span></span>  
  
-   [<span data-ttu-id="ba476-110">Eine einzelne Instanz eines Attributs abrufen</span><span class="sxs-lookup"><span data-stu-id="ba476-110">Retrieving a single instance of an attribute</span></span>](#cpconretrievingsingleinstanceofattribute)  
  
-   [<span data-ttu-id="ba476-111">Abrufen mehrerer Instanzen eines Attributs in demselben Gültigkeitsbereich angewendet</span><span class="sxs-lookup"><span data-stu-id="ba476-111">Retrieving multiple instances of an attribute applied to the same scope</span></span>](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [<span data-ttu-id="ba476-112">Abrufen mehrerer Instanzen eines Attributs auf unterschiedliche Bereiche angewendet</span><span class="sxs-lookup"><span data-stu-id="ba476-112">Retrieving multiple instances of an attribute applied to different scopes</span></span>](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## <a name="retrieving-a-single-instance-of-an-attribute"></a><span data-ttu-id="ba476-113">Eine einzelne Instanz eines Attributs abrufen</span><span class="sxs-lookup"><span data-stu-id="ba476-113">Retrieving a Single Instance of an Attribute</span></span>  
 <span data-ttu-id="ba476-114">Im folgenden Beispiel die `DeveloperAttribute` (im vorherigen Abschnitt beschrieben) wird angewendet, um die `MainApp` Klasse auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="ba476-114">In the following example, the `DeveloperAttribute` (described in the previous section) is applied to the `MainApp` class on the class level.</span></span> <span data-ttu-id="ba476-115">Die `GetAttribute` -Methode verwendet **wurde** zum Abrufen der Werte, die in gespeicherten `DeveloperAttribute` auf Klassenebene, bevor sie auf der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba476-115">The `GetAttribute` method uses **GetCustomAttribute** to retrieve the values stored in `DeveloperAttribute` on the class level before displaying them to the console.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 <span data-ttu-id="ba476-116">Dieses Programm zeigt folgenden Text bei der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="ba476-116">This program displays the following text when executed.</span></span>  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 <span data-ttu-id="ba476-117">Wenn das Attribut nicht gefunden wird, die **wurde** -Methode initialisiert `MyAttribute` mit einem Nullwert.</span><span class="sxs-lookup"><span data-stu-id="ba476-117">If the attribute is not found, the **GetCustomAttribute** method initializes `MyAttribute` to a null value.</span></span> <span data-ttu-id="ba476-118">In diesem Beispiel prüft `MyAttribute` für eine solche Instanz und der Benutzer benachrichtigt, wenn kein Attribut gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="ba476-118">This example checks `MyAttribute` for such an instance and notifies the user if no attribute is found.</span></span> <span data-ttu-id="ba476-119">Wenn die `DeveloperAttribute` befindet sich nicht im Gültigkeitsbereich Klasse die folgende Meldung in der Konsole anzeigt.</span><span class="sxs-lookup"><span data-stu-id="ba476-119">If the `DeveloperAttribute` is not found in the class scope, the following message displays to the console.</span></span>  
  
```  
The attribute was not found.   
```  
  
 <span data-ttu-id="ba476-120">In diesem Beispiel wird davon ausgegangen, dass die Attributdefinition im aktuellen Namespace ist.</span><span class="sxs-lookup"><span data-stu-id="ba476-120">This example assumes that the attribute definition is in the current namespace.</span></span> <span data-ttu-id="ba476-121">Denken Sie daran, um den Namespace zu importieren, in dem sich die Attributdefinition befindet, ist er nicht im aktuellen Namespace.</span><span class="sxs-lookup"><span data-stu-id="ba476-121">Remember to import the namespace in which the attribute definition resides if it is not in the current namespace.</span></span>  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a><span data-ttu-id="ba476-122">Abrufen mehrerer Instanzen eines Attributs in demselben Gültigkeitsbereich angewendet</span><span class="sxs-lookup"><span data-stu-id="ba476-122">Retrieving Multiple Instances of an Attribute Applied to the Same Scope</span></span>  
 <span data-ttu-id="ba476-123">Im vorherigen Beispiel die Klasse, um zu überprüfen und bestimmte zu suchenden Attributs zu übergeben sind <xref:System.Attribute.GetCustomAttribute%2A>.</span><span class="sxs-lookup"><span data-stu-id="ba476-123">In the previous example, the class to inspect and the specific attribute to find are passed to <xref:System.Attribute.GetCustomAttribute%2A>.</span></span> <span data-ttu-id="ba476-124">Dieser Code funktioniert gut, wenn nur eine Instanz eines Attributs auf Klassenebene angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="ba476-124">That code works well if only one instance of an attribute is applied on the class level.</span></span> <span data-ttu-id="ba476-125">Jedoch, wenn mehrere Instanzen eines Attributs auf der Klassenebene des gleichen angewendet werden die **wurde** Methode nicht alle Informationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ba476-125">However, if multiple instances of an attribute are applied on the same class level, the **GetCustomAttribute** method does not retrieve all the information.</span></span> <span data-ttu-id="ba476-126">In Fällen, in dem mehrere Instanzen des gleichen Attributs in demselben Gültigkeitsbereich angewendet werden, können Sie <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> alle Instanzen eines Attributs in einem Array platzieren.</span><span class="sxs-lookup"><span data-stu-id="ba476-126">In cases where multiple instances of the same attribute are applied to the same scope, you can use <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> to place all instances of an attribute into an array.</span></span> <span data-ttu-id="ba476-127">Angenommen, zwei Instanzen von `DeveloperAttribute` auf Klassenebene derselben Klasse angewendet werden die `GetAttribute` Methode zum Anzeigen der Informationen in beide Attribute geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="ba476-127">For example, if two instances of `DeveloperAttribute` are applied on the class level of the same class, the `GetAttribute` method can be modified to display the information found in both attributes.</span></span> <span data-ttu-id="ba476-128">Beachten Sie, dass mehrere Attribute auf derselben Ebene anzuwenden, muss das Attribut definiert werden, mit der **AllowMultiple** -Eigenschaftensatz auf **"true"** in der <xref:System.AttributeUsageAttribute>.</span><span class="sxs-lookup"><span data-stu-id="ba476-128">Remember, to apply multiple attributes on the same level, the attribute must be defined with the **AllowMultiple** property set to **true** in the <xref:System.AttributeUsageAttribute>.</span></span>  
  
 <span data-ttu-id="ba476-129">Im folgenden Codebeispiel wird veranschaulicht, wie die **GetCustomAttributes** Methode, um ein Array zu erstellen, die alle Instanzen von verweist `DeveloperAttribute` in einer angegebenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="ba476-129">The following code example shows how to use the **GetCustomAttributes** method to create an array that references all instances of `DeveloperAttribute` in any given class.</span></span> <span data-ttu-id="ba476-130">Anschließend werden die Werte aller Attribute in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba476-130">The values of all attributes are then displayed to the console.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 <span data-ttu-id="ba476-131">Wenn keine Attribute gefunden werden, weist dieser Code den Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="ba476-131">If no attributes are found, this code alerts the user.</span></span> <span data-ttu-id="ba476-132">Andernfalls enthält die Informationen in beiden Instanzen des `DeveloperAttribute` wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba476-132">Otherwise, the information contained in both instances of `DeveloperAttribute` is displayed.</span></span>  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a><span data-ttu-id="ba476-133">Abrufen mehrerer Instanzen eines Attributs auf unterschiedliche Bereiche angewendet</span><span class="sxs-lookup"><span data-stu-id="ba476-133">Retrieving Multiple Instances of an Attribute Applied to Different Scopes</span></span>  
 <span data-ttu-id="ba476-134">Die <xref:System.Attribute.GetCustomAttributes%2A> und <xref:System.Attribute.GetCustomAttribute%2A> Methoden nicht suchen eine gesamte Objektklasse und alle Instanzen eines Attributs in dieser Klasse zurück.</span><span class="sxs-lookup"><span data-stu-id="ba476-134">The <xref:System.Attribute.GetCustomAttributes%2A> and <xref:System.Attribute.GetCustomAttribute%2A> methods do not search an entire class and return all instances of an attribute in that class.</span></span> <span data-ttu-id="ba476-135">Suchen sie stattdessen nur eine angegebene Methode oder ein Element zu einem Zeitpunkt aus.</span><span class="sxs-lookup"><span data-stu-id="ba476-135">Rather, they search only one specified method or member at a time.</span></span> <span data-ttu-id="ba476-136">Wenn Sie eine Klasse mit dem gleichen Attribut auf jedes Element angewendet haben, und zum Abrufen der Werte in den Attributen, die auf diesen Member angewendet werden sollen, Sie müssen angeben jeder Methode oder der Member einzeln an **GetCustomAttributes** und  **Wurde**.</span><span class="sxs-lookup"><span data-stu-id="ba476-136">If you have a class with the same attribute applied to every member and you want to retrieve the values in all the attributes applied to those members, you must supply every method or member individually to **GetCustomAttributes** and **GetCustomAttribute**.</span></span>  
  
 <span data-ttu-id="ba476-137">Im folgenden Codebeispiel wird eine Klasse als Parameter akzeptiert und sucht nach der `DeveloperAttribute` (definierten zuvor) auf Klassenebene und in jeder einzelnen Methode dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="ba476-137">The following code example takes a class as a parameter and searches for the `DeveloperAttribute` (defined previously) on the class level and on every individual method of that class.</span></span>  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 <span data-ttu-id="ba476-138">Wenn keine Instanzen von der `DeveloperAttribute` befinden sich auf der Methoden- oder Klassenebene, die `GetAttribute` Methode benachrichtigt den Benutzer, die keine Attribute gefunden wurden, und zeigt den Namen der Methode oder Klasse, die nicht das Attribut enthält.</span><span class="sxs-lookup"><span data-stu-id="ba476-138">If no instances of the `DeveloperAttribute` are found on the method level or class level, the `GetAttribute` method notifies the user that no attributes were found and displays the name of the method or class that does not contain the attribute.</span></span> <span data-ttu-id="ba476-139">Wenn ein Attribut gefunden wird, die `Name`, `Level`, und `Reviewed` Felder werden in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba476-139">If an attribute is found, the `Name`, `Level`, and `Reviewed` fields are displayed to the console.</span></span>  
  
 <span data-ttu-id="ba476-140">Können Sie die Mitglieder der <xref:System.Type> Klasse, um die einzelnen Methoden und Elemente in der übergebenen Klasse abrufen.</span><span class="sxs-lookup"><span data-stu-id="ba476-140">You can use the members of the <xref:System.Type> class to get the individual methods and members in the passed class.</span></span> <span data-ttu-id="ba476-141">Abfragen in diesem Beispiel wird zuerst die **Typ** Objekt, Informationen über Bildattribute für Klassenebene abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ba476-141">This example first queries the **Type** object to get attribute information for the class level.</span></span> <span data-ttu-id="ba476-142">Als Nächstes verwendet <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> Instanzen aller Methoden in ein Array von <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> Objekte zum Abrufen von Informationen über Bildattribute für Methodenebene.</span><span class="sxs-lookup"><span data-stu-id="ba476-142">Next, it uses <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> to place instances of all methods into an array of <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> objects to retrieve attribute information for the method level.</span></span> <span data-ttu-id="ba476-143">Sie können auch die <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> Methode, um die Prüfung der Attribute auf der Eigenschaftenebene oder <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> zu suchende Attribute auf der Konstruktorebene.</span><span class="sxs-lookup"><span data-stu-id="ba476-143">You can also use the <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> method to check for attributes on the property level or <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> to check for attributes on the constructor level.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba476-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ba476-144">See Also</span></span>  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="ba476-145">Attribute</span><span class="sxs-lookup"><span data-stu-id="ba476-145">Attributes</span></span>](../../../docs/standard/attributes/index.md)
