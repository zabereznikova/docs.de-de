---
description: -checked (C#-Compileroptionen)
title: -checked (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: c92ad61b2f482631230e0e6aeb0af5716a4fcb61
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "91196831"
---
# <a name="-checked-c-compiler-options"></a><span data-ttu-id="a09d0-103">-checked (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a09d0-103">-checked (C# Compiler Options)</span></span>

<span data-ttu-id="a09d0-104">Die Option **-checked** gibt an, ob eine Anweisung der Ganzzahlarithmetik, die einen Wert außerhalb des Bereichs des Datentyps nach sich zieht und sich nicht im Bereich eines [checked](../keywords/checked.md)- oder [unchecked](../keywords/unchecked.md)-Schlüsselworts befindet, eine Ausnahme verursacht.</span><span class="sxs-lookup"><span data-stu-id="a09d0-104">The **-checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../keywords/checked.md) or [unchecked](../keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a09d0-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a09d0-105">Syntax</span></span>  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="a09d0-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a09d0-106">Remarks</span></span>  

 <span data-ttu-id="a09d0-107">Eine Anweisung der Ganzzahlarithmetik, die im Rahmen eines `checked`- oder `unchecked`-Schlüsselworts liegt, ist nicht der Auswirkung der Option **-checked** unterworfen.</span><span class="sxs-lookup"><span data-stu-id="a09d0-107">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **-checked** option.</span></span>  
  
 <span data-ttu-id="a09d0-108">Wenn eine Anweisung der Ganzzahlarithmetik, die sich nicht im Rahmen eines `checked`- oder `unchecked`-Schlüsselworts befindet, einen Wert außerhalb des Bereichs des Datentyps ergibt, und **-checked+** (oder **-checked**) in der Kompilierung verwendet wird, löst die Anweisung zur Laufzeit eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="a09d0-108">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **-checked+** (or **-checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="a09d0-109">Wenn **-checked-** in der Kompilierung verwendet wird, löst die Anweisung zur Laufzeit keine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="a09d0-109">If **-checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="a09d0-110">Der Standardwert für diese Option lautet **-checked-**; die Überlaufüberprüfung ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a09d0-110">The default value for this option is **-checked-**; overflow checking is disabled.</span></span>

 <span data-ttu-id="a09d0-111">Automatisierte Tools zum Erstellen großer Anwendungen legen „-checked-“ manchmal auf „-checked+“ fest.</span><span class="sxs-lookup"><span data-stu-id="a09d0-111">Sometimes, automated tools that are used to build large applications set -checked to +.</span></span> <span data-ttu-id="a09d0-112">Ein Szenario für die Verwendung von „-checked-“ ist die Überschreibung des globalen Standards des Tools durch Angabe von „-checked-“.</span><span class="sxs-lookup"><span data-stu-id="a09d0-112">One scenario for using -checked- is to override the tool's global default by specifying -checked-.</span></span>

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="a09d0-113">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="a09d0-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="a09d0-114">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="a09d0-114">Open the project's **Properties** page.</span></span> <span data-ttu-id="a09d0-115">Weitere Informationen finden Sie unter [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="a09d0-115">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="a09d0-116">Klicken Sie auf die Eigenschaftenseite **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a09d0-116">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="a09d0-117">Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="a09d0-117">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="a09d0-118">Bearbeiten Sie die Eigenschaft **Auf arithmetischen Überlauf überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="a09d0-118">Modify the **Check for arithmetic overflow** property.</span></span>  
  
 <span data-ttu-id="a09d0-119">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span><span class="sxs-lookup"><span data-stu-id="a09d0-119">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a09d0-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a09d0-120">Example</span></span>  

 <span data-ttu-id="a09d0-121">Der folgende Befehl kompiliert `t2.cs`.</span><span class="sxs-lookup"><span data-stu-id="a09d0-121">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="a09d0-122">Die Verwendung von `-checked` im Befehl gibt an, ob eine Anweisung der Ganzzahlarithmetik in der Datei, die einen Wert außerhalb des Bereichs des `checked`- oder `unchecked`-Schlüsselworts enthält und einen Wert außerhalb des Bereichs des Datentyps auslöst, zur Laufzeit eine Ausnahme verursacht.</span><span class="sxs-lookup"><span data-stu-id="a09d0-122">The use of `-checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="a09d0-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a09d0-123">See also</span></span>

- [<span data-ttu-id="a09d0-124">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="a09d0-124">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="a09d0-125">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="a09d0-125">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
