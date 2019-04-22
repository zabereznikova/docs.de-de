---
title: Sonderzeichen in Code (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
helpviewer_keywords:
- special characters [Visual Basic], in code
- parentheses [Visual Basic], using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator [Visual Basic]
- concatenation operators [Visual Basic], special characters in code
- concatenation operators [Visual Basic], vs. addition operator
- '! operator'
- separators [Visual Basic], using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator [Visual Basic]
- addition operator [Visual Basic]
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
ms.openlocfilehash: 65fcd10521742e287c7934080b3352a06668df7a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58835556"
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="eee0a-102">Sonderzeichen in Code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eee0a-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="eee0a-103">Manchmal müssen Sie Sonderzeichen in Ihrem Code, d. h. Zeichen verwenden, die nicht alphabetisch oder numerisch sind.</span><span class="sxs-lookup"><span data-stu-id="eee0a-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="eee0a-104">Die Interpunktions- und Sonderzeichen in der Visual Basic-Zeichensatz haben verschiedene Programmtexts zum Definieren der Aufgaben, die der Compiler oder das kompilierte Programm ausführt.</span><span class="sxs-lookup"><span data-stu-id="eee0a-104">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="eee0a-105">Sie legen keine auszuführende Operation fest.</span><span class="sxs-lookup"><span data-stu-id="eee0a-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="eee0a-106">Klammern</span><span class="sxs-lookup"><span data-stu-id="eee0a-106">Parentheses</span></span>  
 <span data-ttu-id="eee0a-107">Verwenden Sie Klammern, wenn Sie eine Prozedur, wie z. B. definieren eine `Sub` oder `Function`.</span><span class="sxs-lookup"><span data-stu-id="eee0a-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="eee0a-108">Sie müssen alle Prozedur Argumentlisten in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="eee0a-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="eee0a-109">Können Sie auch Klammern zum Einfügen von Variablen oder Argumente in logischen Gruppen, die insbesondere um die Standardreihenfolge der Operatorrangfolge in einem komplexen Ausdruck außer Kraft zu setzen.</span><span class="sxs-lookup"><span data-stu-id="eee0a-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="eee0a-110">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="eee0a-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 <span data-ttu-id="eee0a-111">Nach der Ausführung des vorherigen Code den Wert der `d` "8.225" und der Wert des `e` ist 3.</span><span class="sxs-lookup"><span data-stu-id="eee0a-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="eee0a-112">Die Berechnung für `d` verwendet die standardmäßige Rangfolge `/` über `+` entspricht `d = b + (c / a)`.</span><span class="sxs-lookup"><span data-stu-id="eee0a-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="eee0a-113">Die Klammern in die Berechnung für `e` außer Kraft setzen der Standardvorrang gilt.</span><span class="sxs-lookup"><span data-stu-id="eee0a-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="eee0a-114">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="eee0a-114">Separators</span></span>  
 <span data-ttu-id="eee0a-115">Trennzeichen sind, was ihr Name besagt: Trennen Sie Abschnitte des Codes.</span><span class="sxs-lookup"><span data-stu-id="eee0a-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="eee0a-116">In Visual Basic ist das Trennzeichen der Doppelpunkt (`:`).</span><span class="sxs-lookup"><span data-stu-id="eee0a-116">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="eee0a-117">Verwenden Sie Trennzeichen, wenn mehrere Anweisungen in einer einzelnen Zeile anstelle von separaten Zeilen enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="eee0a-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="eee0a-118">Dies spart Platz und verbessert die Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="eee0a-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="eee0a-119">Das folgende Beispiel zeigt drei Anweisungen, die durch Doppelpunkte getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="eee0a-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 <span data-ttu-id="eee0a-120">Weitere Informationen finden Sie unter [Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="eee0a-120">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="eee0a-121">Der Doppelpunkt (`:`)-Zeichen wird auch verwendet, um eine anweisungsbezeichnung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="eee0a-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="eee0a-122">Weitere Informationen finden Sie unter [Vorgehensweise: Bezeichnen von Anweisungen](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="eee0a-122">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="eee0a-123">Verkettung</span><span class="sxs-lookup"><span data-stu-id="eee0a-123">Concatenation</span></span>  
 <span data-ttu-id="eee0a-124">Verwenden der `&` Operator für *Verkettung*, oder Zeichenfolgen miteinander zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="eee0a-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="eee0a-125">Ist nicht zu verwechseln mit der `+` -Operator, der numerische Werte addiert.</span><span class="sxs-lookup"><span data-stu-id="eee0a-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="eee0a-126">Bei Verwendung der `+` Operator zum Verketten, wenn Sie numerische Werte arbeiten Sie erhalten falsche Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="eee0a-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="eee0a-127">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="eee0a-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 <span data-ttu-id="eee0a-128">Nach der Ausführung des vorherigen Code den Wert der `resultA` 21.01 und den Wert der `resultB` "10.0111".</span><span class="sxs-lookup"><span data-stu-id="eee0a-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="eee0a-129">Operatoren für den Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="eee0a-129">Member Access Operators</span></span>  
 <span data-ttu-id="eee0a-130">Für den Zugriff auf einen Member eines Typs, die Sie verwenden des Punkts (`.`) oder ein Ausrufezeichen (`!`)-Operator zwischen den Typnamen und den Namen des Members.</span><span class="sxs-lookup"><span data-stu-id="eee0a-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="eee0a-131">Punkt (.) Operator</span><span class="sxs-lookup"><span data-stu-id="eee0a-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="eee0a-132">Verwenden der `.` Operator auf eine Klasse, Struktur, Schnittstelle oder Enumeration als ein Memberzugriffsoperator.</span><span class="sxs-lookup"><span data-stu-id="eee0a-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="eee0a-133">Das Element kann ein Feld, Eigenschaft, Ereignis oder Methode sein.</span><span class="sxs-lookup"><span data-stu-id="eee0a-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="eee0a-134">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="eee0a-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="eee0a-135">Ausrufezeichen (!) Operator</span><span class="sxs-lookup"><span data-stu-id="eee0a-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="eee0a-136">Verwenden der `!` -Operator nur auf eine Klasse oder Schnittstelle wie ein wörterbuchzugriffsoperator.</span><span class="sxs-lookup"><span data-stu-id="eee0a-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="eee0a-137">Die Klasse oder Schnittstelle benötigen eine Standardeigenschaft, die akzeptiert ein einzelnes `String` Argument.</span><span class="sxs-lookup"><span data-stu-id="eee0a-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="eee0a-138">Der Bezeichner sofort nach der `!` Operator wird der Wert des Arguments an die Standardeigenschaft als Zeichenfolge übergeben.</span><span class="sxs-lookup"><span data-stu-id="eee0a-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="eee0a-139">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="eee0a-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="eee0a-140">Die drei Zeilen der Ausgabe `MsgBox` alle zeigt den Wert `32856`.</span><span class="sxs-lookup"><span data-stu-id="eee0a-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="eee0a-141">Die erste Zeile verwendet die herkömmlichen Zugriff auf Eigenschaft `index`, die zweite nutzt die Tatsache, `index` ist die Standardeigenschaft der Klasse `hasDefault`, und das dritte verwendet Wörterbuchzugriff auf die Klasse.</span><span class="sxs-lookup"><span data-stu-id="eee0a-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="eee0a-142">Beachten Sie, dass der zweite Operand, der die `!` Operator muss ein gültiger Visual Basic-Bezeichner, die nicht in doppelte Anführungszeichen eingeschlossen sein (`" "`).</span><span class="sxs-lookup"><span data-stu-id="eee0a-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="eee0a-143">Sie können nicht in anderen Worten, ein Zeichenfolgenliteral oder eine String-Variable verwenden.</span><span class="sxs-lookup"><span data-stu-id="eee0a-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="eee0a-144">Änderungen an den folgenden auf die letzte Zeile der `MsgBox` Aufruf wird ein Fehler generiert, da `"X"` ist eine eingeschlossene Zeichenfolgenliteral.</span><span class="sxs-lookup"><span data-stu-id="eee0a-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="eee0a-145">Verweise auf die Standardsammlungen müssen explizit sein.</span><span class="sxs-lookup"><span data-stu-id="eee0a-145">References to default collections must be explicit.</span></span> <span data-ttu-id="eee0a-146">Insbesondere können keine der `!` Operator für eine spät gebundene Variable.</span><span class="sxs-lookup"><span data-stu-id="eee0a-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="eee0a-147">Die `!` Zeichen dient auch als die `Single` Typzeichen.</span><span class="sxs-lookup"><span data-stu-id="eee0a-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eee0a-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eee0a-148">See also</span></span>

- [<span data-ttu-id="eee0a-149">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="eee0a-149">Program Structure and Code Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
- [<span data-ttu-id="eee0a-150">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="eee0a-150">Type Characters</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
