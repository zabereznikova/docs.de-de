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
author: KrzysztofCwalina
ms.openlocfilehash: d1b9d8bc1f5f6f83a50dbd798894f94937320d2b
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53152135"
---
# <a name="operator-overloads"></a><span data-ttu-id="f2736-102">Operatorüberladungen</span><span class="sxs-lookup"><span data-stu-id="f2736-102">Operator Overloads</span></span>
<span data-ttu-id="f2736-103">Operatorüberladungen können angezeigt werden, als wären sie integrierte Sprachprimitive Framework-Typen.</span><span class="sxs-lookup"><span data-stu-id="f2736-103">Operator overloads allow framework types to appear as if they were built-in language primitives.</span></span>  
  
 <span data-ttu-id="f2736-104">Obwohl zulässig und in einigen Situationen nützlich, sollte die operatorüberladungen mit Vorsicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f2736-104">Although allowed and useful in some situations, operator overloads should be used cautiously.</span></span> <span data-ttu-id="f2736-105">Es gibt viele Fälle, die in der, die, die Operator überladen missbräuchlich verwendet wurde z. B. beim Start der Framework-Designer Verwendung Operatoren für Vorgänge, die einfache Methoden werden soll, ein.</span><span class="sxs-lookup"><span data-stu-id="f2736-105">There are many cases in which operator overloading has been abused, such as when framework designers started to use operators for operations that should be simple methods.</span></span> <span data-ttu-id="f2736-106">Die folgenden Richtlinien sollten Sie entscheiden, wann und wie Sie die Überladung von Operatoren verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f2736-106">The following guidelines should help you decide when and how to use operator overloading.</span></span>  
  
 <span data-ttu-id="f2736-107">**X AVOID** definieren operatorüberladungen, außer in Typen, die z. B. primitive (integrierte) Typen können sollten.</span><span class="sxs-lookup"><span data-stu-id="f2736-107">**X AVOID** defining operator overloads, except in types that should feel like primitive (built-in) types.</span></span>  
  
 <span data-ttu-id="f2736-108">**✓ CONSIDER** operatorüberladungen in einen Typ, der wie ein primitiver Typ denken sollten definieren.</span><span class="sxs-lookup"><span data-stu-id="f2736-108">**✓ CONSIDER** defining operator overloads in a type that should feel like a primitive type.</span></span>  
  
 <span data-ttu-id="f2736-109">Z. B. <xref:System.String?displayProperty=nameWithType> hat `operator==` und `operator!=` definiert.</span><span class="sxs-lookup"><span data-stu-id="f2736-109">For example, <xref:System.String?displayProperty=nameWithType> has `operator==` and `operator!=` defined.</span></span>  
  
 <span data-ttu-id="f2736-110">**✓ DO** operatorüberladungen in Strukturen, die Zahlen darstellen definieren (z. B. <xref:System.Decimal?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="f2736-110">**✓ DO** define operator overloads in structs that represent numbers (such as <xref:System.Decimal?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="f2736-111">**X DO NOT** beim Definieren von operatorüberladungen nette sein.</span><span class="sxs-lookup"><span data-stu-id="f2736-111">**X DO NOT** be cute when defining operator overloads.</span></span>  
  
 <span data-ttu-id="f2736-112">Überladen des Operators ist hilfreich in Fällen, in denen es sofort offensichtlich wird das Ergebnis des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="f2736-112">Operator overloading is useful in cases in which it is immediately obvious what the result of the operation will be.</span></span> <span data-ttu-id="f2736-113">Beispielsweise ist es sinnvoll, eine subtrahieren können <xref:System.DateTime> von einem anderen `DateTime` und erhalten Sie eine <xref:System.TimeSpan>.</span><span class="sxs-lookup"><span data-stu-id="f2736-113">For example, it makes sense to be able to subtract one <xref:System.DateTime> from another `DateTime` and get a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="f2736-114">Es ist jedoch nicht sinnvoll, logische union-Operators auf zwei-union-Datenbankabfragen verwenden oder mithilfe der UMSCHALT-Operator verwenden, um das Schreiben in einen Stream.</span><span class="sxs-lookup"><span data-stu-id="f2736-114">However, it is not appropriate to use the logical union operator to union two database queries, or to use the shift operator to write to a stream.</span></span>  
  
 <span data-ttu-id="f2736-115">**X DO NOT** bieten überlädt, wenn mindestens einer der Operanden den Typ definieren die Überladung aufweist.</span><span class="sxs-lookup"><span data-stu-id="f2736-115">**X DO NOT** provide operator overloads unless at least one of the operands is of the type defining the overload.</span></span>  
  
 <span data-ttu-id="f2736-116">**✓ DO** Überladen von Operatoren symmetrisch.</span><span class="sxs-lookup"><span data-stu-id="f2736-116">**✓ DO** overload operators in a symmetric fashion.</span></span>  
  
 <span data-ttu-id="f2736-117">Wenn Sie überladen, z. B. die `operator==`, überladen Sie auch die `operator!=`.</span><span class="sxs-lookup"><span data-stu-id="f2736-117">For example, if you overload the `operator==`, you should also overload the `operator!=`.</span></span> <span data-ttu-id="f2736-118">Auf ähnliche Weise, wenn Sie überladen der `operator<`, überladen Sie auch die `operator>`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="f2736-118">Similarly, if you overload the `operator<`, you should also overload the `operator>`, and so on.</span></span>  
  
 <span data-ttu-id="f2736-119">**✓ CONSIDER** stellt Methoden bereit, mit dem Anzeigenamen, die entsprechen ab, zu jedem überladener Operator.</span><span class="sxs-lookup"><span data-stu-id="f2736-119">**✓ CONSIDER** providing methods with friendly names that correspond to each overloaded operator.</span></span>  
  
 <span data-ttu-id="f2736-120">Überladen von unterstützt vielen Sprachen nicht.</span><span class="sxs-lookup"><span data-stu-id="f2736-120">Many languages do not support operator overloading.</span></span> <span data-ttu-id="f2736-121">Aus diesem Grund empfiehlt es sich, dass Typen, die Operatoren überladen eine zweite Methode mit einem entsprechenden domänenspezifischen Namen enthalten, die entsprechende Funktionalität bietet.</span><span class="sxs-lookup"><span data-stu-id="f2736-121">For this reason, it is recommended that types that overload operators include a secondary method with an appropriate domain-specific name that provides equivalent functionality.</span></span>  
  
 <span data-ttu-id="f2736-122">Die folgende Tabelle enthält eine Liste der Operatoren und die entsprechenden Anzeigenamen Methodennamen.</span><span class="sxs-lookup"><span data-stu-id="f2736-122">The following table contains a list of operators and the corresponding friendly method names.</span></span>  
  
|<span data-ttu-id="f2736-123">C#-Symbol "Operator"</span><span class="sxs-lookup"><span data-stu-id="f2736-123">C# Operator Symbol</span></span>|<span data-ttu-id="f2736-124">Metadatennamen</span><span class="sxs-lookup"><span data-stu-id="f2736-124">Metadata Name</span></span>|<span data-ttu-id="f2736-125">Anzeigename</span><span class="sxs-lookup"><span data-stu-id="f2736-125">Friendly Name</span></span>|  
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
  
### <a name="overloading-operator-"></a><span data-ttu-id="f2736-126">Überladen des ==</span><span class="sxs-lookup"><span data-stu-id="f2736-126">Overloading Operator ==</span></span>  
 <span data-ttu-id="f2736-127">Überladen von `operator ==` ist ziemlich kompliziert.</span><span class="sxs-lookup"><span data-stu-id="f2736-127">Overloading `operator ==` is quite complicated.</span></span> <span data-ttu-id="f2736-128">Die Semantik des Operators müssen als kompatibel mit mehrere andere Member, z. B. <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f2736-128">The semantics of the operator need to be compatible with several other members, such as <xref:System.Object.Equals%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="conversion-operators"></a><span data-ttu-id="f2736-129">Konvertierungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="f2736-129">Conversion Operators</span></span>  
 <span data-ttu-id="f2736-130">Konvertierungsoperatoren sind unäre Operatoren, die Konvertierung von einem Typ in einen anderen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="f2736-130">Conversion operators are unary operators that allow conversion from one type to another.</span></span> <span data-ttu-id="f2736-131">Die Operatoren müssen als statische Member auf den Operanden oder der Rückgabetyp definiert werden.</span><span class="sxs-lookup"><span data-stu-id="f2736-131">The operators must be defined as static members on either the operand or the return type.</span></span> <span data-ttu-id="f2736-132">Es gibt zwei Typen von Konvertierungsoperatoren: implizite und explizite.</span><span class="sxs-lookup"><span data-stu-id="f2736-132">There are two types of conversion operators: implicit and explicit.</span></span>  
  
 <span data-ttu-id="f2736-133">**X DO NOT** Geben Sie einen Konvertierungsoperator aus, wenn eine solche Konvertierung nicht eindeutig von den Endbenutzern erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="f2736-133">**X DO NOT** provide a conversion operator if such conversion is not clearly expected by the end users.</span></span>  
  
 <span data-ttu-id="f2736-134">**X DO NOT** Konvertierungsoperatoren außerhalb der Domäne des Typs definiert.</span><span class="sxs-lookup"><span data-stu-id="f2736-134">**X DO NOT** define conversion operators outside of a type’s domain.</span></span>  
  
 <span data-ttu-id="f2736-135">Z. B. <xref:System.Int32>, <xref:System.Double>, und <xref:System.Decimal> alle numerische Typen sind, während <xref:System.DateTime> nicht.</span><span class="sxs-lookup"><span data-stu-id="f2736-135">For example, <xref:System.Int32>, <xref:System.Double>, and <xref:System.Decimal> are all numeric types, whereas <xref:System.DateTime> is not.</span></span> <span data-ttu-id="f2736-136">Daher dürfte kein Konvertierungsoperator zum Konvertieren einer `Double(long)` zu einem `DateTime`.</span><span class="sxs-lookup"><span data-stu-id="f2736-136">Therefore, there should be no conversion operator to convert a `Double(long)` to a `DateTime`.</span></span> <span data-ttu-id="f2736-137">Ein Konstruktor wird in diesem Fall bevorzugt.</span><span class="sxs-lookup"><span data-stu-id="f2736-137">A constructor is preferred in such a case.</span></span>  
  
 <span data-ttu-id="f2736-138">**X DO NOT** Geben Sie einen impliziten Konvertierungsoperator, wenn die Konvertierung potenziell lossy ist.</span><span class="sxs-lookup"><span data-stu-id="f2736-138">**X DO NOT** provide an implicit conversion operator if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="f2736-139">Beispielsweise gibt es keine muss eine implizite Konvertierung von `Double` zu `Int32` da `Double` hat einen größeren Bereich als `Int32`.</span><span class="sxs-lookup"><span data-stu-id="f2736-139">For example, there should not be an implicit conversion from `Double` to `Int32` because `Double` has a wider range than `Int32`.</span></span> <span data-ttu-id="f2736-140">Ein expliziten Konvertierungsoperator kann angegeben werden, auch wenn die Konvertierung Datenverlust auftreten kann.</span><span class="sxs-lookup"><span data-stu-id="f2736-140">An explicit conversion operator can be provided even if the conversion is potentially lossy.</span></span>  
  
 <span data-ttu-id="f2736-141">**X DO NOT** lösen Ausnahmen aus implizite Umwandlungen.</span><span class="sxs-lookup"><span data-stu-id="f2736-141">**X DO NOT** throw exceptions from implicit casts.</span></span>  
  
 <span data-ttu-id="f2736-142">Es ist sehr schwierig für Endbenutzer zu verstehen, was passiert, da sie nicht bewusst sein könnten, dass eine Konvertierung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="f2736-142">It is very difficult for end users to understand what is happening, because they might not be aware that a conversion is taking place.</span></span>  
  
 <span data-ttu-id="f2736-143">**✓ DO** auslösen <xref:System.InvalidCastException?displayProperty=nameWithType> Wenn ein Aufruf an ein Cast-Operator eine verlustbehaftete Konvertierung führt und der Vertrag des Operators lossy Konvertierungen nicht zulässt.</span><span class="sxs-lookup"><span data-stu-id="f2736-143">**✓ DO** throw <xref:System.InvalidCastException?displayProperty=nameWithType> if a call to a cast operator results in a lossy conversion and the contract of the operator does not allow lossy conversions.</span></span>  
  
 <span data-ttu-id="f2736-144">*Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*</span><span class="sxs-lookup"><span data-stu-id="f2736-144">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="f2736-145">*Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*</span><span class="sxs-lookup"><span data-stu-id="f2736-145">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2736-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2736-146">See also</span></span>

- [<span data-ttu-id="f2736-147">Entwurfsrichtlinien für Member</span><span class="sxs-lookup"><span data-stu-id="f2736-147">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="f2736-148">Frameworkentwurfsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="f2736-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
