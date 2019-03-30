---
title: Option Infer-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.OptionInfer
- vb.Infer
helpviewer_keywords:
- variables [Visual Basic], declaring
- Option Infer statement [Visual Basic]
- Infer keyword [Visual Basic]
- declaring variables [Visual Basic], inferred
- inferred variable declaration
ms.assetid: 4ad3e6e9-8f5b-4209-a248-de22ef6e4652
ms.openlocfilehash: 43ac5bc9e32892541ed2f9b0410b6e0ef10558a6
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654327"
---
# <a name="option-infer-statement"></a><span data-ttu-id="6e912-102">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e912-102">Option Infer Statement</span></span>
<span data-ttu-id="6e912-103">Ermöglicht die Verwendung des lokalen Typrückschlusses beim Deklarieren von Variablen.</span><span class="sxs-lookup"><span data-stu-id="6e912-103">Enables the use of local type inference in declaring variables.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e912-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e912-104">Syntax</span></span>  
  
```  
Option Infer { On | Off }  
```  
  
## <a name="parts"></a><span data-ttu-id="6e912-105">Teile</span><span class="sxs-lookup"><span data-stu-id="6e912-105">Parts</span></span>  
  
|<span data-ttu-id="6e912-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="6e912-106">Term</span></span>|<span data-ttu-id="6e912-107">Definition</span><span class="sxs-lookup"><span data-stu-id="6e912-107">Definition</span></span>|  
|---|---|  
|`On`|<span data-ttu-id="6e912-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="6e912-108">Optional.</span></span> <span data-ttu-id="6e912-109">Ermöglicht den lokalen Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="6e912-109">Enables local type inference.</span></span>|  
|`Off`|<span data-ttu-id="6e912-110">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="6e912-110">Optional.</span></span> <span data-ttu-id="6e912-111">Deaktiviert den lokalen Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="6e912-111">Disables local type inference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e912-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e912-112">Remarks</span></span>  
 <span data-ttu-id="6e912-113">Geben Sie zum Festlegen von `Option Infer` in einer Datei am Anfang der Datei `Option Infer On` oder `Option Infer Off` ein.</span><span class="sxs-lookup"><span data-stu-id="6e912-113">To set `Option Infer` in a file, type `Option Infer On` or `Option Infer Off` at the top of the file, before any other source code.</span></span> <span data-ttu-id="6e912-114">Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.</span><span class="sxs-lookup"><span data-stu-id="6e912-114">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="6e912-115">Wenn Sie für `Option Infer``On` festlegen, können Sie lokale Variablen deklarieren, ohne explizit einen Datentyp anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6e912-115">When you set `Option Infer` to `On`, you can declare local variables without explicitly stating a data type.</span></span> <span data-ttu-id="6e912-116">Der Compiler leitet den Datentyp einer Variablen vom Typ des Initialisierungsausdrucks ab.</span><span class="sxs-lookup"><span data-stu-id="6e912-116">The compiler infers the data type of a variable from the type of its initialization expression.</span></span>  
  
 <span data-ttu-id="6e912-117">In der folgenden Abbildung ist `Option Infer` eingeschaltet.</span><span class="sxs-lookup"><span data-stu-id="6e912-117">In the following illustration, `Option Infer` is turned on.</span></span> <span data-ttu-id="6e912-118">Die Variable in der Deklaration `Dim someVar = 2` wird als ganze Zahl durch Typrückschluss deklariert.</span><span class="sxs-lookup"><span data-stu-id="6e912-118">The variable in the declaration `Dim someVar = 2` is declared as an integer by type inference.</span></span>

 <span data-ttu-id="6e912-119">Der folgende Screenshot zeigt IntelliSense, wenn Option Infer aktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="6e912-119">The following screenshot shows IntelliSense when Option Infer is on:</span></span> 
  
 ![Bildschirmabbildung von IntelliSense-Ansicht angezeigt, wenn Option Infer aktiviert ist.](./media/option-infer-statement/option-infer-as-integer-on.png)  
  
 <span data-ttu-id="6e912-121">In der folgenden Abbildung ist `Option Infer` deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6e912-121">In the following illustration, `Option Infer` is turned off.</span></span> <span data-ttu-id="6e912-122">Die Variable in der Deklaration `Dim someVar = 2` ist durch Typrückschluss als `Object` deklariert.</span><span class="sxs-lookup"><span data-stu-id="6e912-122">The variable in the declaration `Dim someVar = 2` is declared as an `Object` by type inference.</span></span> <span data-ttu-id="6e912-123">In diesem Beispiel die **Option Strict** Einstellung **aus** auf die [Seite "Kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6e912-123">In this example, the **Option Strict** setting is set to **Off** on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
 <span data-ttu-id="6e912-124">Der folgende Screenshot zeigt IntelliSense, wenn Option Infer deaktiviert ist:</span><span class="sxs-lookup"><span data-stu-id="6e912-124">The following screenshot shows IntelliSense when Option Infer is off:</span></span>
 
 ![Bildschirmabbildung von IntelliSense-Ansicht angezeigt, wenn Option Infer deaktiviert ist.](./media/option-infer-statement/option-infer-as-object-off.png)  
  
> [!NOTE]
>  <span data-ttu-id="6e912-126">Wenn eine Variable als `Object`deklariert ist, kann sich der Laufzeittyp ändern, während das Programm ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6e912-126">When a variable is declared as an `Object`, the run-time type can change while the program is running.</span></span> <span data-ttu-id="6e912-127">Visual Basic führt Operationen mit Bezeichnung *Boxing* und *unboxing* für die Konvertierung zwischen einer `Object` und ein Werttyp, der Ausführung langsamer macht.</span><span class="sxs-lookup"><span data-stu-id="6e912-127">Visual Basic performs operations called *boxing* and *unboxing* to convert between an `Object` and a value type, which makes execution slower.</span></span> <span data-ttu-id="6e912-128">Weitere Informationen zu Boxing und unboxing finden Sie unter den [Visual Basic-Sprachspezifikation](~/_vblang/spec/conversions.md#value-type-conversions).</span><span class="sxs-lookup"><span data-stu-id="6e912-128">For information about boxing and unboxing, see the [Visual Basic Language Specification](~/_vblang/spec/conversions.md#value-type-conversions).</span></span>
  
 <span data-ttu-id="6e912-129">Typrückschluss findet auf Prozedurebene Anwendung und nicht außerhalb einer Prozedur in einer Klasse, Struktur, Modul oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6e912-129">Type inference applies at the procedure level, and does not apply outside a procedure in a class, structure, module, or interface.</span></span>  
  
 <span data-ttu-id="6e912-130">Weitere Informationen finden Sie unter [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="6e912-130">For additional information, see [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>  
  
## <a name="when-an-option-infer-statement-is-not-present"></a><span data-ttu-id="6e912-131">Wenn eine Option Infer-Anweisung nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="6e912-131">When an Option Infer Statement Is Not Present</span></span>  
 <span data-ttu-id="6e912-132">Wenn der Quellcode kein `Option Infer` -Anweisung, die **Option Infer** festlegen auf die [Seite "Kompilieren", Projekt-Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e912-132">If the source code does not contain an `Option Infer` statement, the **Option Infer** setting on the [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="6e912-133">Wenn der Befehlszeilen-Compiler verwendet wird, die [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) -Compileroption verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e912-133">If the command-line compiler is used, the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option is used.</span></span>  
  
#### <a name="to-set-option-infer-in-the-ide"></a><span data-ttu-id="6e912-134">Festlegen der Option Infer in der IDE</span><span class="sxs-lookup"><span data-stu-id="6e912-134">To set Option Infer in the IDE</span></span>  
  
1.  <span data-ttu-id="6e912-135">Wählen Sie im **Projektmappen-Explorer** ein Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="6e912-135">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="6e912-136">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="6e912-136">On the **Project** menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6e912-137">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="6e912-137">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="6e912-138">Legen Sie den Wert der **Option infer-** Feld.</span><span class="sxs-lookup"><span data-stu-id="6e912-138">Set the value in the **Option infer** box.</span></span>  
  
 <span data-ttu-id="6e912-139">Bei der Erstellung eines neuen Projekts die **Option Infer** festlegen auf die **Kompilieren** Registerkarte nastaven NA hodnotu der **Option Infer** festlegen in der **VB Defaults** Das Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="6e912-139">When you create a new project, the **Option Infer** setting on the **Compile** tab is set to the **Option Infer** setting in the **VB Defaults** dialog box.</span></span> <span data-ttu-id="6e912-140">Für den Zugriff auf die **VB Defaults** Dialogfeld auf die **Tools** Menü klicken Sie auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="6e912-140">To access the **VB Defaults** dialog box, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="6e912-141">Erweitern Sie im Dialogfeld **Optionen** **Projekte und Lösungen**, und klicken Sie dann auf **VB Defaults**.</span><span class="sxs-lookup"><span data-stu-id="6e912-141">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="6e912-142">Die ursprüngliche Standardeinstellung in **VB Defaults** ist `On`.</span><span class="sxs-lookup"><span data-stu-id="6e912-142">The initial default setting in **VB Defaults** is `On`.</span></span>  
  
#### <a name="to-set-option-infer-on-the-command-line"></a><span data-ttu-id="6e912-143">Festlegen der Option Infer in der Befehlszeile.</span><span class="sxs-lookup"><span data-stu-id="6e912-143">To set Option Infer on the command line</span></span>  
  
-   <span data-ttu-id="6e912-144">Enthalten die [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) -Compileroption in der **Vbc** Befehl.</span><span class="sxs-lookup"><span data-stu-id="6e912-144">Include the [/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="default-data-types-and-values"></a><span data-ttu-id="6e912-145">Standarddatentypen und -werte</span><span class="sxs-lookup"><span data-stu-id="6e912-145">Default Data Types and Values</span></span>  
 <span data-ttu-id="6e912-146">Die folgende Tabelle beschreibt die Ergebnisse der verschiedenen Kombinationen der Spezifizierung von Datentyp und Initialisierung in einer `Dim`-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="6e912-146">The following table describes the results of various combinations of specifying the data type and initializer in a `Dim` statement.</span></span>  
  
|<span data-ttu-id="6e912-147">Datentyp angegeben?</span><span class="sxs-lookup"><span data-stu-id="6e912-147">Data type specified?</span></span>|<span data-ttu-id="6e912-148">Initialisierung angegeben?</span><span class="sxs-lookup"><span data-stu-id="6e912-148">Initializer specified?</span></span>|<span data-ttu-id="6e912-149">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e912-149">Example</span></span>|<span data-ttu-id="6e912-150">Ergebnis</span><span class="sxs-lookup"><span data-stu-id="6e912-150">Result</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="6e912-151">Nein</span><span class="sxs-lookup"><span data-stu-id="6e912-151">No</span></span>|<span data-ttu-id="6e912-152">Nein</span><span class="sxs-lookup"><span data-stu-id="6e912-152">No</span></span>|`Dim qty`|<span data-ttu-id="6e912-153">Wenn `Option Strict` deaktiviert ist (Standard), ist die Variable auf `Nothing` eingestellt.</span><span class="sxs-lookup"><span data-stu-id="6e912-153">If `Option Strict` is off (the default), the variable is set to `Nothing`.</span></span><br /><br /> <span data-ttu-id="6e912-154">Wenn `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="6e912-154">If `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="6e912-155">Nein</span><span class="sxs-lookup"><span data-stu-id="6e912-155">No</span></span>|<span data-ttu-id="6e912-156">Ja</span><span class="sxs-lookup"><span data-stu-id="6e912-156">Yes</span></span>|`Dim qty = 5`|<span data-ttu-id="6e912-157">Wenn `Option Infer` aktiviert ist (Standard), übernimmt die Variable den Datentyp des Initialisierers an.</span><span class="sxs-lookup"><span data-stu-id="6e912-157">If `Option Infer` is on (the default), the variable takes the data type of the initializer.</span></span> <span data-ttu-id="6e912-158">Finden Sie unter [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span><span class="sxs-lookup"><span data-stu-id="6e912-158">See [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span><br /><br /> <span data-ttu-id="6e912-159">Wenn `Option Infer` und `Option Strict` ausgeschaltet sind, nimmt die Variable den Datentyp des `Object` an.</span><span class="sxs-lookup"><span data-stu-id="6e912-159">If `Option Infer` is off and `Option Strict` is off, the variable takes the data type of `Object`.</span></span><br /><br /> <span data-ttu-id="6e912-160">Wenn `Option Infer` deaktiviert ist und `Option Strict` aktiviert ist, tritt ein Kompilierzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="6e912-160">If `Option Infer` is off and `Option Strict` is on, a compile-time error occurs.</span></span>|  
|<span data-ttu-id="6e912-161">Ja</span><span class="sxs-lookup"><span data-stu-id="6e912-161">Yes</span></span>|<span data-ttu-id="6e912-162">Nein</span><span class="sxs-lookup"><span data-stu-id="6e912-162">No</span></span>|`Dim qty As Integer`|<span data-ttu-id="6e912-163">Die Variable wird auf den Standardwert für den Datentyp initialisiert.</span><span class="sxs-lookup"><span data-stu-id="6e912-163">The variable is initialized to the default value for the data type.</span></span> <span data-ttu-id="6e912-164">Weitere Informationen finden Sie unter [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="6e912-164">For more information, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>|  
|<span data-ttu-id="6e912-165">Ja</span><span class="sxs-lookup"><span data-stu-id="6e912-165">Yes</span></span>|<span data-ttu-id="6e912-166">Ja</span><span class="sxs-lookup"><span data-stu-id="6e912-166">Yes</span></span>|`Dim qty  As Integer = 5`|<span data-ttu-id="6e912-167">Wenn der Datentyp der Initialisierung nicht in den angegebenen Datentyp konvertiert werden kann, tritt ein Fehler während der Kompilierung auf.</span><span class="sxs-lookup"><span data-stu-id="6e912-167">If the data type of the initializer is not convertible to the specified data type, a compile-time error occurs.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6e912-168">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e912-168">Example</span></span>  
 <span data-ttu-id="6e912-169">Die folgenden Beispiele veranschaulichen, wie die `Option Infer`-Anweisung den lokalen Typrückschluss ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6e912-169">The following examples demonstrate how the `Option Infer` statement enables local type inference.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="6e912-170">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6e912-170">Example</span></span>  
 <span data-ttu-id="6e912-171">Das folgende Beispiel veranschaulicht, dass der Laufzeittyp abweichen kann, wenn eine Variable als ein `Object` gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="6e912-171">The following example demonstrates that the run-time type can differ when a variable is identified as an `Object`.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="6e912-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e912-172">See also</span></span>
- [<span data-ttu-id="6e912-173">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e912-173">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="6e912-174">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="6e912-174">Local Type Inference</span></span>](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [<span data-ttu-id="6e912-175">Option Compare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e912-175">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="6e912-176">Option Explicit-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e912-176">Option Explicit Statement</span></span>](../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [<span data-ttu-id="6e912-177">Option Strict-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6e912-177">Option Strict Statement</span></span>](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [<span data-ttu-id="6e912-178">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="6e912-178">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
- [<span data-ttu-id="6e912-179">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="6e912-179">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="6e912-180">Boxing und Unboxing</span><span class="sxs-lookup"><span data-stu-id="6e912-180">Boxing and Unboxing</span></span>](../../../csharp/programming-guide/types/boxing-and-unboxing.md)
