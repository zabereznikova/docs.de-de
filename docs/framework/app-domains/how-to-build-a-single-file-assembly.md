---
title: 'Gewusst wie: Erstellen einer Einzeldateiassembly'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6aa39671da519ebf54dad52638ab940897209517
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-build-a-single-file-assembly"></a><span data-ttu-id="7afd6-102">Gewusst wie: Erstellen einer Einzeldateiassembly</span><span class="sxs-lookup"><span data-stu-id="7afd6-102">How to: Build a Single-File Assembly</span></span>
<span data-ttu-id="7afd6-103">Eine Einzeldateiassembly, die den einfachsten Assemblytyp darstellt, enthält eine Typinformation und Implementierung sowie das [Assemblymanifest](../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="7afd6-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md).</span></span> <span data-ttu-id="7afd6-104">Sie können Befehlszeilencompiler oder [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] verwenden, um eine Einzeldateiassembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7afd6-104">You can use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] to create a single-file assembly.</span></span> <span data-ttu-id="7afd6-105">Standardmäßig erstellt der Compiler eine Assemblydatei mit einer „.exe“-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="7afd6-105">By default, the compiler creates an assembly file with an .exe extension.</span></span>  
  
> [!NOTE]
>  [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]<span data-ttu-id="7afd6-106"> für C# und Visual Basic kann nur genutzt werden, um Einzeldateiassemblys zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7afd6-106"> for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="7afd6-107">Wenn Sie Mehrfachdateiassemblys erstellen möchten, müssen Sie Befehlszeilencompiler oder [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] für Visual C++ verwenden.</span><span class="sxs-lookup"><span data-stu-id="7afd6-107">If you want to create multifile assemblies, you must use command-line compilers or [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] for Visual C++.</span></span>  
  
 <span data-ttu-id="7afd6-108">Das folgende Verfahren zeigt Ihnen, wie Sie Einzeldateiassemblys mithilfe von Befehlszeilencompiler erstellen.</span><span class="sxs-lookup"><span data-stu-id="7afd6-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>  
  
### <a name="to-create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="7afd6-109">So erstellen Sie eine Assembly mit einer „.exe“-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="7afd6-109">To create an assembly with an .exe extension</span></span>  
  
1.  <span data-ttu-id="7afd6-110">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="7afd6-110">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="7afd6-111">\<*compilerbefehl*> \<*modulname*></span><span class="sxs-lookup"><span data-stu-id="7afd6-111">\<*compiler command*> \<*module name*></span></span>  
  
     <span data-ttu-id="7afd6-112">In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7afd6-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="7afd6-113">Das folgende Beispiel erstellt eine Assembly namens `myCode.exe` aus einem Codemodul namens `myCode`.</span><span class="sxs-lookup"><span data-stu-id="7afd6-113">The following example creates an assembly named `myCode.exe` from a code module called `myCode`.</span></span>  
  
```console
csc myCode.cs  
```  

```console
vbc myCode.vb  
```  
  
#### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="7afd6-114">So erstellen Sie eine Assembly mit einer „.exe“-Erweiterung und geben den Namen der Ausgabedatei an</span><span class="sxs-lookup"><span data-stu-id="7afd6-114">To create an assembly with an .exe extension and specify the output file name</span></span>  
  
1.  <span data-ttu-id="7afd6-115">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="7afd6-115">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="7afd6-116">\<*compilerbefehl*> **/out:**\<*dateiname*> \<*modulname*></span><span class="sxs-lookup"><span data-stu-id="7afd6-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>  
  
     <span data-ttu-id="7afd6-117">In diesem Befehl ist *compilerbefehl* der Compilerbefehl für die in Ihrem Codemodul verwendete Sprache, *dateiname* ist der Name der Ausgabedatei und *modulname* der Name des Codemodul, das in die Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="7afd6-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>  
  
 <span data-ttu-id="7afd6-118">Das folgende Beispiel erstellt eine Assembly namens `myAssembly.exe` aus einem Codemodul namens `myCode`.</span><span class="sxs-lookup"><span data-stu-id="7afd6-118">The following example creates an assembly named `myAssembly.exe` from a code module called `myCode`.</span></span>  
  
```console  
csc -out:myAssembly.exe myCode.cs  
```  
  
```console
vbc -out:myAssembly.exe myCode.vb  
```  
  
## <a name="creating-library-assemblies"></a><span data-ttu-id="7afd6-119">Erstellen von Bibliothekassemblys</span><span class="sxs-lookup"><span data-stu-id="7afd6-119">Creating Library Assemblies</span></span>  
 <span data-ttu-id="7afd6-120">Eine Bibliotheksassembly ist ähnlich wie eine Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="7afd6-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="7afd6-121">Sie enthält Typen, die von anderen Assemblys verwiesen werden, jedoch besitzt sie keinen Einstiegspunkt zum Starten der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="7afd6-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>  
  
#### <a name="to-create-a-library-assembly"></a><span data-ttu-id="7afd6-122">So erstellen Sie eine Bibliotheksassembly</span><span class="sxs-lookup"><span data-stu-id="7afd6-122">To create a library assembly</span></span>  
  
1.  <span data-ttu-id="7afd6-123">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="7afd6-123">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="7afd6-124">\<*Compilerbefehl*> **/t:library** \<*Modulname*></span><span class="sxs-lookup"><span data-stu-id="7afd6-124">\<*compiler command*> **-t:library** \<*module name*></span></span>  
  
     <span data-ttu-id="7afd6-125">In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="7afd6-125">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="7afd6-126">Sie können auch andere Compileroptionen verwenden, z.B. die Option **-out:**.</span><span class="sxs-lookup"><span data-stu-id="7afd6-126">You can also use other compiler options, such as the **-out:** option.</span></span>  
  
 <span data-ttu-id="7afd6-127">Das folgende Beispiel erstellt eine Bibliotheksassembly namens `myCodeAssembly.dll` aus einem Codemodul namens `myCode`.</span><span class="sxs-lookup"><span data-stu-id="7afd6-127">The following example creates a library assembly named `myCodeAssembly.dll` from a code module called `myCode`.</span></span>  
  
```console  
csc -out:myCodeLibrary.dll -t:library myCode.cs  
```  
  
```console
vbc -out:myCodeLibrary.dll -t:library myCode.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="7afd6-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7afd6-128">See Also</span></span>  
 [<span data-ttu-id="7afd6-129">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="7afd6-129">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
 [<span data-ttu-id="7afd6-130">Mehrfachdateiassemblys</span><span class="sxs-lookup"><span data-stu-id="7afd6-130">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)  
 [<span data-ttu-id="7afd6-131">Gewusst wie: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="7afd6-131">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 [<span data-ttu-id="7afd6-132">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="7afd6-132">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
