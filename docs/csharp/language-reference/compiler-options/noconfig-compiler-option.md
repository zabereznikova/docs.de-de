---
title: -noconfig (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /noconfig
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
ms.openlocfilehash: 2d6d0c52be2306292224d7831f8818c6f865f2f4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602738"
---
# <a name="-noconfig-c-compiler-options"></a><span data-ttu-id="4543b-102">-noconfig (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="4543b-102">-noconfig (C# Compiler Options)</span></span>
<span data-ttu-id="4543b-103">Die Option **-noconfig** weist den Compiler dazu an, nicht mit der Datei „csc.rsp“ zu kompilieren, die sich im gleichen Verzeichnis wie die Datei „csc.exe“ befindet und daraus geladen wird.</span><span class="sxs-lookup"><span data-stu-id="4543b-103">The **-noconfig** option tells the compiler not to compile with the csc.rsp file, which is located in and loaded from the same directory as the csc.exe file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4543b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4543b-104">Syntax</span></span>  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="4543b-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4543b-105">Remarks</span></span>  
 <span data-ttu-id="4543b-106">Die Datei „csc.rsp“ verweist auf alle Assemblys, die im Lieferumfang von .NET Framework enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="4543b-106">The csc.rsp file references all the assemblies shipped with the .NET Framework.</span></span> <span data-ttu-id="4543b-107">Die tatsächlichen Verweise, die die .NET-Entwicklungsumgebung von Visual Studio enthält, hängen vom Projekttyp ab.</span><span class="sxs-lookup"><span data-stu-id="4543b-107">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span>  
  
 <span data-ttu-id="4543b-108">Sie können die Datei „csc.rsp“ ändern und zusätzliche Compileroptionen angeben, die in jeder Kompilierung über die Befehlszeile mit „csc.exe“ enthalten sein sollen (mit Ausnahme der Option **-noconfig**).</span><span class="sxs-lookup"><span data-stu-id="4543b-108">You can modify the csc.rsp file and specify additional compiler options that should be included in every compilation from the command line with csc.exe (except the **-noconfig** option).</span></span>  
  
 <span data-ttu-id="4543b-109">Der Compiler verarbeitet die an den Befehl **csc** übergebenen Optionen zuletzt.</span><span class="sxs-lookup"><span data-stu-id="4543b-109">The compiler processes the options passed to the **csc** command last.</span></span> <span data-ttu-id="4543b-110">Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung für die gleiche Option in der Datei „csc.rsp“.</span><span class="sxs-lookup"><span data-stu-id="4543b-110">Therefore, any option on the command line overrides the setting of the same option in the csc.rsp file.</span></span>  
  
 <span data-ttu-id="4543b-111">Wenn der Compiler nach den Einstellungen in der Datei „csc.rsp“ suchen und diese verwenden soll, geben Sie **-noconfig** an.</span><span class="sxs-lookup"><span data-stu-id="4543b-111">If you do not want the compiler to look for and use the settings in the csc.rsp file, specify **-noconfig**.</span></span>  
  
 <span data-ttu-id="4543b-112">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="4543b-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4543b-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4543b-113">See also</span></span>

- [<span data-ttu-id="4543b-114">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="4543b-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="4543b-115">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="4543b-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
