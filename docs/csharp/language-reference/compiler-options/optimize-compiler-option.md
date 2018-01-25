---
title: -optimize (C#-Compileroptionen)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /optimize
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2cf6919ee2d4f0a4031e18d46b9e5ebaf816b120
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="-optimize-c-compiler-options"></a><span data-ttu-id="4be6d-102">-optimize (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="4be6d-102">-optimize (C# Compiler Options)</span></span>
<span data-ttu-id="4be6d-103">Die Option **-optimize** aktiviert oder deaktiviert die vom Compiler durchgeführten Optimierungen, damit Ihre Ausgabedatei kleiner, schneller und effizienter wird.</span><span class="sxs-lookup"><span data-stu-id="4be6d-103">The **-optimize** option enables or disables optimizations performed by the compiler to make your output file smaller, faster, and more efficient.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4be6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4be6d-104">Syntax</span></span>  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="4be6d-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4be6d-105">Remarks</span></span>  
 <span data-ttu-id="4be6d-106">Außerdem weist **-optimize** die Common Language Runtime an, den Code zur Laufzeit zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="4be6d-106">**-optimize** also tells the common language runtime to optimize code at runtime.</span></span>  
  
 <span data-ttu-id="4be6d-107">Optimierungen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4be6d-107">By default, optimizations are disabled.</span></span> <span data-ttu-id="4be6d-108">Geben Sie **-optimize+** an, um Optimierungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4be6d-108">Specify **-optimize+** to enable optimizations.</span></span>  
  
 <span data-ttu-id="4be6d-109">Beim Erstellen eines Moduls, das von einer Assembly verwendet werden soll, verwenden Sie dieselben **-optimize**-Einstellungen wie die der Assembly.</span><span class="sxs-lookup"><span data-stu-id="4be6d-109">When building a module to be used by an assembly, use the same **-optimize** settings as those of the assembly.</span></span>  
  
 <span data-ttu-id="4be6d-110">**-o** ist die Kurzform von **-optimize**.</span><span class="sxs-lookup"><span data-stu-id="4be6d-110">**-o** is the short form of **-optimize**.</span></span>  
  
 <span data-ttu-id="4be6d-111">Es ist möglich, die Optionen **-optimize** und [-debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="4be6d-111">It is possible to combine the **-optimize** and [-debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) options.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="4be6d-112">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="4be6d-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="4be6d-113">Öffnen Sie die **Eigenschaftenseite** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="4be6d-113">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="4be6d-114">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="4be6d-114">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="4be6d-115">Ändern Sie die Eigenschaft **Code optimieren**.</span><span class="sxs-lookup"><span data-stu-id="4be6d-115">Modify the **Optimize Code** property.</span></span>  
  
 <span data-ttu-id="4be6d-116">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span><span class="sxs-lookup"><span data-stu-id="4be6d-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4be6d-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4be6d-117">Example</span></span>  
 <span data-ttu-id="4be6d-118">Kompilieren Sie `t2.cs`, um Compileroptimierungen zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="4be6d-118">Compile `t2.cs` and enable compiler optimizations:</span></span>  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="4be6d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4be6d-119">See Also</span></span>  
 [<span data-ttu-id="4be6d-120">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="4be6d-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="4be6d-121">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="4be6d-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
