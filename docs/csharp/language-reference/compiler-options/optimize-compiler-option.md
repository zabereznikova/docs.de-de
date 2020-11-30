---
description: -optimize (C#-Compileroptionen)
title: -optimize (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /optimize
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
ms.openlocfilehash: 1862794e4d823e38ce19780300a0b04f4e57dc44
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91193984"
---
# <a name="-optimize-c-compiler-options"></a><span data-ttu-id="617e4-103">-optimize (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="617e4-103">-optimize (C# Compiler Options)</span></span>

<span data-ttu-id="617e4-104">Die Option **-optimize** aktiviert oder deaktiviert die vom Compiler durchgeführten Optimierungen, damit Ihre Ausgabedatei kleiner, schneller und effizienter wird.</span><span class="sxs-lookup"><span data-stu-id="617e4-104">The **-optimize** option enables or disables optimizations performed by the compiler to make your output file smaller, faster, and more efficient.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="617e4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="617e4-105">Syntax</span></span>  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="617e4-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="617e4-106">Remarks</span></span>  

 <span data-ttu-id="617e4-107">Außerdem weist **-optimize** die Common Language Runtime an, den Code zur Laufzeit zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="617e4-107">**-optimize** also tells the common language runtime to optimize code at runtime.</span></span>  
  
 <span data-ttu-id="617e4-108">Optimierungen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="617e4-108">By default, optimizations are disabled.</span></span> <span data-ttu-id="617e4-109">Geben Sie **-optimize+** an, um Optimierungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="617e4-109">Specify **-optimize+** to enable optimizations.</span></span>  
  
 <span data-ttu-id="617e4-110">Beim Erstellen eines Moduls, das von einer Assembly verwendet werden soll, verwenden Sie dieselben **-optimize**-Einstellungen wie die der Assembly.</span><span class="sxs-lookup"><span data-stu-id="617e4-110">When building a module to be used by an assembly, use the same **-optimize** settings as those of the assembly.</span></span>  
  
 <span data-ttu-id="617e4-111">**-o** ist die Kurzform von **-optimize**.</span><span class="sxs-lookup"><span data-stu-id="617e4-111">**-o** is the short form of **-optimize**.</span></span>  
  
 <span data-ttu-id="617e4-112">Es ist möglich, die Optionen **-optimize** und [-debug](./debug-compiler-option.md) zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="617e4-112">It is possible to combine the **-optimize** and [-debug](./debug-compiler-option.md) options.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="617e4-113">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="617e4-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="617e4-114">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="617e4-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="617e4-115">Klicken Sie auf die Eigenschaftenseite **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="617e4-115">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="617e4-116">Ändern Sie die Eigenschaft **Code optimieren**.</span><span class="sxs-lookup"><span data-stu-id="617e4-116">Modify the **Optimize Code** property.</span></span>  
  
 <span data-ttu-id="617e4-117">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span><span class="sxs-lookup"><span data-stu-id="617e4-117">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="617e4-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="617e4-118">Example</span></span>  

 <span data-ttu-id="617e4-119">Kompilieren Sie `t2.cs`, um Compileroptimierungen zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="617e4-119">Compile `t2.cs` and enable compiler optimizations:</span></span>  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="617e4-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="617e4-120">See also</span></span>

- [<span data-ttu-id="617e4-121">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="617e4-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="617e4-122">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="617e4-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
