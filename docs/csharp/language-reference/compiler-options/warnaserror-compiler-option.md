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
ms.openlocfilehash: 7d43941629e933ac5a9e9c9d6a1388b6194f8d99
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503476"
---
# <a name="-warnaserror-c-compiler-options"></a><span data-ttu-id="8b7d0-102">-warnaserror (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="8b7d0-102">-warnaserror (C# Compiler Options)</span></span>
<span data-ttu-id="8b7d0-103">Die Option **-warnaserror+** behandelt alle Warnungen als Fehler.</span><span class="sxs-lookup"><span data-stu-id="8b7d0-103">The **-warnaserror+** option treats all warnings as errors</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b7d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b7d0-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a><span data-ttu-id="8b7d0-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8b7d0-105">Remarks</span></span>  
 <span data-ttu-id="8b7d0-106">Alle Nachrichten, die in der Regel als Warnungen gemeldet worden wären, werden stattdessen als Fehler gemeldet, und der Buildprozesses wird angehalten (keine Ausgabedateien werden erstellt).</span><span class="sxs-lookup"><span data-stu-id="8b7d0-106">Any messages that would ordinarily be reported as warnings are instead reported as errors, and the build process is halted (no output files are built).</span></span>  
  
 <span data-ttu-id="8b7d0-107">**-warnaserror-** ist standardmäßig gültig, wodurch Warnungen nicht die Generierung einer Ausgabedatei verhindern.</span><span class="sxs-lookup"><span data-stu-id="8b7d0-107">By default, **-warnaserror-** is in effect, which causes warnings to not prevent the generation of an output file.</span></span> <span data-ttu-id="8b7d0-108">**-warnaserror**, ist identisch mit **-warnaserror+** und bewirkt, dass Warnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="8b7d0-108">**-warnaserror**, which is the same as **-warnaserror+**, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="8b7d0-109">Wenn nur bestimmte Warnungen als Fehler behandelt werden sollen, können Sie optional eine durch Trennzeichen getrennte Liste mit Warnungsnummern angeben, die als Fehler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8b7d0-109">Optionally, if you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span> <span data-ttu-id="8b7d0-110">Die Gruppe aller Warnungen zur NULL-Zulässigkeit können mithilfe der Kurzform **nullable** angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8b7d0-110">The set of all nullability warnings can be specified with the **nullable** shorthand.</span></span>
  
 <span data-ttu-id="8b7d0-111">Verwenden Sie [-warn](./warn-compiler-option.md), um die Warnstufe anzugeben, die vom Compiler angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8b7d0-111">Use [-warn](./warn-compiler-option.md) to specify the level of warnings that you want the compiler to display.</span></span> <span data-ttu-id="8b7d0-112">Verwenden Sie [-nowarn](./nowarn-compiler-option.md), um bestimmte Warnungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8b7d0-112">Use [-nowarn](./nowarn-compiler-option.md) to disable certain warnings.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="8b7d0-113">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="8b7d0-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="8b7d0-114">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="8b7d0-114">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="8b7d0-115">Klicken Sie auf die Eigenschaftenseite **Build** .</span><span class="sxs-lookup"><span data-stu-id="8b7d0-115">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="8b7d0-116">Ändern Sie die Eigenschaft **Warnungen als Fehler behandeln**.</span><span class="sxs-lookup"><span data-stu-id="8b7d0-116">Modify the **Treat Warnings As Errors** property.</span></span>  
  
 <span data-ttu-id="8b7d0-117">Um diese Compileroption programmgesteuert festzulegen, sehen Sie sich <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors> an.</span><span class="sxs-lookup"><span data-stu-id="8b7d0-117">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b7d0-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b7d0-118">Example</span></span>  
 <span data-ttu-id="8b7d0-119">Kompilieren Sie `in.cs`, und konfigurieren Sie den Compiler so, dass keine Warnungen angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="8b7d0-119">Compile `in.cs` and have the compiler display no warnings:</span></span>  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652,nullable in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b7d0-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8b7d0-120">See also</span></span>

- [<span data-ttu-id="8b7d0-121">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="8b7d0-121">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="8b7d0-122">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8b7d0-122">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
