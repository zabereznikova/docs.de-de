---
title: Generieren und Kompilieren von Quellcode aus einem CodeDOM-Diagramm
description: Generieren und kompilieren Sie Quellcode aus einem CodeDOM-Graphen in .NET. Verwenden Sie einen CodeDOM-Codeanbieter zum Erstellen von Quellcode und kompilieren Sie Assemblys.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- code compilers
- CodeDOM, generating source code
- Code Document Object Model, graphs
- templated code generation
- source code, generating
- dynamically representing source code
- generating CodeDOM graphs
- Code Document Object Model, generating source code
- translating language to language
- compiling assemblies
- generating source code in multiple languages
- graphing with CodeDOM
- dynamic compilation
- assemblies [.NET Framework], CodeDOM
- source code generation
- outputting source code by CodeDOM
- code generators
- compiling source code, multiple languages
- CodeDOM, graphs
ms.assetid: 6c864c8e-6dd3-4a65-ace0-36879d9a9c42
ms.openlocfilehash: aec7d6b44e63558ae70bc0eb41f94e55c8a6c325
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266336"
---
# <a name="generating-and-compiling-source-code-from-a-codedom-graph"></a><span data-ttu-id="e6bce-104">Generieren und Kompilieren von Quellcode aus einem CodeDOM-Diagramm</span><span class="sxs-lookup"><span data-stu-id="e6bce-104">Generating and Compiling Source Code from a CodeDOM Graph</span></span>

<span data-ttu-id="e6bce-105">Der <xref:System.CodeDom.Compiler>-Namespace stellt Schnittstellen zum Generieren von Sourcecode aus CodeDOM-Objektdiagrammen und zum Verwalten der Kompilierung mit unterstützten Compilern bereit.</span><span class="sxs-lookup"><span data-stu-id="e6bce-105">The <xref:System.CodeDom.Compiler> namespace provides interfaces for generating source code from CodeDOM object graphs and for managing compilation with supported compilers.</span></span> <span data-ttu-id="e6bce-106">Ein Codeanbieter kann Quellcode in einer bestimmten Programmiersprache anhand eines CodeDOM-Diagramms erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6bce-106">A code provider can produce source code in a particular programming language according to a CodeDOM graph.</span></span> <span data-ttu-id="e6bce-107">Eine Klasse, die von <xref:System.CodeDom.Compiler.CodeDomProvider> abgeleitet wurde, kann in der Regel Methoden zum Generieren und Kompilieren von Code für die Sprache bereitstellen, die der Anbieter unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e6bce-107">A class that derives from <xref:System.CodeDom.Compiler.CodeDomProvider> can typically provide methods for generating and compiling code for the language the provider supports.</span></span>  
  
## <a name="using-a-codedom-code-provider-to-generate-source-code"></a><span data-ttu-id="e6bce-108">Verwenden eines CodeDOM-Codeanbieters zum Generieren von Quellcode</span><span class="sxs-lookup"><span data-stu-id="e6bce-108">Using a CodeDOM code provider to generate source code</span></span>  

 <span data-ttu-id="e6bce-109">Zum Generieren von Quellcode in einer bestimmten Sprache benötigen Sie ein CodeDOM-Diagramm, das die Struktur des zu generierenden Quellcode darstellt.</span><span class="sxs-lookup"><span data-stu-id="e6bce-109">To generate source code in a particular language, you need a CodeDOM graph that represents the structure of the source code to generate.</span></span>  
  
 <span data-ttu-id="e6bce-110">Im folgenden Beispiel wird veranschaulicht, wie eine Instanz einer <xref:Microsoft.CSharp.CSharpCodeProvider> erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="e6bce-110">The following example demonstrate how to create an instance of a <xref:Microsoft.CSharp.CSharpCodeProvider>:</span></span>  
  
 [!code-cpp[CodeDomExample#21](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#21)]
 [!code-csharp[CodeDomExample#21](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#21)]
 [!code-vb[CodeDomExample#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#21)]  
  
 <span data-ttu-id="e6bce-111">Das Diagramm für die Generierung von Code ist in der Regel Bestandteil einer <xref:System.CodeDom.CodeCompileUnit>.</span><span class="sxs-lookup"><span data-stu-id="e6bce-111">The graph for code generation is typically contained in a <xref:System.CodeDom.CodeCompileUnit>.</span></span> <span data-ttu-id="e6bce-112">Zum Generieren von Code für eine **CodeCompileUnit**, die ein CodeDOM-Diagramm enthält, rufen Sie die <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A>-Methode des Codeanbieters auf.</span><span class="sxs-lookup"><span data-stu-id="e6bce-112">To generate code for a **CodeCompileUnit** that contains a CodeDOM graph, call the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method of the code provider.</span></span> <span data-ttu-id="e6bce-113">Diese Methode verfügt einen Parameter für eine <xref:System.IO.TextWriter>, die zum Generieren des Quellcodes verwendet wird. Deshalb ist es manchmal erforderlich, zuerst eine **TextWriter**-Klasse zu erstellen, in die geschrieben werden kann.</span><span class="sxs-lookup"><span data-stu-id="e6bce-113">This method has a parameter for a <xref:System.IO.TextWriter> that it uses to generate the source code, so it is sometimes necessary to first create a **TextWriter** that can be written to.</span></span> <span data-ttu-id="e6bce-114">Das folgende Beispiel veranschaulicht die Erstellung von Code aus einer **CodeCompileUnit** und das Schreiben des generierten Quellcodes in eine Datei mit der Bezeichnung „HelloWorld.cs“.</span><span class="sxs-lookup"><span data-stu-id="e6bce-114">The following example demonstrates generating code from a **CodeCompileUnit** and writing the generated source code to a file named HelloWorld.cs.</span></span>  
  
 [!code-cpp[CodeDomExample#22](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#22)]
 [!code-csharp[CodeDomExample#22](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#22)]
 [!code-vb[CodeDomExample#22](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#22)]  
  
## <a name="using-a-codedom-code-provider-to-compile-assemblies"></a><span data-ttu-id="e6bce-115">Verwenden eines CodeDOM-Codeanbieters zum Kompilieren von Assemblys</span><span class="sxs-lookup"><span data-stu-id="e6bce-115">Using a CodeDOM code provider to compile assemblies</span></span>  

 <span data-ttu-id="e6bce-116">**Aufrufen der Kompilierung**</span><span class="sxs-lookup"><span data-stu-id="e6bce-116">**Invoking compilation**</span></span>  
  
 <span data-ttu-id="e6bce-117">Um eine Assembly mit einem CodeDom-Anbieter zu kompilieren, müssen Sie entweder Quellcode besitzen, um in eine Sprache zu kompilieren, für die Sie einen Compiler oder ein CodeDOM-Diagramm besitzen, von dem der zu kompilierende Quellcode generiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="e6bce-117">To compile an assembly using a CodeDom provider, you must have either source code to compile in a language for which you have a compiler, or a CodeDOM graph that source code to compile can be generated from.</span></span>  
  
 <span data-ttu-id="e6bce-118">Wenn Sie aus einem CodeDOM-Diagramm kompilieren, übergeben Sie die <xref:System.CodeDom.CodeCompileUnit> mit dem Diagramm an die <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A>-Methode des Codeanbieters.</span><span class="sxs-lookup"><span data-stu-id="e6bce-118">If you are compiling from a CodeDOM graph, pass the <xref:System.CodeDom.CodeCompileUnit> containing the graph to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A> method of the code provider.</span></span> <span data-ttu-id="e6bce-119">Wenn Sie über eine Quellcodedatei in einer Sprache verfügen, die der Compiler versteht, übergeben Sie den Namen der Datei, die den Quellcode enthält, an die <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A>-Methode des CodeDom-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="e6bce-119">If you have a source code file in a language that the compiler understands, pass the name of the file containing the source code to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A> method of the CodeDom provider.</span></span> <span data-ttu-id="e6bce-120">Sie können auch eine Zeichenfolge an die <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A>-Methode des CodeDom-Anbieters übergeben, die den Quellcode in einer Sprache enthält, die der Compiler versteht.</span><span class="sxs-lookup"><span data-stu-id="e6bce-120">You can also pass a string containing source code in a language that the compiler understands to the <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A> method of the CodeDom provider.</span></span>  
  
 <span data-ttu-id="e6bce-121">**Konfigurieren von Kompilierungsparametern**</span><span class="sxs-lookup"><span data-stu-id="e6bce-121">**Configuring compilation parameters**</span></span>  
  
 <span data-ttu-id="e6bce-122">Alle Standardmethoden zum Kompilierungsaufruf eines CodeDom-Anbieters besitzen einen Parameter vom Typ <xref:System.CodeDom.Compiler.CompilerParameters>, der die erforderlichen Optionen für die Kompilierung anzeigt.</span><span class="sxs-lookup"><span data-stu-id="e6bce-122">All of the standard compilation-invoking methods of a CodeDom provider have a parameter of type <xref:System.CodeDom.Compiler.CompilerParameters> that indicates the options to use for compilation.</span></span>  
  
 <span data-ttu-id="e6bce-123">Sie können den Dateinamen für die Ausgabeassembly in der <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A>-Eigenschaft der **CompilerParameters** angeben.</span><span class="sxs-lookup"><span data-stu-id="e6bce-123">You can specify a file name for the output assembly in the <xref:System.CodeDom.Compiler.CompilerParameters.OutputAssembly%2A> property of the **CompilerParameters**.</span></span> <span data-ttu-id="e6bce-124">Andererseits wird ein Standardname für die Ausgabedatei verwendet.</span><span class="sxs-lookup"><span data-stu-id="e6bce-124">Otherwise, a default output file name will be used.</span></span>  
  
 <span data-ttu-id="e6bce-125">Standardmäßig wird eine **CompilerParameters**-Klasse initialisiert, und deren Eigenschaft <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A> ist auf **FALSE** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e6bce-125">By default, a new **CompilerParameters** is initialized with its <xref:System.CodeDom.Compiler.CompilerParameters.GenerateExecutable%2A> property set to **false**.</span></span> <span data-ttu-id="e6bce-126">Wenn Sie ein ausführbares Programm kompilieren, müssen Sie die Eigenschaft **GenerateExecutable** auf **TRUE** festlegen.</span><span class="sxs-lookup"><span data-stu-id="e6bce-126">If you are compiling an executable program, you must set the **GenerateExecutable** property to **true**.</span></span> <span data-ttu-id="e6bce-127">Wenn die **GenerateExecutable** auf **FALSE** festgelegt ist, generiert der Compiler eine Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="e6bce-127">When the **GenerateExecutable** is set to **false**, the compiler will generate a class library.</span></span>  
  
 <span data-ttu-id="e6bce-128">Wenn Sie eine ausführbare Datei aus einem CodeDOM-Diagramm kompilieren, muss eine <xref:System.CodeDom.CodeEntryPointMethod> im Diagramm definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e6bce-128">If you are compiling an executable from a CodeDOM graph, a <xref:System.CodeDom.CodeEntryPointMethod> must be defined in the graph.</span></span> <span data-ttu-id="e6bce-129">Wenn es mehrere Codeeinstiegspunkte gibt, kann es womöglich erforderlich sein, die <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A>-Eigenschaft der **CompilerParameters** auf den Namen der Klasse festzulegen, die den zu verwendenden Einstiegspunkt definiert.</span><span class="sxs-lookup"><span data-stu-id="e6bce-129">If there are multiple code entry points, it may be necessary to set the <xref:System.CodeDom.Compiler.CompilerParameters.MainClass%2A> property of the **CompilerParameters** to the name of the class that defines the entry point to use.</span></span>  
  
 <span data-ttu-id="e6bce-130">Um die Debuginformation in eine generierte ausführbare Datei einzuschließen, legen Sie die <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A>-Eigenschaft auf **TRUE** fest.</span><span class="sxs-lookup"><span data-stu-id="e6bce-130">To include debug information in a generated executable, set the <xref:System.CodeDom.Compiler.CompilerParameters.IncludeDebugInformation%2A> property to **true**.</span></span>  
  
 <span data-ttu-id="e6bce-131">Wenn Ihr Projekt auf Assemblys verweist, müssen Sie die Assemblynamen als Elemente in einer <xref:System.Collections.Specialized.StringCollection> als <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A>-Eigenschaft der **CompilerParameters** angeben, die Sie beim Aufruf der Kompilierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6bce-131">If your project references any assemblies, you must specify the assembly names as items in a <xref:System.Collections.Specialized.StringCollection> as the <xref:System.CodeDom.Compiler.CompilerParameters.ReferencedAssemblies%2A> property of the **CompilerParameters** you use when invoking compilation.</span></span>  
  
 <span data-ttu-id="e6bce-132">Sie können eine Assembly kompilieren, die zum Speicher und nicht auf den Datenträger geschrieben wurde, indem Sie die <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A>-Eigenschaft auf **TRUE** festlegen.</span><span class="sxs-lookup"><span data-stu-id="e6bce-132">You can compile an assembly that is written to memory rather than disk by setting the <xref:System.CodeDom.Compiler.CompilerParameters.GenerateInMemory%2A> property to **true**.</span></span> <span data-ttu-id="e6bce-133">Wenn eine Assembly im Speicher generiert wird, kann Ihr Code einen Verweis aus einer <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A>-Eigenschaft einer <xref:System.CodeDom.Compiler.CompilerResults> für die generierte Assembly abrufen.</span><span class="sxs-lookup"><span data-stu-id="e6bce-133">When an assembly is generated in memory, your code can obtain a reference to the generated assembly from the <xref:System.CodeDom.Compiler.CompilerResults.CompiledAssembly%2A> property of a <xref:System.CodeDom.Compiler.CompilerResults>.</span></span> <span data-ttu-id="e6bce-134">Wenn eine Assembly auf den Datenträger geschrieben wird, können Sie den Pfad zur generierten Assembly aus einer <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A>-Eigenschaft einer **CompilerResults** abrufen.</span><span class="sxs-lookup"><span data-stu-id="e6bce-134">If an assembly is written to disk, you can obtain the path to the generated assembly from the <xref:System.CodeDom.Compiler.CompilerResults.PathToAssembly%2A> property of a **CompilerResults**.</span></span>  
  
 <span data-ttu-id="e6bce-135">Um einen benutzerdefinierte Argumentzeichenfolge auf Befehlszeilenebene anzugeben, die Sie beim Aufruf des Kompilierungsprozesses verwenden, legen Sie die Zeichenfolge in der <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A>-Eigenschaft fest.</span><span class="sxs-lookup"><span data-stu-id="e6bce-135">To specify a custom command-line arguments string to use when invoking the compilation process, set the string in the <xref:System.CodeDom.Compiler.CompilerParameters.CompilerOptions%2A> property.</span></span>  
  
 <span data-ttu-id="e6bce-136">Wenn ein Win32-Sicherheitstoken erforderlich ist, um den Compilerprozess auszurufen, geben Sie das Token in der <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="e6bce-136">If a Win32 security token is required to invoke the compiler process, specify the token in the <xref:System.CodeDom.Compiler.CompilerParameters.UserToken%2A> property.</span></span>  
  
 <span data-ttu-id="e6bce-137">Um eine Win32-Ressourcendatei in der kompilierten Assembly zu verknüpfen, geben Sie den Namen der Win32-Ressourcendatei in der <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A>-Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="e6bce-137">To link a Win32 resource file into the compiled assembly, specify the name of the Win32 resource file in the <xref:System.CodeDom.Compiler.CompilerParameters.Win32Resource%2A> property.</span></span>  
  
 <span data-ttu-id="e6bce-138">Wenn Sie eine Warnstufe angeben möchten, an der Sie die Kompilierung anhalten möchten, legen Sie die <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A>-Eigenschaft auf einen Integer fest, der die Warnstufe darstellt, an der die Kompilierung angehalten werden soll.</span><span class="sxs-lookup"><span data-stu-id="e6bce-138">To specify a warning level at which to halt compilation, set the <xref:System.CodeDom.Compiler.CompilerParameters.WarningLevel%2A> property to an integer that represents the warning level at which to halt compilation.</span></span> <span data-ttu-id="e6bce-139">Sie können auch den Compiler konfigurieren, um die Kompilierung anzuhalten, wenn Warnungen aufgetreten sind, indem Sie die <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A>-Eigenschaft auf **TRUE** festlegen.</span><span class="sxs-lookup"><span data-stu-id="e6bce-139">You can also configure the compiler to halt compilation if warnings are encountered by setting the <xref:System.CodeDom.Compiler.CompilerParameters.TreatWarningsAsErrors%2A> property to **true**.</span></span>  
  
 <span data-ttu-id="e6bce-140">Das folgende Codebeispiel stellt die Kompilierung einer Quelldatei mithilfe des CodeDom-Anbieters dar, der aus der <xref:System.CodeDom.Compiler.CodeDomProvider>-Klasse abgeleitet wurde.</span><span class="sxs-lookup"><span data-stu-id="e6bce-140">The following code example demonstrates compiling a source file using a CodeDom provider derived from the <xref:System.CodeDom.Compiler.CodeDomProvider> class.</span></span>  
  
 [!code-cpp[CodeDomExample#23](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeDomExample/CPP/source3.cpp#23)]
 [!code-csharp[CodeDomExample#23](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDomExample/CS/source3.cs#23)]
 [!code-vb[CodeDomExample#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDomExample/VB/source3.vb#23)]  
  
## <a name="languages-with-initial-support"></a><span data-ttu-id="e6bce-141">Sprachen mit erweiterter Unterstützung</span><span class="sxs-lookup"><span data-stu-id="e6bce-141">Languages with Initial Support</span></span>  

 <span data-ttu-id="e6bce-142">Das .NET Framework bietet Codecompiler für Codegeneratoren für die folgenden Sprachen: C#, Visual Basic, C++ und JScript.</span><span class="sxs-lookup"><span data-stu-id="e6bce-142">The .NET Framework provides code compilers and code generators for the following languages: C#, Visual Basic, C++, and JScript.</span></span> <span data-ttu-id="e6bce-143">Die CodeDOM-Unterstützung kann auf andere Sprachen durch Implementierung sprachspezifischer Codegeneratoren und Codecompiler erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="e6bce-143">CodeDOM support can be extended to other languages by implementing language-specific code generators and code compilers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6bce-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6bce-144">See also</span></span>

- <xref:System.CodeDom>
- <xref:System.CodeDom.Compiler>
- [<span data-ttu-id="e6bce-145">Generieren und Kompilieren von dynamischem Quellcode</span><span class="sxs-lookup"><span data-stu-id="e6bce-145">Dynamic Source Code Generation and Compilation</span></span>](dynamic-source-code-generation-and-compilation.md)
- <span data-ttu-id="e6bce-146">[Kurzreferenz zum CodeDOM](/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="e6bce-146">[CodeDOM Quick Reference](/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100))</span></span>
