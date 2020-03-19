---
title: Operatorüberladungen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- operators [.NET Framework], overloads
- names [.NET Framework], overloaded operators
- member design guidelines, operators
- overloaded operators
ms.assetid: 37585bf2-4c27-4dee-849a-af70e3338cc1
ms.openlocfilehash: 0999e94c8d77396b237522e89c51206ce1226718
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401220"
---
# <a name="operator-overloads"></a><span data-ttu-id="5ab01-102">Operatorüberladungen</span><span class="sxs-lookup"><span data-stu-id="5ab01-102">Operator Overloads</span></span>
<span data-ttu-id="5ab01-103">Überladungen von Operatoren ermöglichen es Frameworktypen, so zu wie integrierte Sprachprimitive zu erscheinen.</span><span class="sxs-lookup"><span data-stu-id="5ab01-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>

 <span data-ttu-id="5ab01-104">Obwohl es in einigen Situationen zulässig und nützlich ist, sollten Operatorüberladungen vorsichtig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ab01-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="5ab01-105">Es gibt viele Fälle, in denen die Überladung von Operatoren missbraucht wurde, z. B. wenn Frameworkdesigner begannen, Operatoren für Vorgänge zu verwenden, die einfache Methoden sein sollten.</span><span class="sxs-lookup"><span data-stu-id="5ab01-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="5ab01-106">Die folgenden Richtlinien sollten Ihnen bei der Entscheidung helfen, wann und wie Operatorüberlastung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5ab01-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>

 <span data-ttu-id="5ab01-107">❌AVOID definiert Operatorüberladungen, außer in Typen, die sich wie primitive (integrierte) Typen anfühlen sollten.</span><span class="sxs-lookup"><span data-stu-id="5ab01-107">❌ AVOID defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>

 <span data-ttu-id="5ab01-108">✔️ CONSIDER definieren Operatorüberladungen in einem Typ, der sich wie ein primitiver Typ anfühlen sollte.</span><span class="sxs-lookup"><span data-stu-id="5ab01-108">✔️ CONSIDER defining operator overloads in a type that should feel like a primitive type.</span></span>

 <span data-ttu-id="5ab01-109">Zum Beispiel <xref:System.String?displayProperty=nameWithType> `operator==` hat `operator!=` und definiert.</span><span class="sxs-lookup"><span data-stu-id="5ab01-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>

 <span data-ttu-id="5ab01-110">✔️ DO definieren Operatorüberladungen in Strukturen, <xref:System.Decimal?displayProperty=nameWithType>die Zahlen darstellen (z. B. ).</span><span class="sxs-lookup"><span data-stu-id="5ab01-110">✔️ DO define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>

 <span data-ttu-id="5ab01-111">❌Seien Sie NICHT niedlich, wenn Operator-Überlastungen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="5ab01-111">❌ DO NOT be cute when defining operator overloads.</span></span>

 <span data-ttu-id="5ab01-112">Eine Überladung des Bedieners ist in Fällen nützlich, in denen sofort klar ist, was das Ergebnis des Vorgangs sein wird.</span><span class="sxs-lookup"><span data-stu-id="5ab01-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="5ab01-113">Es ist z. B. sinnvoll, <xref:System.DateTime> eine `DateTime` von der <xref:System.TimeSpan>anderen subtrahieren zu können und eine zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5ab01-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="5ab01-114">Es ist jedoch nicht sinnvoll, den logischen Union-Operator zu verwenden, um zwei Datenbankabfragen zu vereinigen, oder den Schichtoperator zum Schreiben in einen Stream zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ab01-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>

 <span data-ttu-id="5ab01-115">❌Stellen Sie KEINE Operatorüberladungen bereit, es sei denn, mindestens einer der Operanden ist vom Typ, der die Überladung definiert.</span><span class="sxs-lookup"><span data-stu-id="5ab01-115">❌ DO NOT provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>

 <span data-ttu-id="5ab01-116">✔️ DO-Überlastoperatoren in symmetrischer Weise.</span><span class="sxs-lookup"><span data-stu-id="5ab01-116">✔️ DO overload operators in a symmetric fashion.</span></span>

 <span data-ttu-id="5ab01-117">Wenn Sie z. B. die `operator==`überladen, `operator!=`sollten Sie auch die überladen.</span><span class="sxs-lookup"><span data-stu-id="5ab01-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="5ab01-118">Wenn Sie die `operator<`überladen, sollten Sie `operator>`auch die überladen usw.</span><span class="sxs-lookup"><span data-stu-id="5ab01-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>

 <span data-ttu-id="5ab01-119">✔️ CONSIDER, methoden mit Anzeigenamen bereitzustellen, die jedem überlasteten Operator entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5ab01-119">✔️ CONSIDER providing methods with friendly names that correspond to each overloaded operator.</span></span>

 <span data-ttu-id="5ab01-120">Viele Sprachen unterstützen keine Operatorüberlastung.</span><span class="sxs-lookup"><span data-stu-id="5ab01-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="5ab01-121">Aus diesem Grund wird empfohlen, dass Typen, die Überlastoperatoren enthalten, eine sekundäre Methode mit einem entsprechenden domänenspezifischen Namen enthalten, der eine gleichwertige Funktionalität bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5ab01-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>

 <span data-ttu-id="5ab01-122">Die folgende Tabelle enthält eine Liste der Operatoren und die entsprechenden Anzeigemethodennamen.</span><span class="sxs-lookup"><span data-stu-id="5ab01-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>

|<span data-ttu-id="5ab01-123">Operatorsymbol für die C-Operator</span><span class="sxs-lookup"><span data-stu-id="5ab01-123">C# Operator Symbol</span></span>|<span data-ttu-id="5ab01-124">Metadatenname</span><span class="sxs-lookup"><span data-stu-id="5ab01-124">Metadata Name</span></span>|<span data-ttu-id="5ab01-125">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="5ab01-125">Friendly Name</span></span>|
|-------------------------|-------------------|-------------------|
|`N/A`|`op_Implicit`|`To<TypeName>/From<TypeName>`|
|`N/A`|`op_Explicit`|`To<TypeName>/From<TypeName>`|
|`+ (binary)`|`op_Addition`|`Add`|
|`- (binary)`|`op_Subtraction`|`Subtract`|
|`* (binary)`|`op_Multiply`|`Multiply`|
|`/`|`op_Division`|`Divide`|
|`%`|`op_Modulus`|`Mod or Remainder`|
|`^`|`op_ExclusiveOr`|`Xor`|
|`& (binary)`|`op_BitwiseAnd`|`BitwiseAnd`|
|<code>&#124;</code>|`op_BitwiseOr`|`BitwiseOr`|
|`&&`|`op_LogicalAnd`|`And`|
|<code>&#124;&#124;</code>|`op_LogicalOr`|`Or`|
|`=`|`op_Assign`|`Assign`|
|`<<`|`op_LeftShift`|`LeftShift`|
|`>>`|`op_RightShift`|`RightShift`|
|`N/A`|`op_SignedRightShift`|`SignedRightShift`|
|`N/A`|`op_UnsignedRightShift`|`UnsignedRightShift`|
|`==`|`op_Equality`|`Equals`|
|`!=`|`op_Inequality`|`Equals`|
|`>`|`op_GreaterThan`|`CompareTo`|
|`<`|`op_LessThan`|`CompareTo`|
|`>=`|`op_GreaterThanOrEqual`|`CompareTo`|
|`<=`|`op_LessThanOrEqual`|`CompareTo`|
|`*=`|`op_MultiplicationAssignment`|`Multiply`|
|`-=`|`op_SubtractionAssignment`|`Subtract`|
|`^=`|`op_ExclusiveOrAssignment`|`Xor`|
|`<<=`|`op_LeftShiftAssignment`|`LeftShift`|
|`%=`|`op_ModulusAssignment`|`Mod`|
|`+=`|`op_AdditionAssignment`|`Add`|
|`&=`|`op_BitwiseAndAssignment`|`BitwiseAnd`|
|<code>&#124;=</code>|`op_BitwiseOrAssignment`|`BitwiseOr`|
|`,`|`op_Comma`|`Comma`|
|`/=`|`op_DivisionAssignment`|`Divide`|
|`--`|`op_Decrement`|`Decrement`|
|`++`|`op_Increment`|`Increment`|
|`- (unary)`|`op_UnaryNegation`|`Negate`|
|`+ (unary)`|`op_UnaryPlus`|`Plus`|
|`~`|`op_OnesComplement`|`OnesComplement`|

### <a name="overloading-operator-"></a><span data-ttu-id="5ab01-126">Überladen des Operators ==</span><span class="sxs-lookup"><span data-stu-id="5ab01-126">Overloading Operator ==</span></span>
 <span data-ttu-id="5ab01-127">Überlastung `operator ==` ist ziemlich kompliziert.</span><span class="sxs-lookup"><span data-stu-id="5ab01-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="5ab01-128">Die Semantik des Operators muss mit mehreren anderen <xref:System.Object.Equals%2A?displayProperty=nameWithType>Elementen kompatibel sein, z. B. .</span><span class="sxs-lookup"><span data-stu-id="5ab01-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>

### <a name="conversion-operators"></a><span data-ttu-id="5ab01-129">Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="5ab01-129">Conversion Operators</span></span>
 <span data-ttu-id="5ab01-130">Konvertierungsoperatoren sind unäre Operatoren, die die Konvertierung von einem Typ in einen anderen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5ab01-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="5ab01-131">Die Operatoren müssen als statische Elemente entweder im Operanden oder im Rückgabetyp definiert werden.</span><span class="sxs-lookup"><span data-stu-id="5ab01-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="5ab01-132">Es gibt zwei Arten von Konvertierungsoperatoren: implizit und explizit.</span><span class="sxs-lookup"><span data-stu-id="5ab01-132">There are two types of conversion operators: implicit and explicit.</span></span>

 <span data-ttu-id="5ab01-133">❌Stellen Sie KEINEN Konvertierungsoperator bereit, wenn eine solche Konvertierung von den Endbenutzern nicht eindeutig erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="5ab01-133">❌ DO NOT provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>

 <span data-ttu-id="5ab01-134">❌Definieren Sie NICHT Konvertierungsoperatoren außerhalb der Domäne eines Typs.</span><span class="sxs-lookup"><span data-stu-id="5ab01-134">❌ DO NOT define conversion operators outside of a type’s domain.</span></span>

 <span data-ttu-id="5ab01-135">Beispiel: <xref:System.Int32>, <xref:System.Double>und <xref:System.Decimal> sind alle numerischen Typen, während <xref:System.DateTime> dies nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="5ab01-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="5ab01-136">Daher sollte es keinen Konvertierungsoperator `Double(long)` geben, um eine in eine `DateTime`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="5ab01-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="5ab01-137">In einem solchen Fall wird ein Konstruktor bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="5ab01-137">A constructor is preferred in such a case.</span></span>

 <span data-ttu-id="5ab01-138">❌Stellen Sie NICHT einen impliziten Konvertierungsoperator bereit, wenn die Konvertierung potenziell verlustbehaftet ist.</span><span class="sxs-lookup"><span data-stu-id="5ab01-138">❌ DO NOT provide an implicit conversion operator if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="5ab01-139">Beispielsweise sollte es keine implizite `Double` Konvertierung `Int32` `Double` von in geben, da sie einen größeren Bereich als `Int32`hat.</span><span class="sxs-lookup"><span data-stu-id="5ab01-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="5ab01-140">Ein expliziter Konvertierungsoperator kann auch dann bereitgestellt werden, wenn die Konvertierung potenziell verlustbehaftet ist.</span><span class="sxs-lookup"><span data-stu-id="5ab01-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>

 <span data-ttu-id="5ab01-141">❌Nicht Ausnahmen von impliziten Umwandlungen auslösen.</span><span class="sxs-lookup"><span data-stu-id="5ab01-141">❌ DO NOT throw exceptions from implicit casts.</span></span>

 <span data-ttu-id="5ab01-142">Es ist sehr schwierig für Endbenutzer zu verstehen, was passiert, weil sie möglicherweise nicht wissen, dass eine Konvertierung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="5ab01-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>

 <span data-ttu-id="5ab01-143">✔️ do <xref:System.InvalidCastException?displayProperty=nameWithType> werfen, wenn ein Anruf bei einem Gussoperator zu einer verlustbehafteten Umwandlung führt und der Vertrag des Operators keine verlustbehafteten Umwandlungen zulässt.</span><span class="sxs-lookup"><span data-stu-id="5ab01-143">✔️ DO throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>

 <span data-ttu-id="5ab01-144">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="5ab01-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="5ab01-145">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="5ab01-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="5ab01-146">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ab01-146">See also</span></span>

- [<span data-ttu-id="5ab01-147">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="5ab01-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="5ab01-148">Framework Design-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="5ab01-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
