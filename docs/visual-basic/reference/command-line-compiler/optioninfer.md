---
title: / optioninfer | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /optioninfer
dev_langs:
- VB
helpviewer_keywords:
- -optioninfer compiler option [Visual Basic]
- /optioninfer compiler option [Visual Basic]
- optioninfer compiler option [Visual Basic]
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4bcc35da2a255ca75805c8a918027d2ccb61b154
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="optioninfer"></a><span data-ttu-id="f7d56-102">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="f7d56-102">/optioninfer</span></span>
<span data-ttu-id="f7d56-103">Ermöglicht die Verwendung von lokalem Typrückschluss in Variablendeklarationen.</span><span class="sxs-lookup"><span data-stu-id="f7d56-103">Enables the use of local type inference in variable declarations.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7d56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f7d56-104">Syntax</span></span>  
  
```  
/optioninfer[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f7d56-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f7d56-105">Arguments</span></span>  
  
|<span data-ttu-id="f7d56-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="f7d56-106">Term</span></span>|<span data-ttu-id="f7d56-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f7d56-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="f7d56-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="f7d56-108">`+` &#124; `-`</span></span>|<span data-ttu-id="f7d56-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="f7d56-109">Optional.</span></span> <span data-ttu-id="f7d56-110">Geben Sie `/optioninfer+` an, um lokalen Typrückschluss zu aktivieren oder `/optioninfer-` zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="f7d56-110">Specify `/optioninfer+` to enable local type inference, or `/optioninfer-` to block it.</span></span> <span data-ttu-id="f7d56-111">Die `/optioninfer` -Option ohne angegebenen Wert entspricht dem `/optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="f7d56-111">The `/optioninfer` option, with no value specified, is the same as `/optioninfer+`.</span></span> <span data-ttu-id="f7d56-112">Der Standardwert, wenn die `/optioninfer` Switch nicht vorhanden ist, ist auch `/optioninfer+`.</span><span class="sxs-lookup"><span data-stu-id="f7d56-112">The default value when the `/optioninfer` switch is not present is also `/optioninfer+`.</span></span> <span data-ttu-id="f7d56-113">Der Standardwert ist in der Vbc.rsp-Antwortdatei festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f7d56-113">The default value is set in the Vbc.rsp response file.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="f7d56-114">Sie können die `/noconfig` Option nutzen, um die internen Standardwerte des Compilers, anstelle der Werte in vbc.rsp, beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="f7d56-114">You can use the `/noconfig` option to retain the compiler's internal defaults instead of those specified in vbc.rsp.</span></span> <span data-ttu-id="f7d56-115">Der Compilerstandardwert für diese Option ist `/optioninfer-`.</span><span class="sxs-lookup"><span data-stu-id="f7d56-115">The compiler default for this option is `/optioninfer-`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7d56-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f7d56-116">Remarks</span></span>  
 <span data-ttu-id="f7d56-117">Wenn die Quellcodedatei enthält eine [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md), überschreibt die Anweisung die `/optioninfer` Befehlszeilencompiler-Einstellung.</span><span class="sxs-lookup"><span data-stu-id="f7d56-117">If the source code file contains an [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md), the statement overrides the `/optioninfer` command-line compiler setting.</span></span>  
  
### <a name="to-set-optioninfer-in-the-visual-studio-ide"></a><span data-ttu-id="f7d56-118">Festlegen von / Optioninfer in der Visual Studio-IDE</span><span class="sxs-lookup"><span data-stu-id="f7d56-118">To set /optioninfer in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="f7d56-119">Wählen Sie ein Projekt in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="f7d56-119">Select a project in **Solution Explorer**.</span></span> <span data-ttu-id="f7d56-120">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f7d56-120">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="f7d56-121">Weitere Informationen finden Sie unter [NIB: Verwalten von Projekteigenschaften mit dem Projekt-Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="f7d56-121">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="f7d56-122">Auf der **Kompilieren** Registerkarte, ändern Sie den Wert in der **Option infer** Feld.</span><span class="sxs-lookup"><span data-stu-id="f7d56-122">On the **Compile** tab, modify the value in the **Option infer** box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7d56-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f7d56-123">Example</span></span>  
 <span data-ttu-id="f7d56-124">Der folgende Code kompiliert `test.vb` mit aktiviertem lokalen Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="f7d56-124">The following code compiles `test.vb` with local type inference enabled.</span></span>  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f7d56-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7d56-125">See Also</span></span>  
 <span data-ttu-id="f7d56-126">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="f7d56-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="f7d56-127"> [/ optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="f7d56-127"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="f7d56-128"> [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="f7d56-128"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="f7d56-129"> [/ optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="f7d56-129"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="f7d56-130"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="f7d56-130"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="f7d56-131"> [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f7d56-131"> [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="f7d56-132"> [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="f7d56-132"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="f7d56-133"> [Visual Basic Standard, Projekte, Optionen (Dialogfeld)](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box) </span><span class="sxs-lookup"><span data-stu-id="f7d56-133"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box) </span></span>  
<span data-ttu-id="f7d56-134"> [Seite „Kompilieren“, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="f7d56-134"> [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="f7d56-135"> [/ noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span><span class="sxs-lookup"><span data-stu-id="f7d56-135"> [/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md) </span></span>  
<span data-ttu-id="f7d56-136"> [Erstellen von der Befehlszeile aus](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)</span><span class="sxs-lookup"><span data-stu-id="f7d56-136"> [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)</span></span>
