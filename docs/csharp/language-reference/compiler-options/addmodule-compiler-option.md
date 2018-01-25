---
title: -addmodule (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
caps.latest.revision: "13"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: db440b58862e372e443c9c51961b0c3cc2dd211e
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-addmodule-c-compiler-options"></a><span data-ttu-id="8b79e-102">-addmodule (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="8b79e-102">-addmodule (C# Compiler Options)</span></span>
<span data-ttu-id="8b79e-103">Mit dieser Option wird ein Modul hinzugefügt, das mit dem Schalter „target:mocule“ in der aktuellen Kompilierung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8b79e-103">This option adds a module that was created with the target:module switch to the current compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b79e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b79e-104">Syntax</span></span>  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a><span data-ttu-id="8b79e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="8b79e-105">Arguments</span></span>  
 <span data-ttu-id="8b79e-106">`file`, `file2`</span><span class="sxs-lookup"><span data-stu-id="8b79e-106">`file`, `file2`</span></span>  
 <span data-ttu-id="8b79e-107">Eine Ausgabedatei, die Metadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="8b79e-107">An output file that contains metadata.</span></span> <span data-ttu-id="8b79e-108">Die Datei kann kein Assemblymanifest enthalten.</span><span class="sxs-lookup"><span data-stu-id="8b79e-108">The file cannot contain an assembly manifest.</span></span> <span data-ttu-id="8b79e-109">Trennen Sie die Dateinamen entweder mit einem Komma oder einem Semikolon, um mehr als eine Datei zu importieren.</span><span class="sxs-lookup"><span data-stu-id="8b79e-109">To import more than one file, separate file names with either a comma or a semicolon.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b79e-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b79e-110">Remarks</span></span>  
 <span data-ttu-id="8b79e-111">Alle Module, die mit **-addmodule** hinzugefügt werden, müssen sich zur Laufzeit im gleichen Verzeichnis wie die Ausgabedatei befinden.</span><span class="sxs-lookup"><span data-stu-id="8b79e-111">All modules added with **-addmodule** must be in the same directory as the output file at run time.</span></span> <span data-ttu-id="8b79e-112">Das bedeutet, dass Sie zur Kompilierzeit ein beliebiges Modul in einem Verzeichnis angeben können, sich das Modul aber zur Laufzeit im Anwendungsverzeichnis befinden muss.</span><span class="sxs-lookup"><span data-stu-id="8b79e-112">That is, you can specify a module in any directory at compile time but the module must be in the application directory at run time.</span></span> <span data-ttu-id="8b79e-113">Wenn sich das Modul zur Laufzeit nicht im Anwendungsverzeichnis befindet, wird eine <xref:System.TypeLoadException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="8b79e-113">If the module is not in the application directory at run time, you will get a <xref:System.TypeLoadException>.</span></span>  
  
 <span data-ttu-id="8b79e-114">`file` kann keine Assembly enthalten.</span><span class="sxs-lookup"><span data-stu-id="8b79e-114">`file` cannot contain an assembly.</span></span> <span data-ttu-id="8b79e-115">Wenn die Ausgabedatei z.B. mit [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) erstellt wurde, können die Metadaten mit **-addmodule** importiert werden.</span><span class="sxs-lookup"><span data-stu-id="8b79e-115">For example, if the output file was created with [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), its metadata can be imported with **-addmodule**.</span></span>  
  
 <span data-ttu-id="8b79e-116">Wenn die Ausgabedatei mit einer anderen **-target**-Option als **-target:module** erstellt wurde, können die Metadaten nicht mit **-addmodule** importiert werden. Stattdessen werden sie mit [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md) importiert.</span><span class="sxs-lookup"><span data-stu-id="8b79e-116">If the output file was created with a **-target** option other than **-target:module**, its metadata cannot be imported with **-addmodule** but can be imported with [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="8b79e-117">Diese Compileroption steht in Visual Studio nicht zur Verfügung, da ein Projekt nicht auf ein Modul verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="8b79e-117">This compiler option is unavailable in Visual Studio; a project cannot reference a module.</span></span> <span data-ttu-id="8b79e-118">Des Weiteren kann diese Compileroption nicht programmgesteuert geändert werden.</span><span class="sxs-lookup"><span data-stu-id="8b79e-118">In addition, this compiler option cannot be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b79e-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b79e-119">Example</span></span>  
 <span data-ttu-id="8b79e-120">Kompilieren Sie die Quelldatei `input.cs`, und fügen Sie Metadaten aus `metad1.netmodule` und `metad2.netmodule` hinzu, um `out.exe` zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="8b79e-120">Compile source file `input.cs` and add metadata from `metad1.netmodule` and `metad2.netmodule` to produce `out.exe`:</span></span>  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b79e-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b79e-121">See Also</span></span>  
 [<span data-ttu-id="8b79e-122">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="8b79e-122">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="8b79e-123">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8b79e-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="8b79e-124">Mehrfachdateiassemblys</span><span class="sxs-lookup"><span data-stu-id="8b79e-124">Multifile Assemblies</span></span>](../../../framework/app-domains/multifile-assemblies.md)  
 [<span data-ttu-id="8b79e-125">Gewusst wie: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="8b79e-125">How to: Build a Multifile Assembly</span></span>](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
