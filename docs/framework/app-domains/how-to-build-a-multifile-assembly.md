---
title: 'Gewusst wie: Erstellen einer Mehrfachdateiassembly'
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
- vb
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- Al.exe
- command-line compilers
- assembly manifest, multifile assemblies
- assemblies [.NET Framework], compiling
- Assembly Linker
- code modules
- multifile assemblies
ms.assetid: 261c5583-8a76-412d-bda7-9b8ee3b131e5
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f77922d08ce17f8b8659eac0dba5a46ca33a7502
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-build-a-multifile-assembly"></a><span data-ttu-id="adf39-102">Gewusst wie: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="adf39-102">How to: Build a Multifile Assembly</span></span>
<span data-ttu-id="adf39-103">In diesem Artikel wird beschrieben, wie eine Mehrfachdateiassembly erstellt wird, und es wird Code vorgestellt, der jeden Schritt in der Vorgehensweise veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="adf39-103">This article explains how to create a multifile assembly and provides code that illustrates each step in the procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="adf39-104">Die Visual Studio-IDE für C# und Visual Basic kann nur zum Erstellen von Einzeldateiassemblys verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="adf39-104">The Visual Studio IDE for C# and Visual Basic can only be used to create single-file assemblies.</span></span> <span data-ttu-id="adf39-105">Wenn Sie Mehrfachdateiassemblys erstellen möchten, müssen Sie auf Befehlszeilencompiler oder auf Visual Studio mit Visual C++ zurückgreifen.</span><span class="sxs-lookup"><span data-stu-id="adf39-105">If you want to create multifile assemblies, you must use the command-line compilers or Visual Studio with Visual C++.</span></span>  
  
### <a name="to-create-a-multifile-assembly"></a><span data-ttu-id="adf39-106">So erstellen Sie eine Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="adf39-106">To create a multifile assembly</span></span>  
  
1.  <span data-ttu-id="adf39-107">Kompilieren Sie alle Dateien mit Namespaces, auf die andere Module der Assembly verweisen, in Codemodule.</span><span class="sxs-lookup"><span data-stu-id="adf39-107">Compile all files that contain namespaces referenced by other modules in the assembly into code modules.</span></span> <span data-ttu-id="adf39-108">Die Standarderweiterung für Codemodule ist "netmodule".</span><span class="sxs-lookup"><span data-stu-id="adf39-108">The default extension for code modules is .netmodule.</span></span>  
  
     <span data-ttu-id="adf39-109">Beispielsweise weist die Datei `Stringer` den Namespace `myStringer` auf, der die Klasse `Stringer` enthält.</span><span class="sxs-lookup"><span data-stu-id="adf39-109">For example, let's say the `Stringer` file has a namespace called `myStringer`, which includes a class called `Stringer`.</span></span> <span data-ttu-id="adf39-110">Die `Stringer`-Klasse enthält die `StringerMethod`-Methode, die eine einzelne Zeile auf der Konsole ausgibt.</span><span class="sxs-lookup"><span data-stu-id="adf39-110">The `Stringer` class contains a method called `StringerMethod` that writes a single line to the console.</span></span>  
  
     [!code-cpp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#1)]
     [!code-csharp[Conceptual.Assembly.Multifile#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#1)]
     [!code-vb[Conceptual.Assembly.Multifile#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#1)]  
  
     <span data-ttu-id="adf39-111">Verwenden Sie folgenden Befehl, um diesen Code zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="adf39-111">Use the following command to compile this code:</span></span>  
  
     [!code-cpp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/stringer.cpp#2)]
     [!code-csharp[Conceptual.Assembly.Multifile#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/stringer.cs#2)]
     [!code-vb[Conceptual.Assembly.Multifile#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/stringer.vb#2)]  
  
     <span data-ttu-id="adf39-112">Durch die Compileroption **/t:** in Verbindung mit dem Parameter *module* wird die Datei als Modul kompiliert, nicht als Assembly.</span><span class="sxs-lookup"><span data-stu-id="adf39-112">Specifying the *module* parameter with the **/t:** compiler option indicates that the file should be compiled as a module rather than as an assembly.</span></span> <span data-ttu-id="adf39-113">Der Compiler erzeugt ein Modul mit dem Namen `Stringer.netmodule`, das anschließend einer Assembly hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="adf39-113">The compiler produces a module called `Stringer.netmodule`, which can be added to an assembly.</span></span>  
  
2.  <span data-ttu-id="adf39-114">Kompilieren Sie alle weiteren Module unter Verwendung der erforderlichen Compileroptionen, um die anderen Module anzugeben, auf die im Code verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="adf39-114">Compile all other modules, using the necessary compiler options to indicate the other modules that are referenced in the code.</span></span> <span data-ttu-id="adf39-115">In diesem Schritt kommt die **/addmodule**-Compileroption zum Einsatz.</span><span class="sxs-lookup"><span data-stu-id="adf39-115">This step uses the **/addmodule** compiler option.</span></span>  
  
     <span data-ttu-id="adf39-116">Im folgenden Beispiel verfügt ein Codemodul mit dem Namen `Client` über die `Main`-Methode als Einstiegspunkt. Diese verweist wiederum auf eine Methode im `Stringer.dll`-Modul, das in Schritt 1 erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="adf39-116">In the following example, a code module called `Client` has an entry point `Main` method that references a method in the `Stringer.dll` module created in step 1.</span></span>  
  
     [!code-cpp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#3)]
     [!code-csharp[Conceptual.Assembly.Multifile#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#3)]
     [!code-vb[Conceptual.Assembly.Multifile#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#3)]  
  
     <span data-ttu-id="adf39-117">Verwenden Sie folgenden Befehl, um diesen Code zu kompilieren:</span><span class="sxs-lookup"><span data-stu-id="adf39-117">Use the following command to compile this code:</span></span>  
  
     [!code-cpp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#4)]
     [!code-csharp[Conceptual.Assembly.Multifile#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#4)]
     [!code-vb[Conceptual.Assembly.Multifile#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#4)]  
  
     <span data-ttu-id="adf39-118">Verwenden Sie die Option **/t:module**, da dieses Modul in einem späteren Schritt zu einer Assembly hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="adf39-118">Specify the **/t:module** option because this module will be added to an assembly in a future step.</span></span> <span data-ttu-id="adf39-119">Legen Sie die **/addmodule**-Option fest, da der Code in `Client` auf einen Namespace verweist, der vom Code in `Stringer.netmodule` erzeugt wurde.</span><span class="sxs-lookup"><span data-stu-id="adf39-119">Specify the **/addmodule** option because the code in `Client` references a namespace created by the code in `Stringer.netmodule`.</span></span> <span data-ttu-id="adf39-120">Der Compiler erzeugt ein Modul mit dem Namen `Client.netmodule`, das einen Verweis auf ein anderes Modul, `Stringer.netmodule`, enthält.</span><span class="sxs-lookup"><span data-stu-id="adf39-120">The compiler produces a module called `Client.netmodule` that contains a reference to another module, `Stringer.netmodule`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="adf39-121">Die C#- und Visual Basic-Compiler unterstützen das direkte Erstellen von Mehrfachdateiassemblys unter Verwendung der beiden folgenden unterschiedlichen Syntaxformen.</span><span class="sxs-lookup"><span data-stu-id="adf39-121">The C# and Visual Basic compilers support directly creating multifile assemblies using the following two different syntaxes.</span></span>  
    >   
    >  -   <span data-ttu-id="adf39-122">Zwei Kompilierungen erzeugen eine aus zwei Dateien bestehende Assembly:</span><span class="sxs-lookup"><span data-stu-id="adf39-122">Two compilations create a two-file assembly:</span></span>  
    >   
    >      [!code-cpp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#5)]
      [!code-csharp[Conceptual.Assembly.Multifile#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#5)]
      [!code-vb[Conceptual.Assembly.Multifile#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#5)]  
    > -   <span data-ttu-id="adf39-123">Eine Kompilierung erzeugt eine aus zwei Dateien bestehende Assembly:</span><span class="sxs-lookup"><span data-stu-id="adf39-123">One compilation creates a two-file assembly:</span></span>  
    >   
    >      [!code-cpp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.assembly.multifile/cpp/client.cpp#6)]
      [!code-csharp[Conceptual.Assembly.Multifile#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.assembly.multifile/cs/client.cs#6)]
      [!code-vb[Conceptual.Assembly.Multifile#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.assembly.multifile/vb/client.vb#6)]  
  
3.  <span data-ttu-id="adf39-124">Erstellen Sie mit dem [Assembly Linker-Tool (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) eine Ausgabedatei, die das Assemblymanifest enthält.</span><span class="sxs-lookup"><span data-stu-id="adf39-124">Use the [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md) to create the output file that contains the assembly manifest.</span></span> <span data-ttu-id="adf39-125">In dieser Datei sind Referenzinformationen zu allen zur Assembly gehörenden Modulen und Ressourcen enthalten.</span><span class="sxs-lookup"><span data-stu-id="adf39-125">This file contains reference information for all modules or resources that are part of the assembly.</span></span>  
  
     <span data-ttu-id="adf39-126">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="adf39-126">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="adf39-127">**al** \<*modulname*> \<*modulname*> …</span><span class="sxs-lookup"><span data-stu-id="adf39-127">**al** \<*module name*> \<*module name*> …</span></span> <span data-ttu-id="adf39-128">**/main:**\<*Methodenname*> **/out:**\<*Dateiname*> **/target:**\<*Assemblydateityp*></span><span class="sxs-lookup"><span data-stu-id="adf39-128">**/main:**\<*method name*> **/out:**\<*file name*> **/target:**\<*assembly file type*></span></span>  
  
     <span data-ttu-id="adf39-129">In diesem Befehl bezeichnen die *Modulname*-Argumente die Namen aller Module, die in der Assembly enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="adf39-129">In this command, the *module name* arguments specify the name of each module to include in the assembly.</span></span> <span data-ttu-id="adf39-130">Die Option **/main:** gibt den Methodennamen an, der den Einstiegspunkt der Assembly darstellt.</span><span class="sxs-lookup"><span data-stu-id="adf39-130">The **/main:** option specifies the method name that is the assembly's entry point.</span></span> <span data-ttu-id="adf39-131">Die Option **/out:** gibt den Namen der Ausgabedatei an, die Assemblymetadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="adf39-131">The **/out:** option specifies the name of the output file, which contains assembly metadata.</span></span> <span data-ttu-id="adf39-132">Die Option **/target:** gibt an, dass die Assembly eine ausführbare Datei für eine Konsolenanwendung (.exe), eine ausführbare Windows-Datei (.win) oder eine Bibliothek ist (.lib).</span><span class="sxs-lookup"><span data-stu-id="adf39-132">The **/target:** option specifies that the assembly is a console application executable (.exe) file, a Windows executable (.win) file, or a library (.lib) file.</span></span>  
  
     <span data-ttu-id="adf39-133">Im folgenden Beispiel erstellt Al.exe`myAssembly.exe` eine Assembly mit dem Namen , die eine ausführbare Datei für eine Konsolenanwendung ist.</span><span class="sxs-lookup"><span data-stu-id="adf39-133">In the following example, Al.exe creates an assembly that is a console application executable called `myAssembly.exe`.</span></span> <span data-ttu-id="adf39-134">Die Anwendung besteht aus zwei Modulen, `Client.netmodule` und `Stringer.netmodule`, sowie der ausführbaren Datei `myAssembly.exe,`, die ausschließlich Assemblymetadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="adf39-134">The application consists of two modules called `Client.netmodule` and `Stringer.netmodule`, and the executable file called `myAssembly.exe,` which contains only assembly metadata .</span></span> <span data-ttu-id="adf39-135">Der Einstiegspunkt der Assembly ist die `Main`-Methode in der `MainClientApp`-Klasse, die sich in der Datei `Client.dll` befindet.</span><span class="sxs-lookup"><span data-stu-id="adf39-135">The entry point of the assembly is the `Main` method in the class `MainClientApp`, which is located in `Client.dll`.</span></span>  
  
    ```  
    al Client.netmodule Stringer.netmodule /main:MainClientApp.Main /out:myAssembly.exe /target:exe   
    ```  
  
     <span data-ttu-id="adf39-136">Sie können das [MSIL Disassembler-Tool (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) verwenden, um den Inhalt einer Assembly zu untersuchen oder um zu bestimmen, ob es sich bei einer Datei um eine Assembly oder ein Modul handelt.</span><span class="sxs-lookup"><span data-stu-id="adf39-136">You can use the [MSIL Disassembler (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the contents of an assembly, or determine whether a file is an assembly or a module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adf39-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="adf39-137">See Also</span></span>  
 [<span data-ttu-id="adf39-138">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="adf39-138">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="adf39-139">Gewusst wie: Anzeigen des Assemblyinhalts</span><span class="sxs-lookup"><span data-stu-id="adf39-139">How to: View Assembly Contents</span></span>](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 [<span data-ttu-id="adf39-140">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="adf39-140">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="adf39-141">Mehrfachdateiassemblys</span><span class="sxs-lookup"><span data-stu-id="adf39-141">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
