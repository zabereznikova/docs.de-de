---
title: 'Vorgehensweise: Erstellen einer Einzeldateiassembly für das .NET Framework'
ms.date: 08/20/2019
helpviewer_keywords:
- assembly manifest, single-file assemblies
- library assemblies
- command-line compilers
- assemblies [.NET Framework], single-file
- output file name for assemblies
- code modules
- single-file assemblies
dev_langs:
- csharp
- vb
ms.assetid: a6063221-43a5-4d3e-814c-288a4ec69aec
ms.openlocfilehash: b7cb06da74a21dab6f60f0d4c3ac1748fcbe4526
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81644302"
---
# <a name="how-to-build-a-net-framework-single-file-assembly"></a><span data-ttu-id="52d59-102">Vorgehensweise: Erstellen einer Einzeldateiassembly für das .NET Framework</span><span class="sxs-lookup"><span data-stu-id="52d59-102">How to: Build a .NET Framework single-file assembly</span></span>

<span data-ttu-id="52d59-103">Eine Einzeldateiassembly, die den einfachsten Assemblytyp darstellt, enthält eine Typinformation und Implementierung sowie das [Assemblymanifest](../../standard/assembly/manifest.md).</span><span class="sxs-lookup"><span data-stu-id="52d59-103">A single-file assembly, which is the simplest type of assembly, contains type information and implementation, as well as the [assembly manifest](../../standard/assembly/manifest.md).</span></span> <span data-ttu-id="52d59-104">Sie können Befehlszeilencompiler oder Visual Studio verwenden, um eine Einzeldateiassembly für das .NET Framework zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="52d59-104">You can use command-line compilers or Visual Studio to create a single-file assembly that targets the .NET Framework.</span></span> <span data-ttu-id="52d59-105">Standardmäßig erstellt der Compiler eine Assemblydatei mit einer *EXE*-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="52d59-105">By default, the compiler creates an assembly file with an *.exe* extension.</span></span>

> [!NOTE]
> <span data-ttu-id="52d59-106">Mit Visual Studio für C# und Visual Basic können nur Einzeldateiassemblys erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="52d59-106">Visual Studio for C# and Visual Basic can be used only to create single-file assemblies.</span></span> <span data-ttu-id="52d59-107">Wenn Sie Mehrfachdateiassemblys erstellen möchten, müssen Sie Befehlszeilencompiler oder Visual C++ verwenden.</span><span class="sxs-lookup"><span data-stu-id="52d59-107">If you want to create multifile assemblies, you must use command-line compilers or Visual C++.</span></span>

<span data-ttu-id="52d59-108">Das folgende Verfahren zeigt Ihnen, wie Sie Einzeldateiassemblys mithilfe von Befehlszeilencompiler erstellen.</span><span class="sxs-lookup"><span data-stu-id="52d59-108">The following procedures show how to create single-file assemblies using command-line compilers.</span></span>

## <a name="create-an-assembly-with-an-exe-extension"></a><span data-ttu-id="52d59-109">Erstellen einer Assembly mit einer EXE-Erweiterung</span><span class="sxs-lookup"><span data-stu-id="52d59-109">Create an assembly with an .exe extension</span></span>

<span data-ttu-id="52d59-110">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="52d59-110">At the command prompt, type the following command:</span></span>

<span data-ttu-id="52d59-111">\<*compilerbefehl*> \<*modulname*></span><span class="sxs-lookup"><span data-stu-id="52d59-111">\<*compiler command*> \<*module name*></span></span>

<span data-ttu-id="52d59-112">In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="52d59-112">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="52d59-113">Im folgenden Beispiel wird die Assembly *myCode.exe* aus dem Codemodul `myCode` erstellt.</span><span class="sxs-lookup"><span data-stu-id="52d59-113">The following example creates an assembly named *myCode.exe* from a code module called `myCode`.</span></span>

```csharp
csc myCode.cs
```

```vb
vbc myCode.vb
```

## <a name="create-an-assembly-with-an-exe-extension-and-specify-the-output-file-name"></a><span data-ttu-id="52d59-114">Erstellen einer Assembly mit einer EXE-Erweiterung und Benennen der Ausgabedatei</span><span class="sxs-lookup"><span data-stu-id="52d59-114">Create an assembly with an .exe extension and specify the output file name</span></span>

<span data-ttu-id="52d59-115">Geben Sie an der Eingabeaufforderung folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="52d59-115">At the command prompt, type the following command:</span></span>

<span data-ttu-id="52d59-116">\<*compilerbefehl*>  **/out:** \<*dateiname*> \<*modulname*></span><span class="sxs-lookup"><span data-stu-id="52d59-116">\<*compiler command*> **/out:**\<*file name*> \<*module name*></span></span>

<span data-ttu-id="52d59-117">In diesem Befehl ist *compilerbefehl* der Compilerbefehl für die in Ihrem Codemodul verwendete Sprache, *dateiname* ist der Name der Ausgabedatei und *modulname* der Name des Codemodul, das in die Assembly kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="52d59-117">In this command, *compiler command* is the compiler command for the language used in your code module, *file name* is the output file name, and *module name* is the name of the code module to compile into the assembly.</span></span>

<span data-ttu-id="52d59-118">Im folgenden Beispiel wird die Assembly *myAssembly.exe* aus dem Codemodul `myCode` erstellt.</span><span class="sxs-lookup"><span data-stu-id="52d59-118">The following example creates an assembly named *myAssembly.exe* from a code module called `myCode`.</span></span>

```csharp
csc -out:myAssembly.exe myCode.cs
```

```vb
vbc -out:myAssembly.exe myCode.vb
```

## <a name="create-library-assemblies"></a><span data-ttu-id="52d59-119">Erstellen von Bibliotheksassemblys</span><span class="sxs-lookup"><span data-stu-id="52d59-119">Create library assemblies</span></span>
 <span data-ttu-id="52d59-120">Eine Bibliotheksassembly ist ähnlich wie eine Klassenbibliothek.</span><span class="sxs-lookup"><span data-stu-id="52d59-120">A library assembly is similar to a class library.</span></span> <span data-ttu-id="52d59-121">Sie enthält Typen, die von anderen Assemblys verwiesen werden, jedoch besitzt sie keinen Einstiegspunkt zum Starten der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="52d59-121">It contains types that will be referenced by other assemblies, but it has no entry point to begin execution.</span></span>

<span data-ttu-id="52d59-122">Geben Sie über die Eingabeaufforderung den folgenden Befehl ein, um eine Bibliotheksassembly zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="52d59-122">To create a library assembly, at the command prompt, type the following command:</span></span>

<span data-ttu-id="52d59-123">\<*Compilerbefehl*>  **-t:Bibliothek** \<*Modulname*></span><span class="sxs-lookup"><span data-stu-id="52d59-123">\<*compiler command*> **-t:library** \<*module name*></span></span>

<span data-ttu-id="52d59-124">In diesem Befehl ist *compilername* der Compilerbefehl für die Sprache, die in Ihrem Codemodul verwendet wird, und *modulname* ist der Name des Codemoduls, um in die Assembly zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="52d59-124">In this command, *compiler command* is the compiler command for the language used in your code module, and *module name* is the name of the code module to compile into the assembly.</span></span> <span data-ttu-id="52d59-125">Sie können auch andere Compileroptionen verwenden, z.B. die Option **-out:** .</span><span class="sxs-lookup"><span data-stu-id="52d59-125">You can also use other compiler options, such as the **-out:** option.</span></span>

<span data-ttu-id="52d59-126">Im folgenden Beispiel wird die Bibliotheksassembly *myCodeAssembly.dll* aus dem Codemodul `myCode` erstellt.</span><span class="sxs-lookup"><span data-stu-id="52d59-126">The following example creates a library assembly named *myCodeAssembly.dll* from a code module called `myCode`.</span></span>

```csharp
csc -out:myCodeLibrary.dll -t:library myCode.cs
```

```vb
vbc -out:myCodeLibrary.dll -t:library myCode.vb
```

## <a name="see-also"></a><span data-ttu-id="52d59-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52d59-127">See also</span></span>

- [<span data-ttu-id="52d59-128">Erstellen von Assemblys</span><span class="sxs-lookup"><span data-stu-id="52d59-128">Create assemblies</span></span>](../../standard/assembly/create.md)
- [<span data-ttu-id="52d59-129">Mehrfachdateiassemblys</span><span class="sxs-lookup"><span data-stu-id="52d59-129">Multifile assemblies</span></span>](multifile-assemblies.md)
- [<span data-ttu-id="52d59-130">How to: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="52d59-130">How to: Build a multifile assembly</span></span>](build-multifile-assembly.md)
- [<span data-ttu-id="52d59-131">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="52d59-131">Program with assemblies</span></span>](../../standard/assembly/index.md)
