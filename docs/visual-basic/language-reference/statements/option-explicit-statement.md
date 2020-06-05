---
title: Option Explicit-Anweisung
ms.date: 07/20/2015
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
ms.openlocfilehash: a352df0323cfeca1ea0e206ae45c3f85a2cd7da3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404368"
---
# <a name="option-explicit-statement-visual-basic"></a><span data-ttu-id="66098-102">Option Explicit-Anweisung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="66098-102">Option Explicit Statement (Visual Basic)</span></span>
<span data-ttu-id="66098-103">Erzwingt die explizite Deklaration aller Variablen in einer Datei oder das zulassen impliziter Deklarationen von Variablen.</span><span class="sxs-lookup"><span data-stu-id="66098-103">Forces explicit declaration of all variables in a file, or allows implicit declarations of variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="66098-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="66098-104">Syntax</span></span>  
  
```vb  
Option Explicit { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="66098-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="66098-105">Parts</span></span>  
 `On`  
 <span data-ttu-id="66098-106">Optional.</span><span class="sxs-lookup"><span data-stu-id="66098-106">Optional.</span></span> <span data-ttu-id="66098-107">Aktiviert die über `Option Explicit` Prüfung.</span><span class="sxs-lookup"><span data-stu-id="66098-107">Enables `Option Explicit` checking.</span></span> <span data-ttu-id="66098-108">Wenn `On` oder `Off` nicht angegeben wird, ist der Standardwert `On` .</span><span class="sxs-lookup"><span data-stu-id="66098-108">If `On` or `Off` is not specified, the default is `On`.</span></span>  
  
 `Off`  
 <span data-ttu-id="66098-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="66098-109">Optional.</span></span> <span data-ttu-id="66098-110">Deaktiviert die über `Option Explicit` Prüfung.</span><span class="sxs-lookup"><span data-stu-id="66098-110">Disables `Option Explicit` checking.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="66098-111">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="66098-111">Remarks</span></span>  
 <span data-ttu-id="66098-112">Wenn `Option Explicit On` oder `Option Explicit` in einer Datei angezeigt wird, müssen Sie mithilfe der-oder-Anweisung explizit alle Variablen deklarieren `Dim` `ReDim` .</span><span class="sxs-lookup"><span data-stu-id="66098-112">When `Option Explicit On` or `Option Explicit` appears in a file, you must explicitly declare all variables by using the `Dim` or `ReDim` statements.</span></span> <span data-ttu-id="66098-113">Wenn Sie versuchen, einen nicht deklarierten Variablennamen zu verwenden, tritt zum Zeitpunkt der Kompilierung ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="66098-113">If you try to use an undeclared variable name, an error occurs at compile time.</span></span> <span data-ttu-id="66098-114">Die- `Option Explicit Off` Anweisung ermöglicht die implizite Deklaration von Variablen.</span><span class="sxs-lookup"><span data-stu-id="66098-114">The `Option Explicit Off` statement allows implicit declaration of variables.</span></span>  
  
 <span data-ttu-id="66098-115">Wenn sie verwendet wird, muss die `Option Explicit`-Anweisung in einer Datei vor allen anderen Quellcodeanweisungen angeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="66098-115">If used, the `Option Explicit` statement must appear in a file before any other source code statements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66098-116">Das Festlegen `Option Explicit` von auf `Off` ist im Allgemeinen keine bewährte Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="66098-116">Setting `Option Explicit` to `Off` is generally not a good practice.</span></span> <span data-ttu-id="66098-117">Sie könnten den Namen einer Variable an einem oder mehreren Orten falsch buchstabieren, wodurch unerwartete Ergebnisse auftreten würden, wenn das Programm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="66098-117">You could misspell a variable name in one or more locations, which would cause unexpected results when the program is run.</span></span>  
  
## <a name="when-an-option-explicit-statement-is-not-present"></a><span data-ttu-id="66098-118">Wenn eine Option explizite Anweisung nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="66098-118">When an Option Explicit Statement Is Not Present</span></span>  
 <span data-ttu-id="66098-119">Wenn der Quellcode keine- `Option Explicit` Anweisung enthält, wird die **Option explizite** Einstellung auf der Seite "kompilieren" [, Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet.</span><span class="sxs-lookup"><span data-stu-id="66098-119">If the source code does not contain an `Option Explicit` statement, the **Option Explicit** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="66098-120">Wenn der Befehlszeilen Compiler verwendet wird, wird die [-optionexplizite-Compileroption](../../reference/command-line-compiler/optionexplicit.md) verwendet.</span><span class="sxs-lookup"><span data-stu-id="66098-120">If the command-line compiler is used, the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-explicit-in-the-ide"></a><span data-ttu-id="66098-121">So legen Sie die Option "explizit" in der IDE fest</span><span class="sxs-lookup"><span data-stu-id="66098-121">To set Option Explicit in the IDE</span></span>  
  
1. <span data-ttu-id="66098-122">Wählen Sie in **Projektmappen-Explorer**ein Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="66098-122">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="66098-123">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="66098-123">On the **Project** menu, click **Properties**.</span></span>  
  
2. <span data-ttu-id="66098-124">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="66098-124">Click the **Compile** tab.</span></span>  
  
3. <span data-ttu-id="66098-125">Legen Sie den Wert im Feld **Option explizit** fest.</span><span class="sxs-lookup"><span data-stu-id="66098-125">Set the value in the **Option Explicit** box.</span></span>  
  
 <span data-ttu-id="66098-126">Wenn Sie ein neues Projekt erstellen, wird die **Option explizite** Einstellung auf der Registerkarte **Kompilieren** auf die **Option explizite** Einstellung im Dialogfeld **VB-Standardeinstellungen** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="66098-126">When you create a new project, the **Option Explicit** setting on the **Compile** tab is set to the **Option Explicit** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="66098-127">Um auf das Dialogfeld **VB-Standardeinstellungen** zuzugreifen, klicken Sie **im Menü Extras** auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="66098-127">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="66098-128">Erweitern Sie im Dialogfeld **Optionen\*\*\*\*Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**.</span><span class="sxs-lookup"><span data-stu-id="66098-128">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="66098-129">Die ursprüngliche Standardeinstellung in **VB-Standardeinstellungen** ist `On` .</span><span class="sxs-lookup"><span data-stu-id="66098-129">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-explicit-on-the-command-line"></a><span data-ttu-id="66098-130">So legen Sie die Option explizit in der Befehlszeile fest</span><span class="sxs-lookup"><span data-stu-id="66098-130">To set Option Explicit on the command line</span></span>  
  
- <span data-ttu-id="66098-131">Schließen Sie die [-optionexplizite-](../../reference/command-line-compiler/optionexplicit.md) Compileroption in den **vbc** -Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="66098-131">Include the [-optionexplicit](../../reference/command-line-compiler/optionexplicit.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66098-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="66098-132">Example</span></span>  
 <span data-ttu-id="66098-133">Im folgenden Beispiel wird die- `Option Explicit` Anweisung verwendet, um die explizite Deklaration aller Variablen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="66098-133">The following example uses the `Option Explicit` statement to force explicit declaration of all variables.</span></span> <span data-ttu-id="66098-134">Der Versuch, eine nicht deklarierte Variable zu verwenden, verursacht einen Fehler zur Kompilierzeit.</span><span class="sxs-lookup"><span data-stu-id="66098-134">Attempting to use an undeclared variable causes an error at compile time.</span></span>  
  
 [!code-vb[VbVbalrStatements#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#47)]  
  
 [!code-vb[VbVbalrStatements#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#48)]  
  
## <a name="see-also"></a><span data-ttu-id="66098-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="66098-135">See also</span></span>

- [<span data-ttu-id="66098-136">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="66098-136">Dim Statement</span></span>](dim-statement.md)
- [<span data-ttu-id="66098-137">ReDim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="66098-137">ReDim Statement</span></span>](redim-statement.md)
- [<span data-ttu-id="66098-138">Option Compare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="66098-138">Option Compare Statement</span></span>](option-compare-statement.md)
- [<span data-ttu-id="66098-139">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="66098-139">Option Strict Statement</span></span>](option-strict-statement.md)
- [<span data-ttu-id="66098-140">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="66098-140">-optioncompare</span></span>](../../reference/command-line-compiler/optioncompare.md)
- [<span data-ttu-id="66098-141">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="66098-141">-optionexplicit</span></span>](../../reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="66098-142">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="66098-142">-optionstrict</span></span>](../../reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="66098-143">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="66098-143">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
