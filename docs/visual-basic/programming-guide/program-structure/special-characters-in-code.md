---
title: Sonderzeichen in Code
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
ms.openlocfilehash: c9b170ed812474cdeee100f1dc388d5c7e85f2cc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400590"
---
# <a name="special-characters-in-code-visual-basic"></a><span data-ttu-id="a0830-102">Sonderzeichen in Code (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0830-102">Special Characters in Code (Visual Basic)</span></span>
<span data-ttu-id="a0830-103">Manchmal müssen Sonderzeichen in Ihrem Code verwendet werden, d. h. Zeichen, die nicht alphabetisch oder numerisch sind.</span><span class="sxs-lookup"><span data-stu-id="a0830-103">Sometimes you have to use special characters in your code, that is, characters that are not alphabetical or numeric.</span></span> <span data-ttu-id="a0830-104">Die Interpunktions-und Sonderzeichen im Visual Basic Zeichensatz weisen verschiedene Verwendungsmöglichkeiten auf, von der Organisation des Programm Texts bis zur Definition der Aufgaben, die der Compiler oder das kompilierte Programm ausführt.</span><span class="sxs-lookup"><span data-stu-id="a0830-104">The punctuation and special characters in the Visual Basic character set have various uses, from organizing program text to defining the tasks that the compiler or the compiled program performs.</span></span> <span data-ttu-id="a0830-105">Sie legen keine auszuführende Operation fest.</span><span class="sxs-lookup"><span data-stu-id="a0830-105">They do not specify an operation to be performed.</span></span>  
  
## <a name="parentheses"></a><span data-ttu-id="a0830-106">Klammern</span><span class="sxs-lookup"><span data-stu-id="a0830-106">Parentheses</span></span>  
 <span data-ttu-id="a0830-107">Verwenden Sie Klammern, wenn Sie eine Prozedur definieren, z. b `Sub` `Function` . oder.</span><span class="sxs-lookup"><span data-stu-id="a0830-107">Use parentheses when you define a procedure, such as a `Sub` or `Function`.</span></span> <span data-ttu-id="a0830-108">Alle Prozedur Argumentlisten müssen in Klammern eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="a0830-108">You must enclose all procedure argument lists in parentheses.</span></span> <span data-ttu-id="a0830-109">Außerdem verwenden Sie Klammern zum Platzieren von Variablen oder Argumenten in logischen Gruppen, insbesondere, um die Standard Reihenfolge der Operator Rangfolge in einem komplexen Ausdruck zu überschreiben.</span><span class="sxs-lookup"><span data-stu-id="a0830-109">You also use parentheses for putting variables or arguments into logical groups, especially to override the default order of operator precedence in a complex expression.</span></span> <span data-ttu-id="a0830-110">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a0830-110">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#11)]  
  
 <span data-ttu-id="a0830-111">Nach der Ausführung des vorherigen Codes ist der Wert von `d` 8,225 und der Wert von `e` 3.</span><span class="sxs-lookup"><span data-stu-id="a0830-111">Following execution of the previous code, the value of `d` is 8.225 and the value of `e` is 3.</span></span> <span data-ttu-id="a0830-112">Die Berechnung für `d` verwendet die Standard Rangfolge von `/` over `+` und entspricht `d = b + (c / a)` .</span><span class="sxs-lookup"><span data-stu-id="a0830-112">The calculation for `d` uses the default precedence of `/` over `+` and is equivalent to `d = b + (c / a)`.</span></span> <span data-ttu-id="a0830-113">Die Klammern in der Berechnung für über `e` schreiben die Standard Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="a0830-113">The parentheses in the calculation for `e` override the default precedence.</span></span>  
  
## <a name="separators"></a><span data-ttu-id="a0830-114">Trennzeichen</span><span class="sxs-lookup"><span data-stu-id="a0830-114">Separators</span></span>  
 <span data-ttu-id="a0830-115">Trennzeichen tun, was der Name vermuten lässt: Sie trennen Code Abschnitte.</span><span class="sxs-lookup"><span data-stu-id="a0830-115">Separators do what their name suggests: they separate sections of code.</span></span> <span data-ttu-id="a0830-116">In Visual Basic ist das Trennzeichen der Doppelpunkt ( `:` ).</span><span class="sxs-lookup"><span data-stu-id="a0830-116">In Visual Basic, the separator character is the colon (`:`).</span></span> <span data-ttu-id="a0830-117">Verwenden Sie Trennzeichen, wenn Sie mehrere-Anweisungen in einer einzelnen Zeile anstelle von separaten Zeilen einschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="a0830-117">Use separators when you want to include multiple statements on a single line instead of separate lines.</span></span> <span data-ttu-id="a0830-118">Dadurch wird Speicherplatz gespart, und die Lesbarkeit des Codes wird verbessert.</span><span class="sxs-lookup"><span data-stu-id="a0830-118">This saves space and improves the readability of your code.</span></span> <span data-ttu-id="a0830-119">Im folgenden Beispiel werden drei durch Doppelpunkte getrennte Anweisungen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a0830-119">The following example shows three statements separated by colons.</span></span>  
  
 [!code-vb[VbVbcnConventions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#12)]  
  
 <span data-ttu-id="a0830-120">Weitere Informationen finden Sie unter Gewusst [wie: unterbrechen und Kombinieren von Anweisungen in Code](how-to-break-and-combine-statements-in-code.md).</span><span class="sxs-lookup"><span data-stu-id="a0830-120">For more information, see [How to: Break and Combine Statements in Code](how-to-break-and-combine-statements-in-code.md).</span></span>  
  
 <span data-ttu-id="a0830-121">Der Doppelpunkt ( `:` ) wird auch verwendet, um eine Anweisungsbezeichnung zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="a0830-121">The colon (`:`) character is also used to identify a statement label.</span></span> <span data-ttu-id="a0830-122">Weitere Informationen finden Sie unter Gewusst [wie: bezeichnen von Anweisungen](how-to-label-statements.md).</span><span class="sxs-lookup"><span data-stu-id="a0830-122">For more information, see [How to: Label Statements](how-to-label-statements.md).</span></span>  
  
## <a name="concatenation"></a><span data-ttu-id="a0830-123">Verkettung</span><span class="sxs-lookup"><span data-stu-id="a0830-123">Concatenation</span></span>  
 <span data-ttu-id="a0830-124">Verwenden Sie den- `&` Operator für die *Verkettung*oder das Verknüpfen von Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="a0830-124">Use the `&` operator for *concatenation*, or linking strings together.</span></span> <span data-ttu-id="a0830-125">Verwechseln Sie diese nicht mit dem- `+` Operator, der numerische Werte addiert.</span><span class="sxs-lookup"><span data-stu-id="a0830-125">Do not confuse it with the `+` operator, which adds together numeric values.</span></span> <span data-ttu-id="a0830-126">Wenn Sie den- `+` Operator zum Verketten verwenden, wenn Sie numerische Werte verarbeiten, können Sie falsche Ergebnisse erzielen.</span><span class="sxs-lookup"><span data-stu-id="a0830-126">If you use the `+` operator to concatenate when you operate on numeric values, you can obtain incorrect results.</span></span> <span data-ttu-id="a0830-127">Das wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a0830-127">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#13)]  
  
 <span data-ttu-id="a0830-128">Nach der Ausführung des vorherigen Codes ist der Wert von `resultA` 21,01 und der Wert von `resultB` "10,0111".</span><span class="sxs-lookup"><span data-stu-id="a0830-128">Following execution of the previous code, the value of `resultA` is 21.01 and the value of `resultB` is "10.0111".</span></span>  
  
## <a name="member-access-operators"></a><span data-ttu-id="a0830-129">Member-Zugriffs Operatoren</span><span class="sxs-lookup"><span data-stu-id="a0830-129">Member Access Operators</span></span>  
 <span data-ttu-id="a0830-130">Wenn Sie auf einen Member eines Typs zugreifen möchten, verwenden Sie den Punkt ( `.` ) oder den Ausrufezeichen `!` Operator () zwischen dem Typnamen und dem Elementnamen.</span><span class="sxs-lookup"><span data-stu-id="a0830-130">To access a member of a type, you use the dot (`.`) or exclamation point (`!`) operator between the type name and the member name.</span></span>  
  
### <a name="dot--operator"></a><span data-ttu-id="a0830-131">Punkt (.) KOM</span><span class="sxs-lookup"><span data-stu-id="a0830-131">Dot (.) Operator</span></span>  
 <span data-ttu-id="a0830-132">Verwenden Sie den- `.` Operator für eine Klasse, eine Struktur, eine Schnittstelle oder eine Enumeration als Member Access Operator.</span><span class="sxs-lookup"><span data-stu-id="a0830-132">Use the `.` operator on a class, structure, interface, or enumeration as a member access operator.</span></span> <span data-ttu-id="a0830-133">Der Member kann ein Feld, eine Eigenschaft, ein Ereignis oder eine Methode sein.</span><span class="sxs-lookup"><span data-stu-id="a0830-133">The member can be a field, property, event, or method.</span></span> <span data-ttu-id="a0830-134">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a0830-134">The following example illustrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#14)]  
  
### <a name="exclamation-point--operator"></a><span data-ttu-id="a0830-135">Ausrufezeichen (!) KOM</span><span class="sxs-lookup"><span data-stu-id="a0830-135">Exclamation Point (!) Operator</span></span>  
 <span data-ttu-id="a0830-136">Verwenden Sie den- `!` Operator nur für eine Klasse oder Schnittstelle als Wörterbuch Zugriffs Operator.</span><span class="sxs-lookup"><span data-stu-id="a0830-136">Use the `!` operator only on a class or interface as a dictionary access operator.</span></span> <span data-ttu-id="a0830-137">Die Klasse oder Schnittstelle muss über eine Default-Eigenschaft verfügen, die ein einzelnes `String` Argument akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="a0830-137">The class or interface must have a default property that accepts a single `String` argument.</span></span> <span data-ttu-id="a0830-138">Der Bezeichner, der direkt `!` auf den Operator folgt, wird zum Argument Wert, der als Zeichenfolge an die Standard Eigenschaft übermittelt wird</span><span class="sxs-lookup"><span data-stu-id="a0830-138">The identifier immediately following the `!` operator becomes the argument value passed to the default property as a string.</span></span> <span data-ttu-id="a0830-139">Das wird im folgenden Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a0830-139">The following example demonstrates this.</span></span>  
  
 [!code-vb[VbVbcnConventions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnConventions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="a0830-140">In den drei Ausgabezeilen von wird `MsgBox` der Wert angezeigt `32856` .</span><span class="sxs-lookup"><span data-stu-id="a0830-140">The three output lines of `MsgBox` all display the value `32856`.</span></span> <span data-ttu-id="a0830-141">Die erste Zeile verwendet die herkömmliche Access-Eigenschaft `index` , die zweite verwendet die Tatsache, dass `index` die Standard Eigenschaft der-Klasse ist `hasDefault` , und die dritte verwendet den Wörterbuch Zugriff auf die-Klasse.</span><span class="sxs-lookup"><span data-stu-id="a0830-141">The first line uses the traditional access to property `index`, the second makes use of the fact that `index` is the default property of class `hasDefault`, and the third uses dictionary access to the class.</span></span>  
  
 <span data-ttu-id="a0830-142">Beachten Sie, dass der zweite Operand des `!` Operators ein gültiger Visual Basic Bezeichner sein muss, der nicht in doppelte Anführungszeichen () eingeschlossen ist `" "` .</span><span class="sxs-lookup"><span data-stu-id="a0830-142">Note that the second operand of the `!` operator must be a valid Visual Basic identifier not enclosed in double quotation marks (`" "`).</span></span> <span data-ttu-id="a0830-143">Anders ausgedrückt: Sie können keine Zeichenfolgenliterale oder Zeichen folgen Variable verwenden.</span><span class="sxs-lookup"><span data-stu-id="a0830-143">In other words, you cannot use a string literal or string variable.</span></span> <span data-ttu-id="a0830-144">Die folgende Änderung an der letzten Zeile des `MsgBox` Aufrufes generiert einen Fehler, da `"X"` ein eingeschlossenes zeichenfolgenliteralist.</span><span class="sxs-lookup"><span data-stu-id="a0830-144">The following change to the last line of the `MsgBox` call generates an error because `"X"` is an enclosed string literal.</span></span>  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
> <span data-ttu-id="a0830-145">Verweise auf Standard Auflistungen müssen explizit sein.</span><span class="sxs-lookup"><span data-stu-id="a0830-145">References to default collections must be explicit.</span></span> <span data-ttu-id="a0830-146">Insbesondere kann der- `!` Operator nicht für eine spät gebundene Variable verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0830-146">In particular, you cannot use the `!` operator on a late-bound variable.</span></span>  
  
 <span data-ttu-id="a0830-147">Das `!` Zeichen wird auch als `Single` Typzeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a0830-147">The `!` character is also used as the `Single` type character.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0830-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a0830-148">See also</span></span>

- [<span data-ttu-id="a0830-149">Programmstruktur und Codekonventionen</span><span class="sxs-lookup"><span data-stu-id="a0830-149">Program Structure and Code Conventions</span></span>](program-structure-and-code-conventions.md)
- [<span data-ttu-id="a0830-150">Typzeichen</span><span class="sxs-lookup"><span data-stu-id="a0830-150">Type Characters</span></span>](../language-features/data-types/type-characters.md)
