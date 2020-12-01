---
title: Zugreifen auf benutzerdefinierte Attribute
description: Hier erfahren Sie, wie Sie in .NET auf benutzerdefinierte Attribute zugreifen. Nachdem Attribute Programmierelementen zugeordnet worden sind, können Sie die Reflexion verwenden, um deren Existenz und Werte abzufragen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- custom attributes, accessibility
- attributes [.NET Framework], accessing
- reflection, custom attributes
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
ms.openlocfilehash: d441bad7d4af3a88c4ede507d1bce7bdd1ab3215
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266817"
---
# <a name="accessing-custom-attributes"></a><span data-ttu-id="62a43-104">Zugreifen auf benutzerdefinierte Attribute</span><span class="sxs-lookup"><span data-stu-id="62a43-104">Accessing Custom Attributes</span></span>

<span data-ttu-id="62a43-105">Nachdem Attribute Programmierelementen zugeordnet worden sind, kann Reflektion benutzt werden, um deren Existenz und Werte abzufragen.</span><span class="sxs-lookup"><span data-stu-id="62a43-105">After attributes have been associated with program elements, reflection can be used to query their existence and values.</span></span> <span data-ttu-id="62a43-106">In der .NET Framework Version 1.0 und 1.1 werden benutzerdefinierte Attribute im Ausführungskontext untersucht.</span><span class="sxs-lookup"><span data-stu-id="62a43-106">In the .NET Framework version 1.0 and 1.1, custom attributes are examined in the execution context.</span></span> <span data-ttu-id="62a43-107">Die .NET Framework Version 2.0 stellt einen neuen Ladekontext bereit, den reflektionsbezogener Ladekontext, der zum Untersuchen von Code benutzt werden kann, der nicht für die Ausführung geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="62a43-107">The .NET Framework version 2.0 provides a new load context, the reflection-only context, which can be used to examine code that cannot be loaded for execution.</span></span>  
  
## <a name="the-reflection-only-context"></a><span data-ttu-id="62a43-108">Der reflektionsbezogene Ladekontext</span><span class="sxs-lookup"><span data-stu-id="62a43-108">The Reflection-Only Context</span></span>  

 <span data-ttu-id="62a43-109">Code, der in den reflektionsbezogenen Ladekontext geladen wird, kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="62a43-109">Code loaded into the reflection-only context cannot be executed.</span></span> <span data-ttu-id="62a43-110">Das bedeutet, dass Instanzen von benutzerdefinierten Attributen nicht erstellt werden können, da dies die Ausführung deren Konstruktoren erfordern würde.</span><span class="sxs-lookup"><span data-stu-id="62a43-110">This means that instances of custom attributes cannot be created, because that would require executing their constructors.</span></span> <span data-ttu-id="62a43-111">Um benutzerdefinierte Attribute im reflektionsbezogenen Kontext zu laden, verwenden Sie die <xref:System.Reflection.CustomAttributeData>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="62a43-111">To load and examine custom attributes in the reflection-only context, use the <xref:System.Reflection.CustomAttributeData> class.</span></span> <span data-ttu-id="62a43-112">Sie können Instanzen dieser Klasse abrufen, indem Sie die geeignete Überladung der statistischen <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="62a43-112">You can obtain instances of this class by using the appropriate overload of the static <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="62a43-113">Weitere Informationen finden Sie unter [How to: Laden von Assemblys in den reflexionsbezogenen Kontext](how-to-load-assemblies-into-the-reflection-only-context.md).</span><span class="sxs-lookup"><span data-stu-id="62a43-113">See [How to: Load Assemblies into the Reflection-Only Context](how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
## <a name="the-execution-context"></a><span data-ttu-id="62a43-114">Der Ausführungskontext</span><span class="sxs-lookup"><span data-stu-id="62a43-114">The Execution Context</span></span>  

 <span data-ttu-id="62a43-115">Die wichtigsten Reflektionsmethoden zum Abfragen von Attributen im Ausführungskontext sind <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> und <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="62a43-115">The main reflection methods to query attributes in the execution context are <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> and <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="62a43-116">Die Überprüfung der Erreichbarkeit eines benutzerdefinierten Attributs erfolgt unter Berücksichtigung der Assembly, in der es angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="62a43-116">The accessibility of a custom attribute is checked with respect to the assembly in which it is attached.</span></span> <span data-ttu-id="62a43-117">Dies entspricht der Überprüfung, ob eine Methode auf einem Typ in der Assembly, in der das benutzerdefinierte Attribut angefügt ist, den Konstruktor des benutzerdefinierten Attributs aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="62a43-117">This is equivalent to checking whether a method on a type in the assembly in which the custom attribute is attached can call the constructor of the custom attribute.</span></span>  
  
 <span data-ttu-id="62a43-118">Methoden wie <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> überprüfen die Sichtbarkeit und die Erreichbarkeit des Typarguments.</span><span class="sxs-lookup"><span data-stu-id="62a43-118">Methods such as <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> check the visibility and accessibility of the type argument.</span></span> <span data-ttu-id="62a43-119">Nur Code in der Assembly, der den benutzerdefinierten Typ enthält, kann ein benutzerdefiniertes Attribut dieses Typs mithilfe von **GetCustomAttributes** abrufen.</span><span class="sxs-lookup"><span data-stu-id="62a43-119">Only code in the assembly that contains the user-defined type can retrieve a custom attribute of that type using **GetCustomAttributes**.</span></span>  
  
 <span data-ttu-id="62a43-120">Das folgende C#-Beispiel ist ein typisches Entwurfsmuster eines benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="62a43-120">The following C# example is a typical custom attribute design pattern.</span></span> <span data-ttu-id="62a43-121">Es stellt das Runtimemodell der Reflektion des benutzerdefinierten Attributs dar.</span><span class="sxs-lookup"><span data-stu-id="62a43-121">It illustrates the runtime custom attribute reflection model.</span></span>  
  
```csharp
System.DLL  
public class DescriptionAttribute : Attribute  
{  
}  
  
System.Web.DLL  
internal class MyDescriptionAttribute : DescriptionAttribute  
{  
}  
  
public class LocalizationExtenderProvider  
{  
    [MyDescriptionAttribute(...)]  
    public CultureInfo GetLanguage(...)  
    {  
    }  
}  
```  
  
 <span data-ttu-id="62a43-122">Wenn die Runtime versucht, die benutzerdefinierten Attribute für den öffentlichen benutzerdefinierten Attributtyp <xref:System.ComponentModel.DescriptionAttribute> abzurufen, der an die **GetLanguage**-Methode angefügt ist, werden folgende Aktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="62a43-122">If the runtime is attempting to retrieve the custom attributes for the public custom attribute type <xref:System.ComponentModel.DescriptionAttribute> attached to the **GetLanguage** method, it performs the following actions:</span></span>  
  
1. <span data-ttu-id="62a43-123">Die Runtime überprüft, dass das Typargument **DescriptionAttribute** für **Type.GetCustomAttributes** (Typ *type*) öffentlich und somit sichtbar und erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="62a43-123">The runtime checks that the type argument **DescriptionAttribute** to **Type.GetCustomAttributes**(Type *type*) is public, and therefore is visible and accessible.</span></span>  
  
2. <span data-ttu-id="62a43-124">Die Runtime überprüft, dass der benutzerdefinierte Typ **MyDescriptionAttribute**, der von **DescriptionAttribute** abgeleitet wurde, in der Assembly **System.Web.DLL** sichtbar und erreichbar ist, wo er an die Methode **GetLanguage**() angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="62a43-124">The runtime checks that the user-defined type **MyDescriptionAttribute** that is derived from **DescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly, where it is attached to the method **GetLanguage**().</span></span>  
  
3. <span data-ttu-id="62a43-125">Die Runtime überprüft, dass der Konstruktor von **MyDescriptionAttribute** innerhalb der **System.Web.DLL**-Assembly sichtbar und erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="62a43-125">The runtime checks that the constructor of **MyDescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly.</span></span>  
  
4. <span data-ttu-id="62a43-126">Die Runtime ruft den Konstruktor von **MyDescriptionAttribute** mit den benutzerdefinierten Attributparametern auf und gibt dem Aufrufer das neue Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="62a43-126">The runtime calls the constructor of **MyDescriptionAttribute** with the custom attribute parameters and returns the new object to the caller.</span></span>  
  
 <span data-ttu-id="62a43-127">Dem Reflektionsmodell des benutzerdefinierten Attributs könnten Instanzen von benutzerdefinierten Typen außerhalb der Assembly fehlen, in der der Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="62a43-127">The custom attribute reflection model could leak instances of user-defined types outside the assembly in which the type is defined.</span></span> <span data-ttu-id="62a43-128">Hier besteht kein Unterschied zu den Membern in der Runtimesystembibliothek, die Instanzen benutzerdefinierter Typen zurückgeben, z.B. <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>, die ein Array von **RuntimeMethodInfo**-Objekten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="62a43-128">This is no different from the members in the runtime system library that return instances of user-defined types, such as <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> returning an array of **RuntimeMethodInfo** objects.</span></span> <span data-ttu-id="62a43-129">Um zu verhindern, dass ein Client Informationen über einen benutzerdefinierten Typ eines benutzerdefinierten Attributs ermittelt, definieren Sie, dass die Member des Typen nicht öffentlich sein sollen.</span><span class="sxs-lookup"><span data-stu-id="62a43-129">To prevent a client from discovering information about a user-defined custom attribute type, define the type's members to be nonpublic.</span></span>  
  
 <span data-ttu-id="62a43-130">Das folgende Beispiel zeigt die einfachste Möglichkeit, Reflektion zu verwenden, um Zugriff auf benutzerdefinierte Attribute zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="62a43-130">The following example demonstrates the basic way of using reflection to get access to custom attributes.</span></span>  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="62a43-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62a43-131">See also</span></span>

- <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType>
- <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>
- [<span data-ttu-id="62a43-132">Anzeigen von Typinformationen</span><span class="sxs-lookup"><span data-stu-id="62a43-132">Viewing Type Information</span></span>](viewing-type-information.md)
- [<span data-ttu-id="62a43-133">Security Considerations for Reflection (Sicherheitsüberlegungen für die Reflektion)</span><span class="sxs-lookup"><span data-stu-id="62a43-133">Security Considerations for Reflection</span></span>](security-considerations-for-reflection.md)
