---
title: Zugreifen auf benutzerdefinierte Attribute
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- custom attributes, accessibility
- attributes [.NET Framework], accessing
- reflection, custom attributes
ms.assetid: 1d8e3398-00d8-47d5-a084-214f9859d3d7
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8ac4bec06f2d5c7f8876c8e4e18a9d5c59f094fb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="accessing-custom-attributes"></a><span data-ttu-id="898b9-102">Zugreifen auf benutzerdefinierte Attribute</span><span class="sxs-lookup"><span data-stu-id="898b9-102">Accessing Custom Attributes</span></span>
<span data-ttu-id="898b9-103">Nachdem Attribute Programmierelementen zugeordnet worden sind, kann Reflektion benutzt werden, um deren Existenz und Werte abzufragen.</span><span class="sxs-lookup"><span data-stu-id="898b9-103">After attributes have been associated with program elements, reflection can be used to query their existence and values.</span></span> <span data-ttu-id="898b9-104">In der .NET Framework Version 1.0 und 1.1 werden benutzerdefinierte Attribute im Ausführungskontext untersucht.</span><span class="sxs-lookup"><span data-stu-id="898b9-104">In the .NET Framework version 1.0 and 1.1, custom attributes are examined in the execution context.</span></span> <span data-ttu-id="898b9-105">Die .NET Framework Version 2.0 stellt einen neuen Ladekontext bereit, den reflektionsbezogener Ladekontext, der zum Untersuchen von Code benutzt werden kann, der nicht für die Ausführung geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="898b9-105">The .NET Framework version 2.0 provides a new load context, the reflection-only context, which can be used to examine code that cannot be loaded for execution.</span></span>  
  
## <a name="the-reflection-only-context"></a><span data-ttu-id="898b9-106">Der reflektionsbezogene Ladekontext</span><span class="sxs-lookup"><span data-stu-id="898b9-106">The Reflection-Only Context</span></span>  
 <span data-ttu-id="898b9-107">Code, der in den reflektionsbezogenen Ladekontext geladen wird, kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="898b9-107">Code loaded into the reflection-only context cannot be executed.</span></span> <span data-ttu-id="898b9-108">Das bedeutet, dass Instanzen von benutzerdefinierten Attributen nicht erstellt werden können, da dies die Ausführung deren Konstruktoren erfordern würde.</span><span class="sxs-lookup"><span data-stu-id="898b9-108">This means that instances of custom attributes cannot be created, because that would require executing their constructors.</span></span> <span data-ttu-id="898b9-109">Um benutzerdefinierte Attribute im reflektionsbezogenen Kontext zu laden, verwenden Sie die <xref:System.Reflection.CustomAttributeData>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="898b9-109">To load and examine custom attributes in the reflection-only context, use the <xref:System.Reflection.CustomAttributeData> class.</span></span> <span data-ttu-id="898b9-110">Sie können Instanzen dieser Klasse abrufen, indem Sie die geeignete Überladung der statistischen <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType>-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="898b9-110">You can obtain instances of this class by using the appropriate overload of the static <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="898b9-111">Weitere Informationen finden Sie unter [How to: Load Assemblies into the Reflection-Only Context (Vorgehensweise: Laden von Assemblys in den reflektionsbezogenen Kontext)](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span><span class="sxs-lookup"><span data-stu-id="898b9-111">See [How to: Load Assemblies into the Reflection-Only Context](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
## <a name="the-execution-context"></a><span data-ttu-id="898b9-112">Der Ausführungskontext</span><span class="sxs-lookup"><span data-stu-id="898b9-112">The Execution Context</span></span>  
 <span data-ttu-id="898b9-113">Die wichtigsten Reflektionsmethoden zum Abfragen von Attributen im Ausführungskontext sind <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> und <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="898b9-113">The main reflection methods to query attributes in the execution context are <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType> and <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="898b9-114">Die Überprüfung der Erreichbarkeit eines benutzerdefinierten Attributs erfolgt unter Berücksichtigung der Assembly, in der es angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="898b9-114">The accessibility of a custom attribute is checked with respect to the assembly in which it is attached.</span></span> <span data-ttu-id="898b9-115">Dies entspricht der Überprüfung, ob eine Methode auf einem Typ in der Assembly, in der das benutzerdefinierte Attribut angefügt ist, den Konstruktor des benutzerdefinierten Attributs aufrufen kann.</span><span class="sxs-lookup"><span data-stu-id="898b9-115">This is equivalent to checking whether a method on a type in the assembly in which the custom attribute is attached can call the constructor of the custom attribute.</span></span>  
  
 <span data-ttu-id="898b9-116">Methoden wie <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> überprüfen die Sichtbarkeit und die Erreichbarkeit des Typarguments.</span><span class="sxs-lookup"><span data-stu-id="898b9-116">Methods such as <xref:System.Reflection.Assembly.GetCustomAttributes%28System.Boolean%29?displayProperty=nameWithType> check the visibility and accessibility of the type argument.</span></span> <span data-ttu-id="898b9-117">Nur Code in der Assembly, der den benutzerdefinierten Typ enthält, kann ein benutzerdefiniertes Attribut dieses Typs mithilfe von **GetCustomAttributes** abrufen.</span><span class="sxs-lookup"><span data-stu-id="898b9-117">Only code in the assembly that contains the user-defined type can retrieve a custom attribute of that type using **GetCustomAttributes**.</span></span>  
  
 <span data-ttu-id="898b9-118">Das folgende C#-Beispiel ist ein typisches Entwurfsmuster eines benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="898b9-118">The following C# example is a typical custom attribute design pattern.</span></span> <span data-ttu-id="898b9-119">Es stellt das Runtimemodell der Reflektion des benutzerdefinierten Attributs dar.</span><span class="sxs-lookup"><span data-stu-id="898b9-119">It illustrates the runtime custom attribute reflection model.</span></span>  
  
```  
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
  
 <span data-ttu-id="898b9-120">Wenn die Runtime versucht, die benutzerdefinierten Attribute für den öffentlichen benutzerdefinierten Attributtyp <xref:System.ComponentModel.DescriptionAttribute> abzurufen, der an die **GetLanguage**-Methode angefügt ist, werden folgende Aktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="898b9-120">If the runtime is attempting to retrieve the custom attributes for the public custom attribute type <xref:System.ComponentModel.DescriptionAttribute> attached to the **GetLanguage** method, it performs the following actions:</span></span>  
  
1.  <span data-ttu-id="898b9-121">Die Runtime überprüft, dass das Typargument **DescriptionAttribute** für **Type.GetCustomAttributes** (Typ *type*) öffentlich und somit sichtbar und erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="898b9-121">The runtime checks that the type argument **DescriptionAttribute** to **Type.GetCustomAttributes**(Type *type*) is public, and therefore is visible and accessible.</span></span>  
  
2.  <span data-ttu-id="898b9-122">Die Runtime überprüft, dass der benutzerdefinierte Typ **MyDescriptionAttribute**, der von **DescriptionAttribute** abgeleitet wurde, in der Assembly **System.Web.DLL** sichtbar und erreichbar ist, wo er an die Methode **GetLanguage**() angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="898b9-122">The runtime checks that the user-defined type **MyDescriptionAttribute** that is derived from **DescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly, where it is attached to the method **GetLanguage**().</span></span>  
  
3.  <span data-ttu-id="898b9-123">Die Runtime überprüft, dass der Konstruktor von **MyDescriptionAttribute** innerhalb der **System.Web.DLL**-Assembly sichtbar und erreichbar ist.</span><span class="sxs-lookup"><span data-stu-id="898b9-123">The runtime checks that the constructor of **MyDescriptionAttribute** is visible and accessible within the **System.Web.DLL** assembly.</span></span>  
  
4.  <span data-ttu-id="898b9-124">Die Runtime ruft den Konstruktor von **MyDescriptionAttribute** mit den benutzerdefinierten Attributparametern auf und gibt dem Aufrufer das neue Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="898b9-124">The runtime calls the constructor of **MyDescriptionAttribute** with the custom attribute parameters and returns the new object to the caller.</span></span>  
  
 <span data-ttu-id="898b9-125">Dem Reflektionsmodell des benutzerdefinierten Attributs könnten Instanzen von benutzerdefinierten Typen außerhalb der Assembly fehlen, in der der Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="898b9-125">The custom attribute reflection model could leak instances of user-defined types outside the assembly in which the type is defined.</span></span> <span data-ttu-id="898b9-126">Hier besteht kein Unterschied zu den Membern in der Runtimesystembibliothek, die Instanzen benutzerdefinierter Typen zurückgeben, z.B. <xref:System.Type.GetMethods%2A?displayProperty=nameWithType>, die ein Array von **RuntimeMethodInfo**-Objekten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="898b9-126">This is no different from the members in the runtime system library that return instances of user-defined types, such as <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> returning an array of **RuntimeMethodInfo** objects.</span></span> <span data-ttu-id="898b9-127">Um zu verhindern, dass ein Client Informationen über einen benutzerdefinierten Typ eines benutzerdefinierten Attributs ermittelt, definieren Sie, dass die Member des Typen nicht öffentlich sein sollen.</span><span class="sxs-lookup"><span data-stu-id="898b9-127">To prevent a client from discovering information about a user-defined custom attribute type, define the type's members to be nonpublic.</span></span>  
  
 <span data-ttu-id="898b9-128">Das folgende Beispiel zeigt die einfachste Möglichkeit, Reflektion zu verwenden, um Zugriff auf benutzerdefinierte Attribute zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="898b9-128">The following example demonstrates the basic way of using reflection to get access to custom attributes.</span></span>  
  
 [!code-cpp[CustomAttributeData#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source2.cpp#2)]
 [!code-csharp[CustomAttributeData#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source2.cs#2)]
 [!code-vb[CustomAttributeData#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="898b9-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="898b9-129">See Also</span></span>  
 <xref:System.Reflection.MemberInfo.GetCustomAttributes%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="898b9-130">Anzeigen von Typinformationen</span><span class="sxs-lookup"><span data-stu-id="898b9-130">Viewing Type Information</span></span>](../../../docs/framework/reflection-and-codedom/viewing-type-information.md)  
 [<span data-ttu-id="898b9-131">Security Considerations for Reflection (Sicherheitsüberlegungen für die Reflektion)</span><span class="sxs-lookup"><span data-stu-id="898b9-131">Security Considerations for Reflection</span></span>](../../../docs/framework/reflection-and-codedom/security-considerations-for-reflection.md)
