---
title: Sonderzeichen in Code (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.)
- vb.(
- vb.colon
- vb.!
- vb..
- 'vb.:'
dev_langs:
- VB
helpviewer_keywords:
- special characters, in code
- parentheses, using in code
- colons (:)
- period character in code
- dot operator (.)
- dictionary access operator
- concatenation operators, special characters in code
- concatenation operators, vs. addition operator
- '! operator'
- separators, using in code
- operators [Visual Basic], dictionary access
- ': separator character'
- member access operator
- addition operator
- operators [Visual Basic], member access
- . operator
- exclamation points
- separators
- exclamation point operator (!)
- Visual Basic code, special characters
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: 21
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
ms.openlocfilehash: cd7fbce5c382c3acd88a12277a3d7899b823d049
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="55dae-102">Sonderzeichen in Code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55dae-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="55dae-103">Manchmal müssen Sie Sonderzeichen in Ihrem Code, d. h. Zeichen verwenden, die nicht alphabetisch oder numerisch sind.</span><span class="sxs-lookup"><span data-stu-id="55dae-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="55dae-104">Interpunktion und Sonderzeichen in den [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Zeichensatz haben verschiedene Funktionen, vom verwalten Programmtext zur Definition der Aufgaben, die der Compiler oder das kompilierte Programm ausführt.</span><span class="sxs-lookup"><span data-stu-id="55dae-104">The punctuation and special characters in the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="55dae-105">Sie legen keine auszuführende Operation fest.</span><span class="sxs-lookup"><span data-stu-id="55dae-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="55dae-106">Klammern</span><span class="sxs-lookup"><span data-stu-id="55dae-106">Parentheses</span></span>  
 <span data-ttu-id="55dae-107">Verwenden Sie Klammern bei der Definition einer Prozedur, z. B. ein `Sub` oder `Function`.</span><span class="sxs-lookup"><span data-stu-id="55dae-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="55dae-108">Sie müssen alle Verfahren Argumentlisten in Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="55dae-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="55dae-109">Sie verwenden auch Klammern zum Einfügen von Variablen oder Argumente in logischen Gruppen, die insbesondere für die Rangfolge der Operatoren in einem komplexen Ausdruck überschreiben.</span><span class="sxs-lookup"><span data-stu-id="55dae-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="55dae-110">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="55dae-110">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="55dae-111">[!code-vb[VbVbcnConventions&#11;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="55dae-111">[!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_1.vb)]</span></span>  
  
 <span data-ttu-id="55dae-112">Nach der Ausführung des vorherigen Code den Wert der `d` "8.225" und der Wert des `e` ist 3.</span><span class="sxs-lookup"><span data-stu-id="55dae-112">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="55dae-113">Die Berechnung für `d` verwendet die standardmäßige Rangfolge `/` über `+` und entspricht dem `d = b + (c / a)`.</span><span class="sxs-lookup"><span data-stu-id="55dae-113">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="55dae-114">Die Klammern in der Berechnung von `e` außer Kraft setzen der Standardvorrang gilt.</span><span class="sxs-lookup"><span data-stu-id="55dae-114">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="55dae-115">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="55dae-115">Separators</span></span>  
 <span data-ttu-id="55dae-116">Trennzeichen sind, was ihr Name besagt: Trennen Sie Abschnitte des Codes.</span><span class="sxs-lookup"><span data-stu-id="55dae-116">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="55dae-117">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], das Trennzeichen ist der Doppelpunkt (`:`).</span><span class="sxs-lookup"><span data-stu-id="55dae-117">In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], the separator character is the colon (`:`).</span></span> <span data-ttu-id="55dae-118">Verwenden Sie als Trennzeichen, wenn mehrere Anweisungen in einer einzelnen Zeile anstelle von separaten Zeilen enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="55dae-118">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="55dae-119">Dies spart Platz und verbessert die Lesbarkeit des Codes.</span><span class="sxs-lookup"><span data-stu-id="55dae-119">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="55dae-120">Das folgende Beispiel zeigt drei Anweisungen, die durch Doppelpunkte getrennt.</span><span class="sxs-lookup"><span data-stu-id="55dae-120">The following example shows three statements separated by colons.</span></span>  
  
 <span data-ttu-id="55dae-121">[!code-vb[VbVbcnConventions&#12;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="55dae-121">[!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_2.vb)]</span></span>  
  
 <span data-ttu-id="55dae-122">Weitere Informationen finden Sie unter [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="55dae-122">For more information, see [How to: Break and Combine Statements in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="55dae-123">Der Doppelpunkt (`:`)-Zeichen wird auch verwendet, um eine Anweisungsmarke zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="55dae-123">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="55dae-124">Weitere Informationen finden Sie unter [wie: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="55dae-124">For more information, see [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="55dae-125">Verkettung</span><span class="sxs-lookup"><span data-stu-id="55dae-125">Concatenation</span></span>  
 <span data-ttu-id="55dae-126">Verwenden der `&` Operator für *Verkettung*, oder Verknüpfen von Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="55dae-126">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="55dae-127">Ist nicht zu verwechseln mit der `+` -Operator, der numerische Werte addiert.</span><span class="sxs-lookup"><span data-stu-id="55dae-127">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="55dae-128">Bei Verwendung der `+` Operator verkettet wird, wenn Sie mit numerischen Werten arbeiten Sie falsche Ergebnisse erhalten.</span><span class="sxs-lookup"><span data-stu-id="55dae-128">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="55dae-129">Das folgende Beispiel veranschaulicht das.</span><span class="sxs-lookup"><span data-stu-id="55dae-129">The following example demonstrates this.</span></span>  
  
 <span data-ttu-id="55dae-130">[!code-vb[VbVbcnConventions&#13;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="55dae-130">[!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_3.vb)]</span></span>  
  
 <span data-ttu-id="55dae-131">Nach der Ausführung des vorherigen Code den Wert der `resultA` 21.01 und der Wert des `resultB` "10.0111".</span><span class="sxs-lookup"><span data-stu-id="55dae-131">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="55dae-132">Operatoren für den Memberzugriff</span><span class="sxs-lookup"><span data-stu-id="55dae-132">Member Access Operators</span></span>  
 <span data-ttu-id="55dae-133">Zugriff auf einen Member eines Typs, verwenden Sie den Punkt (`.`) oder ein Ausrufezeichen (`!`)-Operator zwischen dem Typnamen und den Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="55dae-133">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="55dae-134">Punkt (.) Operator</span><span class="sxs-lookup"><span data-stu-id="55dae-134">Dot (.) Operator</span></span>  
 <span data-ttu-id="55dae-135">Verwenden der `.` Operator auf eine Klasse, Struktur, Schnittstelle oder Enumeration als Operator für den Memberzugriff.</span><span class="sxs-lookup"><span data-stu-id="55dae-135">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="55dae-136">Das Element kann ein Feld, Eigenschaft, Ereignis oder Methode.</span><span class="sxs-lookup"><span data-stu-id="55dae-136">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="55dae-137">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="55dae-137">The following example illustrates this.</span></span>  
  
 <span data-ttu-id="55dae-138">[!code-vb[VbVbcnConventions&14;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="55dae-138">[!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_4.vb)]</span></span>  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="55dae-139">Ausrufezeichen (!) Operator</span><span class="sxs-lookup"><span data-stu-id="55dae-139">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="55dae-140">Verwenden der `!` Operator nur auf eine Klasse oder Schnittstelle als Operator für den Wörterbuchzugriff.</span><span class="sxs-lookup"><span data-stu-id="55dae-140">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="55dae-141">Die Klasse oder Schnittstelle müssen eine Default-Eigenschaft, die ein einzelnes akzeptiert `String` Argument.</span><span class="sxs-lookup"><span data-stu-id="55dae-141">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="55dae-142">Der Bezeichner direkt nach dem `!` Operator wird der Wert des Arguments an die Standardeigenschaft als Zeichenfolge übergeben.</span><span class="sxs-lookup"><span data-stu-id="55dae-142">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="55dae-143">Das folgende Beispiel veranschaulicht das.</span><span class="sxs-lookup"><span data-stu-id="55dae-143">The following example demonstrates this.</span></span>  
  
 <span data-ttu-id="55dae-144">[!code-vb[VbVbcnConventions&#15;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="55dae-144">[!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/special-characters-in-code_5.vb)]</span></span>  
  
 <span data-ttu-id="55dae-145">Die drei Zeilen der Ausgabe `MsgBox` alle zeigt den Wert `32856`.</span><span class="sxs-lookup"><span data-stu-id="55dae-145">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="55dae-146">Die erste Zeile wird der herkömmliche Zugriff auf Eigenschaft verwendet `index`, die zweite nutzt die Tatsache, `index` ist die Standardeigenschaft der Klasse `hasDefault`, und die dritte Wörterbuchzugriff auf die Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="55dae-146">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="55dae-147">Beachten Sie, dass der zweite Operand des der `!` Operator muss ein gültiger Visual Basic-Bezeichner nicht in Anführungszeichen eingeschlossen sein (`" "`).</span><span class="sxs-lookup"><span data-stu-id="55dae-147">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="55dae-148">Sie können nicht in anderen Worten, ein Zeichenfolgenliteral oder eine String-Variable verwenden.</span><span class="sxs-lookup"><span data-stu-id="55dae-148">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="55dae-149">Die folgende Änderung der letzten Zeile der `MsgBox` Aufruf wird ein Fehler generiert, da `"X"` ist eine eingeschlossene Zeichenfolgenliteral.</span><span class="sxs-lookup"><span data-stu-id="55dae-149">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  <span data-ttu-id="55dae-150">Verweise auf Standardsammlungen müssen explizit erfolgen.</span><span class="sxs-lookup"><span data-stu-id="55dae-150">References to default collections must be explicit.</span></span> <span data-ttu-id="55dae-151">Insbesondere können keine der `!` Operator auf eine spät gebundene Variable.</span><span class="sxs-lookup"><span data-stu-id="55dae-151">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="55dae-152">Die `!` Zeichen dient auch als die `Single` Zeichen eingeben.</span><span class="sxs-lookup"><span data-stu-id="55dae-152">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55dae-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55dae-153">See Also</span></span>  
 <span data-ttu-id="55dae-154">[Programmstruktur und Codekonventionen](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="55dae-154">[Program Structure and Code Conventions](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md) </span></span>  
<span data-ttu-id="55dae-155"> [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span><span class="sxs-lookup"><span data-stu-id="55dae-155"> [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)</span></span>
