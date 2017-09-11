---
title: 'Gewusst wie: Erstellen einer Einzeldateiassembly'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1a584e6ded79489e5e33b07d02dde618541c6cc8
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-build-a-single-file-assembly"></a><span data-ttu-id="79341-102">Gewusst wie: Erstellen einer Einzeldateiassembly</span><span class="sxs-lookup"><span data-stu-id="79341-102">How to: Build a Single-File Assembly</span></span>
<span data-ttu-id="79341-103">Eine Einzeldateiassembly, die den einfachsten Assemblytyp darstellt, enthält eine Typinformation und Implementierung sowie das [Assemblymanifest](../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="79341-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md).</span></span> <span data-ttu-id="79341-104">Sie können Befehlszeilencompiler oder [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] verwenden, um eine Einzeldateiassembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="79341-104">You can use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] to create a single-file assembly.</span></span> <span data-ttu-id="79341-105">Standardmäßig erstellt der Compiler eine Assemblydatei mit einer „.exe“-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="79341-105">By default, the compiler creates an assembly file with an .exe extension.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]<span data-ttu-id="79341-106"> für C# und Visual Basic kann nur genutzt werden, um Einzeldateiassemblys zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="79341-106"> for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="79341-107">Wenn Sie Mehrfachdateiassemblys erstellen möchten, müssen Sie Befehlszeilencompiler oder [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] für Visual C++ verwenden.</span><span class="sxs-lookup"><span data-stu-id="79341-107">If you want to create multifile assemblies, you must use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] for Visual C++.</span></span>  
  
 <span data-ttu-id="79341-108">Das folgende Verfahren zeigt Ihnen, wie Sie Einzeldateiassemblys mithilfe von Befehlszeilencompiler erstellen.</span><span class="sxs-lookup"><span data-stu-id="79341-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>  
  
### <a name="to-create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="79341-109">So erstellen Sie eine Assembly mit einer „.exe“-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="79341-109">To create an assembly with an .exe extension</span></span>  
  
1.  <span data-ttu-id="79341-110">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="79341-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="79341-111">\<*compilerbefehl*> \<*modulname*></span><span class="sxs-lookup"><span data-stu-id="79341-111">\<*compiler command*> \<*module name*></span></span>  
  
     <span data-ttu-id="79341-112">In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="79341-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="79341-113">Das folgende Beispiel erstellt eine Assembly namens `myCode.exe` aus einem Codemodul namens `myCode`.</span><span class="sxs-lookup"><span data-stu-id="79341-113">The following example creates an assembly named `myCode.exe` from a code module called `myCode`.</span></span>  
  
```csharp  
csc myCode.cs  
```  
  
```vb  
vbc myCode.vb  
```  
  
#### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="79341-114">So erstellen Sie eine Assembly mit einer „.exe“-Erweiterung und geben den Namen der Ausgabedatei an</span><span class="sxs-lookup"><span data-stu-id="79341-114">To create an assembly with an .exe extension and specify the output file name</span></span>  
  
1.  <span data-ttu-id="79341-115">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="79341-115">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="79341-116">\<*compilerbefehl*> **/out:**\<*dateiname*> \<*modulname*></span><span class="sxs-lookup"><span data-stu-id="79341-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>  
  
     <span data-ttu-id="79341-117">In diesem Befehl ist *compilerbefehl* der Compilerbefehl für die in Ihrem Codemodul verwendete Sprache, *dateiname* ist der Name der Ausgabedatei und *modulname* der Name des Codemodul, das in die Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="79341-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="79341-118">Das folgende Beispiel erstellt eine Assembly namens `myAssembly.exe` aus einem Codemodul namens `myCode`.</span><span class="sxs-lookup"><span data-stu-id="79341-118">The following example creates an assembly named `myAssembly.exe` from a code module called `myCode`.</span></span>  
  
```csharp  
csc /out:myAssembly.exe myCode.cs  
```  
  
```vb  
vbc /out:myAssembly.exe myCode.vb  
```  
  
## <a name="creating-library-assemblies"></a><span data-ttu-id="79341-119">Erstellen von Bibliothekassemblys</span><span class="sxs-lookup"><span data-stu-id="79341-119">Creating Library Assemblies</span></span>  
 <span data-ttu-id="79341-120">Eine Bibliotheksassembly ist ähnlich wie eine Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="79341-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="79341-121">Sie enthält Typen, die von anderen Assemblys verwiesen werden, jedoch besitzt sie keinen Einstiegspunkt zum Starten der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="79341-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>  
  
#### <a name="to-create-a-library-assembly"></a><span data-ttu-id="79341-122">So erstellen Sie eine Bibliotheksassembly</span><span class="sxs-lookup"><span data-stu-id="79341-122">To create a library assembly</span></span>  
  
1.  <span data-ttu-id="79341-123">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="79341-123">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="79341-124">\<*compilerbefehl*> **/t:library** \<*modulname*></span><span class="sxs-lookup"><span data-stu-id="79341-124">\<*compiler command*> **/t:library** \<*module name*></span></span>  
  
     <span data-ttu-id="79341-125">In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="79341-125">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="79341-126">Sie können auch andere Compileroptionen verwenden, z.B. die Option **/out:**.</span><span class="sxs-lookup"><span data-stu-id="79341-126">You can also use other compiler options, such as the **/out:** option.</span></span>  
  
 <span data-ttu-id="79341-127">Das folgende Beispiel erstellt eine Bibliotheksassembly namens `myCodeAssembly.dll` aus einem Codemodul namens `myCode`.</span><span class="sxs-lookup"><span data-stu-id="79341-127">The following example creates a library assembly named `myCodeAssembly.dll` from a code module called `myCode`.</span></span>  
  
```csharp  
csc /out:myCodeLibrary.dll /t:library myCode.cs  
```  
  
```vb  
vbc /out:myCodeLibrary.dll /t:library myCode.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="79341-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79341-128">See Also</span></span>  
 <span data-ttu-id="79341-129">[Erstellen von Assemblys](../../../docs/framework/app-domains/create-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="79341-129">[Creating Assemblies](../../../docs/framework/app-domains/create-assemblies.md) </span></span>  
 <span data-ttu-id="79341-130">[Mehrfachdateiassemblys](../../../docs/framework/app-domains/multifile-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="79341-130">[Multifile Assemblies](../../../docs/framework/app-domains/multifile-assemblies.md) </span></span>  
 <span data-ttu-id="79341-131">[Vorgehensweise: Erstellen einer Mehrfachdateiassembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md) </span><span class="sxs-lookup"><span data-stu-id="79341-131">[How to: Build a Multifile Assembly](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md) </span></span>  
 [<span data-ttu-id="79341-132">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="79341-132">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)

