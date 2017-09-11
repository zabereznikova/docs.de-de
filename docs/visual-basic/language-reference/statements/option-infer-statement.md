---
title: Option Infer-Anweisung | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.OptionInfer
- vb.Infer
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement
- Infer keyword
- declaring variables, inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
caps.latest.revision: 72
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
ms.openlocfilehash: 56c2813f0fcfc23c4eb4039ffbbb1d9deeccb72c
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="option-infer-statement"></a><span data-ttu-id="f5c99-102">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="f5c99-102">Option Infer Statement</span></span>
<span data-ttu-id="f5c99-103">Ermöglicht die Verwendung des lokalen Typrückschlusses beim Deklarieren von Variablen.</span><span class="sxs-lookup"><span data-stu-id="f5c99-103">Enables the use of local type inference in declaring variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5c99-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5c99-104">Syntax</span></span>  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="f5c99-105">Teile</span><span class="sxs-lookup"><span data-stu-id="f5c99-105">Parts</span></span>  
  
|<span data-ttu-id="f5c99-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="f5c99-106">Term</span></span>|<span data-ttu-id="f5c99-107">Definition</span><span class="sxs-lookup"><span data-stu-id="f5c99-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="f5c99-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="f5c99-108">Optional.</span></span> <span data-ttu-id="f5c99-109">Ermöglicht den lokalen Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="f5c99-109">Enables local type inference.</span></span>|  
|`Off`|<span data-ttu-id="f5c99-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="f5c99-110">Optional.</span></span> <span data-ttu-id="f5c99-111">Deaktiviert den lokalen Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="f5c99-111">Disables local type inference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5c99-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5c99-112">Remarks</span></span>  
 <span data-ttu-id="f5c99-113">Geben Sie zum Festlegen von `Option Infer` in einer Datei am Anfang der Datei `Option Infer On` oder `Option Infer Off` ein.</span><span class="sxs-lookup"><span data-stu-id="f5c99-113">To set `Option Infer` in a file, type `Option Infer On` or `Option Infer Off` at the top of the file, before any other source code.</span></span> <span data-ttu-id="f5c99-114">Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.</span><span class="sxs-lookup"><span data-stu-id="f5c99-114">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="f5c99-115">Wenn Sie für `Option Infer` `On` festlegen, können Sie lokale Variablen deklarieren, ohne explizit einen Datentyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f5c99-115">When you set `Option Infer` to `On`, you can declare local variables without explicitly stating a data type.</span></span> <span data-ttu-id="f5c99-116">Der Compiler leitet den Datentyp einer Variablen vom Typ des Initialisierungsausdrucks ab.</span><span class="sxs-lookup"><span data-stu-id="f5c99-116">The compiler infers the data type of a variable from the type of its initialization expression.</span></span>  
  
 <span data-ttu-id="f5c99-117">In der folgenden Abbildung ist `Option Infer` eingeschaltet.</span><span class="sxs-lookup"><span data-stu-id="f5c99-117">In the following illustration, `Option Infer` is turned on.</span></span> <span data-ttu-id="f5c99-118">Die Variable in der Deklaration `Dim someVar = 2` wird als ganze Zahl durch Typrückschluss deklariert.</span><span class="sxs-lookup"><span data-stu-id="f5c99-118">The variable in the declaration `Dim someVar = 2` is declared as an integer by type inference.</span></span>  
  
 <span data-ttu-id="f5c99-119">![IntelliSense-Ansicht der Deklaration.](../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span><span class="sxs-lookup"><span data-stu-id="f5c99-119">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasinteger.png "optionInferAsInteger")</span></span>  
<span data-ttu-id="f5c99-120">IntelliSense, wenn die Option Infer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f5c99-120">IntelliSense when Option Infer is on</span></span>  
  
 <span data-ttu-id="f5c99-121">In der folgenden Abbildung ist `Option Infer` deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="f5c99-121">In the following illustration, `Option Infer` is turned off.</span></span> <span data-ttu-id="f5c99-122">Die Variable in der Deklaration `Dim someVar = 2` ist durch Typrückschluss als `Object` deklariert.</span><span class="sxs-lookup"><span data-stu-id="f5c99-122">The variable in the declaration `Dim someVar = 2` is declared as an `Object` by type inference.</span></span> <span data-ttu-id="f5c99-123">In diesem Beispiel die **Option Strict** eingestellt sind **aus** auf der [Seite kompilieren, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f5c99-123">In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="f5c99-124">![IntelliSense-Ansicht der Deklaration.](../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span><span class="sxs-lookup"><span data-stu-id="f5c99-124">![IntelliSense view of the declaration.](../../../visual-basic/language-reference/statements/media/optioninferasobject.png "optionInferAsObject")</span></span>  
<span data-ttu-id="f5c99-125">IntelliSense, wenn Option Infer deaktiviert ist</span><span class="sxs-lookup"><span data-stu-id="f5c99-125">IntelliSense when Option Infer is off</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5c99-126">Wenn eine Variable als `Object`deklariert ist, kann sich der Laufzeittyp ändern, während das Programm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f5c99-126">When a variable is declared as an `Object`, the run-time type can change while the program is running.</span></span> [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="f5c99-127">Führt Operationen mit Bezeichnung *Boxing* und *unboxing* zum Konvertieren zwischen einer `Object` und ein Werttyp, der Ausführung langsamer macht.</span><span class="sxs-lookup"><span data-stu-id="f5c99-127"> performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower.</span></span> <span data-ttu-id="f5c99-128">Informationen zu Boxing und unboxing finden Sie unter der [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).</span><span class="sxs-lookup"><span data-stu-id="f5c99-128">For information about boxing and unboxing, see the [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).</span></span>  
  
 <span data-ttu-id="f5c99-129">Typrückschluss findet auf Prozedurebene Anwendung und nicht außerhalb einer Prozedur in einer Klasse, Struktur, Modul oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="f5c99-129">Type inference applies at the procedure level, and does not apply outside a procedure in a class, structure, module, or interface.</span></span>  
  
 <span data-ttu-id="f5c99-130">Weitere Informationen finden Sie unter [lokalen Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="f5c99-130">For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="when-an-option-infer-statement-is-not-present"></a><span data-ttu-id="f5c99-131">Wenn eine Option Infer-Anweisung nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="f5c99-131">When an Option Infer Statement Is Not Present</span></span>  
 <span data-ttu-id="f5c99-132">Enthält der Quellcode kein `Option Infer` -Anweisung, die **Option Infer** auf der [Seite kompilieren, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f5c99-132">If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="f5c99-133">Wenn der Befehlszeile-Compiler verwendet wird, die [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) -Compileroption verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f5c99-133">If the command-line compiler is used, the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-infer-in-the-ide"></a><span data-ttu-id="f5c99-134">Festlegen der Option Infer in der IDE</span><span class="sxs-lookup"><span data-stu-id="f5c99-134">To set Option Infer in the IDE</span></span>  
  
1.  <span data-ttu-id="f5c99-135">In **Projektmappen-Explorer**, wählen Sie ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="f5c99-135">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="f5c99-136">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f5c99-136">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="f5c99-137">Weitere Informationen finden Sie unter [NIB: Verwalten von Projekteigenschaften mit dem Projekt-Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="f5c99-137">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="f5c99-138">Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="f5c99-138">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="f5c99-139">Legen Sie den Wert der **Option infer** Feld.</span><span class="sxs-lookup"><span data-stu-id="f5c99-139">Set the value in the **Option infer** box.</span></span>  
  
 <span data-ttu-id="f5c99-140">Wenn Sie ein neues Projekt erstellen die **Option Infer** auf der **Kompilieren** Registerkarte auf festgelegt ist die **Option Infer** festlegen in der **VB-Standard** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="f5c99-140">When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="f5c99-141">Für den Zugriff auf die **VB-Standard** Dialogfelds die **Tools** Menü klicken Sie auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="f5c99-141">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="f5c99-142">In der **Optionen** Dialogfeld erweitern Sie **Projekte und Projektmappen**, und klicken Sie dann auf **VB-Standard**.</span><span class="sxs-lookup"><span data-stu-id="f5c99-142">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="f5c99-143">Die ursprüngliche Standardeinstellung in **VB-Standard** ist `On`.</span><span class="sxs-lookup"><span data-stu-id="f5c99-143">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-infer-on-the-command-line"></a><span data-ttu-id="f5c99-144">Festlegen der Option Infer in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="f5c99-144">To set Option Infer on the command line</span></span>  
  
-   <span data-ttu-id="f5c99-145">Enthalten die [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) -Compileroption in der **Vbc** Befehl.</span><span class="sxs-lookup"><span data-stu-id="f5c99-145">Include the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="default-data-types-and-values"></a><span data-ttu-id="f5c99-146">Standarddatentypen und -werte</span><span class="sxs-lookup"><span data-stu-id="f5c99-146">Default Data Types and Values</span></span>  
 <span data-ttu-id="f5c99-147">Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Spezifizierung von Datentyp und Initialisierung in einer `Dim`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="f5c99-147">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="f5c99-148">Datentyp angegeben?</span><span class="sxs-lookup"><span data-stu-id="f5c99-148">Data type specified?</span></span>|<span data-ttu-id="f5c99-149">Initialisierung angegeben?</span><span class="sxs-lookup"><span data-stu-id="f5c99-149">Initializer specified?</span></span>|<span data-ttu-id="f5c99-150">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5c99-150">Example</span></span>|<span data-ttu-id="f5c99-151">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="f5c99-151">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="f5c99-152">Nein</span><span class="sxs-lookup"><span data-stu-id="f5c99-152">No</span></span>|<span data-ttu-id="f5c99-153">Nein</span><span class="sxs-lookup"><span data-stu-id="f5c99-153">No</span></span>|`Dim qty`|<span data-ttu-id="f5c99-154">Wenn `Option Strict` deaktiviert ist (Standard), ist die Variable auf `Nothing` eingestellt.</span><span class="sxs-lookup"><span data-stu-id="f5c99-154">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="f5c99-155">Wenn `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="f5c99-155">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="f5c99-156">Nein</span><span class="sxs-lookup"><span data-stu-id="f5c99-156">No</span></span>|<span data-ttu-id="f5c99-157">Ja</span><span class="sxs-lookup"><span data-stu-id="f5c99-157">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="f5c99-158">Wenn `Option Infer` aktiviert ist (Standard), übernimmt die Variable den Datentyp des Initialisierers an.</span><span class="sxs-lookup"><span data-stu-id="f5c99-158">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="f5c99-159">Finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="f5c99-159">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="f5c99-160">Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.</span><span class="sxs-lookup"><span data-stu-id="f5c99-160">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="f5c99-161">Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="f5c99-161">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="f5c99-162">Ja</span><span class="sxs-lookup"><span data-stu-id="f5c99-162">Yes</span></span>|<span data-ttu-id="f5c99-163">Nein</span><span class="sxs-lookup"><span data-stu-id="f5c99-163">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="f5c99-164">Die Variable wird auf den Standardwert für den Datentyp initialisiert.</span><span class="sxs-lookup"><span data-stu-id="f5c99-164">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="f5c99-165">Weitere Informationen finden Sie unter [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="f5c99-165">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|  
|<span data-ttu-id="f5c99-166">Ja</span><span class="sxs-lookup"><span data-stu-id="f5c99-166">Yes</span></span>|<span data-ttu-id="f5c99-167">Ja</span><span class="sxs-lookup"><span data-stu-id="f5c99-167">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="f5c99-168">Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.</span><span class="sxs-lookup"><span data-stu-id="f5c99-168">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f5c99-169">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5c99-169">Example</span></span>  
 <span data-ttu-id="f5c99-170">Die folgenden Beispiele veranschaulichen, wie die `Option Infer`-Anweisung den lokalen Typrückschluss ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f5c99-170">The following examples demonstrate how the `Option Infer` statement enables local type inference.</span></span>  
  
 <span data-ttu-id="f5c99-171">[!code-vb[VbVbalrTypeInference&6;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="f5c99-171">[!code-vb[VbVbalrTypeInference#6](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5c99-172">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5c99-172">Example</span></span>  
 <span data-ttu-id="f5c99-173">Das folgende Beispiel veranschaulicht, dass der Laufzeittyp abweichen kann, wenn eine Variable als ein `Object` gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="f5c99-173">The following example demonstrates that the run-time type can differ when a variable is identified as an `Object`.</span></span>  
  
 <span data-ttu-id="f5c99-174">[!code-vb[VbVbalrTypeInference&#11;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="f5c99-174">[!code-vb[VbVbalrTypeInference#11](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/option-infer-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c99-175">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5c99-175">See Also</span></span>  
 <span data-ttu-id="f5c99-176">[Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f5c99-176">[Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="f5c99-177"> [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="f5c99-177"> [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="f5c99-178"> [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f5c99-178"> [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md) </span></span>  
<span data-ttu-id="f5c99-179"> [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f5c99-179"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="f5c99-180"> [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span><span class="sxs-lookup"><span data-stu-id="f5c99-180"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md) </span></span>  
<span data-ttu-id="f5c99-181"> [Visual Basic Standard, Projekte, Optionen (Dialogfeld)](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box) </span><span class="sxs-lookup"><span data-stu-id="f5c99-181"> [Visual Basic Defaults, Projects, Options Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box) </span></span>  
<span data-ttu-id="f5c99-182"> [/ optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="f5c99-182"> [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="f5c99-183"> [Boxing und Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)</span><span class="sxs-lookup"><span data-stu-id="f5c99-183"> [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)</span></span>
