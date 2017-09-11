---
title: Option Explicit-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
dev_langs:
- VB
helpviewer_keywords:
- declaring variables, explicit
- forced variable declaration in Option Explicit statement
- Explicit keyword
- explicit variable declaration
- Option Explicit statement
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: 17
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
ms.openlocfilehash: 4283599d9ed2ad9075ab0b2f404f1a12a31437ec
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="9b57d-102">Option Explicit-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b57d-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="9b57d-103">Erzwingt die explizite Deklaration aller Variablen in einer Datei oder die implizite Deklarationen von Variablen.</span><span class="sxs-lookup"><span data-stu-id="9b57d-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b57d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9b57d-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="9b57d-105">Teile</span><span class="sxs-lookup"><span data-stu-id="9b57d-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="9b57d-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="9b57d-106">Optional.</span></span> <span data-ttu-id="9b57d-107">Ermöglicht `Option Explicit` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9b57d-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="9b57d-108">Wenn `On` oder `Off` nicht angegeben ist, wird der Standardwert ist `On`.</span><span class="sxs-lookup"><span data-stu-id="9b57d-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="9b57d-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="9b57d-109">Optional.</span></span> <span data-ttu-id="9b57d-110">Deaktiviert die `Option Explicit` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="9b57d-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b57d-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9b57d-111">Remarks</span></span>  
 <span data-ttu-id="9b57d-112">Wenn `Option Explicit On` oder `Option Explicit` wird in einer Datei müssen Sie alle Variablen explizit deklarieren, mit der `Dim` oder `ReDim` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="9b57d-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="9b57d-113">Wenn Sie versuchen, einen nicht deklarierten Variablennamen verwenden, tritt ein Fehler zur Kompilierzeit.</span><span class="sxs-lookup"><span data-stu-id="9b57d-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="9b57d-114">Die `Option Explicit Off` Anweisung ermöglicht die implizite Deklaration von Variablen.</span><span class="sxs-lookup"><span data-stu-id="9b57d-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="9b57d-115">Wenn sie verwendet wird, muss die `Option Explicit`-Anweisung in einer Datei vor allen anderen Quellcodeanweisungen angeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="9b57d-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b57d-116">Festlegen von `Option Explicit` zu `Off` ist im Allgemeinen nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="9b57d-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="9b57d-117">Sie könnten einen Variablennamen in einem oder mehreren Standorten, falsch schreiben, die was die unerwarteten Ergebnissen führen würde, wenn das Programm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9b57d-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="9b57d-118">Wenn eine Option Explicit-Anweisung nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="9b57d-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="9b57d-119">Enthält der Quellcode kein `Option Explicit` -Anweisung, die **Option Explicit** auf der [Seite kompilieren, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9b57d-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="9b57d-120">Wenn der Befehlszeile-Compiler verwendet wird, die [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) -Compileroption verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="9b57d-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="9b57d-121">Option Explicit in der IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="9b57d-121">To set Option Explicit in the IDE</span></span>  
  
1.  <span data-ttu-id="9b57d-122">In **Projektmappen-Explorer**, wählen Sie ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="9b57d-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="9b57d-123">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9b57d-123">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="9b57d-124">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="9b57d-124">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span>  
  
2.  <span data-ttu-id="9b57d-125">Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="9b57d-125">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="9b57d-126">Legen Sie den Wert der **Option Explicit** Feld.</span><span class="sxs-lookup"><span data-stu-id="9b57d-126">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="9b57d-127">Wenn Sie ein neues Projekt erstellen die **Option Explicit** auf der **Kompilieren** Registerkarte auf festgelegt ist die **Option Explicit** festlegen in der **VB-Standard** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="9b57d-127">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="9b57d-128">Für den Zugriff auf die **VB-Standard** Dialogfelds die **Tools** Menü klicken Sie auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="9b57d-128">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="9b57d-129">In der **Optionen** Dialogfeld erweitern Sie **Projekte und Projektmappen**, und klicken Sie dann auf **VB-Standard**.</span><span class="sxs-lookup"><span data-stu-id="9b57d-129">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="9b57d-130">Die ursprüngliche Standardeinstellung in **VB-Standard** ist `On`.</span><span class="sxs-lookup"><span data-stu-id="9b57d-130">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="9b57d-131">Option Explicit in der Befehlszeile festlegen</span><span class="sxs-lookup"><span data-stu-id="9b57d-131">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="9b57d-132">Enthalten die [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) -Compileroption in der **Vbc** Befehl.</span><span class="sxs-lookup"><span data-stu-id="9b57d-132">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b57d-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9b57d-133">Example</span></span>  
 <span data-ttu-id="9b57d-134">Im folgenden Beispiel wird die `Option Explicit` Anweisung, um die explizite Deklaration aller Variablen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="9b57d-134">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="9b57d-135">Versucht, eine nicht deklarierte Variable verwenden, verursacht einen Fehler zur Kompilierzeit.</span><span class="sxs-lookup"><span data-stu-id="9b57d-135">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 <span data-ttu-id="9b57d-136">[!code-vb[VbVbalrStatements&#47;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="9b57d-136">[!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]</span></span>  
  
 <span data-ttu-id="9b57d-137">[!code-vb[VbVbalrStatements&#48;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="9b57d-137">[!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b57d-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9b57d-138">See Also</span></span>  
 <span data-ttu-id="9b57d-139">[Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9b57d-139">[Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="9b57d-140"> [ReDim-Anweisung](../../../visual-basic/language-reference/statements/redim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9b57d-140"> [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) </span></span>  
<span data-ttu-id="9b57d-141"> [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9b57d-141"> [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span></span>  
<span data-ttu-id="9b57d-142"> [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9b57d-142"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="9b57d-143"> [/ optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="9b57d-143"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="9b57d-144"> [/ optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span><span class="sxs-lookup"><span data-stu-id="9b57d-144"> [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) </span></span>  
<span data-ttu-id="9b57d-145"> [/ optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span><span class="sxs-lookup"><span data-stu-id="9b57d-145"> [/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md) </span></span>  
<span data-ttu-id="9b57d-146"> [VB-Standard, Projekte, Dialogfeld „Optionen“](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span><span class="sxs-lookup"><span data-stu-id="9b57d-146"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)</span></span>
