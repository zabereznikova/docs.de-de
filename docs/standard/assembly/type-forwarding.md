---
title: Typweiterleitung in der Common Language Runtime
description: Durch Typweiterleitung können Sie einen Typ in eine andere .NET-Assembly verschieben, ohne Anwendungen, die die ursprüngliche Assembly verwenden, neu kompilieren zu müssen.
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
dev_langs:
- csharp
- cpp
ms.openlocfilehash: cd166068993fb5d1a5164615de3926a06dda8098
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687661"
---
# <a name="type-forwarding-in-the-common-language-runtime"></a><span data-ttu-id="b66b4-103">Typweiterleitung in der Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="b66b4-103">Type forwarding in the common language runtime</span></span>

<span data-ttu-id="b66b4-104">Durch Typweiterleitung können Sie einen Typ in eine andere Assembly verschieben, ohne Anwendungen, die die ursprüngliche Assembly verwenden, neu kompilieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="b66b4-104">Type forwarding allows you to move a type to another assembly without having to recompile applications that use the original assembly.</span></span>  
  
 <span data-ttu-id="b66b4-105">Angenommen, eine Anwendung verwendet die `Example`-Klasse in einer Assembly namens *Utility.dll*.</span><span class="sxs-lookup"><span data-stu-id="b66b4-105">For example, suppose an application uses the `Example` class in an assembly named *Utility.dll*.</span></span> <span data-ttu-id="b66b4-106">Die Entwickler von *Utility.dll* könnten beschließen, die Assembly umzugestalten und bei diesem Vorgang die `Example`-Klasse in eine andere Assembly verschieben.</span><span class="sxs-lookup"><span data-stu-id="b66b4-106">The developers of *Utility.dll* might decide to refactor the assembly, and in the process they might move the `Example` class to another assembly.</span></span> <span data-ttu-id="b66b4-107">Wenn die alte Version von *Utility.dll* durch die neue Version von *Utility.dll* und die zugehörige Assembly ersetzt wird, treten Fehler in der Anwendung auf, die die `Example`-Klasse verwendet, weil sie die `Example`-Klasse in der neuen Version von *Utility.dll* nicht finden kann.</span><span class="sxs-lookup"><span data-stu-id="b66b4-107">If the old version of *Utility.dll* is replaced by the new version of *Utility.dll* and its companion assembly, the application that uses the `Example` class fails because it cannot locate the `Example` class in the new version of *Utility.dll*.</span></span>  
  
 <span data-ttu-id="b66b4-108">Die Entwickler von *Utility.dll* können dies durch das Weiterleiten von Anforderungen an die `Example`-Klasse mit dem Attribut <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> vermeiden.</span><span class="sxs-lookup"><span data-stu-id="b66b4-108">The developers of *Utility.dll* can avoid this by forwarding requests for the `Example` class, using the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attribute.</span></span> <span data-ttu-id="b66b4-109">Falls das Attribut auf die neue Version von *Utility.dll* angewendet wurde, werden Anforderungen für die `Example`-Klasse an die Assembly weitergeleitet, die nun die Klasse enthält.</span><span class="sxs-lookup"><span data-stu-id="b66b4-109">If the attribute has been applied to the new version of *Utility.dll* , requests for the `Example` class are forwarded to the assembly that now contains the class.</span></span> <span data-ttu-id="b66b4-110">Die vorhandene Anwendung funktioniert ohne Neukompilierung weiterhin normal.</span><span class="sxs-lookup"><span data-stu-id="b66b4-110">The existing application continues to function normally, without recompilation.</span></span>

## <a name="forward-a-type"></a><span data-ttu-id="b66b4-111">Weiterleiten eines Typs</span><span class="sxs-lookup"><span data-stu-id="b66b4-111">Forward a type</span></span>

 <span data-ttu-id="b66b4-112">Die Weiterleitung eines Typs erfolgt in vier Schritten:</span><span class="sxs-lookup"><span data-stu-id="b66b4-112">There are four steps to forwarding a type:</span></span>  
  
1. <span data-ttu-id="b66b4-113">Verschieben Sie den Quellcode für den Typ aus der ursprünglichen Assembly in die Zielassembly.</span><span class="sxs-lookup"><span data-stu-id="b66b4-113">Move the source code for the type from the original assembly to the destination assembly.</span></span>  

2. <span data-ttu-id="b66b4-114">Fügen Sie in der Assembly, in der sich der Typ ursprünglich befunden hat, ein <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>-Objekt für den verschobenen Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="b66b4-114">In the assembly where the type used to be located, add a <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> for the type that was moved.</span></span> <span data-ttu-id="b66b4-115">Der folgenden Code veranschaulicht das Attribut für einen Typ namens `Example`, der verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="b66b4-115">The following code shows the attribute for a type named `Example` that was moved.</span></span>  

   ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
   ```

   ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
   ```  

3. <span data-ttu-id="b66b4-116">Kompilieren Sie die Assembly, die jetzt den Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="b66b4-116">Compile the assembly that now contains the type.</span></span>  

4. <span data-ttu-id="b66b4-117">Führen Sie für die Assembly, in der sich der Typ befand, eine Neukompilierung mit einem Verweis auf die Assembly durch, die jetzt den Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="b66b4-117">Recompile the assembly where the type used to be located, with a reference to the assembly that now contains the type.</span></span> <span data-ttu-id="b66b4-118">Wenn Sie z.B. eine C#-Datei über die Befehlszeile kompilieren, geben Sie mit [-reference (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) die Assembly an, die den Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="b66b4-118">For example, if you are compiling a C# file from the command line, use the [-reference (C# compiler options)](../../csharp/language-reference/compiler-options/reference-compiler-option.md) option to specify the assembly that contains the type.</span></span> <span data-ttu-id="b66b4-119">In C++ verwenden Sie die [#using](/cpp/preprocessor/hash-using-directive-cpp)-Direktive in der Quelldatei, um die Assembly anzugeben, die den Typ enthält.</span><span class="sxs-lookup"><span data-stu-id="b66b4-119">In C++, use the [#using](/cpp/preprocessor/hash-using-directive-cpp) directive in the source file to specify the assembly that contains the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b66b4-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b66b4-120">See also</span></span>

- <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>
- [<span data-ttu-id="b66b4-121">Typweiterleitung (C++/CLI)</span><span class="sxs-lookup"><span data-stu-id="b66b4-121">Type forwarding (C++/CLI)</span></span>](/cpp/windows/type-forwarding-cpp-cli)
- [<span data-ttu-id="b66b4-122">#using-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b66b4-122">#using directive</span></span>](/cpp/preprocessor/hash-using-directive-cpp)
