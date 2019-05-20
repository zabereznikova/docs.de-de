---
title: C#-Operatoren
ms.date: 04/30/2019
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
ms.openlocfilehash: 07ef96862c04b8245d8365c3d3b419d227e824c4
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65876952"
---
# <a name="c-operators"></a><span data-ttu-id="b1b74-102">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1b74-102">C# operators</span></span>

<span data-ttu-id="b1b74-103">C# bietet eine Reihe vordefinierter Operatoren, die von den integrierten Typen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="b1b74-103">C# provides a number of predefined operators supported by the built-in types.</span></span> <span data-ttu-id="b1b74-104">Beispielsweise führen [arithmetische Operatoren](arithmetic-operators.md) arithmetische Vorgänge mit Operanden von integrierten numerischen Typen durch, und [boolesche logische Operatoren](boolean-logical-operators.md) führen logische Vorgänge mit den [bool](../keywords/bool.md)-Operanden aus.</span><span class="sxs-lookup"><span data-stu-id="b1b74-104">For example, [arithmetic operators](arithmetic-operators.md) perform arithmetic operations with operands of built-in numeric types and [Boolean logical operators](boolean-logical-operators.md) perform logical operations with the [bool](../keywords/bool.md) operands.</span></span>

<span data-ttu-id="b1b74-105">Ein benutzerdefinierter Typ kann bestimmte Operatoren überladen, um das zugehörige Verhalten für die Operanden dieses Typs zu definieren.</span><span class="sxs-lookup"><span data-stu-id="b1b74-105">A user-defined type can overload certain operators to define the corresponding behavior for the operands of that type.</span></span> <span data-ttu-id="b1b74-106">Weitere Informationen finden Sie im Artikel zum Schlüsselwort [operator](../keywords/operator.md).</span><span class="sxs-lookup"><span data-stu-id="b1b74-106">For more information, see the [operator](../keywords/operator.md) keyword article.</span></span>

<span data-ttu-id="b1b74-107">Die folgenden Abschnitte listen die C#-Operatoren auf, und zwar von der höchsten zur niedrigsten Rangfolge.</span><span class="sxs-lookup"><span data-stu-id="b1b74-107">The following sections list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="b1b74-108">Die Operatoren in jedem Abschnitt verwenden die gleiche Rangfolgenebene.</span><span class="sxs-lookup"><span data-stu-id="b1b74-108">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="b1b74-109">Primäre Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1b74-109">Primary operators</span></span>

<span data-ttu-id="b1b74-110">Hierbei handelt es sich um die höchsten Rangfolgenoperatoren.</span><span class="sxs-lookup"><span data-stu-id="b1b74-110">These are the highest precedence operators.</span></span>

<span data-ttu-id="b1b74-111">[x.y](member-access-operators.md#member-access-operator-) – Memberzugriff.</span><span class="sxs-lookup"><span data-stu-id="b1b74-111">[x.y](member-access-operators.md#member-access-operator-) – member access.</span></span>

<span data-ttu-id="b1b74-112">[x?.y](member-access-operators.md#null-conditional-operators--and-) – nullbedingter Memberzugriff.</span><span class="sxs-lookup"><span data-stu-id="b1b74-112">[x?.y](member-access-operators.md#null-conditional-operators--and-) – null conditional member access.</span></span> <span data-ttu-id="b1b74-113">Gibt `null` zurück, wenn der linke Operand `null` ist.</span><span class="sxs-lookup"><span data-stu-id="b1b74-113">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="b1b74-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-) – nullbedingter Arrayelement- oder Typindexerzugriff.</span><span class="sxs-lookup"><span data-stu-id="b1b74-114">[x?[y]](member-access-operators.md#null-conditional-operators--and-) - null conditional array element or type indexer access.</span></span> <span data-ttu-id="b1b74-115">Gibt `null` zurück, wenn der linke Operand `null` ist.</span><span class="sxs-lookup"><span data-stu-id="b1b74-115">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="b1b74-116">[f(x)](member-access-operators.md#invocation-operator-) – Methodenaufruf oder Delegataufruf.</span><span class="sxs-lookup"><span data-stu-id="b1b74-116">[f(x)](member-access-operators.md#invocation-operator-) – method call or delegate invocation.</span></span>

<span data-ttu-id="b1b74-117">[a&#91;x&#93;](member-access-operators.md#indexer-operator-) – Arrayelement- oder Typindexerzugriff.</span><span class="sxs-lookup"><span data-stu-id="b1b74-117">[a&#91;x&#93;](member-access-operators.md#indexer-operator-) – array element or type indexer access.</span></span>

<span data-ttu-id="b1b74-118">[x++](arithmetic-operators.md#increment-operator-) – Postfixinkrement.</span><span class="sxs-lookup"><span data-stu-id="b1b74-118">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="b1b74-119">Gibt den Wert von x zurück und aktualisiert dann den Speicherort mit dem Wert von x, der eins größer ist (für gewöhnlich wird die Ganzzahl 1 addiert).</span><span class="sxs-lookup"><span data-stu-id="b1b74-119">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="b1b74-120">[x--](arithmetic-operators.md#decrement-operator---) – Postfixdekrement.</span><span class="sxs-lookup"><span data-stu-id="b1b74-120">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="b1b74-121">Gibt den Wert von x zurück und aktualisiert dann den Speicherort mit dem Wert von x, der eins kleiner ist (für gewöhnlich wird die Ganzzahl 1 subtrahiert).</span><span class="sxs-lookup"><span data-stu-id="b1b74-121">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="b1b74-122">[new](../keywords/new-operator.md) – Typinstanziierung.</span><span class="sxs-lookup"><span data-stu-id="b1b74-122">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="b1b74-123">[typeof](../keywords/typeof.md): Gibt das den Operanden repräsentierende Objekt <xref:System.Type> zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-123">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="b1b74-124">[checked](../keywords/checked.md) – Aktiviert die Überlaufprüfung für Ganzzahloperationen.</span><span class="sxs-lookup"><span data-stu-id="b1b74-124">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="b1b74-125">[unchecked](../keywords/unchecked.md) – Deaktiviert die Überlaufprüfung für Ganzzahloperationen.</span><span class="sxs-lookup"><span data-stu-id="b1b74-125">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="b1b74-126">Dies ist das Standardverhalten für den Compiler.</span><span class="sxs-lookup"><span data-stu-id="b1b74-126">This is the default compiler behavior.</span></span>

<span data-ttu-id="b1b74-127">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md): erzeugt den Standardwert des Typs T.</span><span class="sxs-lookup"><span data-stu-id="b1b74-127">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="b1b74-128">[nameof](../keywords/nameof.md) – Ruft den einfachen (nicht qualifizierten) Namen einer Variablen, eines Typs oder eines Members als konstante Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="b1b74-128">[nameof](../keywords/nameof.md) - obtains the simple (unqualified) name of a variable, type, or member as a constant string.</span></span>

<span data-ttu-id="b1b74-129">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – Deklariert eine Delegatinstanz und gibt sie zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-129">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="b1b74-130">[sizeof](../keywords/sizeof.md) – Gibt die Größe des Typoperanden in Byte zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-130">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="b1b74-131">[stackalloc](../keywords/stackalloc.md) – Belegt einen Speicherblock auf dem Stapel.</span><span class="sxs-lookup"><span data-stu-id="b1b74-131">[stackalloc](../keywords/stackalloc.md) - allocates a block of memory on the stack.</span></span>

<span data-ttu-id="b1b74-132">[->](pointer-related-operators.md#pointer-member-access-operator--) – Mit Memberzugriff kombinierte Zeigerdereferenzierung</span><span class="sxs-lookup"><span data-stu-id="b1b74-132">[->](pointer-related-operators.md#pointer-member-access-operator--) – pointer indirection combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="b1b74-133">Unäre Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1b74-133">Unary operators</span></span>

<span data-ttu-id="b1b74-134">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-134">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-135">[+x](addition-operator.md) – Gibt den Wert von x zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-135">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="b1b74-136">[-x](subtraction-operator.md) – Numerische Negation.</span><span class="sxs-lookup"><span data-stu-id="b1b74-136">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="b1b74-137">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logische Negation.</span><span class="sxs-lookup"><span data-stu-id="b1b74-137">[\!x](boolean-logical-operators.md#logical-negation-operator-) – logical negation.</span></span>

<span data-ttu-id="b1b74-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – Bitweises Komplement.</span><span class="sxs-lookup"><span data-stu-id="b1b74-138">[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – bitwise complement.</span></span>

<span data-ttu-id="b1b74-139">[++x](arithmetic-operators.md#increment-operator-) – Präfixinkrement.</span><span class="sxs-lookup"><span data-stu-id="b1b74-139">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="b1b74-140">Gibt den Wert von x nach dem Aktualisieren des Speicherorts mit dem Wert von x zurück, der eins größer ist (für gewöhnlich wird die Ganzzahl 1 addiert).</span><span class="sxs-lookup"><span data-stu-id="b1b74-140">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="b1b74-141">[--x](arithmetic-operators.md#decrement-operator---) – Präfixdekrement.</span><span class="sxs-lookup"><span data-stu-id="b1b74-141">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="b1b74-142">Gibt den Wert von x nach dem Aktualisieren des Speicherorts mit dem Wert von x zurück, der eins kleiner ist (für gewöhnlich wird die ganze Zahl 1 subtrahiert).</span><span class="sxs-lookup"><span data-stu-id="b1b74-142">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="b1b74-143">[(T)x](invocation-operator.md) – Typumwandlung.</span><span class="sxs-lookup"><span data-stu-id="b1b74-143">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="b1b74-144">[await](../keywords/await.md) – Wartet auf `Task`.</span><span class="sxs-lookup"><span data-stu-id="b1b74-144">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="b1b74-145">[&x](pointer-related-operators.md#address-of-operator-) – Adresse einer Variablen</span><span class="sxs-lookup"><span data-stu-id="b1b74-145">[&x](pointer-related-operators.md#address-of-operator-) – address of a variable.</span></span>

<span data-ttu-id="b1b74-146">[\*x](pointer-related-operators.md#pointer-indirection-operator-) – Zeigerdereferenzierung</span><span class="sxs-lookup"><span data-stu-id="b1b74-146">[\*x](pointer-related-operators.md#pointer-indirection-operator-) – pointer indirection, or dereference.</span></span>

<span data-ttu-id="b1b74-147">Der [true-Operator](../keywords/true-false-operators.md) gibt den [bool](../keywords/bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand definitiv den Wert „true“ hat.</span><span class="sxs-lookup"><span data-stu-id="b1b74-147">[true operator](../keywords/true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely true.</span></span>

<span data-ttu-id="b1b74-148">Der [false-Operator](../keywords/true-false-operators.md) gibt den [bool](../keywords/bool.md)-Wert `true` zurück, um anzugeben, dass ein Operand definitiv den Wert „false“ hat.</span><span class="sxs-lookup"><span data-stu-id="b1b74-148">[false operator](../keywords/true-false-operators.md) - returns the [bool](../keywords/bool.md) value `true` to indicate that an operand is definitely false.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="b1b74-149">Multiplikative Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1b74-149">Multiplicative operators</span></span>

<span data-ttu-id="b1b74-150">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-150">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-151">[x \* y](arithmetic-operators.md#multiplication-operator-) – Multiplikation.</span><span class="sxs-lookup"><span data-stu-id="b1b74-151">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="b1b74-152">[x / y](arithmetic-operators.md#division-operator-) – Division.</span><span class="sxs-lookup"><span data-stu-id="b1b74-152">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="b1b74-153">Wenn es sich bei den Operanden um Ganzzahlen handelt, ist das Ergebnis eine Ganzzahl, die in Richtung 0 abgeschnitten wird (beispielsweise `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="b1b74-153">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="b1b74-154">[x % y](arithmetic-operators.md#remainder-operator-) – Restwert.</span><span class="sxs-lookup"><span data-stu-id="b1b74-154">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="b1b74-155">Wenn es sich bei den Operanden um Ganzzahlen handelt, wird dadurch der Rest der Division x durch y zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b1b74-155">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="b1b74-156">Wenn `q = x / y` und `r = x % y`, dann `x = q * y + r`.</span><span class="sxs-lookup"><span data-stu-id="b1b74-156">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="b1b74-157">Additive Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1b74-157">Additive operators</span></span>

<span data-ttu-id="b1b74-158">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-158">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-159">[x + y](arithmetic-operators.md#addition-operator-) – Addition.</span><span class="sxs-lookup"><span data-stu-id="b1b74-159">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="b1b74-160">[x – y](arithmetic-operators.md#subtraction-operator--) – Subtraktion.</span><span class="sxs-lookup"><span data-stu-id="b1b74-160">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="b1b74-161">Schiebeoperatoren</span><span class="sxs-lookup"><span data-stu-id="b1b74-161">Shift operators</span></span>

<span data-ttu-id="b1b74-162">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-162">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – Verschiebt Bits nach links und füllt sie mit Null auf der rechten Seite auf.</span><span class="sxs-lookup"><span data-stu-id="b1b74-163">[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="b1b74-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – Verschiebt Bits nach rechts.</span><span class="sxs-lookup"><span data-stu-id="b1b74-164">[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – shift bits right.</span></span> <span data-ttu-id="b1b74-165">Wenn der linke Operand `int` oder `long` ist, werden die linken Bits mit dem Vorzeichenbit gefüllt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-165">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="b1b74-166">Wenn der linke Operand `uint` oder `ulong` ist, werden die linken Bits mit Null gefüllt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-166">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="b1b74-167">Relationale und Typtestoperatoren</span><span class="sxs-lookup"><span data-stu-id="b1b74-167">Relational and type-testing operators</span></span>

<span data-ttu-id="b1b74-168">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-168">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-169">[x \< y](comparison-operators.md#less-than-operator-) – Kleiner als (wahr, wenn x kleiner als y ist).</span><span class="sxs-lookup"><span data-stu-id="b1b74-169">[x \< y](comparison-operators.md#less-than-operator-) – less than (true if x is less than y).</span></span>

<span data-ttu-id="b1b74-170">[x > y](comparison-operators.md#greater-than-operator-) – Größer als (wahr, wenn x größer als y ist).</span><span class="sxs-lookup"><span data-stu-id="b1b74-170">[x > y](comparison-operators.md#greater-than-operator-) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="b1b74-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – Ist kleiner oder gleich.</span><span class="sxs-lookup"><span data-stu-id="b1b74-171">[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – less than or equal to.</span></span>

<span data-ttu-id="b1b74-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – Ist größer gleich.</span><span class="sxs-lookup"><span data-stu-id="b1b74-172">[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – greater than or equal to.</span></span>

<span data-ttu-id="b1b74-173">[is](../keywords/is.md) – Typkompatibilität.</span><span class="sxs-lookup"><span data-stu-id="b1b74-173">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="b1b74-174">Gibt TRUE zurück, wenn der ausgewertete linke Operand in den im rechten Operanden (ein statischer Typ) angegebenen Typ umgewandelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="b1b74-174">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="b1b74-175">[as](../keywords/as.md) – Typkonvertierung.</span><span class="sxs-lookup"><span data-stu-id="b1b74-175">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="b1b74-176">Gibt die Umwandlung des linken Operanden zum durch den rechten Operanden (ein statischer Typ) angegebenen Typ zurück, `as` gibt jedoch `null` zurück, wobei `(T)x` eine Auslösung ausgeben würde.</span><span class="sxs-lookup"><span data-stu-id="b1b74-176">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="b1b74-177">Gleichheitsoperatoren</span><span class="sxs-lookup"><span data-stu-id="b1b74-177">Equality operators</span></span>

<span data-ttu-id="b1b74-178">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-178">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-179">[x == y](equality-operators.md#equality-operator-) – Gleichheit.</span><span class="sxs-lookup"><span data-stu-id="b1b74-179">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="b1b74-180">Standardmäßig wird für Verweistypen, die nicht `string` entsprechen, diese Verweisübereinstimmung (Identitätstest) zurückgeben</span><span class="sxs-lookup"><span data-stu-id="b1b74-180">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="b1b74-181">Typen können `==` jedoch überladen. Wenn Sie also vorhaben, die Identität zu testen, sollten Sie möglichst die `ReferenceEquals`-Methode für `object` verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1b74-181">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="b1b74-182">[x != y](equality-operators.md#inequality-operator-) – ungleich.</span><span class="sxs-lookup"><span data-stu-id="b1b74-182">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="b1b74-183">Siehe hierzu den Kommentar für `==`.</span><span class="sxs-lookup"><span data-stu-id="b1b74-183">See comment for `==`.</span></span> <span data-ttu-id="b1b74-184">Wenn ein Typ `==` überlädt, muss er `!=` überladen.</span><span class="sxs-lookup"><span data-stu-id="b1b74-184">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="b1b74-185">Logischer AND-Operator</span><span class="sxs-lookup"><span data-stu-id="b1b74-185">Logical AND operator</span></span>

<span data-ttu-id="b1b74-186">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-186">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-187">`x & y` –[logische AND](boolean-logical-operators.md#logical-and-operator-)-Operationen für die `bool`-Operanden oder [bitweise logische AND](bitwise-and-shift-operators.md#logical-and-operator-)-Operationen für die Operanden von integralen Typen.</span><span class="sxs-lookup"><span data-stu-id="b1b74-187">`x & y` – [logical AND](boolean-logical-operators.md#logical-and-operator-) for the `bool` operands or [bitwise logical AND](bitwise-and-shift-operators.md#logical-and-operator-) for the operands of the integral types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="b1b74-188">Logischer XOR-Operator</span><span class="sxs-lookup"><span data-stu-id="b1b74-188">Logical XOR operator</span></span>

<span data-ttu-id="b1b74-189">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-190">`x ^ y` –[logische XOR](boolean-logical-operators.md#logical-exclusive-or-operator-)-Operationen für die `bool`-Operanden oder [bitweise logische XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)-Operationen für die Operanden von integralen Typen.</span><span class="sxs-lookup"><span data-stu-id="b1b74-190">`x ^ y` – [logical XOR](boolean-logical-operators.md#logical-exclusive-or-operator-) for the `bool` operands or [bitwise logical XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-) for the operands of the integral types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="b1b74-191">Logischer OR-Operator (||)</span><span class="sxs-lookup"><span data-stu-id="b1b74-191">Logical OR operator</span></span>

<span data-ttu-id="b1b74-192">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-192">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-193">`x | y` –[logische OR](boolean-logical-operators.md#logical-or-operator-)-Operationen für die `bool`-Operanden oder [bitweise logische OR](bitwise-and-shift-operators.md#logical-or-operator-)-Operationen für die Operanden von integralen Typen.</span><span class="sxs-lookup"><span data-stu-id="b1b74-193">`x | y` – [logical OR](boolean-logical-operators.md#logical-or-operator-) for the `bool` operands or [bitwise logical OR](bitwise-and-shift-operators.md#logical-or-operator-) for the operands of the integral types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="b1b74-194">Bedingter AND-Operator</span><span class="sxs-lookup"><span data-stu-id="b1b74-194">Conditional AND operator</span></span>

<span data-ttu-id="b1b74-195">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-195">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logisches AND.</span><span class="sxs-lookup"><span data-stu-id="b1b74-196">[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – logical AND.</span></span> <span data-ttu-id="b1b74-197">Wenn der erste Operand FALSE ist, wertet C# den zweiten Operand nicht aus.</span><span class="sxs-lookup"><span data-stu-id="b1b74-197">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="b1b74-198">Bedingter OR-Operator</span><span class="sxs-lookup"><span data-stu-id="b1b74-198">Conditional OR operator</span></span>

<span data-ttu-id="b1b74-199">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-199">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – Logisches OR.</span><span class="sxs-lookup"><span data-stu-id="b1b74-200">[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – logical OR.</span></span> <span data-ttu-id="b1b74-201">Wenn der erste Operand TRUE ist, wertet C# den zweiten Operand nicht aus.</span><span class="sxs-lookup"><span data-stu-id="b1b74-201">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="b1b74-202">Nullzusammensetzungsoperator</span><span class="sxs-lookup"><span data-stu-id="b1b74-202">Null-coalescing operator</span></span>

<span data-ttu-id="b1b74-203">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-203">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-204">[x ?? y](null-coalescing-operator.md) – Gibt `x` zurück, sofern es Nicht-`null` ist; ansonsten wird `y` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b1b74-204">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="b1b74-205">Bedingter Operator</span><span class="sxs-lookup"><span data-stu-id="b1b74-205">Conditional operator</span></span>

<span data-ttu-id="b1b74-206">Dieser Operator hat eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-206">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-207">[t ? x : y](conditional-operator.md): Wenn der Test `t` TRUE ist, wird `x` ausgewertet und zurückgegeben, ansonsten wird `y` ausgewertet und zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b1b74-207">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="b1b74-208">Zuweisungs- und Lambdaoperatoren</span><span class="sxs-lookup"><span data-stu-id="b1b74-208">Assignment and lambda operators</span></span>

<span data-ttu-id="b1b74-209">Diese Operatoren haben eine höhere Rangfolge als der nächste Abschnitt und eine geringere Rangfolge als der vorherige Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-209">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="b1b74-210">[x = y](assignment-operator.md) – Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="b1b74-210">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="b1b74-211">[x += y](addition-assignment-operator.md) – Inkrement.</span><span class="sxs-lookup"><span data-stu-id="b1b74-211">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="b1b74-212">Fügen Sie dem Wert `x` den Wert `y` hinzu. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-212">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="b1b74-213">Wenn `x` ein `event` festlegt, muss `y` eine entsprechende Funktion sein, die C# als ein Eventhandler hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-213">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="b1b74-214">[x -= y](subtraction-assignment-operator.md) – Dekrement.</span><span class="sxs-lookup"><span data-stu-id="b1b74-214">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="b1b74-215">Subtrahieren Sie vom Wert `x` den Wert `y`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-215">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="b1b74-216">Wenn `x` ein `event` festlegt, muss `y` eine entsprechende Funktion sein, die C# als ein Eventhandler entfernt.</span><span class="sxs-lookup"><span data-stu-id="b1b74-216">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler.</span></span>

<span data-ttu-id="b1b74-217">[x \*= y](arithmetic-operators.md#compound-assignment) – Multiplikationszuweisung.</span><span class="sxs-lookup"><span data-stu-id="b1b74-217">[x \*= y](arithmetic-operators.md#compound-assignment) – multiplication assignment.</span></span> <span data-ttu-id="b1b74-218">Multiplizieren Sie den Wert `y` mit dem Wert `x`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-218">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="b1b74-219">[x /= y](arithmetic-operators.md#compound-assignment) – Divisionszuweisung.</span><span class="sxs-lookup"><span data-stu-id="b1b74-219">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="b1b74-220">Dividieren Sie den Wert `x` durch den Wert `y`. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-220">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="b1b74-221">[x %= y](arithmetic-operators.md#compound-assignment) – Restwertzuweisung.</span><span class="sxs-lookup"><span data-stu-id="b1b74-221">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="b1b74-222">Dividieren Sie den Wert `x` durch den Wert `y`. Speichern Sie den Rest in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-222">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="b1b74-223">[x &= y](boolean-logical-operators.md#compound-assignment) – AND-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="b1b74-223">[x &= y](boolean-logical-operators.md#compound-assignment) – AND assignment.</span></span> <span data-ttu-id="b1b74-224">Führen Sie eine AND-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-224">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="b1b74-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="b1b74-225">[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR assignment.</span></span> <span data-ttu-id="b1b74-226">Führen Sie eine OR-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-226">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="b1b74-227">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR-Zuweisung.</span><span class="sxs-lookup"><span data-stu-id="b1b74-227">[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR assignment.</span></span> <span data-ttu-id="b1b74-228">Führen Sie eine XOR-Operation der Werte `y` und `x` aus. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-228">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="b1b74-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – Linksschiebezuweisung.</span><span class="sxs-lookup"><span data-stu-id="b1b74-229">[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – left-shift assignment.</span></span> <span data-ttu-id="b1b74-230">Verschieben Sie den Wert von `x` nach links um `y` Stellen. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-230">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="b1b74-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – Rechtsschiebezuweisung.</span><span class="sxs-lookup"><span data-stu-id="b1b74-231">[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – right-shift assignment.</span></span> <span data-ttu-id="b1b74-232">Verschieben Sie den Wert von `x` nach rechts um `y` Stellen. Speichern Sie das Ergebnis in `x`, und geben Sie den neuen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="b1b74-232">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="b1b74-233">[=>](lambda-operator.md) – Lambdadeklaration.</span><span class="sxs-lookup"><span data-stu-id="b1b74-233">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1b74-234">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b1b74-234">See also</span></span>

- [<span data-ttu-id="b1b74-235">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b1b74-235">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b1b74-236">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b1b74-236">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b1b74-237">C#</span><span class="sxs-lookup"><span data-stu-id="b1b74-237">C#</span></span>](../../index.md)
- [<span data-ttu-id="b1b74-238">Überladbare Operatoren</span><span class="sxs-lookup"><span data-stu-id="b1b74-238">Overloadable operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="b1b74-239">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b1b74-239">C# Keywords</span></span>](../keywords/index.md)
