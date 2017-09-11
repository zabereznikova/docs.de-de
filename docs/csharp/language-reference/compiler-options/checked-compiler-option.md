---
title: -checked (C#-Compileroptionen)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /checked
dev_langs:
- CSharp
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
caps.latest.revision: 20
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
ms.openlocfilehash: 63ba89ec42748ccea065bf0fd258fb559abca099
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="checked-c-compiler-options"></a><span data-ttu-id="a7902-102">/checked (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="a7902-102">/checked (C# Compiler Options)</span></span>
<span data-ttu-id="a7902-103">Die Option **/checked** gibt an, ob eine Anweisung der Ganzzahlarithmetik, die einen Wert außerhalb des Bereichs des Datentyps nach sich zieht und sich nicht im Bereich eines [checked](../../../csharp/language-reference/keywords/checked.md)- oder [unchecked](../../../csharp/language-reference/keywords/unchecked.md)-Schlüsselworts befindet, eine Ausnahme verursacht.</span><span class="sxs-lookup"><span data-stu-id="a7902-103">The **/checked** option specifies whether an integer arithmetic statement that results in a value that is outside the range of the data type, and that is not in the scope of a [checked](../../../csharp/language-reference/keywords/checked.md) or [unchecked](../../../csharp/language-reference/keywords/unchecked.md) keyword, causes a run-time exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7902-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7902-104">Syntax</span></span>  
  
```console  
/checked[+ | -]  
```  
  
## <a name="remarks"></a><span data-ttu-id="a7902-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7902-105">Remarks</span></span>  
 <span data-ttu-id="a7902-106">Eine Anweisung der Ganzzahlarithmetik, die im Rahmen eines `checked`- oder `unchecked`-Schlüsselworts liegt, ist nicht der Auswirkung der Option **/checked** unterworfen.</span><span class="sxs-lookup"><span data-stu-id="a7902-106">An integer arithmetic statement that is in the scope of a `checked` or `unchecked` keyword is not subject to the effect of the **/checked** option.</span></span>  
  
 <span data-ttu-id="a7902-107">Wenn eine Anweisung der Ganzzahlarithmetik, die sich nicht im Rahmen eines `checked`- oder `unchecked`-Schlüsselworts befindet, einen Wert außerhalb des Bereichs des Datentyps ergibt, und **/checked+** (**/checked**) in der Kompilierung verwendet wird, löst die Anweisung zur Laufzeit eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="a7902-107">If an integer arithmetic statement that is not in the scope of a `checked` or `unchecked` keyword results in a value outside the range of the data type, and **/checked+** (**/checked**) is used in the compilation, that statement causes an exception at run time.</span></span> <span data-ttu-id="a7902-108">Wenn **/checked-** in der Kompilierung verwendet wird, löst die Anweisung zur Laufzeit keine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="a7902-108">If **/checked-** is used in the compilation, that statement does not cause an exception at run time.</span></span>  
  
 <span data-ttu-id="a7902-109">Der Standardwert für diese Option ist **/checked-**.</span><span class="sxs-lookup"><span data-stu-id="a7902-109">The default value for this option is **/checked-**.</span></span> <span data-ttu-id="a7902-110">Ein Szenario für die Verwendung von **/checked-** liegt in der Erstellung großer Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="a7902-110">One scenario for using **/checked-** is in building large applications.</span></span> <span data-ttu-id="a7902-111">Manchmal werden automatisierte Tools zum Erstellen solcher Anwendungen verwendet, und so ein Tool könnte **/checked** automatisch auf + festlegen.</span><span class="sxs-lookup"><span data-stu-id="a7902-111">Sometimes automated tools are used to build such applications, and such a tool might automatically set **/checked** to +.</span></span> <span data-ttu-id="a7902-112">Sie können die allgemeine Standardeinstellung des Tools überschreiben, indem Sie **/checked-** angeben.</span><span class="sxs-lookup"><span data-stu-id="a7902-112">You can override the tool's global default by specifying **/checked-**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="a7902-113">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="a7902-113">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="a7902-114">Öffnen Sie die **Eigenschaftenseite** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="a7902-114">Open the project's **Properties** page.</span></span> <span data-ttu-id="a7902-115">Weitere Informationen finden Sie unter [Seite „Erstellen“, Projekt-Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span><span class="sxs-lookup"><span data-stu-id="a7902-115">For more information, see [Build Page, Project Designer (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).</span></span>  
  
2.  <span data-ttu-id="a7902-116">Klicken Sie auf die Eigenschaftenseite **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="a7902-116">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="a7902-117">Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="a7902-117">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="a7902-118">Bearbeiten Sie die Eigenschaft **Auf arithmetischen Über-/Unterlauf überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="a7902-118">Modify the **Check for arithmetic overflow/underflow** property.</span></span>  
  
 <span data-ttu-id="a7902-119">Informationen zum programmgesteuerten Festlegen dieser Compileroption finden Sie unter <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span><span class="sxs-lookup"><span data-stu-id="a7902-119">To access this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7902-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7902-120">Example</span></span>  
 <span data-ttu-id="a7902-121">Der folgende Befehl kompiliert `t2.cs`.</span><span class="sxs-lookup"><span data-stu-id="a7902-121">The following command compiles `t2.cs`.</span></span> <span data-ttu-id="a7902-122">Die Verwendung von `/checked` im Befehl gibt an, ob eine Anweisung der Ganzzahlarithmetik in der Datei, die einen Wert außerhalb des Bereichs des `checked`- oder `unchecked`-Schlüsselworts enthält und einen Wert außerhalb des Bereichs des Datentyps auslöst, zur Laufzeit eine Ausnahme verursacht.</span><span class="sxs-lookup"><span data-stu-id="a7902-122">The use of `/checked` in the command specifies that any integer arithmetic statement in the file that is not in the scope of a `checked` or `unchecked` keyword, and that results in a value that is outside the range of the data type, causes an exception at run time.</span></span>  
  
```console  
csc t2.cs /checked  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7902-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7902-123">See Also</span></span>  
 <span data-ttu-id="a7902-124">[C#-Compileroptionen](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="a7902-124">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 <span data-ttu-id="a7902-125">[Managing Project and Solution Properties (Verwalten von Projekt- und Projektmappeneigenschaften)](/visualstudio/ide/managing-project-and-solution-properties) </span><span class="sxs-lookup"><span data-stu-id="a7902-125">[Managing Project and Solution Properties](/visualstudio/ide/managing-project-and-solution-properties) </span></span>  
 [<span data-ttu-id="a7902-126">Introduction to the Project Designer (Einführung in den Projekt-Designer)</span><span class="sxs-lookup"><span data-stu-id="a7902-126">Introduction to the Project Designer</span></span>](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)

