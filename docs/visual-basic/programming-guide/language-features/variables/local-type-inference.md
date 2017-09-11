---
title: "Lokaler Typrückschluss (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- local type inference
- vb.TypeInfer
dev_langs:
- VB
helpviewer_keywords:
- Option Infer statement
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
caps.latest.revision: 43
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
ms.openlocfilehash: af8de63eb00db917771600f0fca8f200ec451afe
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="local-type-inference-visual-basic"></a><span data-ttu-id="3d449-102">Lokaler Typrückschluss (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3d449-102">Local Type Inference (Visual Basic)</span></span>
<span data-ttu-id="3d449-103">Visual Basic-Compiler verwendet *Typrückschluss* bestimmt die Datentypen von lokalen Variablen deklariert werden, ohne eine `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="3d449-103">The Visual Basic compiler uses *type inference* to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="3d449-104">Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungsausdrucks ab.</span><span class="sxs-lookup"><span data-stu-id="3d449-104">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="3d449-105">Dadurch können Sie Variablen zu deklarieren, ohne explizit einen Typ anzugeben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3d449-105">This enables you to declare variables without explicitly stating a type, as shown in the following example.</span></span> <span data-ttu-id="3d449-106">Ergebnis der Deklarationen sind beide `num1` und `num2` sind stark typisiert als ganze Zahlen.</span><span class="sxs-lookup"><span data-stu-id="3d449-106">As a result of the declarations, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 <span data-ttu-id="3d449-107">[!code-vb[VbVbalrTypeInference&#1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3d449-107">[!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d449-108">Wenn Sie nicht möchten `num2` im vorherigen Beispiel als typisiert wird ein `Integer`, Sie können einen anderen Typ angeben, indem Sie mit einer Deklaration wie `Dim num3 As Object = 3` oder `Dim num4 As Double = 3`.</span><span class="sxs-lookup"><span data-stu-id="3d449-108">If you do not want `num2` in the previous example to be typed as an `Integer`, you can specify another type by using a declaration like `Dim num3 As Object = 3` or `Dim num4 As Double = 3`.</span></span>  
  
 <span data-ttu-id="3d449-109">Lokaler Typrückschluss gilt auf Prozedurebene.</span><span class="sxs-lookup"><span data-stu-id="3d449-109">Local type inference applies at procedure level.</span></span> <span data-ttu-id="3d449-110">Er kann nicht zum Deklarieren von Variablen auf Modulebene (innerhalb einer Klasse, Struktur, Modul oder Schnittstelle jedoch nicht innerhalb einer Prozedur oder eines Blocks) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3d449-110">It cannot be used to declare variables at module level (within a class, structure, module, or interface but not within a procedure or block).</span></span> <span data-ttu-id="3d449-111">Wenn `num2` im vorherigen Beispiel wurden ein Feld einer Klasse anstelle einer lokalen Variablen in einer Prozedur, die Deklaration würde einen Fehler mit `Option Strict` , und klassifizieren `num2` als ein `Object` mit `Option Strict` deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3d449-111">If `num2` in the previous example were a field of a class instead of a local variable in a procedure, the declaration would cause an error with `Option Strict` on, and would classify `num2` as an `Object` with `Option Strict` off.</span></span> <span data-ttu-id="3d449-112">Auf ähnliche Weise lokaler Typrückschluss gilt nicht für Verfahren auf Variablen, die als `Static`.</span><span class="sxs-lookup"><span data-stu-id="3d449-112">Similarly, local type inference does not apply to procedure level variables declared as `Static`.</span></span>  
  
## <a name="type-inference-vs-late-binding"></a><span data-ttu-id="3d449-113">Typrückschluss und Späte Bindung</span><span class="sxs-lookup"><span data-stu-id="3d449-113">Type Inference vs. Late Binding</span></span>  
 <span data-ttu-id="3d449-114">Code, der Typrückschluss verwendet ähnelt Code, der auf die späte Bindung beruht.</span><span class="sxs-lookup"><span data-stu-id="3d449-114">Code that uses type inference resembles code that relies on late binding.</span></span> <span data-ttu-id="3d449-115">Typrückschluss Typen jedoch dringend die Variable verlassen, als `Object`.</span><span class="sxs-lookup"><span data-stu-id="3d449-115">However, type inference strongly types the variable instead of leaving it as `Object`.</span></span> <span data-ttu-id="3d449-116">Der Compiler verwendet eine Variable Initialisierer bestimmt den Typ der Variablen zum Zeitpunkt der Kompilierung zu früh gebundenen Code zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="3d449-116">The compiler uses a variable's initializer to determine the variable's type at compile time to produce early-bound code.</span></span> <span data-ttu-id="3d449-117">Im vorherigen Beispiel `num2`, z. B. `num1`, als typisiert ist, eine `Integer`.</span><span class="sxs-lookup"><span data-stu-id="3d449-117">In the previous example, `num2`, like `num1`, is typed as an `Integer`.</span></span>  
  
 <span data-ttu-id="3d449-118">Das Verhalten früh gebundener Variablen unterscheidet sich von dem spät gebundenen Variablen, für die der Typ nur zur Laufzeit bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="3d449-118">The behavior of early-bound variables differs from that of late-bound variables, for which the type is known only at run time.</span></span> <span data-ttu-id="3d449-119">Frühes der Typ den Compiler Probleme vor der Ausführung erkennen, Speicher genau zuordnen und weitere Optimierungen durchführen.</span><span class="sxs-lookup"><span data-stu-id="3d449-119">Knowing the type early enables the compiler to identify problems before execution, allocate memory precisely, and perform other optimizations.</span></span> <span data-ttu-id="3d449-120">Frühes Binden ermöglicht auch die Visual Basic-IDE (IDE), um IntelliSense-Hilfe zu den Mitgliedern eines Objekts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="3d449-120">Early binding also enables the Visual Basic integrated development environment (IDE) to provide IntelliSense Help about the members of an object.</span></span> <span data-ttu-id="3d449-121">Frühe Bindung ist auch für Leistung bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="3d449-121">Early binding is also preferred for performance.</span></span> <span data-ttu-id="3d449-122">Dies ist, da alle in einer spät gebundenen Variable gespeicherte Daten als Typ eingebunden sein müssen `Object`, und Zugreifen auf Member des Typs zur Laufzeit des Programms langsamer macht.</span><span class="sxs-lookup"><span data-stu-id="3d449-122">This is because all data stored in a late-bound variable must be wrapped as type `Object`, and accessing members of the type at run time makes the program slower.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3d449-123">Beispiele</span><span class="sxs-lookup"><span data-stu-id="3d449-123">Examples</span></span>  
 <span data-ttu-id="3d449-124">Typrückschluss erfolgt, wenn eine lokale Variable, ohne deklariert wird eine `As` -Klausel und initialisiert.</span><span class="sxs-lookup"><span data-stu-id="3d449-124">Type inference occurs when a local variable is declared without an `As` clause and initialized.</span></span> <span data-ttu-id="3d449-125">Der Compiler verwendet den Typ des zugewiesenen Anfangswerts als Typ der Variablen.</span><span class="sxs-lookup"><span data-stu-id="3d449-125">The compiler uses the type of the assigned initial value as the type of the variable.</span></span> <span data-ttu-id="3d449-126">Die folgenden Zeilen des Codes deklariert beispielsweise eine Variable vom Typ `String`.</span><span class="sxs-lookup"><span data-stu-id="3d449-126">For example, each of the following lines of code declares a variable of type `String`.</span></span>  
  
 <span data-ttu-id="3d449-127">[!code-vb[VbVbalrTypeInference&#2;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="3d449-127">[!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]</span></span>  
  
 <span data-ttu-id="3d449-128">Der folgende Code zeigt zwei äquivalente Verfahren, um ein Array von ganzen Zahlen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3d449-128">The following code demonstrates two equivalent ways to create an array of integers.</span></span>  
  
 <span data-ttu-id="3d449-129">[!code-vb[VbVbalrTypeInference&3;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="3d449-129">[!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]</span></span>  
  
 <span data-ttu-id="3d449-130">Es empfiehlt sich, den Typrückschluss verwenden, um den Typ einer Schleifensteuerungsvariablen zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="3d449-130">It is convenient to use type inference to determine the type of a loop control variable.</span></span> <span data-ttu-id="3d449-131">Im folgenden Code wird der Compiler folgert, die `number` ist ein `Integer` da `someNumbers2` aus dem vorherigen Beispiel wird ein Array von Ganzzahlen.</span><span class="sxs-lookup"><span data-stu-id="3d449-131">In the following code, the compiler infers that `number` is an `Integer` because `someNumbers2` from the previous example is an array of integers.</span></span>  
  
 <span data-ttu-id="3d449-132">[!code-vb[VbVbalrTypeInference&4;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="3d449-132">[!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]</span></span>  
  
 <span data-ttu-id="3d449-133">Lokaler Typrückschluss verwendet werden kann, `Using` Anweisungen, die den Typ des Ressourcennamens, einrichten, wie im folgende Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3d449-133">Local type inference can be used in `Using` statements to establish the type of the resource name, as the following example demonstrates.</span></span>  
  
 <span data-ttu-id="3d449-134">[!code-vb[VbVbalrTypeInference&#7;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="3d449-134">[!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]</span></span>  
  
 <span data-ttu-id="3d449-135">Der Typ einer Variablen kann die Rückgabewerte von Funktionen auch abgeleitet werden, wie im folgende Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="3d449-135">The type of a variable can also be inferred from the return values of functions, as the following example demonstrates.</span></span> <span data-ttu-id="3d449-136">Beide `pList1` und `pList2` von Prozessen sind, da `Process.GetProcesses` gibt ein Array von Prozessen.</span><span class="sxs-lookup"><span data-stu-id="3d449-136">Both `pList1` and `pList2` are arrays of processes because `Process.GetProcesses` returns an array of processes.</span></span>  
  
 <span data-ttu-id="3d449-137">[!code-vb[VbVbalrTypeInference&5;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="3d449-137">[!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]</span></span>  
  
## <a name="option-infer"></a><span data-ttu-id="3d449-138">Option Infer</span><span class="sxs-lookup"><span data-stu-id="3d449-138">Option Infer</span></span>  
 <span data-ttu-id="3d449-139">`Option Infer`können, die Sie angeben, ob der lokale Typrückschluss in einer bestimmten Datei zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="3d449-139">`Option Infer` enables you specify whether local type inference is allowed in a particular file.</span></span> <span data-ttu-id="3d449-140">Aktivieren oder die Option blockieren, geben Sie einen der folgenden Anweisungen am Anfang der Datei ein.</span><span class="sxs-lookup"><span data-stu-id="3d449-140">To enable or to block the option, type one of the following statements at the start of the file.</span></span>  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 <span data-ttu-id="3d449-141">Wenn Sie keinen Wert für angeben `Option Infer` in Ihrem Code der Compilerstandardwert ist `Option Infer On`.</span><span class="sxs-lookup"><span data-stu-id="3d449-141">If you do not specify a value for `Option Infer` in your code, the compiler default is `Option Infer On`.</span></span> <span data-ttu-id="3d449-142">Für aktualisierte Projekte aus [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb_orcas_long_md.md)] oder früher, der Compilerstandardwert ist `Option Infer Off`.</span><span class="sxs-lookup"><span data-stu-id="3d449-142">For projects upgraded from [!INCLUDE[vb_orcas_long](../../../../visual-basic/misc/includes/vb_orcas_long_md.md)] or earlier, the compiler default is `Option Infer Off`.</span></span>  
  
 <span data-ttu-id="3d449-143">Wenn der in einer Datei für `Option Infer` festgelegte Wert mit dem in der IDE oder in der Befehlszeile festgelegten Wert im Konflikt steht, hat der Wert in der Datei Vorrang.</span><span class="sxs-lookup"><span data-stu-id="3d449-143">If the value set for `Option Infer` in a file conflicts with the value set in the IDE or on the command line, the value in the file has precedence.</span></span>  
  
 <span data-ttu-id="3d449-144">Weitere Informationen finden Sie unter [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md) und [Seite kompilieren, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="3d449-144">For more information, see [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="restrictions"></a><span data-ttu-id="3d449-145">Beschränkungen</span><span class="sxs-lookup"><span data-stu-id="3d449-145">Restrictions</span></span>  
 <span data-ttu-id="3d449-146">Typrückschluss kann nur für nicht statische lokale Variablen verwendet werden. Er kann nicht verwendet werden, um den Typ der Klassenfelder, Eigenschaften oder Funktionen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="3d449-146">Type inference can be used only for non-static local variables; it cannot be used to determine the type of class fields, properties, or functions.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d449-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3d449-147">See Also</span></span>  
 <span data-ttu-id="3d449-148">[Anonyme Typen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span><span class="sxs-lookup"><span data-stu-id="3d449-148">[Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md) </span></span>  
<span data-ttu-id="3d449-149"> [Frühes und spätes Binden](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span><span class="sxs-lookup"><span data-stu-id="3d449-149"> [Early and Late Binding](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md) </span></span>  
<span data-ttu-id="3d449-150"> [Für jede... Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="3d449-150"> [For Each...Next Statement](../../../../visual-basic/language-reference/statements/for-each-next-statement.md) </span></span>  
<span data-ttu-id="3d449-151"> [Für... Next-Anweisung](../../../../visual-basic/language-reference/statements/for-next-statement.md) </span><span class="sxs-lookup"><span data-stu-id="3d449-151"> [For...Next Statement](../../../../visual-basic/language-reference/statements/for-next-statement.md) </span></span>  
<span data-ttu-id="3d449-152"> [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md) </span><span class="sxs-lookup"><span data-stu-id="3d449-152"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md) </span></span>  
<span data-ttu-id="3d449-153"> [/ optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span><span class="sxs-lookup"><span data-stu-id="3d449-153"> [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md) </span></span>  
<span data-ttu-id="3d449-154"> [Einführung in LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="3d449-154"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
