---
title: -checked (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: 814e8f3aa7130c6a64e7e27951854bed7b7cbe6c
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59333937"
---
# <a name="-checked-c-compiler-options"></a><span data-ttu-id="48ee0-102">-checked (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="48ee0-102">-checked (C# Compiler Options)</span></span>
<span data-ttu-id="48ee0-103">Die Option **-checked** gibt an, ob eine Anweisung der Ganzzahlarithmetik, die einen Wert außerhalb des Bereichs des Datentyps nach sich zieht und sich nicht im Bereich eines [checked](../../../csharp/language-reference/keywords/checked.md)- oder [unchecked](../../../csharp/language-reference/keywords/unchecked.md)-Schlüsselworts befindet, eine Ausnahme verursacht.</span><span class="sxs-lookup"><span data-stu-id="48ee0-103">The **-checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../../../csharp/language-reference/keywords/checked.md) or [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48ee0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48ee0-104">Syntax</span></span>  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="48ee0-105">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="48ee0-105">Remarks</span></span>  
 <span data-ttu-id="48ee0-106">Eine Anweisung der Ganzzahlarithmetik, die im Rahmen eines `checked`- oder `unchecked`-Schlüsselworts liegt, ist nicht der Auswirkung der Option **-checked** unterworfen.</span><span class="sxs-lookup"><span data-stu-id="48ee0-106">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **-checked** option.</span></span>  
  
 <span data-ttu-id="48ee0-107">Wenn eine Anweisung der Ganzzahlarithmetik, die sich nicht im Rahmen eines `checked`- oder `unchecked`-Schlüsselworts befindet, einen Wert außerhalb des Bereichs des Datentyps ergibt, und **-checked+** (oder **-checked**) in der Kompilierung verwendet wird, löst die Anweisung zur Laufzeit eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="48ee0-107">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **-checked+** (or **-checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="48ee0-108">Wenn **-checked-** in der Kompilierung verwendet wird, löst die Anweisung zur Laufzeit keine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="48ee0-108">If **-checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="48ee0-109">Der Standardwert für diese Option lautet **-checked-**; die Überlaufüberprüfung ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="48ee0-109">The default value for this option is **-checked-**; overflow checking is disabled.</span></span>
 
 <span data-ttu-id="48ee0-110">Automatisierte Tools zum Erstellen großer Anwendungen legen „-checked-“ manchmal auf „-checked+“ fest.</span><span class="sxs-lookup"><span data-stu-id="48ee0-110">Sometimes, automated tools that are used to build large applications set -checked to +.</span></span> <span data-ttu-id="48ee0-111">Ein Szenario für die Verwendung von „-checked-“ ist die Überschreibung des globalen Standards des Tools durch Angabe von „-checked-“.</span><span class="sxs-lookup"><span data-stu-id="48ee0-111">One scenario for using -checked- is to override the tool's global default by specifying -checked-.</span></span>
 
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="48ee0-112">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="48ee0-112">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="48ee0-113">Öffnen Sie die **Eigenschaftenseite** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="48ee0-113">Open the project's **Properties** page.</span></span> <span data-ttu-id="48ee0-114">Weitere Informationen finden Sie unter [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="48ee0-114">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2. <span data-ttu-id="48ee0-115">Klicken Sie auf die Eigenschaftenseite **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="48ee0-115">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="48ee0-116">Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="48ee0-116">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="48ee0-117">Bearbeiten Sie die Eigenschaft **Auf arithmetischen Über-/Unterlauf überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="48ee0-117">Modify the **Check for arithmetic overflow/underflow** property.</span></span>  
  
 <span data-ttu-id="48ee0-118">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span><span class="sxs-lookup"><span data-stu-id="48ee0-118">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48ee0-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48ee0-119">Example</span></span>  
 <span data-ttu-id="48ee0-120">Der folgende Befehl kompiliert `t2.cs`.</span><span class="sxs-lookup"><span data-stu-id="48ee0-120">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="48ee0-121">Die Verwendung von `-checked` im Befehl gibt an, ob eine Anweisung der Ganzzahlarithmetik in der Datei, die einen Wert außerhalb des Bereichs des `checked`- oder `unchecked`-Schlüsselworts enthält und einen Wert außerhalb des Bereichs des Datentyps auslöst, zur Laufzeit eine Ausnahme verursacht.</span><span class="sxs-lookup"><span data-stu-id="48ee0-121">The use of `-checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="48ee0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48ee0-122">See also</span></span>

- [<span data-ttu-id="48ee0-123">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="48ee0-123">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="48ee0-124">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="48ee0-124">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
