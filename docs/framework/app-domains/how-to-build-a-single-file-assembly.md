---
title: 'Vorgehensweise: Erstellen einer Einzeldateiassembly'
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
ms.openlocfilehash: a73b2d8948c9a046fd77c02f1bcc87f5738105d9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303998"
---
# <a name="how-to-build-a-single-file-assembly"></a><span data-ttu-id="daafc-102">Vorgehensweise: Erstellen einer Einzeldateiassembly</span><span class="sxs-lookup"><span data-stu-id="daafc-102">How to: Build a Single-File Assembly</span></span>

<span data-ttu-id="daafc-103">Eine Einzeldateiassembly, die den einfachsten Assemblytyp darstellt, enthält eine Typinformation und Implementierung sowie das [Assemblymanifest](../../../docs/framework/app-domains/assembly-manifest.md).</span><span class="sxs-lookup"><span data-stu-id="daafc-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../../docs/framework/app-domains/assembly-manifest.md).</span></span> <span data-ttu-id="daafc-104">Sie können Befehlszeilencompiler oder Visual Studio verwenden, um eine Einzeldateiassembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="daafc-104">You can use command-line compilers or Visual Studio to create a single-file assembly.</span></span> <span data-ttu-id="daafc-105">Standardmäßig erstellt der Compiler eine Assemblydatei mit einer „.exe“-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="daafc-105">By default, the compiler creates an assembly file with an .exe extension.</span></span>

> [!NOTE]
> <span data-ttu-id="daafc-106">Mit Visual Studio für C# und Visual Basic können nur Einzeldateiassemblys erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="daafc-106">Visual Studio for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="daafc-107">Wenn Sie Mehrfachdateiassemblys erstellen möchten, müssen Sie Befehlszeilencompiler oder Visual C++ verwenden.</span><span class="sxs-lookup"><span data-stu-id="daafc-107">If you want to create multifile assemblies, you must use command-line compilers or Visual C++.</span></span>

<span data-ttu-id="daafc-108">Das folgende Verfahren zeigt Ihnen, wie Sie Einzeldateiassemblys mithilfe von Befehlszeilencompiler erstellen.</span><span class="sxs-lookup"><span data-stu-id="daafc-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>

## <a name="to-create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="daafc-109">So erstellen Sie eine Assembly mit einer „.exe“-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="daafc-109">To create an assembly with an .exe extension</span></span>

1. <span data-ttu-id="daafc-110">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="daafc-110">At the command prompt, type the following command:</span></span>

     <span data-ttu-id="daafc-111">\<*compilerbefehl*> \<*modulname*></span><span class="sxs-lookup"><span data-stu-id="daafc-111">\<*compiler command*> \<*module name*></span></span>

     <span data-ttu-id="daafc-112">In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="daafc-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>

 <span data-ttu-id="daafc-113">Das folgende Beispiel erstellt eine Assembly namens `myCode.exe` aus einem Codemodul namens `myCode`.</span><span class="sxs-lookup"><span data-stu-id="daafc-113">The following example creates an assembly named `myCode.exe` from a code module called `myCode`.</span></span>

```console
csc myCode.cs
```

```console
vbc myCode.vb
```

### <a name="to-create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="daafc-114">So erstellen Sie eine Assembly mit einer „.exe“-Erweiterung und geben den Namen der Ausgabedatei an</span><span class="sxs-lookup"><span data-stu-id="daafc-114">To create an assembly with an .exe extension and specify the output file name</span></span>

1. <span data-ttu-id="daafc-115">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="daafc-115">At the command prompt, type the following command:</span></span>

     <span data-ttu-id="daafc-116">\<*compilerbefehl*> **/out:**\<*dateiname*> \<*modulname*></span><span class="sxs-lookup"><span data-stu-id="daafc-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>

     <span data-ttu-id="daafc-117">In diesem Befehl ist *compilerbefehl* der Compilerbefehl für die in Ihrem Codemodul verwendete Sprache, *dateiname* ist der Name der Ausgabedatei und *modulname* der Name des Codemodul, das in die Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="daafc-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>

 <span data-ttu-id="daafc-118">Das folgende Beispiel erstellt eine Assembly namens `myAssembly.exe` aus einem Codemodul namens `myCode`.</span><span class="sxs-lookup"><span data-stu-id="daafc-118">The following example creates an assembly named `myAssembly.exe` from a code module called `myCode`.</span></span>

```console
csc -out:myAssembly.exe myCode.cs
```

```console
vbc -out:myAssembly.exe myCode.vb
```

## <a name="creating-library-assemblies"></a><span data-ttu-id="daafc-119">Erstellen von Bibliothekassemblys</span><span class="sxs-lookup"><span data-stu-id="daafc-119">Creating Library Assemblies</span></span>
 <span data-ttu-id="daafc-120">Eine Bibliotheksassembly ist ähnlich wie eine Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="daafc-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="daafc-121">Sie enthält Typen, die von anderen Assemblys verwiesen werden, jedoch besitzt sie keinen Einstiegspunkt zum Starten der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="daafc-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>

### <a name="to-create-a-library-assembly"></a><span data-ttu-id="daafc-122">So erstellen Sie eine Bibliotheksassembly</span><span class="sxs-lookup"><span data-stu-id="daafc-122">To create a library assembly</span></span>

1. <span data-ttu-id="daafc-123">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="daafc-123">At the command prompt, type the following command:</span></span>

     <span data-ttu-id="daafc-124">\<*Compilerbefehl*> **/t:library** \<*Modulname*></span><span class="sxs-lookup"><span data-stu-id="daafc-124">\<*compiler command*> **-t:library** \<*module name*></span></span>

     <span data-ttu-id="daafc-125">In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="daafc-125">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="daafc-126">Sie können auch andere Compileroptionen verwenden, z.B. die Option **-out:**.</span><span class="sxs-lookup"><span data-stu-id="daafc-126">You can also use other compiler options, such as the **-out:** option.</span></span>

 <span data-ttu-id="daafc-127">Das folgende Beispiel erstellt eine Bibliotheksassembly namens `myCodeAssembly.dll` aus einem Codemodul namens `myCode`.</span><span class="sxs-lookup"><span data-stu-id="daafc-127">The following example creates a library assembly named `myCodeAssembly.dll` from a code module called `myCode`.</span></span>

```console
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```console
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a><span data-ttu-id="daafc-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="daafc-128">See also</span></span>

- [<span data-ttu-id="daafc-129">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="daafc-129">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)
- [<span data-ttu-id="daafc-130">Mehrfachdateiassemblys</span><span class="sxs-lookup"><span data-stu-id="daafc-130">Multifile Assemblies</span></span>](../../../docs/framework/app-domains/multifile-assemblies.md)
- [<span data-ttu-id="daafc-131">Vorgehensweise: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="daafc-131">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="daafc-132">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="daafc-132">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)