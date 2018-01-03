---
title: Option Explicit-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Explicit
- vb.OptionExplicit
helpviewer_keywords:
- declaring variables [Visual Basic], explicit
- forced variable declaration in Option Explicit statement [Visual Basic]
- Explicit keyword
- explicit variable declaration
- Option Explicit statement [Visual Basic]
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f3d4c9cd3310e0ec3943c4e2b5e28be5b9a393db
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="48bee-102">Option Explicit-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48bee-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="48bee-103">Erzwingt die explizite Deklaration aller Variablen in einer Datei oder die Erweiterung impliziter Deklarationen von Variablen.</span><span class="sxs-lookup"><span data-stu-id="48bee-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48bee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48bee-104">Syntax</span></span>  
  
```  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="48bee-105">Teile</span><span class="sxs-lookup"><span data-stu-id="48bee-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="48bee-106">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="48bee-106">Optional.</span></span> <span data-ttu-id="48bee-107">Ermöglicht `Option Explicit` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="48bee-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="48bee-108">Wenn `On` oder `Off` nicht angegeben ist, wird der Standardwert ist `On`.</span><span class="sxs-lookup"><span data-stu-id="48bee-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="48bee-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="48bee-109">Optional.</span></span> <span data-ttu-id="48bee-110">Deaktiviert die `Option Explicit` überprüfen.</span><span class="sxs-lookup"><span data-stu-id="48bee-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48bee-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48bee-111">Remarks</span></span>  
 <span data-ttu-id="48bee-112">Wenn `Option Explicit On` oder `Option Explicit` wird in einer Datei müssen Sie alle Variablen explizit deklarieren, indem die `Dim` oder `ReDim` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="48bee-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="48bee-113">Wenn Sie versuchen, einen nicht deklarierten Variablennamen verwenden, tritt ein Fehler zur Kompilierzeit.</span><span class="sxs-lookup"><span data-stu-id="48bee-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="48bee-114">Die `Option Explicit Off` Anweisung ermöglicht die implizite Deklaration von Variablen.</span><span class="sxs-lookup"><span data-stu-id="48bee-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="48bee-115">Wenn sie verwendet wird, muss die `Option Explicit`-Anweisung in einer Datei vor allen anderen Quellcodeanweisungen angeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="48bee-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48bee-116">Festlegen von `Option Explicit` auf `Off` sind im Allgemeinen nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="48bee-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="48bee-117">Sie könnten den Namen einer Variable an einem oder mehreren Orten falsch buchstabieren, wodurch unerwartete Ergebnisse auftreten würden, wenn das Programm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="48bee-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="48bee-118">Wenn eine Option Explicit-Anweisung nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="48bee-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="48bee-119">Wenn der Quellcode nicht enthält ein `Option Explicit` -Anweisung, die **Option Explicit** festlegen für die [Seite kompilieren, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="48bee-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="48bee-120">Wenn Sie der Befehlszeilencompiler verwendet wird, die [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) -Compileroption verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="48bee-120">If the command-line compiler is used, the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="48bee-121">Option Explicit festlegen, in der IDE</span><span class="sxs-lookup"><span data-stu-id="48bee-121">To set Option Explicit in the IDE</span></span>  
  
1.  <span data-ttu-id="48bee-122">Wählen Sie im **Projektmappen-Explorer** ein Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="48bee-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="48bee-123">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="48bee-123">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="48bee-124">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="48bee-124">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="48bee-125">Legen Sie den Wert der **Option Explicit** Feld.</span><span class="sxs-lookup"><span data-stu-id="48bee-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="48bee-126">Bei der Erstellung eines neuen Projekts die **Option Explicit** festlegen, auf die **Kompilieren** auf die Registerkarte "festgelegt ist die **Option Explicit** festlegen in der **VB Defaults**(Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="48bee-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="48bee-127">Für den Zugriff auf die **VB Defaults** Dialogfeld auf die **Tools** Menü klicken Sie auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="48bee-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="48bee-128">Erweitern Sie im Dialogfeld **Optionen** **Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**.</span><span class="sxs-lookup"><span data-stu-id="48bee-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="48bee-129">Die ursprüngliche Standardeinstellung in **VB-Standard** ist `On`.</span><span class="sxs-lookup"><span data-stu-id="48bee-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="48bee-130">Option Explicit in der Befehlszeile festlegen</span><span class="sxs-lookup"><span data-stu-id="48bee-130">To set Option Explicit on the command line</span></span>  
  
-   <span data-ttu-id="48bee-131">Enthalten die [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) -Compileroption in der **Vbc** Befehl.</span><span class="sxs-lookup"><span data-stu-id="48bee-131">Include the [/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48bee-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="48bee-132">Example</span></span>  
 <span data-ttu-id="48bee-133">Im folgenden Beispiel wird die `Option Explicit` Anweisung, um die explizite Deklaration aller Variablen durchzusetzen.</span><span class="sxs-lookup"><span data-stu-id="48bee-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="48bee-134">Versucht, eine nicht deklarierte Variable verwenden, verursacht einen Fehler zur Kompilierzeit.</span><span class="sxs-lookup"><span data-stu-id="48bee-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-explicit-statement_2.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="48bee-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48bee-135">See Also</span></span>  
 [<span data-ttu-id="48bee-136">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="48bee-136">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [<span data-ttu-id="48bee-137">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="48bee-137">ReDim Statement</span></span>](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [<span data-ttu-id="48bee-138">Option Compare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="48bee-138">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)  
 [<span data-ttu-id="48bee-139">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="48bee-139">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [<span data-ttu-id="48bee-140">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="48bee-140">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)  
 [<span data-ttu-id="48bee-141">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="48bee-141">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)  
 [<span data-ttu-id="48bee-142">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="48bee-142">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)  
 [<span data-ttu-id="48bee-143">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="48bee-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
