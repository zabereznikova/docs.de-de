---
title: -target (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /target
helpviewer_keywords:
- target compiler options [C#]
- /target compiler options [C#]
- assemblies [C#], compiling
- -target compiler options [C#]
ms.assetid: a18bbd8e-bbf7-49e7-992c-717d0eb1f76f
ms.openlocfilehash: af7bd917f57c8752a2026fbb98aa8b22adc98db7
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204520"
---
# <a name="-target-c-compiler-options"></a><span data-ttu-id="d9b93-102">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="d9b93-102">-target (C# Compiler Options)</span></span>
<span data-ttu-id="d9b93-103">Die Compileroption **-target** kann in einem von vier Formaten angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="d9b93-103">The **-target** compiler option can be specified in one of four forms:</span></span>  
  
 [<span data-ttu-id="d9b93-104">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="d9b93-104">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)  
 <span data-ttu-id="d9b93-105">So erstellen Sie eine EXE-Datei für Windows 8.x Store-Apps.</span><span class="sxs-lookup"><span data-stu-id="d9b93-105">To create an .exe file for Windows 8.x Store apps.</span></span>  
  
 [<span data-ttu-id="d9b93-106">/target:exe</span><span class="sxs-lookup"><span data-stu-id="d9b93-106">-target:exe</span></span>](./target-exe-compiler-option.md)  
 <span data-ttu-id="d9b93-107">So erstellen Sie eine EXE-Datei.</span><span class="sxs-lookup"><span data-stu-id="d9b93-107">To create an .exe file.</span></span>  
  
 [<span data-ttu-id="d9b93-108">/target:library</span><span class="sxs-lookup"><span data-stu-id="d9b93-108">-target:library</span></span>](./target-library-compiler-option.md)  
 <span data-ttu-id="d9b93-109">So erstellen Sie eine Codebibliothek.</span><span class="sxs-lookup"><span data-stu-id="d9b93-109">To create a code library.</span></span>  
  
 [<span data-ttu-id="d9b93-110">/target:module</span><span class="sxs-lookup"><span data-stu-id="d9b93-110">-target:module</span></span>](./target-module-compiler-option.md)  
 <span data-ttu-id="d9b93-111">So erstellen Sie ein Modul.</span><span class="sxs-lookup"><span data-stu-id="d9b93-111">To create a module.</span></span>  
  
 [<span data-ttu-id="d9b93-112">/target:winexe</span><span class="sxs-lookup"><span data-stu-id="d9b93-112">-target:winexe</span></span>](./target-winexe-compiler-option.md)  
 <span data-ttu-id="d9b93-113">So erstellen Sie ein Windows-Programm.</span><span class="sxs-lookup"><span data-stu-id="d9b93-113">To create a Windows program.</span></span>  
  
 [<span data-ttu-id="d9b93-114">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="d9b93-114">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)  
 <span data-ttu-id="d9b93-115">So erstellen Sie eine WINMDOBJ-Zwischendatei.</span><span class="sxs-lookup"><span data-stu-id="d9b93-115">To create an intermediate .winmdobj file.</span></span>  
  
 <span data-ttu-id="d9b93-116">Wenn Sie **-target:module** nicht angegeben haben, verursacht **-target**, dass ein .NET Framework-Assemblymanifest in einer Ausgabedatei platziert wird.</span><span class="sxs-lookup"><span data-stu-id="d9b93-116">Unless you specify **-target:module**, **-target** causes a .NET Framework assembly manifest to be placed in an output file.</span></span> <span data-ttu-id="d9b93-117">Weitere Informationen finden Sie unter [Assemblys in .NET](../../../standard/assembly/index.md) und [Häufig verwendete Attribute](../../programming-guide/concepts/attributes/common-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="d9b93-117">For more information, see [Assemblies in .NET](../../../standard/assembly/index.md) and [Common Attributes](../../programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
 <span data-ttu-id="d9b93-118">Das Assemblymanifest wird in der ersten EXE-Ausgabedatei in der Kompilierung oder in der ersten DLL platziert, falls es keine EXE-Ausgabedatei gibt.</span><span class="sxs-lookup"><span data-stu-id="d9b93-118">The assembly manifest is placed in the first .exe output file in the compilation or in the first DLL, if there is no .exe output file.</span></span> <span data-ttu-id="d9b93-119">In der folgenden Befehlszeile wird das Manifest z.B. in `1.exe` platziert:</span><span class="sxs-lookup"><span data-stu-id="d9b93-119">For example, in the following command line, the manifest will be placed in `1.exe`:</span></span>  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 <span data-ttu-id="d9b93-120">Der Compiler erstellt nur ein Assemblymanifest pro Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="d9b93-120">The compiler creates only one assembly manifest per compilation.</span></span> <span data-ttu-id="d9b93-121">Informationen über alle Dateien in einer Kompilierung werden im Assemblymanifest platziert.</span><span class="sxs-lookup"><span data-stu-id="d9b93-121">Information about all files in a compilation is placed in the assembly manifest.</span></span> <span data-ttu-id="d9b93-122">Alle Ausgabedateien außer denen, die mit **-target:module** erstellt wurden, können ein Assemblymanifest enthalten.</span><span class="sxs-lookup"><span data-stu-id="d9b93-122">All output files except those created with **-target:module** can contain an assembly manifest.</span></span> <span data-ttu-id="d9b93-123">Wenn mehrere Ausgabedateien in der Befehlszeile erstellt werden, kann nur ein Assemblymanifest erstellt werden, und es muss in die erste Ausgabedatei gehen, die in der Befehlszeile angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d9b93-123">When producing multiple output files at the command line, only one assembly manifest can be created and it must go into the first output file specified on the command line.</span></span> <span data-ttu-id="d9b93-124">Unabhängig von der ersten Ausgabedatei ( **-target:exe**, **-target:winexe**, **-target:library** oder **-target:module**) müssen alle anderen Ausgabedateien, die in der selben Kompilierung erzeugt wurden, Module sein ( **-target:module**).</span><span class="sxs-lookup"><span data-stu-id="d9b93-124">No matter what the first output file is (**-target:exe**, **-target:winexe**, **-target:library** or **-target:module**), any other output files produced in the same compilation must be modules (**-target:module**).</span></span>  
  
 <span data-ttu-id="d9b93-125">Wenn Sie eine Assembly erstellen, können Sie angeben, dass der ganze oder ein Teil des Codes mit dem <xref:System.CLSCompliantAttribute>-Attribut CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="d9b93-125">If you create an assembly, you can indicate that all or part of your code is CLS compliant with the <xref:System.CLSCompliantAttribute> attribute.</span></span>  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 <span data-ttu-id="d9b93-126">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="d9b93-126">For more information about setting this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9b93-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9b93-127">See also</span></span>

- [<span data-ttu-id="d9b93-128">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="d9b93-128">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="d9b93-129">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="d9b93-129">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="d9b93-130">-subsystemversion (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="d9b93-130">-subsystemversion (C# Compiler Options)</span></span>](./subsystemversion-compiler-option.md)
