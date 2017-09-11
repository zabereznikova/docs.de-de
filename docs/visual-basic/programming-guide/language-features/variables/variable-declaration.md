---
title: Variablendeklaration in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables, declarations
- Dim statement, variable declaration
- declaring variables
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime, variables
- variables [Visual Basic], lifetime
- access levels, variables
- scope, declaration statements
- variables [Visual Basic], access level
- local variables, declarations
- scope, variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: dac536b99eb4515c75381dc4e28720a92e1001f0
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="37fe4-102">Variablendeklaration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="37fe4-102">Variable Declaration in Visual Basic</span></span>
<span data-ttu-id="37fe4-103">Sie deklarieren eine Variable, die den Namen und die Eigenschaften angeben.</span><span class="sxs-lookup"><span data-stu-id="37fe4-103">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="37fe4-104">Die deklarationsanweisung für Variablen ist der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="37fe4-104">The declaration statement for variables is the [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="37fe4-105">Bestimmen den Speicherort und den Inhalt Merkmale der Variablen.</span><span class="sxs-lookup"><span data-stu-id="37fe4-105">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="37fe4-106">Regeln für Variablennamen und Überlegungen finden Sie unter [Elementnamen deklariert](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="37fe4-106">For variable naming rules and considerations, see [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="37fe4-107">Deklaration von Ebenen</span><span class="sxs-lookup"><span data-stu-id="37fe4-107">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="37fe4-108">Lokale und Membervariablen</span><span class="sxs-lookup"><span data-stu-id="37fe4-108">Local and Member Variables</span></span>  
 <span data-ttu-id="37fe4-109">Ein *lokale Variable* wird innerhalb einer Prozedur deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="37fe4-109">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="37fe4-110">Ein *Membervariable* ist ein Mitglied einer [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] eingeben; er wird auf Modulebene in einer Klasse, Struktur oder Modul, aber nicht innerhalb einer Prozedur, die für diese Klasse, Struktur oder Modul intern deklariert.</span><span class="sxs-lookup"><span data-stu-id="37fe4-110">A *member variable* is a member of a [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="37fe4-111">Freigegebene und Instanzvariablen</span><span class="sxs-lookup"><span data-stu-id="37fe4-111">Shared and Instance Variables</span></span>  
 <span data-ttu-id="37fe4-112">Die Kategorie einer Membervariable hängt in einer Klasse oder Struktur davon, ob sie freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="37fe4-112">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="37fe4-113">Deklarierte mit der [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) -Schlüsselwort, es ist ein *freigegebene Variable*, und eine Kopie von allen Instanzen der Klasse oder Struktur gemeinsam genutztes.</span><span class="sxs-lookup"><span data-stu-id="37fe4-113">If it is declared with the [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="37fe4-114">Andernfalls ist es eine *Instanzvariable*, und eine separate Kopie für jede Instanz der Klasse oder Struktur erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="37fe4-114">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="37fe4-115">Eine solche Kopie einer Instanzvariablen steht nur für die Instanz der Klasse oder Struktur, in der sie erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="37fe4-115">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="37fe4-116">Sie ist unabhängig von der eine Kopie der Instanzvariablen in einer anderen Instanz der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="37fe4-116">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="37fe4-117">Deklarieren von-Datentyp</span><span class="sxs-lookup"><span data-stu-id="37fe4-117">Declaring Data Type</span></span>  
 <span data-ttu-id="37fe4-118">Die [als](../../../../visual-basic/language-reference/statements/as-clause.md) -Klausel in der deklarationsanweisung können Sie den Datentyp oder Objekttyp der deklarieren Sie Variablen definieren.</span><span class="sxs-lookup"><span data-stu-id="37fe4-118">The [As](../../../../visual-basic/language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="37fe4-119">Sie können einen der folgenden Typen für eine Variable angeben:</span><span class="sxs-lookup"><span data-stu-id="37fe4-119">You can specify any of the following types for a variable:</span></span>  
  
-   <span data-ttu-id="37fe4-120">Ein elementarer Datentyp, z. B. `Boolean`, `Long`, oder`Decimal`</span><span class="sxs-lookup"><span data-stu-id="37fe4-120">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
-   <span data-ttu-id="37fe4-121">Ein zusammengesetzter Datentyp, z. B. ein Array oder eine Struktur</span><span class="sxs-lookup"><span data-stu-id="37fe4-121">A composite data type, such as an array or structure</span></span>  
  
-   <span data-ttu-id="37fe4-122">Ein Objekttyp oder eine Klasse, die in der Anwendung oder in einer anderen Anwendung definiert</span><span class="sxs-lookup"><span data-stu-id="37fe4-122">An object type, or class, defined either in your application or in another application</span></span>  
  
-   <span data-ttu-id="37fe4-123">Ein [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] Klasse, z. B. <xref:System.Windows.Forms.Label>oder <xref:System.Windows.Forms.TextBox></xref:System.Windows.Forms.TextBox> </xref:System.Windows.Forms.Label></span><span class="sxs-lookup"><span data-stu-id="37fe4-123">A [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
-   <span data-ttu-id="37fe4-124">Geben Sie eine Schnittstelle, wie z. B. <xref:System.IComparable>oder <xref:System.IDisposable></xref:System.IDisposable> </xref:System.IComparable></span><span class="sxs-lookup"><span data-stu-id="37fe4-124">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="37fe4-125">Sie können mehrere Variablen in einer Anweisung deklarieren, ohne den Datentyp wiederholen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="37fe4-125">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="37fe4-126">In den folgenden Anweisungen, die Variablen `i`, `j`, und `k` werden als Typ deklariert `Integer`, `l` und `m` als `Long`, und `x` und `y` als `Single`:</span><span class="sxs-lookup"><span data-stu-id="37fe4-126">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="37fe4-127">Weitere Informationen zu Datentypen finden Sie unter [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="37fe4-127">For more information on data types, see [Data Types](../../../../visual-basic/programming-guide/language-features/data-types/index.md).</span></span> <span data-ttu-id="37fe4-128">Weitere Informationen zu Objekten finden Sie unter [Objekte und Klassen](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) und [Programmieren mit Komponenten](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span><span class="sxs-lookup"><span data-stu-id="37fe4-128">For more information on objects, see [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) and [Programming with Components](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="37fe4-129">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="37fe4-129">Local Type Inference</span></span>  
 <span data-ttu-id="37fe4-130">*Typrückschluss* ermittelt, die die Datentypen für lokale Variablen, die ohne eine `As` Klausel.</span><span class="sxs-lookup"><span data-stu-id="37fe4-130">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="37fe4-131">Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungsausdrucks ab.</span><span class="sxs-lookup"><span data-stu-id="37fe4-131">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="37fe4-132">Dadurch können Sie Variablen deklarieren, ohne explizit einen Typ anzugeben.</span><span class="sxs-lookup"><span data-stu-id="37fe4-132">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="37fe4-133">Im folgenden Beispiel beide `num1` und `num2` sind stark typisiert als ganze Zahlen.</span><span class="sxs-lookup"><span data-stu-id="37fe4-133">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 <span data-ttu-id="37fe4-134">[!code-vb[VbVbalrTypeInference&#1;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="37fe4-134">[!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]</span></span>  
  
 <span data-ttu-id="37fe4-135">Wenn Sie lokalen Typrückschluss verwenden möchten `Option Infer` muss festgelegt werden, um `On`.</span><span class="sxs-lookup"><span data-stu-id="37fe4-135">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="37fe4-136">Weitere Informationen finden Sie unter [lokalen Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) und [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="37fe4-136">For more information, see [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) and [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="37fe4-137">Merkmale der deklarierten Variablen</span><span class="sxs-lookup"><span data-stu-id="37fe4-137">Characteristics of Declared Variables</span></span>  
 <span data-ttu-id="37fe4-138">Die *Lebensdauer* einer Variablen ist der Zeitraum der sie verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="37fe4-138">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="37fe4-139">Im Allgemeinen existiert eine Variable, solange das Element, das es (z. B. eine Prozedur oder Klasse) deklariert weiterhin vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="37fe4-139">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="37fe4-140">Wenn die Variable nicht bestehen bleiben nach Ablauf der Lebensdauer des enthaltenden Elements muss, müssen Sie nicht lediglich in der Deklaration.</span><span class="sxs-lookup"><span data-stu-id="37fe4-140">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="37fe4-141">Wenn die Variable länger als ihr enthaltendes Element bestehen bleiben muss, können Sie enthalten die `Static` oder `Shared` -Schlüsselwort in der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="37fe4-141">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="37fe4-142">Weitere Informationen finden Sie unter [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span><span class="sxs-lookup"><span data-stu-id="37fe4-142">For more information, see [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="37fe4-143">Die *Bereich* einer Variablen ist ein Satz von Code, die darauf verweisen kann, ohne dessen Namen zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="37fe4-143">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="37fe4-144">Der Gültigkeitsbereich einer Variablen wird bestimmt, wo sie deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="37fe4-144">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="37fe4-145">Code befindet sich in einer bestimmten Region können die Variablen, die in diesem Bereich definiert werden, ohne ihren Namen zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="37fe4-145">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="37fe4-146">Weitere Informationen finden Sie unter [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="37fe4-146">For more information, see [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="37fe4-147">Einer Variablentyps *Zugriffsebene* wird das Ausmaß der Code die Berechtigung zum Zugriff darauf hat.</span><span class="sxs-lookup"><span data-stu-id="37fe4-147">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="37fe4-148">Dies richtet sich nach den Zugriffsmodifizierer (wie z. B. [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) oder [Private](../../../../visual-basic/language-reference/modifiers/private.md)), mit denen Sie der `Dim` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="37fe4-148">This is determined by the access modifier (such as [Public](../../../../visual-basic/language-reference/modifiers/public.md) or [Private](../../../../visual-basic/language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="37fe4-149">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="37fe4-149">For more information, see [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37fe4-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="37fe4-150">See Also</span></span>  
 <span data-ttu-id="37fe4-151">[Gewusst wie: Erstellen einer neuen Variablen](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md) </span><span class="sxs-lookup"><span data-stu-id="37fe4-151">[How to: Create a New Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md) </span></span>  
<span data-ttu-id="37fe4-152"> [Gewusst wie: Verschieben von Daten in und aus einer Variablen](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span><span class="sxs-lookup"><span data-stu-id="37fe4-152"> [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md) </span></span>  
<span data-ttu-id="37fe4-153"> [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="37fe4-153"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="37fe4-154"> [Geschützte](../../../../visual-basic/language-reference/modifiers/protected.md) </span><span class="sxs-lookup"><span data-stu-id="37fe4-154"> [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) </span></span>  
<span data-ttu-id="37fe4-155"> [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) </span><span class="sxs-lookup"><span data-stu-id="37fe4-155"> [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) </span></span>  
<span data-ttu-id="37fe4-156"> [Statische](../../../../visual-basic/language-reference/modifiers/static.md) </span><span class="sxs-lookup"><span data-stu-id="37fe4-156"> [Static](../../../../visual-basic/language-reference/modifiers/static.md) </span></span>  
<span data-ttu-id="37fe4-157"> [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span><span class="sxs-lookup"><span data-stu-id="37fe4-157"> [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md) </span></span>  
<span data-ttu-id="37fe4-158"> [Lokaler Typrückschluss](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span><span class="sxs-lookup"><span data-stu-id="37fe4-158"> [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) </span></span>  
<span data-ttu-id="37fe4-159"> [Option Infer-Anweisung](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span><span class="sxs-lookup"><span data-stu-id="37fe4-159"> [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)</span></span>
