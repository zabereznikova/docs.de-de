---
title: -warnaserror (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /warnaserror
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
ms.openlocfilehash: 762db1b3d72b5b4c3d606f3517f0b384f466d231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33218945"
---
# <a name="-warnaserror-c-compiler-options"></a><span data-ttu-id="e231a-102">-warnaserror (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="e231a-102">-warnaserror (C# Compiler Options)</span></span>
<span data-ttu-id="e231a-103">Die Option **-warnaserror+** behandelt alle Warnungen als Fehler.</span><span class="sxs-lookup"><span data-stu-id="e231a-103">The **-warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e231a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e231a-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="e231a-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e231a-105">Remarks</span></span>  
 <span data-ttu-id="e231a-106">Alle Nachrichten, die in der Regel als Warnungen gemeldet worden wären, werden stattdessen als Fehler gemeldet, und der Buildprozesses wird angehalten (keine Ausgabedateien werden erstellt).</span><span class="sxs-lookup"><span data-stu-id="e231a-106">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="e231a-107">**-warnaserror-** ist standardmäßig gültig, wodurch Warnungen nicht die Generierung einer Ausgabedatei verhindern.</span><span class="sxs-lookup"><span data-stu-id="e231a-107">By default, **-warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="e231a-108">**-warnaserror**, ist identisch mit **-warnaserror+** und bewirkt, dass Warnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e231a-108">**-warnaserror**, which is the same as **-warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="e231a-109">Wenn nur bestimmte Warnungen als Fehler behandelt werden sollen, können Sie optional eine durch Trennzeichen getrennte Liste mit Warnungsnummern angeben, die als Fehler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e231a-109">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
 <span data-ttu-id="e231a-110">Verwenden Sie [-warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md), um die Warnstufe anzugeben, die vom Compiler angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e231a-110">Use [-warn](../../../csharp/language-reference/compiler-options/warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="e231a-111">Verwenden Sie [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md), um bestimmte Warnungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e231a-111">Use [-nowarn](../../../csharp/language-reference/compiler-options/nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e231a-112">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="e231a-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="e231a-113">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="e231a-113">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="e231a-114">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="e231a-114">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="e231a-115">Ändern Sie die Eigenschaft **Warnungen als Fehler behandeln**.</span><span class="sxs-lookup"><span data-stu-id="e231a-115">Modify the **Treat Warnings As Errors** property.</span></span>  
  
 <span data-ttu-id="e231a-116">Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span><span class="sxs-lookup"><span data-stu-id="e231a-116">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e231a-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e231a-117">Example</span></span>  
 <span data-ttu-id="e231a-118">Kompilieren Sie `in.cs`, und konfigurieren Sie den Compiler so, dass keine Warnungen angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="e231a-118">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="e231a-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e231a-119">See Also</span></span>  
 [<span data-ttu-id="e231a-120">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="e231a-120">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="e231a-121">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="e231a-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
