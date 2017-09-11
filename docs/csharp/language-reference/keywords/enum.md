---
title: enum (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- enum
- enum_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- enum keyword [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
caps.latest.revision: 36
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cf12724ec9e450a2bc237db614f235d7f03a4a7e
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="enum-c-reference"></a><span data-ttu-id="bc394-102">enum (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bc394-102">enum (C# Reference)</span></span>
<span data-ttu-id="bc394-103">Das Schlüsselwort `enum` wird zum Deklarieren einer Enumeration verwendet. Dies ist ein eigener Typ, der aus einer Gruppe benannter Konstanten besteht, die Enumeratorliste genannt wird.</span><span class="sxs-lookup"><span data-stu-id="bc394-103">The `enum` keyword is used to declare an enumeration, a distinct type that consists of a set of named constants called the enumerator list.</span></span>  
  
 <span data-ttu-id="bc394-104">In der Regel ist es am besten, eine Enumeration direkt innerhalb eines Namespaces so zu definieren, dass alle Klassen im Namespace auf gleiche Weise darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="bc394-104">Usually it is best to define an enum directly within a namespace so that all classes in the namespace can access it with equal convenience.</span></span> <span data-ttu-id="bc394-105">Eine Enumeration kann aber auch innerhalb einer Klasse oder einer Struktur geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="bc394-105">However, an enum can also be nested within a class or struct.</span></span>  
  
 <span data-ttu-id="bc394-106">Der erste Enumerator hat standardmäßig den Wert 0. Der Wert jedes nachfolgenden Enumerators wird um 1 erhöht.</span><span class="sxs-lookup"><span data-stu-id="bc394-106">By default, the first enumerator has the value 0, and the value of each successive enumerator is increased by 1.</span></span> <span data-ttu-id="bc394-107">In der folgenden Enumeration gilt z. B.: `Sat` ist `0`, `Sun` ist `1`, `Mon` ist `2`usw.</span><span class="sxs-lookup"><span data-stu-id="bc394-107">For example, in the following enumeration, `Sat` is `0`, `Sun` is `1`, `Mon` is `2`, and so forth.</span></span>  
  
```  
enum Days {Sat, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 <span data-ttu-id="bc394-108">Enumeratoren können mithilfe von Initialisierern die Standardwerte überschreiben, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc394-108">Enumerators can use initializers to override the default values, as shown in the following example.</span></span>  
  
```  
enum Days {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 <span data-ttu-id="bc394-109">In dieser Enumeration wird erzwungen, dass die Abfolge von Elementen mit `1` und nicht mit `0`beginnt.</span><span class="sxs-lookup"><span data-stu-id="bc394-109">In this enumeration, the sequence of elements is forced to start from `1` instead of `0`.</span></span> <span data-ttu-id="bc394-110">Allerdings wird das Einfügen einer Konstanten mit dem Wert 0 empfohlen.</span><span class="sxs-lookup"><span data-stu-id="bc394-110">However, including a constant that has the value of 0 is recommended.</span></span> <span data-ttu-id="bc394-111">Weitere Informationen finden Sie unter [Enumerationstypen](../../../csharp/programming-guide/enumeration-types.md).</span><span class="sxs-lookup"><span data-stu-id="bc394-111">For more information, see [Enumeration Types](../../../csharp/programming-guide/enumeration-types.md).</span></span>  
  
 <span data-ttu-id="bc394-112">Jeder Enumerationstyp hat einen zugrunde liegenden Typ, bei dem es sich um jeden ganzzahligen Typ außer [char](../../../csharp/language-reference/keywords/char.md) handeln kann.</span><span class="sxs-lookup"><span data-stu-id="bc394-112">Every enumeration type has an underlying type, which can be any integral type except [char](../../../csharp/language-reference/keywords/char.md).</span></span> <span data-ttu-id="bc394-113">Der zugrunde liegende Standardtyp von Enumerationselementen ist [int](../../../csharp/language-reference/keywords/int.md).</span><span class="sxs-lookup"><span data-stu-id="bc394-113">The default underlying type of enumeration elements is [int](../../../csharp/language-reference/keywords/int.md).</span></span> <span data-ttu-id="bc394-114">Um eine Enumeration eines anderen ganzzahligen Typs, z. B. [byte](../../../csharp/language-reference/keywords/byte.md)zu deklarieren, setzen Sie einen Doppelpunkt hinter dem Bezeichner, auf den der Typ folgt, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc394-114">To declare an enum of another integral type, such as [byte](../../../csharp/language-reference/keywords/byte.md), use a colon after the identifier followed by the type, as shown in the following example.</span></span>  
  
```  
enum Days : byte {Sat=1, Sun, Mon, Tue, Wed, Thu, Fri};  
```  
  
 <span data-ttu-id="bc394-115">Die zulässigen Typen für eine Enumeration sind `byte`, [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md)und [ulong](../../../csharp/language-reference/keywords/ulong.md).</span><span class="sxs-lookup"><span data-stu-id="bc394-115">The approved types for an enum are `byte`, [sbyte](../../../csharp/language-reference/keywords/sbyte.md), [short](../../../csharp/language-reference/keywords/short.md), [ushort](../../../csharp/language-reference/keywords/ushort.md), [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
 <span data-ttu-id="bc394-116">Einer Variablen des Typs `Days` kann jeder Wert im Werbebereich des zugrunde liegenden Typs zugewiesen werden. Die Werte sind nicht auf benannte Konstanten beschränkt.</span><span class="sxs-lookup"><span data-stu-id="bc394-116">A variable of type `Days` can be assigned any value in the range of the underlying type; the values are not limited to the named constants.</span></span>  
  
 <span data-ttu-id="bc394-117">Der Standardwert von `enum E` ist der Wert, der vom Ausdruck `(E)0`erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="bc394-117">The default value of an `enum E` is the value produced by the expression `(E)0`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc394-118">Namen von Enumeratoren dürfen keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc394-118">An enumerator cannot contain white space in its name.</span></span>  
  
 <span data-ttu-id="bc394-119">Der zugrunde liegende Typ gibt an, wie viel Speicher für jeden Enumerator reserviert wird.</span><span class="sxs-lookup"><span data-stu-id="bc394-119">The underlying type specifies how much storage is allocated for each enumerator.</span></span> <span data-ttu-id="bc394-120">Eine explizite Typumwandlung ist jedoch erforderlich, um einen `enum` -Typ in einen ganzzahligen Typ zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="bc394-120">However, an explicit cast is necessary to convert from `enum` type to an integral type.</span></span> <span data-ttu-id="bc394-121">Durch die folgende Anweisung wird der `Sun` -Enumerator beispielsweise einer Variablen des Typs [int](../../../csharp/language-reference/keywords/int.md) zugewiesen. Dabei erfolgt für die Konvertierung von `enum` in `int`eine Typumwandlung.</span><span class="sxs-lookup"><span data-stu-id="bc394-121">For example, the following statement assigns the enumerator `Sun` to a variable of the type [int](../../../csharp/language-reference/keywords/int.md) by using a cast to convert from `enum` to `int`.</span></span>  
  
```  
int x = (int)Days.Sun;  
```  
  
 <span data-ttu-id="bc394-122">Wenn <xref:System.FlagsAttribute?displayProperty=fullName> auf eine Enumeration mit Elementen angewendet wird, die mit einer bitweisen `OR` -Operation kombiniert werden können, beeinflusst das Attribut das Verhalten von `enum` bei der Verwendung bestimmter Tools.</span><span class="sxs-lookup"><span data-stu-id="bc394-122">When you apply <xref:System.FlagsAttribute?displayProperty=fullName> to an enumeration that contains elements that can be combined with a bitwise `OR` operation, the attribute affects the behavior of the `enum` when it is used with some tools.</span></span> <span data-ttu-id="bc394-123">Solche Änderungen sind bei Verwendung von Tools wie den Methoden der <xref:System.Console> -Klasse und der Ausdrucksauswertung zu beobachten.</span><span class="sxs-lookup"><span data-stu-id="bc394-123">You can notice these changes when you use tools such as the <xref:System.Console> class methods and the Expression Evaluator.</span></span> <span data-ttu-id="bc394-124">(Siehe das dritte Beispiel.)</span><span class="sxs-lookup"><span data-stu-id="bc394-124">(See the third example.)</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="bc394-125">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="bc394-125">Robust Programming</span></span>  
 <span data-ttu-id="bc394-126">Wie bei Konstanten werden zur Kompilierzeit alle Verweise auf die einzelnen Werte einer Enumeration in numerische Literale konvertiert.</span><span class="sxs-lookup"><span data-stu-id="bc394-126">Just as with any constant, all references to the individual values of an enum are converted to numeric literals at compile time.</span></span> <span data-ttu-id="bc394-127">Dies kann, wie unter [Konstanten](../../../csharp/programming-guide/classes-and-structs/constants.md) beschrieben, zu möglichen Versionsproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="bc394-127">This can create potential versioning issues as described in [Constants](../../../csharp/programming-guide/classes-and-structs/constants.md).</span></span>  
  
 <span data-ttu-id="bc394-128">Das Zuweisen zusätzlicher Werte zu neuen Enumerationsversionen oder das Ändern der Werte von Enumerationsmembern in einer neuen Version kann für abhängigen Quellcode Probleme verursachen.</span><span class="sxs-lookup"><span data-stu-id="bc394-128">Assigning additional values to new versions of enums, or changing the values of the enum members in a new version, can cause problems for dependent source code.</span></span> <span data-ttu-id="bc394-129">Enumerationswerte werden oft in [switch](../../../csharp/language-reference/keywords/switch.md) -Anweisungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="bc394-129">Enum values often are used in [switch](../../../csharp/language-reference/keywords/switch.md) statements.</span></span> <span data-ttu-id="bc394-130">Wenn dem `enum` -Typ weitere Elemente hinzugefügt wurden, kann der Standardabschnitt der „switch“-Anweisung unerwartet ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="bc394-130">If additional elements have been added to the `enum` type, the default section of the switch statement can be selected unexpectedly.</span></span>  
  
 <span data-ttu-id="bc394-131">Falls andere Entwickler Ihren Code verwenden, sollten Sie Richtlinien festlegen, die angeben, wie deren Code reagieren soll, wenn `enum` -Typen neue Elemente hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bc394-131">If other developers use your code, you should provide guidelines about how their code should react if new elements are added to any `enum` types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc394-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc394-132">Example</span></span>  
 <span data-ttu-id="bc394-133">Im folgenden Beispiel wird die Enumeration `Days`deklariert.</span><span class="sxs-lookup"><span data-stu-id="bc394-133">In the following example, an enumeration, `Days`, is declared.</span></span> <span data-ttu-id="bc394-134">Zwei Enumeratoren werden explizit in ganze Zahlen konvertiert und „Integer“-Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="bc394-134">Two enumerators are explicitly converted to integer and assigned to integer variables.</span></span>  
  
 <span data-ttu-id="bc394-135">[!code-cs[csrefKeywordsTypes#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="bc394-135">[!code-cs[csrefKeywordsTypes#10](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc394-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc394-136">Example</span></span>  
 <span data-ttu-id="bc394-137">Im folgenden Beispiel wird die Basistypoption verwendet, um ein `enum` zu deklarieren, dessen Member den Typ `long`haben.</span><span class="sxs-lookup"><span data-stu-id="bc394-137">In the following example, the base-type option is used to declare an `enum` whose members are of type `long`.</span></span> <span data-ttu-id="bc394-138">Beachten Sie, dass obwohl der Enumeration der Typ `long`zugrunde liegt, die Enumerationsmember noch explizit mithilfe einer Typumwandlung in den Typ `long` umgewandelt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bc394-138">Notice that even though the underlying type of the enumeration is `long`, the enumeration members still must be explicitly converted to type `long` by using a cast.</span></span>  
  
 <span data-ttu-id="bc394-139">[!code-cs[csrefKeywordsTypes#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="bc394-139">[!code-cs[csrefKeywordsTypes#11](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_2.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc394-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc394-140">Example</span></span>  
 <span data-ttu-id="bc394-141">Im folgenden Codebeispiel werden die Verwendung des <xref:System.FlagsAttribute?displayProperty=fullName> -Attributs in einer `enum` -Deklaration und seine Wirkung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bc394-141">The following code example illustrates the use and effect of the <xref:System.FlagsAttribute?displayProperty=fullName> attribute on an `enum` declaration.</span></span>  
  
 <span data-ttu-id="bc394-142">[!code-cs[csrefKeywordsTypes#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="bc394-142">[!code-cs[csrefKeywordsTypes#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/enum_3.cs)]</span></span>  
  
## <a name="comments"></a><span data-ttu-id="bc394-143">Kommentare</span><span class="sxs-lookup"><span data-stu-id="bc394-143">Comments</span></span>  
 <span data-ttu-id="bc394-144">Wenn Sie `Flags`entfernen, werden im Beispiel die folgenden Werte angezeigt:</span><span class="sxs-lookup"><span data-stu-id="bc394-144">If you remove `Flags`, the example displays the following values:</span></span>  
  
 `5`  
  
 `5`  
  
## <a name="c-language-specification"></a><span data-ttu-id="bc394-145">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="bc394-145">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bc394-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc394-146">See Also</span></span>  
 <span data-ttu-id="bc394-147">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="bc394-147">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="bc394-148">[Enumerationstypen](../../../csharp/programming-guide/enumeration-types.md) </span><span class="sxs-lookup"><span data-stu-id="bc394-148">[Enumeration Types](../../../csharp/programming-guide/enumeration-types.md) </span></span>  
 <span data-ttu-id="bc394-149">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="bc394-149">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="bc394-150">[Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="bc394-150">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="bc394-151">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="bc394-151">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="bc394-152">[Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="bc394-152">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="bc394-153">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="bc394-153">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)

