---
title: C#-Operatoren
ms.date: 04/04/2018
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: f4267caeb6301950b9f6a8b9545a47b9f48e7920
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61689813"
---
# <a name="c-operators"></a><span data-ttu-id="a47e3-102">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="a47e3-102">C# operators</span></span>

<span data-ttu-id="a47e3-103">C# bietet viele Operatoren, bei denen es sich um Symbole handelt, die angeben, welche Operationen (Mathematik, Indizierung, Funktionsaufruf usw.) in einem Ausdruck ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a47e3-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="a47e3-104">Sie können viele Operatoren [überladen](../../programming-guide/statements-expressions-operators/overloadable-operators.md), um ihre Bedeutung zu ändern, wenn sie auf einen benutzerdefinierten Typ angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a47e3-104">You can [overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>

<span data-ttu-id="a47e3-105">Operationen mit Ganzzahltypen (wie `==`, `!=`, `<`, `>`, `&`, `|`) sind grundsätzlich auch für Aufzählungstypen (`enum`) zulässig.</span><span class="sxs-lookup"><span data-stu-id="a47e3-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>

<span data-ttu-id="a47e3-106">Die folgenden Abschnitte listen die C#-Operatoren auf, und zwar von der höchsten zur niedrigsten Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="a47e3-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="a47e3-107">Die Operatoren in jedem Abschnitt verwenden die gleiche Rangfolgenebene.</span><span class="sxs-lookup"><span data-stu-id="a47e3-107">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="a47e3-108">Primäre Operatoren</span><span class="sxs-lookup"><span data-stu-id="a47e3-108">Primary operators</span></span>

<span data-ttu-id="a47e3-109">Hierbei handelt es sich um die höchsten Rangfolgenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="a47e3-109">These are the highest precedence operators.</span></span>

<span data-ttu-id="a47e3-110">[x.y](member-access-operator.md) – Memberzugriff.</span><span class="sxs-lookup"><span data-stu-id="a47e3-110">[x.y](member-access-operator.md) – member access.</span></span>

<span data-ttu-id="a47e3-111">[x?.y](null-conditional-operators.md) – nullbedingter Memberzugriff.</span><span class="sxs-lookup"><span data-stu-id="a47e3-111">[x?.y](null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="a47e3-112">Gibt `null` zurück, wenn der linke Operand `null` ist.</span><span class="sxs-lookup"><span data-stu-id="a47e3-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="a47e3-113">[x?[y]](null-conditional-operators.md) – nullbedingter Indexzugriff.</span><span class="sxs-lookup"><span data-stu-id="a47e3-113">[x?[y]](null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="a47e3-114">Gibt `null` zurück, wenn der linke Operand `null` ist.</span><span class="sxs-lookup"><span data-stu-id="a47e3-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="a47e3-115">[f(x)](invocation-operator.md) – Funktionsaufruf.</span><span class="sxs-lookup"><span data-stu-id="a47e3-115">[f(x)](invocation-operator.md) – function invocation.</span></span>

<span data-ttu-id="a47e3-116">[a&#91;x&#93;](index-operator.md) – Aggregatobjektindizierung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-116">[a&#91;x&#93;](index-operator.md) – aggregate object indexing.</span></span>

<span data-ttu-id="a47e3-117">[x++](arithmetic-operators.md#increment-operator-) – Postfixinkrement.</span><span class="sxs-lookup"><span data-stu-id="a47e3-117">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="a47e3-118">Gibt den Wert von x zurück und aktualisiert dann den Speicherort mit dem Wert von x, der eins größer ist (für gewöhnlich wird die Ganzzahl 1 addiert).</span><span class="sxs-lookup"><span data-stu-id="a47e3-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="a47e3-119">[x--](arithmetic-operators.md#decrement-operator---) – Postfixdekrement.</span><span class="sxs-lookup"><span data-stu-id="a47e3-119">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="a47e3-120">Gibt den Wert von x zurück und aktualisiert dann den Speicherort mit dem Wert von x, der eins kleiner ist (für gewöhnlich wird die Ganzzahl 1 subtrahiert).</span><span class="sxs-lookup"><span data-stu-id="a47e3-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="a47e3-121">[new](../keywords/new-operator.md) – Typinstanziierung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-121">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="a47e3-122">[typeof](../keywords/typeof.md): Gibt das den Operanden repräsentierende Objekt <xref:System.Type> zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-122">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="a47e3-123">[checked](../keywords/checked.md) – Aktiviert die Überlaufprüfung für Ganzzahloperationen.</span><span class="sxs-lookup"><span data-stu-id="a47e3-123">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="a47e3-124">[unchecked](../keywords/unchecked.md) – Deaktiviert die Überlaufprüfung für Ganzzahloperationen.</span><span class="sxs-lookup"><span data-stu-id="a47e3-124">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="a47e3-125">Dies ist das Standardverhalten für den Compiler.</span><span class="sxs-lookup"><span data-stu-id="a47e3-125">This is the default compiler behavior.</span></span>

<span data-ttu-id="a47e3-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md): erzeugt den Standardwert des Typs T.</span><span class="sxs-lookup"><span data-stu-id="a47e3-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="a47e3-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – Deklariert eine Delegatinstanz und gibt sie zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="a47e3-128">[sizeof](../keywords/sizeof.md) – Gibt die Größe des Typoperanden in Byte zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-128">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="a47e3-129">[->](dereference-operator.md) – Mit Memberzugriff kombinierte Zeigerdereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-129">[->](dereference-operator.md) – pointer dereferencing combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="a47e3-130">Unäre Operatoren</span><span class="sxs-lookup"><span data-stu-id="a47e3-130">Unary operators</span></span>

<span data-ttu-id="a47e3-131">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-132">[+x](addition-operator.md) – Gibt den Wert von x zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-132">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="a47e3-133">[-x](subtraction-operator.md) – Numerische Negation.</span><span class="sxs-lookup"><span data-stu-id="a47e3-133">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="a47e3-134">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logische Negation.</span><span class="sxs-lookup"><span data-stu-id="a47e3-134">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="a47e3-135">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – Bitweises Komplement.</span><span class="sxs-lookup"><span data-stu-id="a47e3-135">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – bitwise complement.</span></span>

<span data-ttu-id="a47e3-136">[++x](arithmetic-operators.md#increment-operator-) – Präfixinkrement.</span><span class="sxs-lookup"><span data-stu-id="a47e3-136">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="a47e3-137">Gibt den Wert von x nach dem Aktualisieren des Speicherorts mit dem Wert von x zurück, der eins größer ist (für gewöhnlich wird die Ganzzahl 1 addiert).</span><span class="sxs-lookup"><span data-stu-id="a47e3-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="a47e3-138">[--x](arithmetic-operators.md#decrement-operator---) – Präfixdekrement.</span><span class="sxs-lookup"><span data-stu-id="a47e3-138">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="a47e3-139">Gibt den Wert von x nach dem Aktualisieren des Speicherorts mit dem Wert von x zurück, der eins kleiner ist (für gewöhnlich wird die ganze Zahl 1 subtrahiert).</span><span class="sxs-lookup"><span data-stu-id="a47e3-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="a47e3-140">[(T)x](invocation-operator.md) – Typumwandlung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-140">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="a47e3-141">[await](../keywords/await.md) – Wartet auf `Task`.</span><span class="sxs-lookup"><span data-stu-id="a47e3-141">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="a47e3-142">[&x](and-operator.md) – Adresse von.</span><span class="sxs-lookup"><span data-stu-id="a47e3-142">[&x](and-operator.md) – address of.</span></span>

<span data-ttu-id="a47e3-143">[\*x](multiplication-operator.md) – Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-143">[\*x](multiplication-operator.md) – dereferencing.</span></span>

<span data-ttu-id="a47e3-144">Der [true-Operator](../keywords/true-false-operators.md) gibt den [bool](../keywords/bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand definitiv den Wert „true“ hat.</span><span class="sxs-lookup"><span data-stu-id="a47e3-144">[true operator](../keywords/true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span>

<span data-ttu-id="a47e3-145">Der [false-Operator](../keywords/true-false-operators.md) gibt den [bool](../keywords/bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand definitiv den Wert „false“ hat.</span><span class="sxs-lookup"><span data-stu-id="a47e3-145">[false operator](../keywords/true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely false.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="a47e3-146">Multiplikative Operatoren</span><span class="sxs-lookup"><span data-stu-id="a47e3-146">Multiplicative operators</span></span>

<span data-ttu-id="a47e3-147">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-147">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-148">[x \* y](arithmetic-operators.md#multiplication-operator-) – Multiplikation.</span><span class="sxs-lookup"><span data-stu-id="a47e3-148">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="a47e3-149">[x / y](arithmetic-operators.md#division-operator-) – Division.</span><span class="sxs-lookup"><span data-stu-id="a47e3-149">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="a47e3-150">Wenn es sich bei den Operanden um Ganzzahlen handelt, ist das Ergebnis eine Ganzzahl, die in Richtung 0 abgeschnitten wird (beispielsweise `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="a47e3-150">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="a47e3-151">[x % y](arithmetic-operators.md#remainder-operator-) – Restwert.</span><span class="sxs-lookup"><span data-stu-id="a47e3-151">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="a47e3-152">Wenn es sich bei den Operanden um Ganzzahlen handelt, wird dadurch der Rest der Division x durch y zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a47e3-152">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="a47e3-153">Wenn `q = x / y` und `r = x % y`, dann `x = q * y + r`.</span><span class="sxs-lookup"><span data-stu-id="a47e3-153">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="a47e3-154">Additive Operatoren</span><span class="sxs-lookup"><span data-stu-id="a47e3-154">Additive operators</span></span>

<span data-ttu-id="a47e3-155">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-155">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-156">[x + y](arithmetic-operators.md#addition-operator-) – Addition.</span><span class="sxs-lookup"><span data-stu-id="a47e3-156">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="a47e3-157">[x – y](arithmetic-operators.md#subtraction-operator--) – Subtraktion.</span><span class="sxs-lookup"><span data-stu-id="a47e3-157">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="a47e3-158">Schiebeoperatoren</span><span class="sxs-lookup"><span data-stu-id="a47e3-158">Shift operators</span></span>

<span data-ttu-id="a47e3-159">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-159">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-160">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – Verschiebt Bits nach links und füllt sie mit Null auf der rechten Seite auf.</span><span class="sxs-lookup"><span data-stu-id="a47e3-160">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="a47e3-161">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – Verschiebt Bits nach rechts.</span><span class="sxs-lookup"><span data-stu-id="a47e3-161">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – shift bits right.</span></span> <span data-ttu-id="a47e3-162">Wenn der linke Operand `int` oder `long` ist, werden die linken Bits mit dem Vorzeichenbit gefüllt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-162">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="a47e3-163">Wenn der linke Operand `uint` oder `ulong` ist, werden die linken Bits mit Null gefüllt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-163">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="a47e3-164">Relationale und Typtestoperatoren</span><span class="sxs-lookup"><span data-stu-id="a47e3-164">Relational and type-testing operators</span></span>

<span data-ttu-id="a47e3-165">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-165">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-166">[x \< y](less-than-operator.md) – Kleiner als (wahr, wenn x kleiner als y ist).</span><span class="sxs-lookup"><span data-stu-id="a47e3-166">[x \< y](less-than-operator.md) – less than (true if x is less than y).</span></span>

<span data-ttu-id="a47e3-167">[x > y](greater-than-operator.md) – Größer als (wahr, wenn x größer als y ist).</span><span class="sxs-lookup"><span data-stu-id="a47e3-167">[x > y](greater-than-operator.md) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="a47e3-168">[x \<= y](less-than-equal-operator.md) – Ist kleiner oder gleich.</span><span class="sxs-lookup"><span data-stu-id="a47e3-168">[x \<= y](less-than-equal-operator.md) – less than or equal to.</span></span>

<span data-ttu-id="a47e3-169">[x >= y](greater-than-equal-operator.md) – Ist größer gleich.</span><span class="sxs-lookup"><span data-stu-id="a47e3-169">[x >= y](greater-than-equal-operator.md) – greater than or equal to.</span></span>

<span data-ttu-id="a47e3-170">[is](../keywords/is.md) – Typkompatibilität.</span><span class="sxs-lookup"><span data-stu-id="a47e3-170">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="a47e3-171">Gibt TRUE zurück, wenn der ausgewertete linke Operand in den im rechten Operanden (ein statischer Typ) angegebenen Typ umgewandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a47e3-171">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="a47e3-172">[as](../keywords/as.md) – Typkonvertierung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-172">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="a47e3-173">Gibt die Umwandlung des linken Operanden zum durch den rechten Operanden (ein statischer Typ) angegebenen Typ zurück, `as` gibt jedoch `null` zurück, wobei `(T)x` eine Auslösung ausgeben würde.</span><span class="sxs-lookup"><span data-stu-id="a47e3-173">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="a47e3-174">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="a47e3-174">Equality operators</span></span>

<span data-ttu-id="a47e3-175">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-175">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-176">[x == y](equality-operators.md#equality-operator-) – Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="a47e3-176">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="a47e3-177">Standardmäßig wird für Verweistypen, die nicht `string` entsprechen, diese Verweisübereinstimmung (Identitätstest) zurückgeben</span><span class="sxs-lookup"><span data-stu-id="a47e3-177">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="a47e3-178">Typen können `==` jedoch überladen. Wenn Sie also vorhaben, die Identität zu testen, sollten Sie möglichst die `ReferenceEquals`-Methode für `object` verwenden.</span><span class="sxs-lookup"><span data-stu-id="a47e3-178">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="a47e3-179">[x != y](equality-operators.md#inequality-operator-) – ungleich.</span><span class="sxs-lookup"><span data-stu-id="a47e3-179">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="a47e3-180">Siehe hierzu den Kommentar für `==`.</span><span class="sxs-lookup"><span data-stu-id="a47e3-180">See comment for `==`.</span></span> <span data-ttu-id="a47e3-181">Wenn ein Typ `==` überlädt, muss er `!=` überladen.</span><span class="sxs-lookup"><span data-stu-id="a47e3-181">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="a47e3-182">Logischer AND-Operator</span><span class="sxs-lookup"><span data-stu-id="a47e3-182">Logical AND operator</span></span>

<span data-ttu-id="a47e3-183">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-183">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-184">`x & y` –[logische AND](boolean-logical-operators.md#logical-and-operator-)-Operationen für die `bool`-Operanden oder [bitweise logische AND](bitwise-and-shift-operators.md#logical-and-operator-)-Operationen für die Operanden von integralen Typen.</span><span class="sxs-lookup"><span data-stu-id="a47e3-184">`x & y` – [logical AND](boolean-logical-operators.md#logical-and-operator-) for the `bool` operands or [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) for the operands of the integral types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="a47e3-185">Logischer XOR-Operator</span><span class="sxs-lookup"><span data-stu-id="a47e3-185">Logical XOR operator</span></span>

<span data-ttu-id="a47e3-186">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-186">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-187">`x ^ y` –[logische XOR](boolean-logical-operators.md#logical-exclusive-or-operator-)-Operationen für die `bool`-Operanden oder [bitweise logische XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)-Operationen für die Operanden von integralen Typen.</span><span class="sxs-lookup"><span data-stu-id="a47e3-187">`x ^ y` – [logical XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) for the `bool` operands or [bitwise logical XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) for the operands of the integral types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="a47e3-188">Logischer OR-Operator (||)</span><span class="sxs-lookup"><span data-stu-id="a47e3-188">Logical OR operator</span></span>

<span data-ttu-id="a47e3-189">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-190">`x | y` –[logische OR](boolean-logical-operators.md#logical-or-operator-)-Operationen für die `bool`-Operanden oder [bitweise logische OR](bitwise-and-shift-operators.md#logical-or-operator-)-Operationen für die Operanden von integralen Typen.</span><span class="sxs-lookup"><span data-stu-id="a47e3-190">`x | y` – [logical OR](boolean-logical-operators.md#logical-or-operator-) for the `bool` operands or [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) for the operands of the integral types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="a47e3-191">Bedingter AND-Operator</span><span class="sxs-lookup"><span data-stu-id="a47e3-191">Conditional AND operator</span></span>

<span data-ttu-id="a47e3-192">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-192">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-193">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logisches AND.</span><span class="sxs-lookup"><span data-stu-id="a47e3-193">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="a47e3-194">Wenn der erste Operand FALSE ist, wertet C# den zweiten Operand nicht aus.</span><span class="sxs-lookup"><span data-stu-id="a47e3-194">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="a47e3-195">Bedingter OR-Operator</span><span class="sxs-lookup"><span data-stu-id="a47e3-195">Conditional OR operator</span></span>

<span data-ttu-id="a47e3-196">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-196">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-197">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – Logisches OR.</span><span class="sxs-lookup"><span data-stu-id="a47e3-197">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="a47e3-198">Wenn der erste Operand TRUE ist, wertet C# den zweiten Operand nicht aus.</span><span class="sxs-lookup"><span data-stu-id="a47e3-198">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="a47e3-199">Nullzusammensetzungsoperator</span><span class="sxs-lookup"><span data-stu-id="a47e3-199">Null-coalescing operator</span></span>

<span data-ttu-id="a47e3-200">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-200">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-201">[x ?? y](null-coalescing-operator.md) – Gibt `x` zurück, sofern es Nicht-`null` ist; ansonsten wird `y` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a47e3-201">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="a47e3-202">Bedingter Operator</span><span class="sxs-lookup"><span data-stu-id="a47e3-202">Conditional operator</span></span>

<span data-ttu-id="a47e3-203">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-203">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-204">[t ? x : y](conditional-operator.md): Wenn der Test `t` TRUE ist, wird `x` ausgewertet und zurückgegeben, ansonsten wird `y` ausgewertet und zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a47e3-204">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="a47e3-205">Zuweisung- und Lambdaoperatoren</span><span class="sxs-lookup"><span data-stu-id="a47e3-205">Assignment and Lambda operators</span></span>

<span data-ttu-id="a47e3-206">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-206">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="a47e3-207">[x = y](assignment-operator.md) – Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-207">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="a47e3-208">[x += y](addition-assignment-operator.md) – Inkrement.</span><span class="sxs-lookup"><span data-stu-id="a47e3-208">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="a47e3-209">Fügen Sie dem Wert `x` den Wert `y` hinzu. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-209">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="a47e3-210">Wenn `x` ein `event` festlegt, muss `y` eine entsprechende Funktion sein, die C# als ein Eventhandler hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-210">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="a47e3-211">[x -= y](subtraction-assignment-operator.md) – Dekrement.</span><span class="sxs-lookup"><span data-stu-id="a47e3-211">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="a47e3-212">Subtrahieren Sie vom Wert `x` den Wert `y`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-212">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="a47e3-213">Wenn `x` ein `event` festlegt, muss `y` eine entsprechende Funktion sein, die C# als ein Eventhandler entfernt.</span><span class="sxs-lookup"><span data-stu-id="a47e3-213">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler.</span></span>

<span data-ttu-id="a47e3-214">[x \*= y](arithmetic-operators.md#compound-assignment) – Multiplikationszuweisung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-214">[x \*= y](arithmetic-operators.md#compound-assignment) – multiplication assignment.</span></span> <span data-ttu-id="a47e3-215">Multiplizieren Sie den Wert `y` mit dem Wert `x`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-215">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a47e3-216">[x /= y](arithmetic-operators.md#compound-assignment) – Divisionszuweisung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-216">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="a47e3-217">Dividieren Sie den Wert `x` durch den Wert `y`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-217">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a47e3-218">[x %= y](arithmetic-operators.md#compound-assignment) – Restwertzuweisung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-218">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="a47e3-219">Dividieren Sie den Wert `x` durch den Wert `y`. Speichern Sie den Rest in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-219">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="a47e3-220">[x &= y](boolean-logical-operators.md#compound-assignment) – AND-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-220">[x &= y](boolean-logical-operators.md#compound-assignment) – AND assignment.</span></span> <span data-ttu-id="a47e3-221">Führen Sie eine AND-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-221">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a47e3-222">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-222">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR assignment.</span></span> <span data-ttu-id="a47e3-223">Führen Sie eine OR-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-223">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a47e3-224">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-224">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR assignment.</span></span> <span data-ttu-id="a47e3-225">Führen Sie eine XOR-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-225">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a47e3-226">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – Linksschiebezuweisung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-226">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – left-shift assignment.</span></span> <span data-ttu-id="a47e3-227">Verschieben Sie den Wert von `x` nach links um `y` Stellen. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-227">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a47e3-228">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – Rechtsschiebezuweisung.</span><span class="sxs-lookup"><span data-stu-id="a47e3-228">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – right-shift assignment.</span></span> <span data-ttu-id="a47e3-229">Verschieben Sie den Wert von `x` nach rechts um `y` Stellen. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="a47e3-229">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="a47e3-230">[=>](lambda-operator.md) – Lambdadeklaration.</span><span class="sxs-lookup"><span data-stu-id="a47e3-230">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="a47e3-231">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a47e3-231">See also</span></span>

- [<span data-ttu-id="a47e3-232">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a47e3-232">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a47e3-233">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a47e3-233">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a47e3-234">C#</span><span class="sxs-lookup"><span data-stu-id="a47e3-234">C#</span></span>](../../index.md)
- [<span data-ttu-id="a47e3-235">Überladbare Operatoren</span><span class="sxs-lookup"><span data-stu-id="a47e3-235">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="a47e3-236">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a47e3-236">C# Keywords</span></span>](../keywords/index.md)
