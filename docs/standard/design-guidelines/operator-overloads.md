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
ms.openlocfilehash: 4cea3c17de40a873d977223f36b6dcef4f2c2d78
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709139"
---
# <a name="operator-overloads"></a><span data-ttu-id="958c8-102">Operatorüberladungen</span><span class="sxs-lookup"><span data-stu-id="958c8-102">Operator Overloads</span></span>
<span data-ttu-id="958c8-103">Mit Operator Überladungen können Frameworktypen so angezeigt werden, als wären Sie integrierte Sprach primitive.</span><span class="sxs-lookup"><span data-stu-id="958c8-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>  
  
 <span data-ttu-id="958c8-104">Obwohl es in manchen Situationen zulässig und nützlich ist, sollten Operator Überladungen vorsichtig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="958c8-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="958c8-105">Es gibt viele Fälle, in denen das Überladen von Operatoren missbraucht wurde, z. b. wenn frameworkdesigner die Verwendung von Operatoren für Vorgänge gestartet haben, die einfache Methoden sein sollten.</span><span class="sxs-lookup"><span data-stu-id="958c8-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="958c8-106">Die folgenden Richtlinien sollten Sie bei der Entscheidung unterstützen, wann und wie die Operator Überladung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="958c8-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>  
  
 <span data-ttu-id="958c8-107">**X AVOID** definieren operatorüberladungen, außer in Typen, die z. B. primitive (integrierte) Typen können sollten.</span><span class="sxs-lookup"><span data-stu-id="958c8-107">**X AVOID** defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>  
  
 <span data-ttu-id="958c8-108">**✓ CONSIDER** operatorüberladungen in einen Typ, der wie ein primitiver Typ denken sollten definieren.</span><span class="sxs-lookup"><span data-stu-id="958c8-108">**✓ CONSIDER** defining operator overloads in a type that should feel like a primitive type.</span></span>  
  
 <span data-ttu-id="958c8-109">Beispielsweise ist <xref:System.String?displayProperty=nameWithType> `operator==` und `operator!=` definiert.</span><span class="sxs-lookup"><span data-stu-id="958c8-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>  
  
 <span data-ttu-id="958c8-110">**✓ DO** operatorüberladungen in Strukturen, die Zahlen darstellen definieren (z. B. <xref:System.Decimal?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="958c8-110">**✓ DO** define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="958c8-111">**X DO NOT** beim Definieren von operatorüberladungen nette sein.</span><span class="sxs-lookup"><span data-stu-id="958c8-111">**X DO NOT** be cute when defining operator overloads.</span></span>  
  
 <span data-ttu-id="958c8-112">Die Operator Überladung ist in Fällen nützlich, in denen es sofort offensichtlich ist, was das Ergebnis des Vorgangs sein wird.</span><span class="sxs-lookup"><span data-stu-id="958c8-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="958c8-113">Beispielsweise ist es sinnvoll, eine <xref:System.DateTime> von einem anderen `DateTime` zu subtrahieren und eine <xref:System.TimeSpan>zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="958c8-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="958c8-114">Es ist jedoch nicht geeignet, den logischen Union-Operator für die Union zweier Datenbankabfragen zu verwenden oder den Shift-Operator zum Schreiben in einen Stream zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="958c8-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>  
  
 <span data-ttu-id="958c8-115">**X DO NOT** bieten überlädt, wenn mindestens einer der Operanden den Typ definieren die Überladung aufweist.</span><span class="sxs-lookup"><span data-stu-id="958c8-115">**X DO NOT** provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>  
  
 <span data-ttu-id="958c8-116">**✓ DO** Überladen von Operatoren symmetrisch.</span><span class="sxs-lookup"><span data-stu-id="958c8-116">**✓ DO** overload operators in a symmetric fashion.</span></span>  
  
 <span data-ttu-id="958c8-117">Wenn Sie z. b. die `operator==`überladen, sollten Sie auch die `operator!=`überladen.</span><span class="sxs-lookup"><span data-stu-id="958c8-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="958c8-118">Wenn Sie die `operator<`überladen, sollten Sie auch die `operator>`überladen usw.</span><span class="sxs-lookup"><span data-stu-id="958c8-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>  
  
 <span data-ttu-id="958c8-119">**✓ CONSIDER** stellt Methoden bereit, mit dem Anzeigenamen, die entsprechen ab, zu jedem überladener Operator.</span><span class="sxs-lookup"><span data-stu-id="958c8-119">**✓ CONSIDER** providing methods with friendly names that correspond to each overloaded operator.</span></span>  
  
 <span data-ttu-id="958c8-120">Viele Sprachen unterstützen das Überladen von Operatoren nicht.</span><span class="sxs-lookup"><span data-stu-id="958c8-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="958c8-121">Aus diesem Grund wird empfohlen, dass Typen, die Operatoren überlasten, eine sekundäre Methode mit einem entsprechenden domänenspezifischen Namen enthalten, der entsprechende Funktionalität bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="958c8-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>  
  
 <span data-ttu-id="958c8-122">Die folgende Tabelle enthält eine Liste der Operatoren und der entsprechenden anzeigen amen der Methode.</span><span class="sxs-lookup"><span data-stu-id="958c8-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>  
  
|<span data-ttu-id="958c8-123">C#Operator Symbol</span><span class="sxs-lookup"><span data-stu-id="958c8-123">C# Operator Symbol</span></span>|<span data-ttu-id="958c8-124">Metadatenname</span><span class="sxs-lookup"><span data-stu-id="958c8-124">Metadata Name</span></span>|<span data-ttu-id="958c8-125">Geeigneter Name</span><span class="sxs-lookup"><span data-stu-id="958c8-125">Friendly Name</span></span>|  
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
  
### <a name="overloading-operator-"></a><span data-ttu-id="958c8-126">Überladen des Operators = =</span><span class="sxs-lookup"><span data-stu-id="958c8-126">Overloading Operator ==</span></span>  
 <span data-ttu-id="958c8-127">Das Überladen von `operator ==` ist recht kompliziert.</span><span class="sxs-lookup"><span data-stu-id="958c8-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="958c8-128">Die Semantik des Operators muss mit mehreren anderen Membern kompatibel sein, z. b. <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="958c8-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="conversion-operators"></a><span data-ttu-id="958c8-129">Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="958c8-129">Conversion Operators</span></span>  
 <span data-ttu-id="958c8-130">Konvertierungs Operatoren sind unäre Operatoren, die eine Konvertierung von einem Typ in einen anderen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="958c8-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="958c8-131">Die Operatoren müssen als statische Member entweder für den Operanden oder den Rückgabetyp definiert werden.</span><span class="sxs-lookup"><span data-stu-id="958c8-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="958c8-132">Es gibt zwei Typen von Konvertierungs Operatoren: implizit und explizit.</span><span class="sxs-lookup"><span data-stu-id="958c8-132">There are two types of conversion operators: implicit and explicit.</span></span>  
  
 <span data-ttu-id="958c8-133">**X DO NOT** Geben Sie einen Konvertierungsoperator aus, wenn eine solche Konvertierung nicht eindeutig von den Endbenutzern erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="958c8-133">**X DO NOT** provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>  
  
 <span data-ttu-id="958c8-134">**X DO NOT** Konvertierungsoperatoren außerhalb der Domäne des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="958c8-134">**X DO NOT** define conversion operators outside of a type’s domain.</span></span>  
  
 <span data-ttu-id="958c8-135">Beispielsweise sind <xref:System.Int32>, <xref:System.Double>und <xref:System.Decimal> alle numerischen Typen, während <xref:System.DateTime> nicht ist.</span><span class="sxs-lookup"><span data-stu-id="958c8-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="958c8-136">Daher sollte kein Konvertierungs Operator vorhanden sein, um eine `Double(long)` in eine `DateTime`zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="958c8-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="958c8-137">Ein Konstruktor wird in einem solchen Fall bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="958c8-137">A constructor is preferred in such a case.</span></span>  
  
 <span data-ttu-id="958c8-138">**X DO NOT** Geben Sie einen impliziten Konvertierungsoperator, wenn die Konvertierung potenziell lossy ist.</span><span class="sxs-lookup"><span data-stu-id="958c8-138">**X DO NOT** provide an implicit conversion operator if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="958c8-139">Beispielsweise sollte keine implizite Konvertierung von `Double` in `Int32` vorhanden sein, da `Double` über einen größeren Bereich als `Int32`verfügt.</span><span class="sxs-lookup"><span data-stu-id="958c8-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="958c8-140">Ein expliziter Konvertierungs Operator kann auch dann bereitgestellt werden, wenn die Konvertierung potenziell Verlust Haft ist.</span><span class="sxs-lookup"><span data-stu-id="958c8-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="958c8-141">**X DO NOT** lösen Ausnahmen aus implizite Umwandlungen.</span><span class="sxs-lookup"><span data-stu-id="958c8-141">**X DO NOT** throw exceptions from implicit casts.</span></span>  
  
 <span data-ttu-id="958c8-142">Es ist für Endbenutzer sehr schwierig, herauszufinden, was passiert, da Sie möglicherweise nicht erkennen, dass eine Konvertierung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="958c8-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>  
  
 <span data-ttu-id="958c8-143">**✓ DO** auslösen <xref:System.InvalidCastException?displayProperty=nameWithType> Wenn ein Aufruf an ein Cast-Operator eine verlustbehaftete Konvertierung führt und der Vertrag des Operators lossy Konvertierungen nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="958c8-143">**✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>  
  
 <span data-ttu-id="958c8-144">*Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="958c8-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="958c8-145">*Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="958c8-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="958c8-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="958c8-146">See also</span></span>

- [<span data-ttu-id="958c8-147">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="958c8-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)
- [<span data-ttu-id="958c8-148">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="958c8-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
