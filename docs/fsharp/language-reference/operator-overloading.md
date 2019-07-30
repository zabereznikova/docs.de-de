---
title: Operatorüberladung
description: Erfahren Sie, wie arithmetische Operatoren in einer Klasse oder einem Datensatztyp sowie auf globaler Ebene in F# zu überladen.
ms.date: 05/16/2016
ms.openlocfilehash: c656c1c47938e62386c8f063cf9a6caaaf69d0fe
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627390"
---
# <a name="operator-overloading"></a><span data-ttu-id="b1f0d-103">Operatorüberladung</span><span class="sxs-lookup"><span data-stu-id="b1f0d-103">Operator Overloading</span></span>

<span data-ttu-id="b1f0d-104">In diesem Thema wird beschrieben, wie arithmetische Operatoren in einer Klasse oder einem Datensatztyp sowie auf globaler Ebene überladen werden.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-104">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>

## <a name="syntax"></a><span data-ttu-id="b1f0d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1f0d-105">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="b1f0d-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b1f0d-106">Remarks</span></span>

<span data-ttu-id="b1f0d-107">In der vorherigen Syntax ist das *Operator-Symbol* eine `+`von, `*` `-`,, `/`, `=`usw.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-107">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="b1f0d-108">Der *Parameter-List* gibt die Operanden in der Reihenfolge an, in der Sie in der üblichen Syntax für diesen Operator angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-108">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="b1f0d-109">Der *Methoden Text* erstellt den resultierenden Wert.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-109">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="b1f0d-110">Operatorüberladungen müssen statisch sein.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-110">Operator overloads for operators must be static.</span></span> <span data-ttu-id="b1f0d-111">Operator Überladungen für unäre Operatoren, wie `+` z `-`. b. und, müssen eine`~`Tilde () im *Operator-Symbol* verwenden, um anzugeben, dass der Operator ein unärer Operator und kein binärer Operator ist, wie im folgenden Beispiel gezeigt. Zuverlässigkeits.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-111">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="b1f0d-112">Im folgenden Code wird eine Vektorklasse veranschaulicht, die über nur zwei Operatoren verfügt, einer für unäres Minus und einer für Multiplikation mit einem Skalar.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-112">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="b1f0d-113">In dem Beispiel werden zwei Überladungen für skalare Multiplikation benötigt, da der Operator unabhängig von der Reihenfolge verwendet werden können muss, in der der Vektor und der Skalar angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-113">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="b1f0d-114">Erstellen von neuen Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1f0d-114">Creating New Operators</span></span>

<span data-ttu-id="b1f0d-115">Sie können alle Standardoperatoren überladen, Sie können jedoch auch aus Sequenzen bestimmter Zeichen neue Operatoren erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-115">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="b1f0d-116">Zulässige Operator Zeichen sind `!`, `%`, `&`, `*`, `+`, ,,`.`,, ,`=`, `/` `-` `<` `>` `?` ,`@`, ,`^` und`~`. `|`</span><span class="sxs-lookup"><span data-stu-id="b1f0d-116">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="b1f0d-117">Das Zeichen `~` hat eine besondere Bedeutung, da mit ihm ein Operator als unärer Operator festgelegt wird. Es kann nicht in einer Operatorzeichenfolge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-117">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="b1f0d-118">Nicht alle Operatoren können unär gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-118">Not all operators can be made unary.</span></span>

<span data-ttu-id="b1f0d-119">Rangfolge und Assoziativität des Operators hängen von der verwendeten Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-119">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="b1f0d-120">Die Assoziativität kann entweder von links nach rechts oder von rechts nach links sein. Sie wird immer verwendet, wenn Operatoren der gleichen Rangfolge nacheinander ohne Klammern angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-120">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="b1f0d-121">Das Operatorzeichen `.` wirkt sich nicht auf die Rangfolge aus. Wenn Sie eine eigene Version von Multiplikation definieren möchten, die die gleiche Rangfolge und Assoziativität wie die übliche Multiplikation aufweist, können Sie daher z. B. den Operator `.*` erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-121">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="b1f0d-122">Nur die `?` Operatoren `?<-` und können mit `?`beginnen.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-122">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="b1f0d-123">Eine Tabelle mit der Rangfolge aller Operatoren in F# finden Sie im [Symbol- und Operatorenreferenz](./symbol-and-operator-reference/index.md).</span><span class="sxs-lookup"><span data-stu-id="b1f0d-123">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](./symbol-and-operator-reference/index.md).</span></span>

## <a name="overloaded-operator-names"></a><span data-ttu-id="b1f0d-124">Namen von überladenen Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1f0d-124">Overloaded Operator Names</span></span>

<span data-ttu-id="b1f0d-125">Wenn der F#-Compiler einen Operatorausdruck kompiliert, wird eine Methode mit einem vom Compiler generierten Namen für den Operator erzeugt.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-125">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="b1f0d-126">Dies ist der Name, der in MSIL (Microsoft Intermediate Language) sowie in IntelliSense und bei Reflektion für die Methode angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-126">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="b1f0d-127">Sie müssen diese Namen normalerweise nicht in F#-Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-127">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="b1f0d-128">In der folgenden Tabelle werden die Standardoperatoren und die entsprechenden generierten Namen dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-128">The following table shows the standard operators and their corresponding generated names.</span></span>

|<span data-ttu-id="b1f0d-129">Operator</span><span class="sxs-lookup"><span data-stu-id="b1f0d-129">Operator</span></span>|<span data-ttu-id="b1f0d-130">Generierter Name</span><span class="sxs-lookup"><span data-stu-id="b1f0d-130">Generated name</span></span>|
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

<span data-ttu-id="b1f0d-131">Andere, hier nicht aufgeführte Kombinationen von Operatorzeichen können als Operatoren verwendet werden, und ihre Namen werden durch das Verketten von Namen für die einzelnen Zeichen in der folgenden Tabelle gebildet.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-131">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="b1f0d-132">Beispiel: +!</span><span class="sxs-lookup"><span data-stu-id="b1f0d-132">For example, +!</span></span> <span data-ttu-id="b1f0d-133">wird `op_PlusBang`zu.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-133">becomes `op_PlusBang`.</span></span>

|<span data-ttu-id="b1f0d-134">Operatorzeichen</span><span class="sxs-lookup"><span data-stu-id="b1f0d-134">Operator character</span></span>|<span data-ttu-id="b1f0d-135">name</span><span class="sxs-lookup"><span data-stu-id="b1f0d-135">Name</span></span>|
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

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="b1f0d-136">Präfix- und Infixoperatoren</span><span class="sxs-lookup"><span data-stu-id="b1f0d-136">Prefix and Infix Operators</span></span>

<span data-ttu-id="b1f0d-137">Es wird erwartet, dass *Präfix* Operatoren vor einem Operanden oder Operanden platziert werden, ähnlich wie eine Funktion.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-137">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="b1f0d-138">Es wird erwartet, dass *Infix* -Operatoren zwischen den beiden Operanden platziert werden.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-138">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="b1f0d-139">Nur bestimmte Operatoren können als Präfixoperatoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-139">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="b1f0d-140">Einige Operatoren sind immer Präfixoperatoren, andere können Infix- oder Präfixoperatoren sein und der Rest ist immer Infixoperatoren.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-140">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="b1f0d-141">Operatoren, die mit `!` beginnen, außer `!=` und der Operator `~` oder wiederholte Sequenzen von `~`, sind immer Präfixoperatoren.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-141">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="b1f0d-142">Die Operatoren `+`, `-`, `+.`, `-.`, `&`, `&&`, `%` und `%%` können Vorzeichenoperatoren oder Infixoperatoren sein.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-142">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="b1f0d-143">Sie unterscheiden die Präfix-Version dieser Operatoren von der Infix-Version, indem Sie `~` am Anfang eines Präfixoperators hinzufügen, wenn er definiert wird.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-143">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="b1f0d-144">Das Symbol `~` wird nicht verwendet, wenn Sie den Operator verwenden, sondern nur wenn definiert.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-144">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="b1f0d-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b1f0d-145">Example</span></span>

<span data-ttu-id="b1f0d-146">Im folgenden Code wird veranschaulicht, wie mit Operatorüberladung ein Bruchtyp implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-146">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="b1f0d-147">Ein Bruch wird durch einen Zähler und einen Nenner dargestellt.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-147">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="b1f0d-148">Mit der Funktion `hcf` wird der größte gemeinsame Teiler zum Kürzen von Brüchen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-148">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="b1f0d-149">**Ausgabe:**</span><span class="sxs-lookup"><span data-stu-id="b1f0d-149">**Output:**</span></span>

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="b1f0d-150">Operatoren auf globaler Ebene</span><span class="sxs-lookup"><span data-stu-id="b1f0d-150">Operators at the Global Level</span></span>

<span data-ttu-id="b1f0d-151">Sie können Operatoren auch auf globaler Ebene definieren.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-151">You can also define operators at the global level.</span></span> <span data-ttu-id="b1f0d-152">Der folgende Code definiert einen Operator `+?`.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-152">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="b1f0d-153">Die Ausgabe des vorangehenden Codes lautet `12`.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-153">The output of the above code is `12`.</span></span>

<span data-ttu-id="b1f0d-154">Sie können die normalen arithmetischen Operatoren auf diese Weise neu definieren, da gemäß den Bereichsregeln für F# neu definierte Operatoren Vorrang vor den integrierten Operatoren haben.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-154">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="b1f0d-155">Das Schlüsselwort `inline` wird oft mit globalen Operatoren verwendet, bei denen es sich häufig um kleine Funktionen handelt, die nach Möglichkeit in den aufrufenden Code integriert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-155">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="b1f0d-156">Wenn Sie Operatorfunktionen als Inlinefunktionen festlegen, können diese auch mit statisch aufgelösten Typparametern verwendet werden, um statisch aufgelösten generischen Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b1f0d-156">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="b1f0d-157">Weitere Informationen finden Sie unter [Inline Funktionen](./functions/inline-functions.md) und [statisch aufgelöste Typparameter](./generics/statically-resolved-type-parameters.md).</span><span class="sxs-lookup"><span data-stu-id="b1f0d-157">For more information, see [Inline Functions](./functions/inline-functions.md) and [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1f0d-158">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1f0d-158">See also</span></span>

- [<span data-ttu-id="b1f0d-159">Mitglieder</span><span class="sxs-lookup"><span data-stu-id="b1f0d-159">Members</span></span>](./members/index.md)
