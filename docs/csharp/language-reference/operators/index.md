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
ms.openlocfilehash: 877992227df417badf7322be7f9be79bf7256e69
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59308652"
---
# <a name="c-operators"></a><span data-ttu-id="c7fe2-102">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="c7fe2-102">C# operators</span></span>

<span data-ttu-id="c7fe2-103">C# bietet viele Operatoren, bei denen es sich um Symbole handelt, die angeben, welche Operationen (Mathematik, Indizierung, Funktionsaufruf usw.) in einem Ausdruck ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="c7fe2-104">Sie können viele Operatoren [überladen](../../programming-guide/statements-expressions-operators/overloadable-operators.md), um ihre Bedeutung zu ändern, wenn sie auf einen benutzerdefinierten Typ angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-104">You can [overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>

<span data-ttu-id="c7fe2-105">Operationen mit Ganzzahltypen (wie `==`, `!=`, `<`, `>`, `&`, `|`) sind grundsätzlich auch für Aufzählungstypen (`enum`) zulässig.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>

<span data-ttu-id="c7fe2-106">Die folgenden Abschnitte listen die C#-Operatoren auf, und zwar von der höchsten zur niedrigsten Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="c7fe2-107">Die Operatoren in jedem Abschnitt verwenden die gleiche Rangfolgenebene.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-107">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="c7fe2-108">Primäre Operatoren</span><span class="sxs-lookup"><span data-stu-id="c7fe2-108">Primary operators</span></span>

<span data-ttu-id="c7fe2-109">Hierbei handelt es sich um die höchsten Rangfolgenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-109">These are the highest precedence operators.</span></span>

<span data-ttu-id="c7fe2-110">[x.y](member-access-operator.md) – Memberzugriff.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-110">[x.y](member-access-operator.md) – member access.</span></span>

<span data-ttu-id="c7fe2-111">[x?.y](null-conditional-operators.md) – nullbedingter Memberzugriff.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-111">[x?.y](null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="c7fe2-112">Gibt `null` zurück, wenn der linke Operand `null` ist.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="c7fe2-113">[x?[y]](null-conditional-operators.md) – nullbedingter Indexzugriff.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-113">[x?[y]](null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="c7fe2-114">Gibt `null` zurück, wenn der linke Operand `null` ist.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="c7fe2-115">[f(x)](invocation-operator.md) – Funktionsaufruf.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-115">[f(x)](invocation-operator.md) – function invocation.</span></span>

<span data-ttu-id="c7fe2-116">[a&#91;x&#93;](index-operator.md) – Aggregatobjektindizierung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-116">[a&#91;x&#93;](index-operator.md) – aggregate object indexing.</span></span>

<span data-ttu-id="c7fe2-117">[x++](arithmetic-operators.md#increment-operator-) – Postfixinkrement.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-117">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="c7fe2-118">Gibt den Wert von x zurück und aktualisiert dann den Speicherort mit dem Wert von x, der eins größer ist (für gewöhnlich wird die Ganzzahl 1 addiert).</span><span class="sxs-lookup"><span data-stu-id="c7fe2-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="c7fe2-119">[x--](arithmetic-operators.md#decrement-operator---) – Postfixdekrement.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-119">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="c7fe2-120">Gibt den Wert von x zurück und aktualisiert dann den Speicherort mit dem Wert von x, der eins kleiner ist (für gewöhnlich wird die Ganzzahl 1 subtrahiert).</span><span class="sxs-lookup"><span data-stu-id="c7fe2-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="c7fe2-121">[new](../keywords/new-operator.md) – Typinstanziierung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-121">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="c7fe2-122">[typeof](../keywords/typeof.md): Gibt das den Operanden repräsentierende Objekt <xref:System.Type> zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-122">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="c7fe2-123">[checked](../keywords/checked.md) – Aktiviert die Überlaufprüfung für Ganzzahloperationen.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-123">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="c7fe2-124">[unchecked](../keywords/unchecked.md) – Deaktiviert die Überlaufprüfung für Ganzzahloperationen.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-124">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="c7fe2-125">Dies ist das Standardverhalten für den Compiler.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-125">This is the default compiler behavior.</span></span>

<span data-ttu-id="c7fe2-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md): erzeugt den Standardwert des Typs T.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="c7fe2-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – Deklariert eine Delegatinstanz und gibt sie zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="c7fe2-128">[sizeof](../keywords/sizeof.md) – Gibt die Größe des Typoperanden in Byte zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-128">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="c7fe2-129">[->](dereference-operator.md) – Mit Memberzugriff kombinierte Zeigerdereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-129">[->](dereference-operator.md) – pointer dereferencing combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="c7fe2-130">Unäre Operatoren</span><span class="sxs-lookup"><span data-stu-id="c7fe2-130">Unary operators</span></span>

<span data-ttu-id="c7fe2-131">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-132">[+x](addition-operator.md) – Gibt den Wert von x zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-132">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="c7fe2-133">[-x](subtraction-operator.md) – Numerische Negation.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-133">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="c7fe2-134">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logische Negation.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-134">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="c7fe2-135">[~x](bitwise-complement-operator.md) – Bitweises Komplement.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-135">[~x](bitwise-complement-operator.md) – bitwise complement.</span></span>

<span data-ttu-id="c7fe2-136">[++x](arithmetic-operators.md#increment-operator-) – Präfixinkrement.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-136">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="c7fe2-137">Gibt den Wert von x nach dem Aktualisieren des Speicherorts mit dem Wert von x zurück, der eins größer ist (für gewöhnlich wird die Ganzzahl 1 addiert).</span><span class="sxs-lookup"><span data-stu-id="c7fe2-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="c7fe2-138">[--x](arithmetic-operators.md#decrement-operator---) – Präfixdekrement.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-138">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="c7fe2-139">Gibt den Wert von x nach dem Aktualisieren des Speicherorts mit dem Wert von x zurück, der eins kleiner ist (für gewöhnlich wird die ganze Zahl 1 subtrahiert).</span><span class="sxs-lookup"><span data-stu-id="c7fe2-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="c7fe2-140">[(T)x](invocation-operator.md) – Typumwandlung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-140">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="c7fe2-141">[await](../keywords/await.md) – Wartet auf `Task`.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-141">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="c7fe2-142">[&x](and-operator.md) – Adresse von.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-142">[&x](and-operator.md) – address of.</span></span>

<span data-ttu-id="c7fe2-143">[\*x](multiplication-operator.md) – Dereferenzierung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-143">[\*x](multiplication-operator.md) – dereferencing.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="c7fe2-144">Multiplikative Operatoren</span><span class="sxs-lookup"><span data-stu-id="c7fe2-144">Multiplicative operators</span></span>

<span data-ttu-id="c7fe2-145">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-145">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-146">[x \* y](arithmetic-operators.md#multiplication-operator-) – Multiplikation.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-146">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="c7fe2-147">[x / y](arithmetic-operators.md#division-operator-) – Division.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-147">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="c7fe2-148">Wenn es sich bei den Operanden um Ganzzahlen handelt, ist das Ergebnis eine Ganzzahl, die in Richtung 0 abgeschnitten wird (beispielsweise `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="c7fe2-148">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="c7fe2-149">[x % y](arithmetic-operators.md#remainder-operator-) – Restwert.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-149">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="c7fe2-150">Wenn es sich bei den Operanden um Ganzzahlen handelt, wird dadurch der Rest der Division x durch y zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-150">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="c7fe2-151">Wenn `q = x / y` und `r = x % y`, dann `x = q * y + r`.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-151">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="c7fe2-152">Additive Operatoren</span><span class="sxs-lookup"><span data-stu-id="c7fe2-152">Additive operators</span></span>

<span data-ttu-id="c7fe2-153">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-153">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-154">[x + y](arithmetic-operators.md#addition-operator-) – Addition.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-154">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="c7fe2-155">[x – y](arithmetic-operators.md#subtraction-operator--) – Subtraktion.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-155">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="c7fe2-156">Schiebeoperatoren</span><span class="sxs-lookup"><span data-stu-id="c7fe2-156">Shift operators</span></span>

<span data-ttu-id="c7fe2-157">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-157">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-158">[x <\<  y](left-shift-operator.md) – Verschiebt Bits nach links und füllt sie mit Null auf der rechten Seite auf.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-158">[x <\<  y](left-shift-operator.md) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="c7fe2-159">[x >> y](right-shift-operator.md) – Verschiebt Bits nach rechts.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-159">[x >> y](right-shift-operator.md) – shift bits right.</span></span> <span data-ttu-id="c7fe2-160">Wenn der linke Operand `int` oder `long` ist, werden die linken Bits mit dem Vorzeichenbit gefüllt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-160">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="c7fe2-161">Wenn der linke Operand `uint` oder `ulong` ist, werden die linken Bits mit Null gefüllt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-161">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="c7fe2-162">Relationale und Typtestoperatoren</span><span class="sxs-lookup"><span data-stu-id="c7fe2-162">Relational and type-testing operators</span></span>

<span data-ttu-id="c7fe2-163">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-163">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-164">[x \< y](less-than-operator.md) – Kleiner als (wahr, wenn x kleiner als y ist).</span><span class="sxs-lookup"><span data-stu-id="c7fe2-164">[x \< y](less-than-operator.md) – less than (true if x is less than y).</span></span>

<span data-ttu-id="c7fe2-165">[x > y](greater-than-operator.md) – Größer als (wahr, wenn x größer als y ist).</span><span class="sxs-lookup"><span data-stu-id="c7fe2-165">[x > y](greater-than-operator.md) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="c7fe2-166">[x \<= y](less-than-equal-operator.md) – Ist kleiner oder gleich.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-166">[x \<= y](less-than-equal-operator.md) – less than or equal to.</span></span>

<span data-ttu-id="c7fe2-167">[x >= y](greater-than-equal-operator.md) – Ist größer gleich.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-167">[x >= y](greater-than-equal-operator.md) – greater than or equal to.</span></span>

<span data-ttu-id="c7fe2-168">[is](../keywords/is.md) – Typkompatibilität.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-168">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="c7fe2-169">Gibt TRUE zurück, wenn der ausgewertete linke Operand in den im rechten Operanden (ein statischer Typ) angegebenen Typ umgewandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-169">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="c7fe2-170">[as](../keywords/as.md) – Typkonvertierung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-170">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="c7fe2-171">Gibt die Umwandlung des linken Operanden zum durch den rechten Operanden (ein statischer Typ) angegebenen Typ zurück, `as` gibt jedoch `null` zurück, wobei `(T)x` eine Auslösung ausgeben würde.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-171">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="c7fe2-172">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="c7fe2-172">Equality operators</span></span>

<span data-ttu-id="c7fe2-173">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-173">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-174">[x == y](equality-operators.md#equality-operator-) – Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-174">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="c7fe2-175">Standardmäßig wird für Verweistypen, die nicht `string` entsprechen, diese Verweisübereinstimmung (Identitätstest) zurückgeben</span><span class="sxs-lookup"><span data-stu-id="c7fe2-175">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="c7fe2-176">Typen können `==` jedoch überladen. Wenn Sie also vorhaben, die Identität zu testen, sollten Sie möglichst die `ReferenceEquals`-Methode für `object` verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-176">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="c7fe2-177">[x != y](equality-operators.md#inequality-operator-) – ungleich.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-177">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="c7fe2-178">Siehe hierzu den Kommentar für `==`.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-178">See comment for `==`.</span></span> <span data-ttu-id="c7fe2-179">Wenn ein Typ `==` überlädt, muss er `!=` überladen.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-179">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="c7fe2-180">Logischer AND-Operator</span><span class="sxs-lookup"><span data-stu-id="c7fe2-180">Logical AND operator</span></span>

<span data-ttu-id="c7fe2-181">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-181">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-182">[x & y](and-operator.md) – logisches oder bitweises AND.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-182">[x & y](and-operator.md) – logical or bitwise AND.</span></span> <span data-ttu-id="c7fe2-183">Sie können dies im Allgemeinen mit Ganzzahltypen und `enum`-Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-183">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="c7fe2-184">Logischer XOR-Operator</span><span class="sxs-lookup"><span data-stu-id="c7fe2-184">Logical XOR operator</span></span>

<span data-ttu-id="c7fe2-185">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-185">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-186">[x ^ y](xor-operator.md) – logisches oder bitweises XOR.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-186">[x ^ y](xor-operator.md) – logical or bitwise XOR.</span></span> <span data-ttu-id="c7fe2-187">Sie können dies im Allgemeinen mit Ganzzahltypen und `enum`-Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-187">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="c7fe2-188">Logischer OR-Operator (||)</span><span class="sxs-lookup"><span data-stu-id="c7fe2-188">Logical OR operator</span></span>

<span data-ttu-id="c7fe2-189">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-190">[x &#124; y](or-operator.md) – logisches oder bitweises OR.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-190">[x &#124; y](or-operator.md) – logical or bitwise OR.</span></span> <span data-ttu-id="c7fe2-191">Sie können dies im Allgemeinen mit Ganzzahltypen und `enum`-Typen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-191">You can generally use this with integer types and `enum` types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="c7fe2-192">Bedingter AND-Operator</span><span class="sxs-lookup"><span data-stu-id="c7fe2-192">Conditional AND operator</span></span>

<span data-ttu-id="c7fe2-193">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-193">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-194">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logisches AND.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-194">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="c7fe2-195">Wenn der erste Operand FALSE ist, wertet C# den zweiten Operand nicht aus.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-195">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="c7fe2-196">Bedingter OR-Operator</span><span class="sxs-lookup"><span data-stu-id="c7fe2-196">Conditional OR operator</span></span>

<span data-ttu-id="c7fe2-197">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-197">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-198">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – Logisches OR.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-198">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="c7fe2-199">Wenn der erste Operand TRUE ist, wertet C# den zweiten Operand nicht aus.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-199">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="c7fe2-200">Nullzusammensetzungsoperator</span><span class="sxs-lookup"><span data-stu-id="c7fe2-200">Null-coalescing operator</span></span>

<span data-ttu-id="c7fe2-201">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-201">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-202">[x ?? y](null-coalescing-operator.md) – Gibt `x` zurück, sofern es Nicht-`null` ist; ansonsten wird `y` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-202">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="c7fe2-203">Bedingter Operator</span><span class="sxs-lookup"><span data-stu-id="c7fe2-203">Conditional operator</span></span>

<span data-ttu-id="c7fe2-204">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-204">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-205">[t ? x : y](conditional-operator.md): Wenn der Test `t` TRUE ist, wird `x` ausgewertet und zurückgegeben, ansonsten wird `y` ausgewertet und zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-205">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="c7fe2-206">Zuweisung- und Lambdaoperatoren</span><span class="sxs-lookup"><span data-stu-id="c7fe2-206">Assignment and Lambda operators</span></span>

<span data-ttu-id="c7fe2-207">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-207">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="c7fe2-208">[x = y](assignment-operator.md) – Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-208">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="c7fe2-209">[x += y](addition-assignment-operator.md) – Inkrement.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-209">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="c7fe2-210">Fügen Sie dem Wert `x` den Wert `y` hinzu. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-210">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="c7fe2-211">Wenn `x` ein `event` festlegt, muss `y` eine entsprechende Funktion sein, die C# als ein Eventhandler hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-211">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="c7fe2-212">[x -= y](subtraction-assignment-operator.md) – Dekrement.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-212">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="c7fe2-213">Subtrahieren Sie vom Wert `x` den Wert `y`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-213">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="c7fe2-214">Wenn `x` ein `event` festlegt, muss `y` eine entsprechende Funktion sein, die C# als ein Eventhandler entfernt.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-214">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler</span></span>

<span data-ttu-id="c7fe2-215">[x \*= y](multiplication-assignment-operator.md) – Multiplikationszuweisung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-215">[x \*= y](multiplication-assignment-operator.md) – multiplication assignment.</span></span> <span data-ttu-id="c7fe2-216">Multiplizieren Sie den Wert `y` mit dem Wert `x`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-216">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="c7fe2-217">[x /= y](arithmetic-operators.md#compound-assignment) – Divisionszuweisung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-217">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="c7fe2-218">Dividieren Sie den Wert `x` durch den Wert `y`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-218">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="c7fe2-219">[x %= y](arithmetic-operators.md#compound-assignment) – Restwertzuweisung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-219">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="c7fe2-220">Dividieren Sie den Wert `x` durch den Wert `y`. Speichern Sie den Rest in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-220">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="c7fe2-221">[x &= y](and-assignment-operator.md) – AND-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-221">[x &= y](and-assignment-operator.md) – AND assignment.</span></span> <span data-ttu-id="c7fe2-222">Führen Sie eine AND-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-222">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="c7fe2-223">[x &#124;= y](or-assignment-operator.md) – OR-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-223">[x &#124;= y](or-assignment-operator.md) – OR assignment.</span></span> <span data-ttu-id="c7fe2-224">Führen Sie eine OR-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-224">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="c7fe2-225">[x ^= y](xor-assignment-operator.md) – XOR-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-225">[x ^= y](xor-assignment-operator.md) – XOR assignment.</span></span> <span data-ttu-id="c7fe2-226">Führen Sie eine XOR-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-226">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="c7fe2-227">[x <<= y](left-shift-assignment-operator.md) – Linksschiebezuweisung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-227">[x <<= y](left-shift-assignment-operator.md) – left-shift assignment.</span></span> <span data-ttu-id="c7fe2-228">Verschieben Sie den Wert von `x` nach links um `y` Stellen. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-228">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="c7fe2-229">[x >>= y](right-shift-assignment-operator.md) – Rechtsschiebezuweisung.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-229">[x >>= y](right-shift-assignment-operator.md) – right-shift assignment.</span></span> <span data-ttu-id="c7fe2-230">Verschieben Sie den Wert von `x` nach rechts um `y` Stellen. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-230">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="c7fe2-231">[=>](lambda-operator.md) – Lambdadeklaration.</span><span class="sxs-lookup"><span data-stu-id="c7fe2-231">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7fe2-232">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7fe2-232">See also</span></span>

- [<span data-ttu-id="c7fe2-233">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c7fe2-233">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c7fe2-234">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c7fe2-234">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c7fe2-235">C#</span><span class="sxs-lookup"><span data-stu-id="c7fe2-235">C#</span></span>](../../index.md)
- [<span data-ttu-id="c7fe2-236">Überladbare Operatoren</span><span class="sxs-lookup"><span data-stu-id="c7fe2-236">Overloadable Operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="c7fe2-237">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c7fe2-237">C# Keywords</span></span>](../keywords/index.md)