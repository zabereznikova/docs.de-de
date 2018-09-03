---
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
ms.openlocfilehash: f8fec2c4da49aa6cac2f8dc1dc9b07c5864b837a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43417167"
---
# <a name="-optimize-c-compiler-options"></a><span data-ttu-id="17464-102">-optimize (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="17464-102">-optimize (C# Compiler Options)</span></span>
<span data-ttu-id="17464-103">Die Option **-optimize** aktiviert oder deaktiviert die vom Compiler durchgeführten Optimierungen, damit Ihre Ausgabedatei kleiner, schneller und effizienter wird.</span><span class="sxs-lookup"><span data-stu-id="17464-103">The **-optimize** option enables or disables optimizations performed by the compiler to make your output file smaller, faster, and more efficient.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17464-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17464-104">Syntax</span></span>  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="17464-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17464-105">Remarks</span></span>  
 <span data-ttu-id="17464-106">Außerdem weist **-optimize** die Common Language Runtime an, den Code zur Laufzeit zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="17464-106">**-optimize** also tells the common language runtime to optimize code at runtime.</span></span>  
  
 <span data-ttu-id="17464-107">Optimierungen sind standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="17464-107">By default, optimizations are disabled.</span></span> <span data-ttu-id="17464-108">Geben Sie **-optimize+** an, um Optimierungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="17464-108">Specify **-optimize+** to enable optimizations.</span></span>  
  
 <span data-ttu-id="17464-109">Beim Erstellen eines Moduls, das von einer Assembly verwendet werden soll, verwenden Sie dieselben **-optimize**-Einstellungen wie die der Assembly.</span><span class="sxs-lookup"><span data-stu-id="17464-109">When building a module to be used by an assembly, use the same **-optimize** settings as those of the assembly.</span></span>  
  
 <span data-ttu-id="17464-110">**-o** ist die Kurzform von **-optimize**.</span><span class="sxs-lookup"><span data-stu-id="17464-110">**-o** is the short form of **-optimize**.</span></span>  
  
 <span data-ttu-id="17464-111">Es ist möglich, die Optionen **-optimize** und [-debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) zu kombinieren.</span><span class="sxs-lookup"><span data-stu-id="17464-111">It is possible to combine the **-optimize** and [-debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md) options.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="17464-112">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="17464-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="17464-113">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="17464-113">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="17464-114">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="17464-114">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="17464-115">Ändern Sie die Eigenschaft **Code optimieren**.</span><span class="sxs-lookup"><span data-stu-id="17464-115">Modify the **Optimize Code** property.</span></span>  
  
 <span data-ttu-id="17464-116">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span><span class="sxs-lookup"><span data-stu-id="17464-116">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17464-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17464-117">Example</span></span>  
 <span data-ttu-id="17464-118">Kompilieren Sie `t2.cs`, um Compileroptimierungen zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="17464-118">Compile `t2.cs` and enable compiler optimizations:</span></span>  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a><span data-ttu-id="17464-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17464-119">See Also</span></span>  

- [<span data-ttu-id="17464-120">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="17464-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="17464-121">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="17464-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
