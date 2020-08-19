---
title: Operatorüberladung
description: 'Erfahren Sie, wie Sie arithmetische Operatoren in einer Klasse oder einem Daten Satz Typ und auf globaler Ebene in F # überladen.'
ms.date: 08/15/2020
ms.openlocfilehash: fb86ceb95101fcc1f157ec9ba17a9d8145b11a91
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557580"
---
# <a name="operator-overloading"></a><span data-ttu-id="df26f-103">Operatorüberladung</span><span class="sxs-lookup"><span data-stu-id="df26f-103">Operator Overloading</span></span>

<span data-ttu-id="df26f-104">In diesem Thema wird beschrieben, wie arithmetische Operatoren in einer Klasse oder einem Datensatztyp sowie auf globaler Ebene überladen werden.</span><span class="sxs-lookup"><span data-stu-id="df26f-104">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>

## <a name="syntax"></a><span data-ttu-id="df26f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="df26f-105">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="df26f-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="df26f-106">Remarks</span></span>

<span data-ttu-id="df26f-107">In der vorherigen Syntax ist das *Operator-Symbol* eine von `+` , `-` , `*` , `/` , `=` usw.</span><span class="sxs-lookup"><span data-stu-id="df26f-107">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="df26f-108">Der *Parameter-List* gibt die Operanden in der Reihenfolge an, in der Sie in der üblichen Syntax für diesen Operator angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="df26f-108">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="df26f-109">Der *Methoden Text* erstellt den resultierenden Wert.</span><span class="sxs-lookup"><span data-stu-id="df26f-109">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="df26f-110">Operatorüberladungen müssen statisch sein.</span><span class="sxs-lookup"><span data-stu-id="df26f-110">Operator overloads for operators must be static.</span></span> <span data-ttu-id="df26f-111">Operator Überladungen für unäre Operatoren, wie z. b. `+` und `-` , müssen eine Tilde ( `~` ) im *Operator-Symbol* verwenden, um anzugeben, dass der Operator ein unärer Operator und kein binärer Operator ist, wie in der folgenden Deklaration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="df26f-111">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="df26f-112">Im folgenden Code wird eine Vektorklasse veranschaulicht, die über nur zwei Operatoren verfügt, einer für unäres Minus und einer für Multiplikation mit einem Skalar.</span><span class="sxs-lookup"><span data-stu-id="df26f-112">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="df26f-113">In dem Beispiel werden zwei Überladungen für skalare Multiplikation benötigt, da der Operator unabhängig von der Reihenfolge verwendet werden können muss, in der der Vektor und der Skalar angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="df26f-113">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="df26f-114">Erstellen von neuen Operatoren</span><span class="sxs-lookup"><span data-stu-id="df26f-114">Creating New Operators</span></span>

<span data-ttu-id="df26f-115">Sie können alle Standardoperatoren überladen, Sie können jedoch auch aus Sequenzen bestimmter Zeichen neue Operatoren erstellen.</span><span class="sxs-lookup"><span data-stu-id="df26f-115">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="df26f-116">Zulässige Operator Zeichen sind `!` , `%` , `&` , `*` , `+` , `-` , `.` , `/` , `<` , `=` , `>` , `?` , `@` , `^` , `|` und `~` .</span><span class="sxs-lookup"><span data-stu-id="df26f-116">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="df26f-117">Das Zeichen `~` hat eine besondere Bedeutung, da mit ihm ein Operator als unärer Operator festgelegt wird. Es kann nicht in einer Operatorzeichenfolge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="df26f-117">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="df26f-118">Nicht alle Operatoren können unär gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="df26f-118">Not all operators can be made unary.</span></span>

<span data-ttu-id="df26f-119">Rangfolge und Assoziativität des Operators hängen von der verwendeten Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="df26f-119">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="df26f-120">Die Assoziativität kann entweder von links nach rechts oder von rechts nach links sein. Sie wird immer verwendet, wenn Operatoren der gleichen Rangfolge nacheinander ohne Klammern angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="df26f-120">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="df26f-121">Das Operatorzeichen `.` wirkt sich nicht auf die Rangfolge aus. Wenn Sie eine eigene Version von Multiplikation definieren möchten, die die gleiche Rangfolge und Assoziativität wie die übliche Multiplikation aufweist, können Sie daher z. B. den Operator `.*` erstellen.</span><span class="sxs-lookup"><span data-stu-id="df26f-121">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="df26f-122">Nur die Operatoren `?` und `?<-` können mit beginnen `?` .</span><span class="sxs-lookup"><span data-stu-id="df26f-122">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="df26f-123">Eine Tabelle, in der die Rangfolge aller Operatoren in F # angezeigt wird, finden Sie unter [Symbol-und Operator Verweis](./symbol-and-operator-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="df26f-123">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](./symbol-and-operator-reference/index.md).</span></span>

## <a name="overloaded-operator-names"></a><span data-ttu-id="df26f-124">Namen von überladenen Operatoren</span><span class="sxs-lookup"><span data-stu-id="df26f-124">Overloaded Operator Names</span></span>

<span data-ttu-id="df26f-125">Wenn der F#-Compiler einen Operatorausdruck kompiliert, wird eine Methode mit einem vom Compiler generierten Namen für den Operator erzeugt.</span><span class="sxs-lookup"><span data-stu-id="df26f-125">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="df26f-126">Dies ist der Name, der in MSIL (Microsoft Intermediate Language) sowie in IntelliSense und bei Reflektion für die Methode angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="df26f-126">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="df26f-127">Sie müssen diese Namen normalerweise nicht in F#-Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="df26f-127">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="df26f-128">In der folgenden Tabelle werden die Standardoperatoren und die entsprechenden generierten Namen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="df26f-128">The following table shows the standard operators and their corresponding generated names.</span></span>

|<span data-ttu-id="df26f-129">Operator</span><span class="sxs-lookup"><span data-stu-id="df26f-129">Operator</span></span>|<span data-ttu-id="df26f-130">Generierter Name</span><span class="sxs-lookup"><span data-stu-id="df26f-130">Generated name</span></span>|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|

<span data-ttu-id="df26f-131">Beachten Sie, dass der- `not` Operator in F # nicht ausgibt, `op_Inequality` weil es sich nicht um einen symbolischen Operator handelt.</span><span class="sxs-lookup"><span data-stu-id="df26f-131">Note that the `not` operator in F# does not emit `op_Inequality` because it is not a symbolic operator.</span></span> <span data-ttu-id="df26f-132">Diese Funktion gibt Il aus, die einen booleschen Ausdruck negiert.</span><span class="sxs-lookup"><span data-stu-id="df26f-132">It is a function that emits IL that negates a boolean expression.</span></span>

<span data-ttu-id="df26f-133">Andere, hier nicht aufgeführte Kombinationen von Operatorzeichen können als Operatoren verwendet werden, und ihre Namen werden durch das Verketten von Namen für die einzelnen Zeichen in der folgenden Tabelle gebildet.</span><span class="sxs-lookup"><span data-stu-id="df26f-133">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="df26f-134">Beispiel: +!</span><span class="sxs-lookup"><span data-stu-id="df26f-134">For example, +!</span></span> <span data-ttu-id="df26f-135"> wird `op_PlusBang`.</span><span class="sxs-lookup"><span data-stu-id="df26f-135">becomes `op_PlusBang`.</span></span>

|<span data-ttu-id="df26f-136">Operatorzeichen</span><span class="sxs-lookup"><span data-stu-id="df26f-136">Operator character</span></span>|<span data-ttu-id="df26f-137">Name</span><span class="sxs-lookup"><span data-stu-id="df26f-137">Name</span></span>|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="df26f-138">Präfix- und Infixoperatoren</span><span class="sxs-lookup"><span data-stu-id="df26f-138">Prefix and Infix Operators</span></span>

<span data-ttu-id="df26f-139">Es wird erwartet, dass *Präfix* Operatoren vor einem Operanden oder Operanden platziert werden, ähnlich wie eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="df26f-139">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="df26f-140">Es wird erwartet, dass *Infix* -Operatoren zwischen den beiden Operanden platziert werden.</span><span class="sxs-lookup"><span data-stu-id="df26f-140">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="df26f-141">Nur bestimmte Operatoren können als Präfixoperatoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="df26f-141">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="df26f-142">Einige Operatoren sind immer Präfixoperatoren, andere können Infix- oder Präfixoperatoren sein und der Rest ist immer Infixoperatoren.</span><span class="sxs-lookup"><span data-stu-id="df26f-142">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="df26f-143">Operatoren, die mit `!` beginnen, außer `!=` und der Operator `~` oder wiederholte Sequenzen von `~`, sind immer Präfixoperatoren.</span><span class="sxs-lookup"><span data-stu-id="df26f-143">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="df26f-144">Die Operatoren `+`, `-`, `+.`, `-.`, `&`, `&&`, `%` und `%%` können Vorzeichenoperatoren oder Infixoperatoren sein.</span><span class="sxs-lookup"><span data-stu-id="df26f-144">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="df26f-145">Sie unterscheiden die Präfix-Version dieser Operatoren von der Infix-Version, indem Sie `~` am Anfang eines Präfixoperators hinzufügen, wenn er definiert wird.</span><span class="sxs-lookup"><span data-stu-id="df26f-145">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="df26f-146">Das Symbol `~` wird nicht verwendet, wenn Sie den Operator verwenden, sondern nur wenn definiert.</span><span class="sxs-lookup"><span data-stu-id="df26f-146">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="df26f-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="df26f-147">Example</span></span>

<span data-ttu-id="df26f-148">Im folgenden Code wird veranschaulicht, wie mit Operatorüberladung ein Bruchtyp implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="df26f-148">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="df26f-149">Ein Bruch wird durch einen Zähler und einen Nenner dargestellt.</span><span class="sxs-lookup"><span data-stu-id="df26f-149">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="df26f-150">Mit der Funktion `hcf` wird der größte gemeinsame Teiler zum Kürzen von Brüchen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="df26f-150">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="df26f-151">**Ausgabe:**</span><span class="sxs-lookup"><span data-stu-id="df26f-151">**Output:**</span></span>

```console
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="df26f-152">Operatoren auf globaler Ebene</span><span class="sxs-lookup"><span data-stu-id="df26f-152">Operators at the Global Level</span></span>

<span data-ttu-id="df26f-153">Sie können Operatoren auch auf globaler Ebene definieren.</span><span class="sxs-lookup"><span data-stu-id="df26f-153">You can also define operators at the global level.</span></span> <span data-ttu-id="df26f-154">Der folgende Code definiert einen Operator `+?` .</span><span class="sxs-lookup"><span data-stu-id="df26f-154">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="df26f-155">Die Ausgabe des vorangehenden Codes lautet `12`.</span><span class="sxs-lookup"><span data-stu-id="df26f-155">The output of the above code is `12`.</span></span>

<span data-ttu-id="df26f-156">Sie können die normalen arithmetischen Operatoren auf diese Weise neu definieren, da gemäß den Bereichsregeln für F# neu definierte Operatoren Vorrang vor den integrierten Operatoren haben.</span><span class="sxs-lookup"><span data-stu-id="df26f-156">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="df26f-157">Das Schlüsselwort `inline` wird oft mit globalen Operatoren verwendet, bei denen es sich häufig um kleine Funktionen handelt, die nach Möglichkeit in den aufrufenden Code integriert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="df26f-157">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="df26f-158">Wenn Sie Operatorfunktionen als Inlinefunktionen festlegen, können diese auch mit statisch aufgelösten Typparametern verwendet werden, um statisch aufgelösten generischen Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="df26f-158">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="df26f-159">Weitere Informationen finden Sie unter [Inline Funktionen](./functions/inline-functions.md) und [statisch aufgelöste Typparameter](./generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="df26f-159">For more information, see [Inline Functions](./functions/inline-functions.md) and [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="df26f-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df26f-160">See also</span></span>

- [<span data-ttu-id="df26f-161">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="df26f-161">Members</span></span>](./members/index.md)
