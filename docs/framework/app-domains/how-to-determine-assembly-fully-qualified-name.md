---
title: 'Vorgehensweise: Bestimmen des vollqualifizierten Namens einer Assembly'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 009dae23-e1f6-4a64-9a9a-32e4c34802b0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb5978859ba25e1595ac3da7a2d7dad8cc2cad85
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50041101"
---
# <a name="how-to-determine-an-assembly39s-fully-qualified-name"></a><span data-ttu-id="7d1ce-102">Vorgehensweise: Bestimmen des vollqualifizierten Namens einer Assembly</span><span class="sxs-lookup"><span data-stu-id="7d1ce-102">How to: Determine an Assembly&#39;s Fully Qualified Name</span></span>
<span data-ttu-id="7d1ce-103">Um den vollqualifizierten Namen einer Assembly im globalen Assemblycache zu ermitteln, verwenden Sie das GAC-Tool ([Gacutil.exe](../../../docs/framework/tools/gacutil-exe-gac-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="7d1ce-103">To discover the fully qualified name of an assembly in the global assembly cache, use the Global Assembly Cache Tool ([Gacutil.exe](../../../docs/framework/tools/gacutil-exe-gac-tool.md)).</span></span> <span data-ttu-id="7d1ce-104">Siehe [Vorgehensweise: Anzeigen der Inhalte des globalen Assemblycaches](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md).</span><span class="sxs-lookup"><span data-stu-id="7d1ce-104">See [How to: View the Contents of the Global Assembly Cache](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md).</span></span>  
  
 <span data-ttu-id="7d1ce-105">Für Assemblys, die sich nicht im globalen Assemblycache befinden, können Sie den vollqualifizierten Assemblynamen auf verschiedene Weisen abrufen: Sie können Code verwenden, um die Informationen auf der Konsole oder in einer Variablen auszugeben. Alternativ können Sie auch den [Ildasm.exe (IL-Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) zum Untersuchen der Metadaten verwenden, die den vollqualifizierten Namen der Assembly enthalten.</span><span class="sxs-lookup"><span data-stu-id="7d1ce-105">For assemblies that are not in the global assembly cache, you can get the fully qualified assembly name in a number of ways: can use code to output the information to the console or to a variable, or you can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>  
  
-   <span data-ttu-id="7d1ce-106">Wenn die Assembly bereits von der Anwendung geladen wird, können Sie den Wert der <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType>-Eigenschaft abrufen, um den vollqualifizierten Namen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7d1ce-106">If the assembly is already loaded by the application, you can retrieve the value of the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property to get the fully qualified name.</span></span> <span data-ttu-id="7d1ce-107">Sie können diesen Ansatz verwenden, und zwar unabhängig davon, ob sich die Assembly im GAC befindet.</span><span class="sxs-lookup"><span data-stu-id="7d1ce-107">You can use this approach whether or not the assembly is in the GAC.</span></span> <span data-ttu-id="7d1ce-108">Dies wird im Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7d1ce-108">The example provides an illustration.</span></span>  
  
-   <span data-ttu-id="7d1ce-109">Wenn Sie den Dateisystempfad der Assembly kennen, können Sie die statische (`Shared` in Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType>-Methode aufrufen, um den vollqualifizierten Assemblynamen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="7d1ce-109">If you know the assembly's file system path, you can call the static (`Shared` in Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> method to get the fully qualified assembly name.</span></span> <span data-ttu-id="7d1ce-110">Im Folgenden finden Sie ein einfaches Beispiel.</span><span class="sxs-lookup"><span data-stu-id="7d1ce-110">The following is a simple example.</span></span>  
  
     [!code-csharp[System.Reflection.AssemblyName.GetAssemblyName#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflection.assemblyname.getassemblyname/cs/getassemblyname1.cs#1)]
     [!code-vb[System.Reflection.AssemblyName.GetAssemblyName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflection.assemblyname.getassemblyname/vb/getassemblyname1.vb#1)]  
  
-   <span data-ttu-id="7d1ce-111">Sie können den [Ildasm.exe (IL-Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) verwenden, um die Metadaten der Assembly zu überprüfen, die den vollqualifizierten Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="7d1ce-111">You can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>  
  
 <span data-ttu-id="7d1ce-112">Weitere Informationen zum Festlegen von Assemblyattributen wie Version, Kultur und Assemblyname finden Sie unter [Festlegen von Assemblyattributen](../../../docs/framework/app-domains/set-assembly-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="7d1ce-112">For more information about setting assembly attributes such as version, culture, and assembly name, see [Setting Assembly Attributes](../../../docs/framework/app-domains/set-assembly-attributes.md).</span></span> <span data-ttu-id="7d1ce-113">Weitere Informationen zum Vergeben eines starken Namens für eine Assembly finden Sie unter [Erstellen und Verwenden von Assemblys mit starkem Namen](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="7d1ce-113">For more information about giving an assembly a strong name, see [Creating and Using Strong-Named Assemblies](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d1ce-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7d1ce-114">Example</span></span>  
 <span data-ttu-id="7d1ce-115">Das folgende Codebeispiel zeigt, wie Sie den voll gekennzeichneten Namen einer Assembly, die eine angegebene Klasse enthält, auf der Konsole anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="7d1ce-115">The following code example shows how to display the fully qualified name of an assembly containing a specified class to the console.</span></span> <span data-ttu-id="7d1ce-116">Da der Name einer Assembly abgerufen wird, die die Anwendung bereits geladen hat, spielt es keine Rolle, ob sich die Assembly im GAC befindet.</span><span class="sxs-lookup"><span data-stu-id="7d1ce-116">Because it retrieves the name of an assembly that the app has already loaded, it does not matter whether the assembly is in the GAC.</span></span>  
  
 [!code-cpp[Assembly.Fullname#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.FullName/CPP/example2.cpp#2)]
 [!code-csharp[Assembly.Fullname#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.FullName/CS/example2.cs#2)]
 [!code-vb[Assembly.Fullname#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.FullName/VB/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="7d1ce-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7d1ce-117">See Also</span></span>  
- [<span data-ttu-id="7d1ce-118">Assemblynamen</span><span class="sxs-lookup"><span data-stu-id="7d1ce-118">Assembly Names</span></span>](../../../docs/framework/app-domains/assembly-names.md)  
- [<span data-ttu-id="7d1ce-119">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="7d1ce-119">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
- [<span data-ttu-id="7d1ce-120">Erstellen und Verwenden von Assemblys mit starkem Namen</span><span class="sxs-lookup"><span data-stu-id="7d1ce-120">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
- [<span data-ttu-id="7d1ce-121">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="7d1ce-121">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
- [<span data-ttu-id="7d1ce-122">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="7d1ce-122">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
- [<span data-ttu-id="7d1ce-123">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="7d1ce-123">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
