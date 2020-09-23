---
title: Variablendeklaration
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
ms.openlocfilehash: 8d78509e1604fee4a151608f6166de6fc8ccfdaa
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91080152"
---
# <a name="variable-declaration-in-visual-basic"></a><span data-ttu-id="26c30-102">Variablendeklaration in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="26c30-102">Variable Declaration in Visual Basic</span></span>

<span data-ttu-id="26c30-103">Sie deklarieren eine Variable, um deren Namen und Merkmale anzugeben.</span><span class="sxs-lookup"><span data-stu-id="26c30-103">You declare a variable to specify its name and characteristics.</span></span> <span data-ttu-id="26c30-104">Die Deklarations Anweisung für Variablen ist die [Dim-Anweisung](../../../language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="26c30-104">The declaration statement for variables is the [Dim Statement](../../../language-reference/statements/dim-statement.md).</span></span> <span data-ttu-id="26c30-105">Speicherort und Inhalt bestimmen die Merkmale der Variablen.</span><span class="sxs-lookup"><span data-stu-id="26c30-105">Its location and contents determine the variable's characteristics.</span></span>  
  
 <span data-ttu-id="26c30-106">Informationen zu Variablen Benennungs Regeln und-Überlegungen finden Sie unter [deklarierte Element Namen](../declared-elements/declared-element-names.md).</span><span class="sxs-lookup"><span data-stu-id="26c30-106">For variable naming rules and considerations, see [Declared Element Names](../declared-elements/declared-element-names.md).</span></span>  
  
## <a name="declaration-levels"></a><span data-ttu-id="26c30-107">Deklarations Stufen</span><span class="sxs-lookup"><span data-stu-id="26c30-107">Declaration Levels</span></span>  
  
### <a name="local-and-member-variables"></a><span data-ttu-id="26c30-108">Lokale Variablen und Element Variablen</span><span class="sxs-lookup"><span data-stu-id="26c30-108">Local and Member Variables</span></span>  

 <span data-ttu-id="26c30-109">Eine *lokale Variable* ist eine, die innerhalb einer Prozedur deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="26c30-109">A *local variable* is one that is declared within a procedure.</span></span> <span data-ttu-id="26c30-110">Eine *Member-Variable* ist ein Member eines Visual Basic Typs. Sie wird auf Modulebene innerhalb einer Klasse, Struktur oder eines Moduls deklariert, jedoch nicht innerhalb einer Prozedur, die für diese Klasse, Struktur oder dieses Modul intern ist.</span><span class="sxs-lookup"><span data-stu-id="26c30-110">A *member variable* is a member of a Visual Basic type; it is declared at module level, inside a class, structure, or module, but not within any procedure internal to that class, structure, or module.</span></span>  
  
### <a name="shared-and-instance-variables"></a><span data-ttu-id="26c30-111">Freigegebene und Instanzvariablen</span><span class="sxs-lookup"><span data-stu-id="26c30-111">Shared and Instance Variables</span></span>  

 <span data-ttu-id="26c30-112">In einer Klasse oder Struktur ist die Kategorie einer Element Variablen davon abhängig, ob Sie freigegeben ist.</span><span class="sxs-lookup"><span data-stu-id="26c30-112">In a class or structure, the category of a member variable depends on whether or not it is shared.</span></span> <span data-ttu-id="26c30-113">Wenn Sie mit dem [Shared](../../../language-reference/modifiers/shared.md) -Schlüsselwort deklariert ist, handelt es sich um eine frei *gegebene Variable*, die in einer einzelnen Kopie vorhanden ist, die von allen Instanzen der Klasse oder Struktur gemeinsam genutzt wird.</span><span class="sxs-lookup"><span data-stu-id="26c30-113">If it is declared with the [Shared](../../../language-reference/modifiers/shared.md) keyword, it is a *shared variable*, and it exists in a single copy shared among all instances of the class or structure.</span></span>  
  
 <span data-ttu-id="26c30-114">Andernfalls handelt es sich um eine *Instanzvariable*, und für jede Instanz der Klasse oder Struktur wird eine separate Kopie davon erstellt.</span><span class="sxs-lookup"><span data-stu-id="26c30-114">Otherwise it is an *instance variable*, and a separate copy of it is created for each instance of the class or structure.</span></span> <span data-ttu-id="26c30-115">Eine bestimmte Kopie einer Instanzvariablen ist nur für die Instanz der Klasse oder Struktur verfügbar, in der Sie erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="26c30-115">A given copy of an instance variable is available only to the instance of the class or structure in which it was created.</span></span> <span data-ttu-id="26c30-116">Es ist unabhängig von einer Kopie der Instanzvariablen in einer anderen Instanz der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="26c30-116">It is independent of a copy of the instance variable in any other instance of the class or structure.</span></span>  
  
## <a name="declaring-data-type"></a><span data-ttu-id="26c30-117">Deklarierender Datentyp</span><span class="sxs-lookup"><span data-stu-id="26c30-117">Declaring Data Type</span></span>  

 <span data-ttu-id="26c30-118">Mit der [As](../../../language-reference/statements/as-clause.md) -Klausel in der Deklarations Anweisung können Sie den Datentyp oder Objekttyp der Variablen definieren, die Sie deklarieren.</span><span class="sxs-lookup"><span data-stu-id="26c30-118">The [As](../../../language-reference/statements/as-clause.md) clause in the declaration statement allows you to define the data type or object type of the variable you are declaring.</span></span> <span data-ttu-id="26c30-119">Sie können einen der folgenden Typen für eine Variable angeben:</span><span class="sxs-lookup"><span data-stu-id="26c30-119">You can specify any of the following types for a variable:</span></span>  
  
- <span data-ttu-id="26c30-120">Ein grundlegender Datentyp, z. b. `Boolean` , `Long` oder. `Decimal`</span><span class="sxs-lookup"><span data-stu-id="26c30-120">An elementary data type, such as `Boolean`, `Long`, or `Decimal`</span></span>  
  
- <span data-ttu-id="26c30-121">Ein zusammengesetzter Datentyp, z. b. ein Array oder eine Struktur.</span><span class="sxs-lookup"><span data-stu-id="26c30-121">A composite data type, such as an array or structure</span></span>  
  
- <span data-ttu-id="26c30-122">Ein Objekttyp oder eine Klasse, die entweder in der Anwendung oder in einer anderen Anwendung definiert ist.</span><span class="sxs-lookup"><span data-stu-id="26c30-122">An object type, or class, defined either in your application or in another application</span></span>  
  
- <span data-ttu-id="26c30-123">Eine .NET Framework Klasse, z. b. <xref:System.Windows.Forms.Label> oder. <xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="26c30-123">A .NET Framework class, such as <xref:System.Windows.Forms.Label> or <xref:System.Windows.Forms.TextBox></span></span>  
  
- <span data-ttu-id="26c30-124">Ein Schnittstellentyp, z. b. <xref:System.IComparable> oder. <xref:System.IDisposable></span><span class="sxs-lookup"><span data-stu-id="26c30-124">An interface type, such as <xref:System.IComparable> or <xref:System.IDisposable></span></span>  
  
 <span data-ttu-id="26c30-125">Sie können mehrere Variablen in einer Anweisung deklarieren, ohne den Datentyp wiederholen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="26c30-125">You can declare several variables in one statement without having to repeat the data type.</span></span> <span data-ttu-id="26c30-126">In den folgenden-Anweisungen werden die Variablen, `i` `j` und `k` als-Typ und als und als und `Integer` `l` als deklariert `m` `Long` `x` `y` `Single` :</span><span class="sxs-lookup"><span data-stu-id="26c30-126">In the following statements, the variables `i`, `j`, and `k` are declared as type `Integer`, `l` and `m` as `Long`, and `x` and `y` as `Single`:</span></span>  
  
```vb  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 <span data-ttu-id="26c30-127">Weitere Informationen zu-Datentypen finden Sie unter [Datentypen](../data-types/index.md).</span><span class="sxs-lookup"><span data-stu-id="26c30-127">For more information on data types, see [Data Types](../data-types/index.md).</span></span> <span data-ttu-id="26c30-128">Weitere Informationen zu-Objekten finden Sie unter [Objekte und Klassen](../objects-and-classes/index.md) und [Programmieren mit-Komponenten](/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="26c30-128">For more information on objects, see [Objects and Classes](../objects-and-classes/index.md) and [Programming with Components](/previous-versions/visualstudio/visual-studio-2013/0ffkdtkf(v=vs.120)).</span></span>  
  
## <a name="local-type-inference"></a><span data-ttu-id="26c30-129">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="26c30-129">Local Type Inference</span></span>  

 <span data-ttu-id="26c30-130">Der *Typrückschluss* wird verwendet, um die Datentypen von lokalen Variablen zu bestimmen, die ohne-Klausel deklariert werden `As` .</span><span class="sxs-lookup"><span data-stu-id="26c30-130">*Type inference* is used to determine the data types of local variables declared without an `As` clause.</span></span> <span data-ttu-id="26c30-131">Der Compiler leitet den Typ der Variablen vom Typ des Initialisierungs Ausdrucks ab.</span><span class="sxs-lookup"><span data-stu-id="26c30-131">The compiler infers the type of the variable from the type of the initialization expression.</span></span> <span data-ttu-id="26c30-132">Dadurch können Sie Variablen deklarieren, ohne explizit einen Typ anzugeben.</span><span class="sxs-lookup"><span data-stu-id="26c30-132">This enables you to declare variables without explicitly stating a type.</span></span> <span data-ttu-id="26c30-133">Im folgenden Beispiel werden sowohl als `num1` auch `num2` als ganze Zahlen stark typisiert.</span><span class="sxs-lookup"><span data-stu-id="26c30-133">In the following example, both `num1` and `num2` are strongly typed as integers.</span></span>  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
  
 <span data-ttu-id="26c30-134">Wenn Sie den lokalen Typrückschluss verwenden möchten, `Option Infer` muss auf festgelegt werden `On` .</span><span class="sxs-lookup"><span data-stu-id="26c30-134">If you want to use local type inference, `Option Infer` must be set to `On`.</span></span> <span data-ttu-id="26c30-135">Weitere Informationen finden Sie unter [Local Type Inference (Lokaler Typrückschluss)](local-type-inference.md) und [Option Infer Statement (Option Infer-Anweisung)](../../../language-reference/statements/option-infer-statement.md).</span><span class="sxs-lookup"><span data-stu-id="26c30-135">For more information, see [Local Type Inference](local-type-inference.md) and [Option Infer Statement](../../../language-reference/statements/option-infer-statement.md).</span></span>  
  
## <a name="characteristics-of-declared-variables"></a><span data-ttu-id="26c30-136">Merkmale von deklarierten Variablen</span><span class="sxs-lookup"><span data-stu-id="26c30-136">Characteristics of Declared Variables</span></span>  

 <span data-ttu-id="26c30-137">Die *Lebensdauer* einer Variablen ist der Zeitraum, in dem Sie zur Verwendung verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="26c30-137">The *lifetime* of a variable is the period of time during which it is available for use.</span></span> <span data-ttu-id="26c30-138">Im Allgemeinen ist eine Variable vorhanden, solange das Element, das Sie deklariert (z. b. eine Prozedur oder eine Klasse), weiterhin vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="26c30-138">In general, a variable exists as long as the element that declares it (such as a procedure or class) continues to exist.</span></span> <span data-ttu-id="26c30-139">Wenn die Variable nicht fortgesetzt werden muss, wenn Sie die Lebensdauer des enthaltenden Elements überschreitet, müssen Sie in der Deklaration nichts Besonderes tun.</span><span class="sxs-lookup"><span data-stu-id="26c30-139">If the variable does not need to continue existing beyond the lifetime of its containing element, you do not need to do anything special in the declaration.</span></span> <span data-ttu-id="26c30-140">Wenn die Variable länger vorhanden sein muss als das enthaltende Element, können Sie das- `Static` Schlüsselwort oder das- `Shared` Schlüsselwort in seine- `Dim` Anweisung einschließen.</span><span class="sxs-lookup"><span data-stu-id="26c30-140">If the variable needs to continue to exist longer than its containing element, you can include the `Static` or `Shared` keyword in its `Dim` statement.</span></span> <span data-ttu-id="26c30-141">Weitere Informationen finden Sie unter [Lebensdauer in Visual Basic](../declared-elements/lifetime.md).</span><span class="sxs-lookup"><span data-stu-id="26c30-141">For more information, see [Lifetime in Visual Basic](../declared-elements/lifetime.md).</span></span>  
  
 <span data-ttu-id="26c30-142">Der Gültigkeits *Bereich* einer Variablen ist der Satz des gesamten Codes, der darauf verweisen kann, ohne den Namen zu qualifizieren.</span><span class="sxs-lookup"><span data-stu-id="26c30-142">The *scope* of a variable is the set of all code that can refer to it without qualifying its name.</span></span> <span data-ttu-id="26c30-143">Der Gültigkeitsbereich einer Variablen wird bestimmt, wo Sie deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="26c30-143">A variable's scope is determined by where it is declared.</span></span> <span data-ttu-id="26c30-144">Code, der sich in einer bestimmten Region befindet, kann die Variablen verwenden, die in dieser Region definiert sind, ohne deren Namen qualifizieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="26c30-144">Code located in a given region can use the variables defined in that region without having to qualify their names.</span></span> <span data-ttu-id="26c30-145">Weitere Informationen finden Sie unter [Scope in Visual Basic](../declared-elements/scope.md).</span><span class="sxs-lookup"><span data-stu-id="26c30-145">For more information, see [Scope in Visual Basic](../declared-elements/scope.md).</span></span>  
  
 <span data-ttu-id="26c30-146">Die *Zugriffsebene* einer Variablen ist der Umfang des Codes, der über die entsprechende Zugriffsberechtigung verfügt.</span><span class="sxs-lookup"><span data-stu-id="26c30-146">A variable's *access level* is the extent of code that has permission to access it.</span></span> <span data-ttu-id="26c30-147">Dies wird durch den Zugriffsmodifizierer (z. b. [öffentlich](../../../language-reference/modifiers/public.md) oder [Privat](../../../language-reference/modifiers/private.md)) bestimmt, den Sie in der- `Dim` Anweisung verwenden.</span><span class="sxs-lookup"><span data-stu-id="26c30-147">This is determined by the access modifier (such as [Public](../../../language-reference/modifiers/public.md) or [Private](../../../language-reference/modifiers/private.md)) that you use in the `Dim` statement.</span></span> <span data-ttu-id="26c30-148">Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../declared-elements/access-levels.md).</span><span class="sxs-lookup"><span data-stu-id="26c30-148">For more information, see [Access levels in Visual Basic](../declared-elements/access-levels.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c30-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="26c30-149">See also</span></span>

- [<span data-ttu-id="26c30-150">Vorgehensweise: Erstellen einer neuen Variablen</span><span class="sxs-lookup"><span data-stu-id="26c30-150">How to: Create a New Variable</span></span>](how-to-create-a-new-variable.md)
- [<span data-ttu-id="26c30-151">Vorgehensweise: Verschieben von Daten in eine und aus einer Variablen</span><span class="sxs-lookup"><span data-stu-id="26c30-151">How to: Move Data Into and Out of a Variable</span></span>](how-to-move-data-into-and-out-of-a-variable.md)
- [<span data-ttu-id="26c30-152">Datentypen</span><span class="sxs-lookup"><span data-stu-id="26c30-152">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="26c30-153">Gebieten</span><span class="sxs-lookup"><span data-stu-id="26c30-153">Protected</span></span>](../../../language-reference/modifiers/protected.md)
- [<span data-ttu-id="26c30-154">Friend</span><span class="sxs-lookup"><span data-stu-id="26c30-154">Friend</span></span>](../../../language-reference/modifiers/friend.md)
- [<span data-ttu-id="26c30-155">Statisch</span><span class="sxs-lookup"><span data-stu-id="26c30-155">Static</span></span>](../../../language-reference/modifiers/static.md)
- [<span data-ttu-id="26c30-156">Merkmale deklarierter Elemente</span><span class="sxs-lookup"><span data-stu-id="26c30-156">Declared Element Characteristics</span></span>](../declared-elements/declared-element-characteristics.md)
- [<span data-ttu-id="26c30-157">Lokaler Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="26c30-157">Local Type Inference</span></span>](local-type-inference.md)
- [<span data-ttu-id="26c30-158">Option Infer-Anweisung</span><span class="sxs-lookup"><span data-stu-id="26c30-158">Option Infer Statement</span></span>](../../../language-reference/statements/option-infer-statement.md)
