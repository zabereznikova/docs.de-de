---
title: -noconfig (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /noconfig
dev_langs:
- CSharp
helpviewer_keywords:
- /noconfig compiler option [C#]
- csc.rsp
- -noconfig compiler option [C#]
- noconfig compiler option [C#]
ms.assetid: cd26967e-e494-4c8c-b5c9-af13b2f78b2e
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 594e972dc834ab74412e30a48428f850ae02b5ac
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="noconfig-c-compiler-options"></a><span data-ttu-id="1ce32-102">/noconfig (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="1ce32-102">/noconfig (C# Compiler Options)</span></span>
<span data-ttu-id="1ce32-103">Die Option **/noconfig** weist den Compiler an, nicht mit der Datei „csc.rsp“ zu kompilieren, die sich im gleichen Verzeichnis wie die Datei „csc.exe“ befindet und daraus geladen wird.</span><span class="sxs-lookup"><span data-stu-id="1ce32-103">The **/noconfig** option tells the compiler not to compile with the csc.rsp file, which is located in and loaded from the same directory as the csc.exe file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ce32-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ce32-104">Syntax</span></span>  
  
```console  
/noconfig  
```  
  
## <a name="remarks"></a><span data-ttu-id="1ce32-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1ce32-105">Remarks</span></span>  
 <span data-ttu-id="1ce32-106">Die Datei „csc.rsp“ verweist auf alle Assemblys, die im Lieferumfang von .NET Framework enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="1ce32-106">The csc.rsp file references all the assemblies shipped with the .NET Framework.</span></span> <span data-ttu-id="1ce32-107">Die tatsächlichen Verweise, die die .NET-Entwicklungsumgebung von Visual Studio enthält, hängen vom Projekttyp ab.</span><span class="sxs-lookup"><span data-stu-id="1ce32-107">The actual references that the Visual Studio .NET development environment includes depend on the project type.</span></span>  
  
 <span data-ttu-id="1ce32-108">Sie können die Datei „csc.rsp“ ändern und zusätzliche Compileroptionen angeben, die in jeder Kompilierung über die Befehlszeile mit „csc.exe“ enthalten sein sollen (mit Ausnahme der Option **/noconfig**).</span><span class="sxs-lookup"><span data-stu-id="1ce32-108">You can modify the csc.rsp file and specify additional compiler options that should be included in every compilation from the command line with csc.exe (except the **/noconfig** option).</span></span>  
  
 <span data-ttu-id="1ce32-109">Der Compiler verarbeitet die an den Befehl **csc** übergebenen Optionen zuletzt.</span><span class="sxs-lookup"><span data-stu-id="1ce32-109">The compiler processes the options passed to the **csc** command last.</span></span> <span data-ttu-id="1ce32-110">Aus diesem Grund überschreibt jede Option in der Befehlszeile die Einstellung für die gleiche Option in der Datei „csc.rsp“.</span><span class="sxs-lookup"><span data-stu-id="1ce32-110">Therefore, any option on the command line overrides the setting of the same option in the csc.rsp file.</span></span>  
  
 <span data-ttu-id="1ce32-111">Wenn der Compiler nach den Einstellungen in der Datei „csc.rsp“ suchen und diese verwenden soll, geben Sie **/noconfig** an.</span><span class="sxs-lookup"><span data-stu-id="1ce32-111">If you do not want the compiler to look for and use the settings in the csc.rsp file, specify **/noconfig**.</span></span>  
  
 <span data-ttu-id="1ce32-112">Diese Compileroption steht in Visual Studio nicht zur Verfügung und kann auch nicht programmgesteuert angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="1ce32-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce32-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ce32-113">See Also</span></span>  
 <span data-ttu-id="1ce32-114">[C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="1ce32-114">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="1ce32-115">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="1ce32-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

