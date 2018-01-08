---
title: "Typweiterleitung in der Common Language Runtime"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32dad99e8d5caa7d88fa302a1bea8b83847bfde3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="type-forwarding-in-the-common-language-runtime"></a><span data-ttu-id="af7f0-102">Typweiterleitung in der Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="af7f0-102">Type Forwarding in the Common Language Runtime</span></span>
<span data-ttu-id="af7f0-103">Durch Typweiterleitung können Sie einen Typ in eine andere Assembly verschieben, ohne Anwendungen, die die ursprüngliche Assembly verwenden, neu kompilieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="af7f0-103">Type forwarding allows you to move a type to another assembly without having to recompile applications that use the original assembly.</span></span>  
  
 <span data-ttu-id="af7f0-104">Angenommen, eine Anwendung verwendet die `Example`-Klasse in einer Assembly namens `Utility.dll`.</span><span class="sxs-lookup"><span data-stu-id="af7f0-104">For example, suppose an application uses the `Example` class in an assembly named `Utility.dll`.</span></span> <span data-ttu-id="af7f0-105">Die Entwickler von `Utility.dll` könnten beschließen, die Assembly umzugestalten und bei diesem Vorgang die `Example`-Klasse in eine andere Assembly verschieben.</span><span class="sxs-lookup"><span data-stu-id="af7f0-105">The developers of `Utility.dll` might decide to refactor the assembly, and in the process they might move the `Example` class to another assembly.</span></span> <span data-ttu-id="af7f0-106">Wenn die alte Version von `Utility.dll` durch die neue Version von `Utility.dll` und die zugehörige Assembly ersetzt wird, treten Fehler in der Anwendung auf, die die `Example`-Klasse verwendet, weil sie die `Example`-Klasse in der neuen Version von `Utility.dll` nicht finden kann.</span><span class="sxs-lookup"><span data-stu-id="af7f0-106">If the old version of `Utility.dll` is replaced by the new version of `Utility.dll` and its companion assembly, the application that uses the `Example` class fails because it cannot locate the `Example` class in the new version of `Utility.dll`.</span></span>  
  
 <span data-ttu-id="af7f0-107">Die Entwickler von `Utility.dll` können dies durch das Weiterleiten von Anforderungen an die `Example`-Klasse mit dem Attribut <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> vermeiden.</span><span class="sxs-lookup"><span data-stu-id="af7f0-107">The developers of `Utility.dll` can avoid this by forwarding requests for the `Example` class, using the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attribute.</span></span> <span data-ttu-id="af7f0-108">Falls das Attribut auf die neue Version von `Utility.dll` angewendet wurde, werden Anforderungen für die `Example`-Klasse an die Assembly weitergeleitet, die nun die Klasse enthält.</span><span class="sxs-lookup"><span data-stu-id="af7f0-108">If the attribute has been applied to the new version of `Utility.dll`, requests for the `Example` class are forwarded to the assembly that now contains the class.</span></span> <span data-ttu-id="af7f0-109">Die vorhandene Anwendung funktioniert ohne Neukompilierung weiterhin normal.</span><span class="sxs-lookup"><span data-stu-id="af7f0-109">The existing application continues to function normally, without recompilation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af7f0-110">In .NET Framework, Version 2.0, können Sie keine Typen aus Assemblys weiterleiten, die in Visual Basic geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="af7f0-110">In the .NET Framework version 2.0, you cannot forward types from assemblies written in Visual Basic.</span></span> <span data-ttu-id="af7f0-111">Eine in Visual Basic geschriebene Anwendung kann jedoch weitergeleitete Typen verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="af7f0-111">However, an application written in Visual Basic can consume forwarded types.</span></span> <span data-ttu-id="af7f0-112">Wenn die Anwendung also eine in C# oder C++ codierte Assembly verwendet und ein Typ aus dieser Assembly an eine andere Assembly weitergeleitet wird, kann die Visual Basic-Anwendung den weitergeleiteten Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="af7f0-112">That is, if the application uses an assembly coded in C# or C++, and a type from that assembly is forwarded to another assembly, the Visual Basic application can use the forwarded type.</span></span>  
  
## <a name="forwarding-types"></a><span data-ttu-id="af7f0-113">Weiterleiten von Typen</span><span class="sxs-lookup"><span data-stu-id="af7f0-113">Forwarding Types</span></span>  
 <span data-ttu-id="af7f0-114">Die Weiterleitung eines Typs erfolgt in vier Schritten:</span><span class="sxs-lookup"><span data-stu-id="af7f0-114">There are four steps to forwarding a type:</span></span>  
  
1.  <span data-ttu-id="af7f0-115">Verschieben Sie den Quellcode für den Typ aus der ursprünglichen Assembly in die Zielassembly.</span><span class="sxs-lookup"><span data-stu-id="af7f0-115">Move the source code for the type from the original assembly to the destination assembly.</span></span>  
  
2.  <span data-ttu-id="af7f0-116">Fügen Sie in der Assembly, in der sich der Typ ursprünglich befunden hat, ein <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>-Objekt für den verschobenen Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="af7f0-116">In the assembly where the type used to be located, add a <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> for the type that was moved.</span></span> <span data-ttu-id="af7f0-117">Der folgenden Code veranschaulicht das Attribut für einen Typ namens `Example`, der verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="af7f0-117">The following code shows the attribute for a type named `Example` that was moved.</span></span>  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3.  <span data-ttu-id="af7f0-118">Kompilieren Sie die Assembly, die jetzt den Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="af7f0-118">Compile the assembly that now contains the type.</span></span>  
  
4.  <span data-ttu-id="af7f0-119">Führen Sie für die Assembly, in der sich der Typ befand, eine Neukompilierung mit einem Verweis auf die Assembly durch, die jetzt den Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="af7f0-119">Recompile the assembly where the type used to be located, with a reference to the assembly that now contains the type.</span></span> <span data-ttu-id="af7f0-120">Wenn Sie z. B. eine C#-Datei über die Befehlszeile kompilieren, geben Sie mit der [/reference (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md)-Option die Assembly an, die den Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="af7f0-120">For example, if you are compiling a C# file from the command line, use the [/reference (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md) option to specify the assembly that contains the type.</span></span> <span data-ttu-id="af7f0-121">In C++ verwenden Sie die [#using](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a)-Direktive in der Quelldatei, um die Assembly anzugeben, die den Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="af7f0-121">In C++, use the [#using](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a) directive in the source file to specify the assembly that contains the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af7f0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af7f0-122">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>  
 [<span data-ttu-id="af7f0-123">Typweiterleitung (C++/CLI)</span><span class="sxs-lookup"><span data-stu-id="af7f0-123">Type Forwarding (C++/CLI)</span></span>](/cpp/windows/type-forwarding-cpp-cli)  
 [<span data-ttu-id="af7f0-124">#using-Direktive</span><span class="sxs-lookup"><span data-stu-id="af7f0-124">#using Directive</span></span>](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a)
