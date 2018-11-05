---
title: Kompilieren eines Interop-Projekts
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7088c7f7765f0c5cfc4d6151dcda6f57b8de10d2
ms.sourcegitcommit: 2eb5ca4956231c1a0efd34b6a9cab6153a5438af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49086647"
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="16e37-102">Kompilieren eines Interop-Projekts</span><span class="sxs-lookup"><span data-stu-id="16e37-102">Compiling an Interop Project</span></span>

<span data-ttu-id="16e37-103">COM-Interop-Projekte, die auf eine oder mehrere Assemblys mit importierten COM-Typen verweisen, werden wie jedes andere verwaltete Projekt kompiliert.</span><span class="sxs-lookup"><span data-stu-id="16e37-103">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="16e37-104">Sie können auf Interop-Assemblys in einer Entwicklungsumgebung wie Visual Studio verweisen, oder Sie können darauf verweisen, wenn Sie einen Befehlszeilencompiler verwenden.</span><span class="sxs-lookup"><span data-stu-id="16e37-104">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="16e37-105">In beiden Fällen muss die Interop-Assembly zur ordnungsgemäßen Kompilierung im selben Verzeichnis wie die anderen Projektdateien sein.</span><span class="sxs-lookup"><span data-stu-id="16e37-105">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>

 <span data-ttu-id="16e37-106">Es gibt zwei Möglichkeiten zur Verweisung auf Interop-Assemblys:</span><span class="sxs-lookup"><span data-stu-id="16e37-106">There are two ways to reference interop assemblies:</span></span>

-   <span data-ttu-id="16e37-107">Eingebettete Interop-Typen: Ab [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] und Visual Studio 2010 können Sie den Compiler anweisen, die Typinformationen aus einer Interopassembly in die ausführbare Datei einzubetten.</span><span class="sxs-lookup"><span data-stu-id="16e37-107">Embedded interop types: Beginning with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] and Visual Studio 2010, you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="16e37-108">Dies ist das empfohlene Verfahren.</span><span class="sxs-lookup"><span data-stu-id="16e37-108">This is the recommended technique.</span></span>

-   <span data-ttu-id="16e37-109">Durch die Bereitstellung von Interop-Assemblys können Sie einen Standardverweis auf eine Interop-Assembly erstellen.</span><span class="sxs-lookup"><span data-stu-id="16e37-109">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="16e37-110">In diesem Fall muss die Interop-Assembly mit Ihrer Anwendung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="16e37-110">In this case, the interop assembly must be deployed with your application.</span></span>

 <span data-ttu-id="16e37-111">Die Unterschiede zwischen diesen beiden Verfahren werden ausführlich in [Verwenden von COM-Typen in verwaltetem Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)) erläutert.</span><span class="sxs-lookup"><span data-stu-id="16e37-111">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100)).</span></span>

 <span data-ttu-id="16e37-112">Das Einbetten von Interop-Typen mit Visual Studio wird in [Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100)) und [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21) veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="16e37-112">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Type Information from Microsoft Office Assemblies](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100)) and [Walkthrough: Embedding Types from Managed Assemblies](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21).</span></span>

 <span data-ttu-id="16e37-113">Verwenden Sie zum Verweisen auf eine Interop-Assembly mit einem Befehlszeilencompiler und Einbetten von Typinformationen in Ihre ausführbaren Dateien die Compilerschalter [/Link (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/link-compiler-option.md) oder [/Link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md), und geben Sie den Namen der Interop-Assembly an.</span><span class="sxs-lookup"><span data-stu-id="16e37-113">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [/link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or the [/link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="16e37-114">Visual C++-Anwendungen können keine Typinformationen einbetten, aber sie können mit Anwendungen oder Add-Ins zusammenarbeiten, die dies können.</span><span class="sxs-lookup"><span data-stu-id="16e37-114">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>

 <span data-ttu-id="16e37-115">Verwenden Sie zum Kompilieren einer Anwendung, die bei der Bereitstellung eine primäre Interop-Assembly enthält, einen **/Referenz**-Compilerschalter, und geben Sie den Namen der Interop-Assembly an.</span><span class="sxs-lookup"><span data-stu-id="16e37-115">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="16e37-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16e37-116">See Also</span></span>

- [<span data-ttu-id="16e37-117">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="16e37-117">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="16e37-118">Sprachunabhängigkeit und sprachunabhängige Komponenten</span><span class="sxs-lookup"><span data-stu-id="16e37-118">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- <span data-ttu-id="16e37-119">[Verwenden von COM-Typen in verwaltetem Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="16e37-119">[Using COM Types in Managed Code](https://msdn.microsoft.com/library/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66(v=vs.100))</span></span>
- <span data-ttu-id="16e37-120">[Exemplarische Vorgehensweise: Einbetten von Typinformationen aus Microsoft Office-Assemblys](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="16e37-120">[Walkthrough: Embedding Type Information from Microsoft Office Assemblies](https://msdn.microsoft.com/library/85b55e05-bc5e-4665-b6ae-e1ada9299fd3(v=vs.100))</span></span>
- [<span data-ttu-id="16e37-121">Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys</span><span class="sxs-lookup"><span data-stu-id="16e37-121">Walkthrough: Embedding Types from Managed Assemblies</span></span>](https://msdn.microsoft.com/library/b28ec92c-1867-4847-95c0-61adfe095e21)
- [<span data-ttu-id="16e37-122">Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)</span><span class="sxs-lookup"><span data-stu-id="16e37-122">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)