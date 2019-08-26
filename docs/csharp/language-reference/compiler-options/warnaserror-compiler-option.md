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
ms.openlocfilehash: 66c78ee56c9d5153b5b878b2e695ad4ee6bffe0b
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69606257"
---
# <a name="-warnaserror-c-compiler-options"></a><span data-ttu-id="8f5a2-102">-warnaserror (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="8f5a2-102">-warnaserror (C# Compiler Options)</span></span>
<span data-ttu-id="8f5a2-103">Die Option **-warnaserror+** behandelt alle Warnungen als Fehler.</span><span class="sxs-lookup"><span data-stu-id="8f5a2-103">The **-warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f5a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f5a2-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="8f5a2-105">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="8f5a2-105">Remarks</span></span>  
 <span data-ttu-id="8f5a2-106">Alle Nachrichten, die in der Regel als Warnungen gemeldet worden wären, werden stattdessen als Fehler gemeldet, und der Buildprozesses wird angehalten (keine Ausgabedateien werden erstellt).</span><span class="sxs-lookup"><span data-stu-id="8f5a2-106">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="8f5a2-107">**-warnaserror-** ist standardmäßig gültig, wodurch Warnungen nicht die Generierung einer Ausgabedatei verhindern.</span><span class="sxs-lookup"><span data-stu-id="8f5a2-107">By default, **-warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="8f5a2-108">**-warnaserror**, ist identisch mit **-warnaserror+** und bewirkt, dass Warnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="8f5a2-108">**-warnaserror**, which is the same as **-warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="8f5a2-109">Wenn nur bestimmte Warnungen als Fehler behandelt werden sollen, können Sie optional eine durch Trennzeichen getrennte Liste mit Warnungsnummern angeben, die als Fehler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8f5a2-109">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
 <span data-ttu-id="8f5a2-110">Verwenden Sie [-warn](./warn-compiler-option.md), um die Warnstufe anzugeben, die vom Compiler angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f5a2-110">Use [-warn](./warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="8f5a2-111">Verwenden Sie [-nowarn](./nowarn-compiler-option.md), um bestimmte Warnungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8f5a2-111">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="8f5a2-112">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="8f5a2-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="8f5a2-113">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="8f5a2-113">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="8f5a2-114">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="8f5a2-114">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="8f5a2-115">Ändern Sie die Eigenschaft **Warnungen als Fehler behandeln**.</span><span class="sxs-lookup"><span data-stu-id="8f5a2-115">Modify the **Treat Warnings As Errors** property.</span></span>  
  
 <span data-ttu-id="8f5a2-116">Wie Sie diese Compileroption programmgesteuert festlegen, erfahren Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span><span class="sxs-lookup"><span data-stu-id="8f5a2-116">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8f5a2-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8f5a2-117">Example</span></span>  
 <span data-ttu-id="8f5a2-118">Kompilieren Sie `in.cs`, und konfigurieren Sie den Compiler so, dass keine Warnungen angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="8f5a2-118">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652 in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f5a2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f5a2-119">See also</span></span>

- [<span data-ttu-id="8f5a2-120">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="8f5a2-120">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="8f5a2-121">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8f5a2-121">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
