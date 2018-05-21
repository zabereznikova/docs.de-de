---
title: Anzeigen von Typinformationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- types, viewing type information
- Type object
- viewing type information
- reflection, viewing type information
ms.assetid: 7e7303a9-4064-4738-b4e7-b75974ed70d2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc957b345c1e66059551508f73e37e0f6d69f6cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="viewing-type-information"></a><span data-ttu-id="f0d3b-102">Anzeigen von Typinformationen</span><span class="sxs-lookup"><span data-stu-id="f0d3b-102">Viewing Type Information</span></span>
<span data-ttu-id="f0d3b-103">Die Klasse <xref:System.Type?displayProperty=nameWithType> ist für die Reflektion wesentlich.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-103">The <xref:System.Type?displayProperty=nameWithType> class is central to reflection.</span></span> <span data-ttu-id="f0d3b-104">Die Common Language Runtime (CLR) erstellt **Type** für einen geladenen Typ, wenn die Reflektion diesen anfordert.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-104">The common language runtime creates the **Type** for a loaded type when reflection requests it.</span></span> <span data-ttu-id="f0d3b-105">Sie können die Methoden, Felder, Eigenschaften und geschachtelten Klassen eines **Type**-Objekts dazu verwenden, alle Informationen zu diesem Typ zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-105">You can use a **Type** object's methods, fields, properties, and nested classes to find out everything about that type.</span></span>  
  
 <span data-ttu-id="f0d3b-106">Verwenden Sie <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> und <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>, um **Type**-Objekte von Assemblys abzurufen, die nicht geladen wurden, und übergeben Sie den Namen des Typs oder der Typen, die Sie möchten.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-106">Use <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType> or <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> to obtain **Type** objects from assemblies that have not been loaded, passing in the name of the type or types you want.</span></span> <span data-ttu-id="f0d3b-107">Verwenden Sie <xref:System.Type.GetType%2A?displayProperty=nameWithType>, um **Type**-Objekte von Assemblys abzurufen, die bereits geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-107">Use <xref:System.Type.GetType%2A?displayProperty=nameWithType> to get the **Type** objects from an assembly that is already loaded.</span></span> <span data-ttu-id="f0d3b-108">Verwenden Sie <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> und <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType>, um **Type**-Modulobjekte zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-108">Use <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType> and <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType> to obtain module **Type** objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0d3b-109">Weitere Informationen zum Untersuchen und Manipulieren von generischen Typen und Methoden finden Sie in den Artikeln [Reflection and Generic Types (Reflektion und generische Typen)](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md) und [How to: Examine and Instantiate Generic Types with Reflection (Vorgehensweise: Untersuchen und Instanziieren von generischen Typen mit Reflektion)](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md).</span><span class="sxs-lookup"><span data-stu-id="f0d3b-109">If you want to examine and manipulate generic types and methods, please see the additional information provided in [Reflection and Generic Types](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md) and [How to: Examine and Instantiate Generic Types with Reflection](../../../docs/framework/reflection-and-codedom/how-to-examine-and-instantiate-generic-types-with-reflection.md).</span></span>  
  
 <span data-ttu-id="f0d3b-110">In folgendem Beispiel wird die Syntax veranschaulicht, die für das Abrufen des <xref:System.Reflection.Assembly>-Objekts und -Moduls für eine Assembly erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-110">The following example shows the syntax necessary to get the <xref:System.Reflection.Assembly> object and module for an assembly.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#6)]
 [!code-csharp[Conceptual.Types.ViewInfo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#6)]
 [!code-vb[Conceptual.Types.ViewInfo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#6)]  
  
 <span data-ttu-id="f0d3b-111">In folgendem Beispiel wird das Abrufen eines **Type**-Objekts von einer geladenen Assembly veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-111">The following example demonstrates getting **Type** objects from a loaded assembly.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source5.cpp#7)]
 [!code-csharp[Conceptual.Types.ViewInfo#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source5.cs#7)]
 [!code-vb[Conceptual.Types.ViewInfo#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source5.vb#7)]  
  
 <span data-ttu-id="f0d3b-112">Sobald Sie ein **Type**-Objekt abgerufen haben, gibt es viele Möglichkeiten, wie Sie Informationen zu den Membern des Typs erhalten können.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-112">Once you obtain a **Type**, there are many ways you can discover information about the members of that type.</span></span> <span data-ttu-id="f0d3b-113">Sie können z.B. alle Informationen zu den Membern des Typs erhalten, indem Sie die Methode <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> aufrufen, die ein Array von <xref:System.Reflection.MemberInfo>-Objekten abruft, die jeden Member des aktuellen Typs beschreiben.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-113">For example, you can find out about all the type's members by calling the <xref:System.Type.GetMembers%2A?displayProperty=nameWithType> method, which obtains an array of <xref:System.Reflection.MemberInfo> objects describing each of the members of the current type.</span></span>  
  
 <span data-ttu-id="f0d3b-114">Außerdem können Sie Methoden auf die **Type**-Klasse anwenden, um Informationen zu einem oder mehreren Konstruktoren, Methoden, Ereignissen, Felder oder Eigenschaften abzurufen, die Sie durch Namen angeben.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-114">You can also use methods on the **Type** class to retrieve information about one or more constructors, methods, events, fields, or properties that you specify by name.</span></span> <span data-ttu-id="f0d3b-115"><xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> kapselt z.B. einen spezifischen Konstruktor für die aktuelle Klasse.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-115">For example, <xref:System.Type.GetConstructor%2A?displayProperty=nameWithType> encapsulates a specific constructor of the current class.</span></span>  
  
 <span data-ttu-id="f0d3b-116">Wenn Sie ein **Type**-Objekt haben, können Sie die <xref:System.Type.Module%2A?displayProperty=nameWithType>-Eigenschaft verwenden, um ein Objekt zu erhalten, das das Modul kapselt, das den Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-116">If you have a **Type**, you can use the <xref:System.Type.Module%2A?displayProperty=nameWithType> property to obtain an object that encapsulates the module containing that type.</span></span> <span data-ttu-id="f0d3b-117">Verwenden Sie die <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType>-Eigenschaft, um ein Objekt zu finden, das die Assembly kapselt, die das Modul enthält.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-117">Use the <xref:System.Reflection.Module.Assembly%2A?displayProperty=nameWithType> property to locate an object that encapsulates the assembly containing the module.</span></span> <span data-ttu-id="f0d3b-118">Sie können die Assembly, die den Typ kapselt, direkt mithilfe der <xref:System.Type.Assembly%2A?displayProperty=nameWithType>-Eigenschaft erhalten.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-118">You can obtain the assembly that encapsulates the type directly by using the <xref:System.Type.Assembly%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="systemtype-and-constructorinfo"></a><span data-ttu-id="f0d3b-119">System.Type und ConstructorInfo</span><span class="sxs-lookup"><span data-stu-id="f0d3b-119">System.Type and ConstructorInfo</span></span>  
 <span data-ttu-id="f0d3b-120">In folgendem Beispiel wird veranschaulicht, wie Sie die Konstruktoren für eine Klasse auflisten können, in diesem Fall die Klasse <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-120">The following example shows how to list the constructors for a class, in this case, the <xref:System.String> class.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.Types.ViewInfo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source1.cs#1)]
 [!code-vb[Conceptual.Types.ViewInfo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source1.vb#1)]  
  
## <a name="memberinfo-methodinfo-fieldinfo-and-propertyinfo"></a><span data-ttu-id="f0d3b-121">MemberInfo, MethodInfo, FieldInfo und PropertyInfo</span><span class="sxs-lookup"><span data-stu-id="f0d3b-121">MemberInfo, MethodInfo, FieldInfo, and PropertyInfo</span></span>  
 <span data-ttu-id="f0d3b-122">Rufen Informationen zu den Methoden, Eigenschaften, Ereignissen und Feldern eines Typs mithilfe der Objekte <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo> und <xref:System.Reflection.PropertyInfo> ab.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-122">Obtain information about the type's methods, properties, events, and fields using <xref:System.Reflection.MemberInfo>, <xref:System.Reflection.MethodInfo>, <xref:System.Reflection.FieldInfo>, or <xref:System.Reflection.PropertyInfo> objects.</span></span>  
  
 <span data-ttu-id="f0d3b-123">In folgendem Beispiel wird das **MemberInfo**-Objekt verwendet, um die Anzahl von Membern in der **Klasse** aufzulisten. Zudem wird die <xref:System.Type.IsPublic%2A>-Eigenschaft verwendet, um die Sichtbarkeit der Klasse zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-123">The following example uses **MemberInfo** to list the number of members in the **System.IO.File** class and uses the <xref:System.Type.IsPublic%2A> property to determine the visibility of the class.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.Types.ViewInfo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source2.cs#2)]
 [!code-vb[Conceptual.Types.ViewInfo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source2.vb#2)]  
  
 <span data-ttu-id="f0d3b-124">In folgendem Beispiel wird der Typ des angegeben Members untersucht.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-124">The following example investigates the type of the specified member.</span></span> <span data-ttu-id="f0d3b-125">Es wird eine Reflektion für einen Member der Klasse **MemberInfo** ausgeführt, und deren Typ wird aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-125">It performs reflection on a member of the **MemberInfo** class, and lists its type.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.Types.ViewInfo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source3.cs#3)]
 [!code-vb[Conceptual.Types.ViewInfo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source3.vb#3)]  
  
 <span data-ttu-id="f0d3b-126">Im folgenden Beispiel werden alle **\*Info**-Reflektionsklassen mit <xref:System.Reflection.BindingFlags> verwendet, um alle Member (Konstruktoren, Felder, Eigenschaften, Ereignisse und Methoden) der angegebenen Klasse aufzulisten. Dabei werden die Member in die Kategorien „Statisch“ und „Instanz“ aufgeteilt.</span><span class="sxs-lookup"><span data-stu-id="f0d3b-126">The following example uses all the Reflection **\*Info** classes along with <xref:System.Reflection.BindingFlags> to list all the members (constructors, fields, properties, events, and methods) of the specified class, dividing the members into static and instance categories.</span></span>  
  
 [!code-cpp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.types.viewinfo/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.Types.ViewInfo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.types.viewinfo/cs/source4.cs#4)]
 [!code-vb[Conceptual.Types.ViewInfo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.types.viewinfo/vb/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f0d3b-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0d3b-127">See Also</span></span>  
 <xref:System.Reflection.BindingFlags>  
 <xref:System.Reflection.Assembly.GetType%2A?displayProperty=nameWithType>  
 <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType>  
 <xref:System.Type.GetType%2A?displayProperty=nameWithType>  
 <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>  
 <xref:System.Type.GetFields%2A?displayProperty=nameWithType>  
 <xref:System.Reflection.Module.GetType%2A?displayProperty=nameWithType>  
 <xref:System.Reflection.Module.GetTypes%2A?displayProperty=nameWithType>  
 <xref:System.Reflection.MemberInfo>  
 <xref:System.Reflection.ConstructorInfo>  
 <xref:System.Reflection.MethodInfo>  
 <xref:System.Reflection.FieldInfo>  
 <xref:System.Reflection.EventInfo>  
 <xref:System.Reflection.ParameterInfo>  
 [<span data-ttu-id="f0d3b-128">Reflektion und generische Typen</span><span class="sxs-lookup"><span data-stu-id="f0d3b-128">Reflection and Generic Types</span></span>](../../../docs/framework/reflection-and-codedom/reflection-and-generic-types.md)
