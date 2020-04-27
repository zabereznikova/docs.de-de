---
title: 'Vorgehensweise: Laden von Assemblys in den auf Reflektion beschränkten Kontext'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- reflection, reflection-only loader context
- assemblies [.NET Framework], loading for reflection
- attributes [.NET Framework], retrieving
- assemblies [.NET Framework], reflection-only loader context
- reflection-only loader context
ms.assetid: 9818b660-52f5-423d-a9af-e75163aa7068
ms.openlocfilehash: cac6b3b3adf070ad6070e5c5941653f20dedd907
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130102"
---
# <a name="how-to-load-assemblies-into-the-reflection-only-context"></a><span data-ttu-id="935dd-102">Vorgehensweise: Laden von Assemblys in den auf Reflektion beschränkten Kontext</span><span class="sxs-lookup"><span data-stu-id="935dd-102">How to: Load Assemblies into the Reflection-Only Context</span></span>

<span data-ttu-id="935dd-103">Mit dem ReflectionOnly-Load-Kontext können Sie Assemblys untersuchen, die für andere Plattformen oder andere Versionen von .NET Framework kompiliert wurden.</span><span class="sxs-lookup"><span data-stu-id="935dd-103">The reflection-only load context allows you to examine assemblies compiled for other platforms or for other versions of the .NET Framework.</span></span> <span data-ttu-id="935dd-104">In diesen Kontext geladener Code kann nur untersucht werden. Er kann nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="935dd-104">Code loaded into this context can only be examined; it cannot be executed.</span></span> <span data-ttu-id="935dd-105">Dies bedeutet, dass keine Objekte erstellt werden können, weil Konstruktoren nicht ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="935dd-105">This means that objects cannot be created, because constructors cannot be executed.</span></span> <span data-ttu-id="935dd-106">Da der Code nicht ausgeführt werden kann, werden Abhängigkeiten nicht automatische geladen.</span><span class="sxs-lookup"><span data-stu-id="935dd-106">Because the code cannot be executed, dependencies are not automatically loaded.</span></span> <span data-ttu-id="935dd-107">Wenn Sie diese untersuchen möchten, müssen Sie sie selbst laden.</span><span class="sxs-lookup"><span data-stu-id="935dd-107">If you need to examine them, you must load them yourself.</span></span>

## <a name="to-load-an-assembly-into-the-reflection-only-load-context"></a><span data-ttu-id="935dd-108">So können Sie eine Assembly in den ReflectionOnly-Kontext laden</span><span class="sxs-lookup"><span data-stu-id="935dd-108">To load an assembly into the reflection-only load context</span></span>

1. <span data-ttu-id="935dd-109">Verwenden Sie die <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29>-Methodenüberladung, um die Assembly mit deren Anzeigenamen zu laden, oder die <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A>-Methode, um die Assembly mit deren Pfad zu laden.</span><span class="sxs-lookup"><span data-stu-id="935dd-109">Use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.String%29> method overload to load the assembly given its display name, or the <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> method to load the assembly given its path.</span></span> <span data-ttu-id="935dd-110">Wenn die Assembly ein binäres Image ist, verwenden Sie die <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29>-Methodenüberladung.</span><span class="sxs-lookup"><span data-stu-id="935dd-110">If the assembly is a binary image, use the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%28System.Byte%5B%5D%29> method overload.</span></span>

    > [!NOTE]
    > <span data-ttu-id="935dd-111">Sie können den ReflectionOnly-Kontext nicht zum Laden einer Version von „mscorlib.dll“ aus einer Version von .NET Framework verwenden, wenn sich diese Version von der Version des Ausführungskontexts unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="935dd-111">You cannot use the reflection-only context to load a version of mscorlib.dll from a version of the .NET Framework other than the version in the execution context.</span></span>

2. <span data-ttu-id="935dd-112">Wenn die Assembly Abhängigkeiten hat, werden diese von der <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>-Methode nicht geladen.</span><span class="sxs-lookup"><span data-stu-id="935dd-112">If the assembly has dependencies, the <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> method does not load them.</span></span> <span data-ttu-id="935dd-113">Wenn Sie diese untersuchen möchten, müssen Sie sie selbst laden.</span><span class="sxs-lookup"><span data-stu-id="935dd-113">If you need to examine them, you must load them yourself.</span></span>

3. <span data-ttu-id="935dd-114">Sie können mit der <xref:System.Reflection.Assembly.ReflectionOnly%2A>-Eigenschaft einer Assembly feststellen, ob die Assembly in einen ReflectionOnly-Kontext geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="935dd-114">Determine whether an assembly is loaded into the reflection-only context by using the assembly's <xref:System.Reflection.Assembly.ReflectionOnly%2A> property.</span></span>

4. <span data-ttu-id="935dd-115">Wenn Attribute auf die Assembly oder auf Typen in der Assembly angewendet wurden, können Sie sich diese Attribute mit der <xref:System.Reflection.CustomAttributeData>-Klasse anschauen, um sicherzustellen, dass der Code nicht im ReflectionOnly-Kontext ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="935dd-115">If attributes have been applied to the assembly or to types in the assembly, examine those attributes by using the <xref:System.Reflection.CustomAttributeData> class to ensure that no attempt is made to execute code in the reflection-only context.</span></span> <span data-ttu-id="935dd-116">Verwenden Sie die entsprechende Überladung der <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType>-Methode, um <xref:System.Reflection.CustomAttributeData>-Objekte zu erhalten, die die auf eine Assembly, einen Member, ein Modul oder einen Parameter angewendeten Attribute darstellen.</span><span class="sxs-lookup"><span data-stu-id="935dd-116">Use the appropriate overload of the <xref:System.Reflection.CustomAttributeData.GetCustomAttributes%2A?displayProperty=nameWithType> method to obtain <xref:System.Reflection.CustomAttributeData> objects representing the attributes applied to an assembly, member, module, or parameter.</span></span>

    > [!NOTE]
    > <span data-ttu-id="935dd-117">Auf die Assembly oder auf deren Inhalte angewendete Attribute sind möglicherweise in der Assembly oder in einer anderen in den ReflectionOnly-Kontext geladenen Assembly definiert.</span><span class="sxs-lookup"><span data-stu-id="935dd-117">Attributes applied to the assembly or to its contents might be defined in the assembly, or they might be defined in another assembly loaded into the reflection-only context.</span></span> <span data-ttu-id="935dd-118">Es ist nicht möglich, im Voraus zu bestimmen, wo die Attribute definiert sind.</span><span class="sxs-lookup"><span data-stu-id="935dd-118">There is no way to tell in advance where the attributes are defined.</span></span>

## <a name="example"></a><span data-ttu-id="935dd-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="935dd-119">Example</span></span>

<span data-ttu-id="935dd-120">In folgendem Codebeispiel wird veranschaulicht, wie Sie die Attribute, die auf eine in den ReflectionOnly-Kontext geladene Assembly angewendet wurden, untersuchen können.</span><span class="sxs-lookup"><span data-stu-id="935dd-120">The following code example shows how to examine the attributes applied to an assembly loaded into the reflection-only context.</span></span>

<span data-ttu-id="935dd-121">Im Codebeispiel wird ein benutzerdefiniertes Attribut mit zwei Konstruktoren und einer Eigenschaft definiert.</span><span class="sxs-lookup"><span data-stu-id="935dd-121">The code example defines a custom attribute with two constructors and one property.</span></span> <span data-ttu-id="935dd-122">Das Attribut wird auf die Assembly angewendet sowie auf einen in der Assembly deklarierten Typ, eine Methode dieses Typs und einen Parameter der Methode.</span><span class="sxs-lookup"><span data-stu-id="935dd-122">The attribute is applied to the assembly, to a type declared in the assembly, to a method of the type, and to a parameter of the method.</span></span> <span data-ttu-id="935dd-123">Bei der Ausführung lädt die Assembly sich selbst in den ReflectionOnly-Kontext und zeigt Informationen zu den benutzerdefinierten Attributen an, die auf die Assembly und die Typen und Member, die sie enthält, angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="935dd-123">When executed, the assembly loads itself into the reflection-only context and displays information about the custom attributes that were applied to it and to the types and members it contains.</span></span>

> [!NOTE]
> <span data-ttu-id="935dd-124">Um das Codebeispiel einfacher zu halten, lädt und untersucht die Assembly sich selbst.</span><span class="sxs-lookup"><span data-stu-id="935dd-124">To simplify the code example, the assembly loads and examines itself.</span></span> <span data-ttu-id="935dd-125">Für gewöhnlich ist nicht zu erwarten, dass die gleiche Assembly sowohl in den Ausführungskontext und den ReflectionOnly-Kontext geladen wird.</span><span class="sxs-lookup"><span data-stu-id="935dd-125">Normally, you would not expect to find the same assembly loaded into both the execution context and the reflection-only context.</span></span>

[!code-cpp[CustomAttributeData#1](../../../samples/snippets/cpp/VS_Snippets_CLR/CustomAttributeData/CPP/source.cpp#1)]
[!code-csharp[CustomAttributeData#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CustomAttributeData/CS/source.cs#1)]
[!code-vb[CustomAttributeData#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CustomAttributeData/VB/source.vb#1)]

## <a name="see-also"></a><span data-ttu-id="935dd-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="935dd-126">See also</span></span>

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- <xref:System.Reflection.Assembly.ReflectionOnly%2A>
- <xref:System.Reflection.CustomAttributeData>
