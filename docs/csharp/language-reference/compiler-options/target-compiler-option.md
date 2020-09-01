---
description: -target (C#-Compileroptionen)
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
ms.openlocfilehash: 5bfd988e8e399273dbd3292543a3730234c022d6
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128555"
---
# <a name="-target-c-compiler-options"></a><span data-ttu-id="b2883-103">-target (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="b2883-103">-target (C# Compiler Options)</span></span>
<span data-ttu-id="b2883-104">Die Compileroption **-target** kann in einem der folgenden Formate angegeben werden:</span><span class="sxs-lookup"><span data-stu-id="b2883-104">The **-target** compiler option can be specified in one of the following forms:</span></span>  
  
 [<span data-ttu-id="b2883-105">/target:appcontainerexe</span><span class="sxs-lookup"><span data-stu-id="b2883-105">-target:appcontainerexe</span></span>](./target-appcontainerexe-compiler-option.md)  
 <span data-ttu-id="b2883-106">So erstellen Sie eine EXE-Datei für Windows 8.x Store-Apps.</span><span class="sxs-lookup"><span data-stu-id="b2883-106">To create an .exe file for Windows 8.x Store apps.</span></span>  
  
 [<span data-ttu-id="b2883-107">/target:exe</span><span class="sxs-lookup"><span data-stu-id="b2883-107">-target:exe</span></span>](./target-exe-compiler-option.md)  
 <span data-ttu-id="b2883-108">So erstellen Sie eine EXE-Datei.</span><span class="sxs-lookup"><span data-stu-id="b2883-108">To create an .exe file.</span></span>  
  
 [<span data-ttu-id="b2883-109">/target:library</span><span class="sxs-lookup"><span data-stu-id="b2883-109">-target:library</span></span>](./target-library-compiler-option.md)  
 <span data-ttu-id="b2883-110">So erstellen Sie eine Codebibliothek.</span><span class="sxs-lookup"><span data-stu-id="b2883-110">To create a code library.</span></span>  
  
 [<span data-ttu-id="b2883-111">/target:module</span><span class="sxs-lookup"><span data-stu-id="b2883-111">-target:module</span></span>](./target-module-compiler-option.md)  
 <span data-ttu-id="b2883-112">So erstellen Sie ein Modul.</span><span class="sxs-lookup"><span data-stu-id="b2883-112">To create a module.</span></span>  
  
 [<span data-ttu-id="b2883-113">/target:winexe</span><span class="sxs-lookup"><span data-stu-id="b2883-113">-target:winexe</span></span>](./target-winexe-compiler-option.md)  
 <span data-ttu-id="b2883-114">So erstellen Sie ein Windows-Programm.</span><span class="sxs-lookup"><span data-stu-id="b2883-114">To create a Windows program.</span></span>  
  
 [<span data-ttu-id="b2883-115">/target:winmdobj</span><span class="sxs-lookup"><span data-stu-id="b2883-115">-target:winmdobj</span></span>](./target-winmdobj-compiler-option.md)  
 <span data-ttu-id="b2883-116">So erstellen Sie eine WINMDOBJ-Zwischendatei.</span><span class="sxs-lookup"><span data-stu-id="b2883-116">To create an intermediate .winmdobj file.</span></span>  
  
 <span data-ttu-id="b2883-117">Wenn Sie **-target:module** nicht angegeben haben, verursacht **-target**, dass ein .NET Framework-Assemblymanifest in einer Ausgabedatei platziert wird.</span><span class="sxs-lookup"><span data-stu-id="b2883-117">Unless you specify **-target:module**, **-target** causes a .NET Framework assembly manifest to be placed in an output file.</span></span> <span data-ttu-id="b2883-118">Weitere Informationen finden Sie unter [Assemblys in .NET](../../../standard/assembly/index.md) und [Häufig verwendete Attribute](../attributes/global.md).</span><span class="sxs-lookup"><span data-stu-id="b2883-118">For more information, see [Assemblies in .NET](../../../standard/assembly/index.md) and [Common Attributes](../attributes/global.md).</span></span>  
  
 <span data-ttu-id="b2883-119">Das Assemblymanifest wird in der ersten EXE-Ausgabedatei in der Kompilierung oder in der ersten DLL platziert, falls es keine EXE-Ausgabedatei gibt.</span><span class="sxs-lookup"><span data-stu-id="b2883-119">The assembly manifest is placed in the first .exe output file in the compilation or in the first DLL, if there is no .exe output file.</span></span> <span data-ttu-id="b2883-120">In der folgenden Befehlszeile wird das Manifest z.B. in `1.exe` platziert:</span><span class="sxs-lookup"><span data-stu-id="b2883-120">For example, in the following command line, the manifest will be placed in `1.exe`:</span></span>  
  
```console  
csc -out:1.exe t1.cs -out:2.netmodule t2.cs  
```  
  
 <span data-ttu-id="b2883-121">Der Compiler erstellt nur ein Assemblymanifest pro Kompilierung.</span><span class="sxs-lookup"><span data-stu-id="b2883-121">The compiler creates only one assembly manifest per compilation.</span></span> <span data-ttu-id="b2883-122">Informationen über alle Dateien in einer Kompilierung werden im Assemblymanifest platziert.</span><span class="sxs-lookup"><span data-stu-id="b2883-122">Information about all files in a compilation is placed in the assembly manifest.</span></span> <span data-ttu-id="b2883-123">Alle Ausgabedateien außer denen, die mit **-target:module** erstellt wurden, können ein Assemblymanifest enthalten.</span><span class="sxs-lookup"><span data-stu-id="b2883-123">All output files except those created with **-target:module** can contain an assembly manifest.</span></span> <span data-ttu-id="b2883-124">Wenn mehrere Ausgabedateien in der Befehlszeile erstellt werden, kann nur ein Assemblymanifest erstellt werden, und es muss in die erste Ausgabedatei gehen, die in der Befehlszeile angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b2883-124">When producing multiple output files at the command line, only one assembly manifest can be created and it must go into the first output file specified on the command line.</span></span> <span data-ttu-id="b2883-125">Unabhängig von der ersten Ausgabedatei ( **-target:exe**, **-target:winexe**, **-target:library** oder **-target:module**) müssen alle anderen Ausgabedateien, die in der selben Kompilierung erzeugt wurden, Module sein ( **-target:module**).</span><span class="sxs-lookup"><span data-stu-id="b2883-125">No matter what the first output file is (**-target:exe**, **-target:winexe**, **-target:library** or **-target:module**), any other output files produced in the same compilation must be modules (**-target:module**).</span></span>  
  
 <span data-ttu-id="b2883-126">Wenn Sie eine Assembly erstellen, können Sie angeben, dass der ganze oder ein Teil des Codes mit dem <xref:System.CLSCompliantAttribute>-Attribut CLS-kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="b2883-126">If you create an assembly, you can indicate that all or part of your code is CLS compliant with the <xref:System.CLSCompliantAttribute> attribute.</span></span>  
  
```csharp  
// target_clscompliant.cs  
[assembly:System.CLSCompliant(true)]   // specify assembly compliance  
  
[System.CLSCompliant(false)]   // specify compliance for an element  
public class TestClass  
{  
    public static void Main() {}  
}  
```  
  
 <span data-ttu-id="b2883-127">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span><span class="sxs-lookup"><span data-stu-id="b2883-127">For more information about setting this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2883-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2883-128">See also</span></span>

- [<span data-ttu-id="b2883-129">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="b2883-129">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="b2883-130">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="b2883-130">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="b2883-131">-subsystemversion (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="b2883-131">-subsystemversion (C# Compiler Options)</span></span>](./subsystemversion-compiler-option.md)
