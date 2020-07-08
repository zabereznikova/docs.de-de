---
title: Kompilieren eines Interop-Projekts
description: Erfahren Sie, wie ein COM-Interop-Projekt kompiliert wird, das wie eine verwaltetes Projekt kompiliert wird, wenn es auf eine oder mehrere Assemblys verweist, die importierte COM-Typen enthalten.
ms.date: 03/30/2017
helpviewer_keywords:
- interoperation with unmanaged code, compiling
- COM interop, compiling
- exposing COM components to .NET Framework
- compiling interop projects
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: 6fcf6588-5e25-41af-b4ae-780974f2c3df
ms.openlocfilehash: a8dfbeb88d0057eb3c9047b4435f021750ed86d2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620858"
---
# <a name="compiling-an-interop-project"></a><span data-ttu-id="4477f-103">Kompilieren eines Interop-Projekts</span><span class="sxs-lookup"><span data-stu-id="4477f-103">Compiling an Interop Project</span></span>

<span data-ttu-id="4477f-104">COM-Interop-Projekte, die auf eine oder mehrere Assemblys mit importierten COM-Typen verweisen, werden wie jedes andere verwaltete Projekt kompiliert.</span><span class="sxs-lookup"><span data-stu-id="4477f-104">COM interop projects that reference one or more assemblies containing imported COM types are compiled like any other managed project.</span></span> <span data-ttu-id="4477f-105">Sie können auf Interop-Assemblys in einer Entwicklungsumgebung wie Visual Studio verweisen, oder Sie können darauf verweisen, wenn Sie einen Befehlszeilencompiler verwenden.</span><span class="sxs-lookup"><span data-stu-id="4477f-105">You can reference interop assemblies in a development environment such as Visual Studio, or you can reference them when you use a command-line compiler.</span></span> <span data-ttu-id="4477f-106">In beiden Fällen muss die Interop-Assembly zur ordnungsgemäßen Kompilierung im selben Verzeichnis wie die anderen Projektdateien sein.</span><span class="sxs-lookup"><span data-stu-id="4477f-106">In either case, to compile properly, the interop assembly must be in the same directory as the other project files.</span></span>

 <span data-ttu-id="4477f-107">Es gibt zwei Möglichkeiten zur Verweisung auf Interop-Assemblys:</span><span class="sxs-lookup"><span data-stu-id="4477f-107">There are two ways to reference interop assemblies:</span></span>

- <span data-ttu-id="4477f-108">Eingebettete Interoptypen: Ab .NET Framework 4 und Visual Studio 2010 können Sie den Compiler anweisen, die Typinformationen aus einer Interopassembly in die ausführbare Datei einzubetten.</span><span class="sxs-lookup"><span data-stu-id="4477f-108">Embedded interop types: Beginning with the .NET Framework 4 and Visual Studio 2010, you can instruct the compiler to embed type information from an interop assembly into your executable.</span></span> <span data-ttu-id="4477f-109">Dies ist das empfohlene Verfahren.</span><span class="sxs-lookup"><span data-stu-id="4477f-109">This is the recommended technique.</span></span>

- <span data-ttu-id="4477f-110">Bereitstellen von Interopassemblys: Sie können einen Standardverweis auf eine Interopassembly erstellen.</span><span class="sxs-lookup"><span data-stu-id="4477f-110">Deploying interop assemblies: You can create a standard reference to an interop assembly.</span></span> <span data-ttu-id="4477f-111">In diesem Fall muss die Interop-Assembly mit Ihrer Anwendung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4477f-111">In this case, the interop assembly must be deployed with your application.</span></span>

 <span data-ttu-id="4477f-112">Die Unterschiede zwischen diesen beiden Verfahren werden ausführlich in [Verwenden von COM-Typen in verwaltetem Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)) erläutert.</span><span class="sxs-lookup"><span data-stu-id="4477f-112">The differences between these two techniques are discussed in greater detail in [Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100)).</span></span>

 <span data-ttu-id="4477f-113">Wie Interoptypen mit Visual Studio eingebettet werden, sehen Sie unter [Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio](../../standard/assembly/embed-types-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="4477f-113">Embedding interop types with Visual Studio is demonstrated in [Walkthrough: Embedding Types from Managed Assemblies in Visual Studio](../../standard/assembly/embed-types-visual-studio.md).</span></span>

 <span data-ttu-id="4477f-114">Verwenden Sie zum Verweisen auf eine Interop-Assembly mit einem Befehlszeilencompiler und Einbetten von Typinformationen in Ihre ausführbaren Dateien die Compilerschalter [-Link (C#-Compileroptionen)](../../csharp/language-reference/compiler-options/link-compiler-option.md) oder [-Link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md), und geben Sie den Namen der Interop-Assembly an.</span><span class="sxs-lookup"><span data-stu-id="4477f-114">To reference an interop assembly with a command-line compiler and embed type information in your executables, use the [-link (C# Compiler Options)](../../csharp/language-reference/compiler-options/link-compiler-option.md) or the [-link (Visual Basic)](../../visual-basic/reference/command-line-compiler/link.md) compiler switch and specify the name of the interop assembly.</span></span>

> [!NOTE]
> <span data-ttu-id="4477f-115">Visual C++-Anwendungen können keine Typinformationen einbetten, aber sie können mit Anwendungen oder Add-Ins zusammenarbeiten, die dies können.</span><span class="sxs-lookup"><span data-stu-id="4477f-115">Visual C++ applications cannot embed type information, but they can interoperate with applications or add-ins that do.</span></span>

 <span data-ttu-id="4477f-116">Verwenden Sie zum Kompilieren einer Anwendung, die bei der Bereitstellung eine primäre Interop-Assembly enthält, einen **/Referenz**-Compilerschalter, und geben Sie den Namen der Interop-Assembly an.</span><span class="sxs-lookup"><span data-stu-id="4477f-116">To compile an application that includes a primary interop assembly when it is deployed, use the **/reference** compiler switch and specify the name of the interop assembly.</span></span>

## <a name="see-also"></a><span data-ttu-id="4477f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4477f-117">See also</span></span>

- [<span data-ttu-id="4477f-118">Verfügbarmachen von COM-Komponenten für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="4477f-118">Exposing COM Components to the .NET Framework</span></span>](exposing-com-components.md)
- [<span data-ttu-id="4477f-119">Sprachunabhängigkeit und sprachunabhängige Komponenten</span><span class="sxs-lookup"><span data-stu-id="4477f-119">Language Independence and Language-Independent Components</span></span>](../../standard/language-independence-and-language-independent-components.md)
- <span data-ttu-id="4477f-120">[Verwenden von COM-Typen in verwaltetem Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4477f-120">[Using COM Types in Managed Code](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/3y76b69k(v=vs.100))</span></span>
- [<span data-ttu-id="4477f-121">Exemplarische Vorgehensweise: Einbetten von Typen aus verwalteten Assemblys in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4477f-121">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio</span></span>](../../standard/assembly/embed-types-visual-studio.md)
- [<span data-ttu-id="4477f-122">Importing a Type Library as an Assembly (Importieren einer Typbibliothek als Assembly)</span><span class="sxs-lookup"><span data-stu-id="4477f-122">Importing a Type Library as an Assembly</span></span>](importing-a-type-library-as-an-assembly.md)
