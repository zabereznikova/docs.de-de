---
title: 'Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne'
description: Hier erfahren Sie, wie Sie Assemblys in eine Anwendungsdomäne in .NET laden. Es wird empfohlen, die static (oder Shared) Load-Methode in System.Reflection.Assembly zu verwenden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- application domains, loading assemblies
- loading assemblies
ms.assetid: 1432aa2d-bd83-4346-bf3b-a1b7920e2aa9
ms.openlocfilehash: c91c70625b79002e9297755dfdfac8aa6e283208
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104759"
---
# <a name="how-to-load-assemblies-into-an-application-domain"></a><span data-ttu-id="57be5-104">Vorgehensweise: Laden von Assemblys in eine Anwendungsdomäne</span><span class="sxs-lookup"><span data-stu-id="57be5-104">How to: Load Assemblies into an Application Domain</span></span>
<span data-ttu-id="57be5-105">Es gibt mehrere Möglichkeiten, eine Assembly in eine Anwendungsdomäne zu laden.</span><span class="sxs-lookup"><span data-stu-id="57be5-105">There are several ways to load an assembly into an application domain.</span></span> <span data-ttu-id="57be5-106">Es wird empfohlen, die `static`<xref:System.Reflection.Assembly.Load%2A>-Methode (`Shared` in Visual Basic) der Klasse <xref:System.Reflection.Assembly?displayProperty=nameWithType> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="57be5-106">The recommended way is to use the `static` (`Shared` in Visual Basic) <xref:System.Reflection.Assembly.Load%2A> method of the <xref:System.Reflection.Assembly?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="57be5-107">Es gibt noch weitere Möglichkeiten, Assemblys zu laden:</span><span class="sxs-lookup"><span data-stu-id="57be5-107">Other ways assemblies can be loaded include:</span></span>  
  
- <span data-ttu-id="57be5-108">Die <xref:System.Reflection.Assembly.LoadFrom%2A>-Methode der Klasse <xref:System.Reflection.Assembly> lädt eine Assembly, sofern deren Speicherort angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="57be5-108">The <xref:System.Reflection.Assembly.LoadFrom%2A> method of the <xref:System.Reflection.Assembly> class loads an assembly given its file location.</span></span> <span data-ttu-id="57be5-109">Beim Laden von Assemblys mit dieser Methode wird ein anderer Load-Kontext verwendet.</span><span class="sxs-lookup"><span data-stu-id="57be5-109">Loading assemblies with this method uses a different load context.</span></span>  
  
- <span data-ttu-id="57be5-110">Die Methoden <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> und <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> laden eine Assembly in den ReflectionOnly-Kontext.</span><span class="sxs-lookup"><span data-stu-id="57be5-110">The <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A> and <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom%2A> methods load an assembly into the reflection-only context.</span></span> <span data-ttu-id="57be5-111">In diesen Kontext geladene Assemblys können untersucht, aber nicht ausgeführt werden. So können Assemblys untersucht werden, die andere Zielplattformen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="57be5-111">Assemblies loaded into this context can be examined but not executed, allowing the examination of assemblies that target other platforms.</span></span> <span data-ttu-id="57be5-112">Weitere Informationen finden Sie unter [How to: Laden von Assemblys in den reflexionsbezogenen Kontext](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span><span class="sxs-lookup"><span data-stu-id="57be5-112">See [How to: Load Assemblies into the Reflection-Only Context](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57be5-113">Der ReflectionOnly-Kontext ist neu in .NET Framework Version 2.0.</span><span class="sxs-lookup"><span data-stu-id="57be5-113">The reflection-only context is new in the .NET Framework version 2.0.</span></span>  
  
- <span data-ttu-id="57be5-114">Methoden der <xref:System.AppDomain>-Klasse, wie etwa <xref:System.AppDomain.CreateInstance%2A> und <xref:System.AppDomain.CreateInstanceAndUnwrap%2A>, können Assemblys in eine Anwendungsdomäne laden.</span><span class="sxs-lookup"><span data-stu-id="57be5-114">Methods such as <xref:System.AppDomain.CreateInstance%2A> and <xref:System.AppDomain.CreateInstanceAndUnwrap%2A> of the <xref:System.AppDomain> class can load assemblies into an application domain.</span></span>  
  
- <span data-ttu-id="57be5-115">Die <xref:System.Type.GetType%2A>-Methode der <xref:System.Type>-Klasse kann Assemblys laden.</span><span class="sxs-lookup"><span data-stu-id="57be5-115">The <xref:System.Type.GetType%2A> method of the <xref:System.Type> class can load assemblies.</span></span>  
  
- <span data-ttu-id="57be5-116">Die <xref:System.AppDomain.Load%2A>-Methode der <xref:System.AppDomain?displayProperty=nameWithType>-Klasse kann Assemblys laden, wird aber hauptsächlich für COM-Interoperabilität verwendet.</span><span class="sxs-lookup"><span data-stu-id="57be5-116">The <xref:System.AppDomain.Load%2A> method of the <xref:System.AppDomain?displayProperty=nameWithType> class can load assemblies, but is primarily used for COM interoperability.</span></span> <span data-ttu-id="57be5-117">Sie sollte nicht zum Laden von Assemblys in eine andere als diejenige Anwendungsdomäne verwendet werden, aus der sie geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="57be5-117">It should not be used to load assemblies into an application domain other than the application domain from which it is called.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57be5-118">Ab .NET Framework-Version 2.0 lädt die Runtime keine Assembly, die mit einer Version von .NET Framework kompiliert wurde, die eine höhere Versionsnummer als die aktuell geladene Runtime besitzt.</span><span class="sxs-lookup"><span data-stu-id="57be5-118">Starting with the .NET Framework version 2.0, the runtime will not load an assembly that was compiled with a version of the .NET Framework that has a higher version number than the currently loaded runtime.</span></span> <span data-ttu-id="57be5-119">Dies gilt für die Kombination der Haupt- und Nebenkomponenten der Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="57be5-119">This applies to the combination of the major and minor components of the version number.</span></span>  
  
 <span data-ttu-id="57be5-120">Sie können angeben, wie der kompilierte Just-In-Time-Code (JIT) aus geladenen Assemblys von mehreren Anwendungsdomänen gemeinsam verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="57be5-120">You can specify the way the just-in-time (JIT) compiled code from loaded assemblies is shared between application domains.</span></span> <span data-ttu-id="57be5-121">Weitere Informationen finden Sie unter [Application Domains and Assemblies (Anwendungsdomänen und Assemblys)](application-domains.md#application-domains-and-assemblies).</span><span class="sxs-lookup"><span data-stu-id="57be5-121">For more information, see [Application domains and assemblies](application-domains.md#application-domains-and-assemblies).</span></span>  
  
## <a name="example"></a><span data-ttu-id="57be5-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="57be5-122">Example</span></span>  
 <span data-ttu-id="57be5-123">Der folgende Code lädt eine Assembly mit dem Namen „example.exe“ oder „example.dll“ in die aktuelle Anwendungsdomäne, ruft einen Typ mit dem Namen `Example` aus der Assembly ab, ruft für diesen Typ eine Methode mit dem Namen `MethodA` ohne Parameter ab, und führt die Methode aus.</span><span class="sxs-lookup"><span data-stu-id="57be5-123">The following code loads an assembly named "example.exe" or "example.dll" into the current application domain, gets a type named `Example` from the assembly, gets a parameterless method named `MethodA` for that type, and executes the method.</span></span> <span data-ttu-id="57be5-124">Eine vollständige Erläuterung des Abrufens von Informationen aus einer geladenen Assembly finden Sie unter [Dynamically Loading and Using Types (Dynamisches Laden und Verwenden von Typen)](../reflection-and-codedom/dynamically-loading-and-using-types.md).</span><span class="sxs-lookup"><span data-stu-id="57be5-124">For a complete discussion on obtaining information from a loaded assembly, see [Dynamically Loading and Using Types](../reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>  
  
 [!code-cpp[System.AppDomain.Load#2](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.appdomain.load/cpp/source2.cpp#2)]
 [!code-csharp[System.AppDomain.Load#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.appdomain.load/cs/source2.cs#2)]
 [!code-vb[System.AppDomain.Load#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.appdomain.load/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="57be5-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57be5-125">See also</span></span>

- <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A>
- [<span data-ttu-id="57be5-126">Programming with Application Domains (Programmieren mit Anwendungsdomänen)</span><span class="sxs-lookup"><span data-stu-id="57be5-126">Programming with Application Domains</span></span>](application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="57be5-127">Reflexion</span><span class="sxs-lookup"><span data-stu-id="57be5-127">Reflection</span></span>](../reflection-and-codedom/reflection.md)
- [<span data-ttu-id="57be5-128">Verwenden von Anwendungsdomänen</span><span class="sxs-lookup"><span data-stu-id="57be5-128">Using Application Domains</span></span>](use.md)
- <span data-ttu-id="57be5-129">[How to: Load Assemblies into the Reflection-Only Context](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md) (Gewusst wie: Laden von Assemblys in den auf Reflektion beschränkten Kontext)</span><span class="sxs-lookup"><span data-stu-id="57be5-129">[How to: Load Assemblies into the Reflection-Only Context](../reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)</span></span>
- [<span data-ttu-id="57be5-130">Anwendungsdomänen und Assemblys</span><span class="sxs-lookup"><span data-stu-id="57be5-130">Application domains and assemblies</span></span>](application-domains.md#application-domains-and-assemblies)
