---
title: Integrierte Verweistypen – C#-Referenz
description: Hier erhalten Sie Informationen zu Verweistypen mit C#-Schlüsselwörtern, die Sie zu deren Deklaration verwenden können.
ms.date: 06/25/2019
f1_keywords:
- object_CSharpKeyword
- object
- delegate_CSharpKeyword
- delegate
- dynamic_CSharpKeyword
- string
- string_CSharpKeyword
helpviewer_keywords:
- object keyword [C#]
- delegate keyword [C#]
- function pointers [C#]
- dynamic [C#]
- dynamic keyword [C#]
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.openlocfilehash: d8858acb2743b26cc3a5172edf4765976d81adf4
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2019
ms.locfileid: "73973013"
---
# <a name="built-in-reference-types-c-reference"></a><span data-ttu-id="b4efd-103">Integrierte Verweistypen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b4efd-103">Built-in reference types (C# reference)</span></span>

<span data-ttu-id="b4efd-104">C# enthält eine Reihe von integrierten Verweistypen.</span><span class="sxs-lookup"><span data-stu-id="b4efd-104">C# has a number of built-in reference types.</span></span> <span data-ttu-id="b4efd-105">Diese enthalten Schlüsselwörter oder Operatoren, die Synonyme für einen Typ in der .NET-Bibliothek sind.</span><span class="sxs-lookup"><span data-stu-id="b4efd-105">They have keywords or operators that are synonyms for a type in the .NET library.</span></span> 

## <a name="the-object-type"></a><span data-ttu-id="b4efd-106">Der Objekttyp</span><span class="sxs-lookup"><span data-stu-id="b4efd-106">The object type</span></span>

<span data-ttu-id="b4efd-107">Der `object`-Typ ist ein Alias für <xref:System.Object?displayProperty=nameWithType> in .NET.</span><span class="sxs-lookup"><span data-stu-id="b4efd-107">The `object` type is an alias for <xref:System.Object?displayProperty=nameWithType> in .NET.</span></span> <span data-ttu-id="b4efd-108">Im vereinheitlichen Typsystem von C# erben alle Typen, vordefiniert und benutzerdefiniert sowie Verweis- und Werttypen, direkt oder indirekt von <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b4efd-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b4efd-109">Sie können Werte eines beliebigen Typs Variablen des Typs `object` zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b4efd-109">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="b4efd-110">Diesem Standardwert kann mithilfe des Literals `null` eine beliebige `object`-Variable zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b4efd-110">Any `object` variable can be assigned to its default value using the literal `null`.</span></span> <span data-ttu-id="b4efd-111">Wenn eine Variable eines Werttyps in ein Objekt konvertiert wird, gilt es als *geschachtelt*.</span><span class="sxs-lookup"><span data-stu-id="b4efd-111">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="b4efd-112">Wenn eine Variable eines Typobjekts in ein Wertobjekt konvertiert wird, gilt es als *nicht geschachtelt*.</span><span class="sxs-lookup"><span data-stu-id="b4efd-112">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="b4efd-113">Weitere Informationen finden Sie unter [Boxing und Unboxing](../../programming-guide/types/boxing-and-unboxing.md).</span><span class="sxs-lookup"><span data-stu-id="b4efd-113">For more information, see [Boxing and Unboxing](../../programming-guide/types/boxing-and-unboxing.md).</span></span> 

## <a name="the-string-type"></a><span data-ttu-id="b4efd-114">Der Zeichenfolgentyp</span><span class="sxs-lookup"><span data-stu-id="b4efd-114">The string type</span></span>

<span data-ttu-id="b4efd-115">Der Typ `string` stellt eine Sequenz von Null oder mehr Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="b4efd-115">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="b4efd-116">`string` ist ein Alias für <xref:System.String?displayProperty=nameWithType> in .NET.</span><span class="sxs-lookup"><span data-stu-id="b4efd-116">`string` is an alias for <xref:System.String?displayProperty=nameWithType> in .NET.</span></span>

<span data-ttu-id="b4efd-117">Obwohl `string` ein Verweistyp ist, werden die [Gleichheitsoperatoren`==` und `!=`](../operators/equality-operators.md#string-equality) zum Vergleichen der Werte von `string`-Objekten, nicht von Verweisen, definiert.</span><span class="sxs-lookup"><span data-stu-id="b4efd-117">Although `string` is a reference type, the [equality operators `==` and `!=`](../operators/equality-operators.md#string-equality) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="b4efd-118">Dadurch wird das Testen auf Zeichenfolgengleichheit intuitiver.</span><span class="sxs-lookup"><span data-stu-id="b4efd-118">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="b4efd-119">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b4efd-119">For example:</span></span>

```csharp-interactive
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine(object.ReferenceEquals(a, b));
```

<span data-ttu-id="b4efd-120">Dies zeigt TRUE und anschließend FALSE an, weil der Inhalt der Zeichenfolgen gleich sind. Jedoch verweisen `a` und `b` nicht auf die gleiche Zeichenfolgeninstanz.</span><span class="sxs-lookup"><span data-stu-id="b4efd-120">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>

<span data-ttu-id="b4efd-121">Der [Operator „+“](../operators/addition-operator.md#string-concatenation) verkettet Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="b4efd-121">The [+ operator](../operators/addition-operator.md#string-concatenation) concatenates strings:</span></span>

```csharp
string a = "good " + "morning";
```

<span data-ttu-id="b4efd-122">Dadurch wird ein Zeichenfolgenobjekt erstellt, das „Guten Morgen“ enthält.</span><span class="sxs-lookup"><span data-stu-id="b4efd-122">This creates a string object that contains "good morning".</span></span>

<span data-ttu-id="b4efd-123">Zeichenfolgen sind *unveränderlich*. Die Inhalte eines Zeichenfolgenobjekts können nicht geändert werden, nachdem ein Objekt erstellt wurde, obwohl die Syntax den Eindruck erweckt, dass es machbar wäre.</span><span class="sxs-lookup"><span data-stu-id="b4efd-123">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="b4efd-124">Wenn Sie z. B. diesen Code schreiben, erstellt der Compiler tatsächlich ein neues Zeichenfolgenobjekt, um die neue Zeichensequenz zu speichern. Das neue Objekt wird `b` zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="b4efd-124">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to `b`.</span></span> <span data-ttu-id="b4efd-125">Der Speicherplatz, der `b` zugeordnet wurde (sofern die Zeichenfolge „h“ enthalten war), hat dann Anspruch auf die Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="b4efd-125">The memory that had been allocated for `b` (when it contained the string "h") is then eligible for garbage collection.</span></span>

```csharp
string b = "h";
b += "ello";
```

<span data-ttu-id="b4efd-126">Der `[]`-[Operator](../operators/member-access-operators.md#indexer-operator-) kann für schreibgeschützten Zugriff auf einzelne Zeichen eines `string` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="b4efd-126">The `[]` [operator](../operators/member-access-operators.md#indexer-operator-) can be used for readonly access to individual characters of a `string`.</span></span> <span data-ttu-id="b4efd-127">Gültige Werte beginnen bei `0` und müssen eine Länge kleiner als die von `string` aufweisen:</span><span class="sxs-lookup"><span data-stu-id="b4efd-127">Valid values start at `0` and must be less than the length of the `string`:</span></span>

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

<span data-ttu-id="b4efd-128">Auf gleiche Weise kann der `[]`-Operator auch für das Durchlaufen jedes Zeichens in `string` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="b4efd-128">In similar fashion, the `[]` operator can also be used for iterating over each character in a `string`:</span></span>

```csharp-interactive
string str = "test";

for (int i = 0; i < str.Length; i++)
{
  Console.Write(str[i] + " ");
}
// Output: t e s t
``` 

<span data-ttu-id="b4efd-129">Zeichenfolgenliterale sind Typ `string` und können in zwei Formaten geschrieben werden: in Anführungszeichen und mit `@`.</span><span class="sxs-lookup"><span data-stu-id="b4efd-129">String literals are of type `string` and can be written in two forms, quoted and `@`-quoted.</span></span> <span data-ttu-id="b4efd-130">Zeichenfolgenliterale in Anführungszeichen werden in doppelte Anführungszeichen (") eingeschlossen:</span><span class="sxs-lookup"><span data-stu-id="b4efd-130">Quoted string literals are enclosed in double quotation marks ("):</span></span>

```csharp
"good morning"  // a string literal
```

<span data-ttu-id="b4efd-131">Zeichenfolgenliterale können jeden Zeichenliteral enthalten.</span><span class="sxs-lookup"><span data-stu-id="b4efd-131">String literals can contain any character literal.</span></span> <span data-ttu-id="b4efd-132">Escapesequenzen sind enthalten.</span><span class="sxs-lookup"><span data-stu-id="b4efd-132">Escape sequences are included.</span></span> <span data-ttu-id="b4efd-133">Im folgenden Beispiel wird die Escapesequenz `\\` für den umgekehrten Schrägstrich, `\u0066` für den Buchstaben „f“ und `\n` für den Zeilenumbruch verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4efd-133">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>

```csharp-interactive
string a = "\\\u0066\n F";
Console.WriteLine(a);
\\ Output:
\\ \f
\\  F
```

> [!NOTE]
> <span data-ttu-id="b4efd-134">Der Escapecode `\udddd` (wobei `dddd` eine vierstellige Zahl ist) stellt das Unicode-Zeichen U+`dddd` dar.</span><span class="sxs-lookup"><span data-stu-id="b4efd-134">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="b4efd-135">Escapecodes aus achtstelligen Unicode werden auch erkannt: `\Udddddddd`.</span><span class="sxs-lookup"><span data-stu-id="b4efd-135">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>

<span data-ttu-id="b4efd-136">[Wörtliche Zeichenfolgenliterale](../tokens/verbatim.md) beginnen mit `@` und sind ebenfalls in doppelte Anführungszeichen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b4efd-136">[Verbatim string literals](../tokens/verbatim.md) start with `@` and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="b4efd-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b4efd-137">For example:</span></span>

```csharp
@"good morning"  // a string literal
```

<span data-ttu-id="b4efd-138">Der Vorteil von wörtlichen Zeichenfolgen besteht darin, dass Escapesequenzen *nicht* verarbeitet werden, wodurch z. B. das Schreiben eines vollqualifizierten Windows-Dateinamens erleichtert wird:</span><span class="sxs-lookup"><span data-stu-id="b4efd-138">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified Windows file name:</span></span>

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

<span data-ttu-id="b4efd-139">Verdoppeln Sie das doppelte Anführungszeichen, um es in einer @-quoted-Zeichenfolge aufzunehmen:</span><span class="sxs-lookup"><span data-stu-id="b4efd-139">To include a double quotation mark in an @-quoted string, double it:</span></span>

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

## <a name="the-delegate-type"></a><span data-ttu-id="b4efd-140">Der Delegattyp</span><span class="sxs-lookup"><span data-stu-id="b4efd-140">The delegate type</span></span>

<span data-ttu-id="b4efd-141">Die Deklaration eines Delegattyps ähnelt einer Methodensignatur.</span><span class="sxs-lookup"><span data-stu-id="b4efd-141">The declaration of a delegate type is similar to a method signature.</span></span> <span data-ttu-id="b4efd-142">Er verfügt über einen Rückgabewert und eine beliebige Anzahl Parameter eines beliebigen Typs:</span><span class="sxs-lookup"><span data-stu-id="b4efd-142">It has a return value and any number of parameters of any type:</span></span>

```csharp
public delegate void MessageDelegate(string message);
public delegate int AnotherDelegate(MyType m, long num);
```

<span data-ttu-id="b4efd-143">In .NET stellen die Typen `System.Action` und `System.Func` generische Definitionen für zahlreiche allgemeine Delegaten bereit.</span><span class="sxs-lookup"><span data-stu-id="b4efd-143">In .NET, `System.Action` and `System.Func` types provide generic definitions for many common delegates.</span></span> <span data-ttu-id="b4efd-144">Sie werden sehr wahrscheinlich keine neuen benutzerdefinierten Delegattypen definieren müssen.</span><span class="sxs-lookup"><span data-stu-id="b4efd-144">You likely don't need to define new custom delegate types.</span></span> <span data-ttu-id="b4efd-145">Stattdessen können Sie Instanziierungen der bereitgestellten generischen Typen erstellen.</span><span class="sxs-lookup"><span data-stu-id="b4efd-145">Instead, you can create instantiations of the provided generic types.</span></span>

<span data-ttu-id="b4efd-146">Ein `delegate` ist ein Verweistyp, der verwendet werden kann, um eine benannte oder anonyme Methode zu kapseln.</span><span class="sxs-lookup"><span data-stu-id="b4efd-146">A `delegate` is a reference type that can be used to encapsulate a named or an anonymous method.</span></span> <span data-ttu-id="b4efd-147">Delegaten entsprechen den Funktionszeigern in C++, sind jedoch typsicher und geschützt.</span><span class="sxs-lookup"><span data-stu-id="b4efd-147">Delegates are similar to function pointers in C++; however, delegates are type-safe and secure.</span></span> <span data-ttu-id="b4efd-148">Anwendungsmöglichkeiten von Delegaten finden Sie unter [Delegaten](../../programming-guide/delegates/index.md) und [Generische Delegaten](../../programming-guide/generics/generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="b4efd-148">For applications of delegates, see [Delegates](../../programming-guide/delegates/index.md) and [Generic Delegates](../../programming-guide/generics/generic-delegates.md).</span></span> <span data-ttu-id="b4efd-149">Delegaten bilden die Grundlage für [Ereignisse](../../programming-guide/events/index.md).</span><span class="sxs-lookup"><span data-stu-id="b4efd-149">Delegates are the basis for [Events](../../programming-guide/events/index.md).</span></span> <span data-ttu-id="b4efd-150">Ein Delegat kann instanziiert werden, entweder durch Zuordnen mit einer benannten oder einer anonymen Methode.</span><span class="sxs-lookup"><span data-stu-id="b4efd-150">A delegate can be instantiated by associating it either with a named or anonymous method.</span></span>

<span data-ttu-id="b4efd-151">Der Delegat muss mit einer Methode oder einem Lambda-Ausdruck instanziiert werden, der über einen kompatiblen Rückgabetypen und Eingabeparameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="b4efd-151">The delegate must be instantiated with a method or lambda expression that has a compatible return type and input parameters.</span></span> <span data-ttu-id="b4efd-152">Weitere Informationen zum Grad der Varianz, der in der Methodensignatur zulässig ist, finden Sie unter [Varianz bei Delegaten](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="b4efd-152">For more information on the degree of variance that is allowed in the method signature, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).</span></span> <span data-ttu-id="b4efd-153">Für die Verwendung mit anonymen Methoden werden der Delegat und der Code, der mit ihm zugeordnet werden soll, zusammen deklariert.</span><span class="sxs-lookup"><span data-stu-id="b4efd-153">For use with anonymous methods, the delegate and the code to be associated with it are declared together.</span></span> 

## <a name="the-dynamic-type"></a><span data-ttu-id="b4efd-154">Der dynamische Typ</span><span class="sxs-lookup"><span data-stu-id="b4efd-154">The dynamic type</span></span>

<span data-ttu-id="b4efd-155">Der `dynamic`-Typ gibt an, dass durch die Verwendung der Variablen und Verweise auf die entsprechenden Member die Prüfung des Kompilierzeittyps umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="b4efd-155">The `dynamic` type indicates that use of the variable and references to its members bypass compile-time type checking.</span></span> <span data-ttu-id="b4efd-156">Stattdessen werden diese Vorgänge zur Laufzeit aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="b4efd-156">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="b4efd-157">Der `dynamic`-Typ vereinfacht den Zugriff auf COM-APIs, z. B. die Office Automation-APIs, auf dynamische APIs, beispielsweise IronPython-Bibliotheken und auf das HTML-Dokumentobjektmodell (Document Object Model, DOM).</span><span class="sxs-lookup"><span data-stu-id="b4efd-157">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>

<span data-ttu-id="b4efd-158">Der Typ `dynamic` verhält sich in den meisten Fällen wie Typ `object`.</span><span class="sxs-lookup"><span data-stu-id="b4efd-158">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="b4efd-159">Insbesondere können alle Ausdrücke, die nicht NULL sind, in den `dynamic`-Typ konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="b4efd-159">In particular, any non-null expression can be converted to the `dynamic` type.</span></span> <span data-ttu-id="b4efd-160">Der `dynamic`-Typ unterscheidet sich jedoch von `object` insofern, als dass Vorgänge, die Ausdrücke des Typs `dynamic` enthalten, nicht aufgelöst oder durch den Compiler typgeprüft werden.</span><span class="sxs-lookup"><span data-stu-id="b4efd-160">The `dynamic` type differs from `object` in that operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="b4efd-161">Der Compiler packt Informationen über den Vorgang. Diese Informationen werden später zur Evaluierung des Vorgangs zur Laufzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="b4efd-161">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="b4efd-162">Als Teil dieses Prozesses werden Variablen des Typs `dynamic` in Variablen des Typs `object` kompiliert.</span><span class="sxs-lookup"><span data-stu-id="b4efd-162">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="b4efd-163">Deshalb existiert der Typ `dynamic` nur zur Kompilierzeit und nicht zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="b4efd-163">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>

<span data-ttu-id="b4efd-164">Das folgende Beispiel vergleicht den Unterschied einer Variable des Typs `dynamic` mit einer Variable des Typs `object`.</span><span class="sxs-lookup"><span data-stu-id="b4efd-164">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="b4efd-165">Um den Typ jeder Variable zur Kompilierzeit zu überprüfen, zeigen Sie mit dem Mauszeiger auf `dyn` oder `obj` in den `WriteLine`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b4efd-165">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="b4efd-166">Kopieren Sie den folgenden Code in einen Editor, in dem IntelliSense verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="b4efd-166">Copy the following code into an editor where IntelliSense is available.</span></span> <span data-ttu-id="b4efd-167">IntelliSense zeigt **dynamic** für `dyn` und **object** für `obj`.</span><span class="sxs-lookup"><span data-stu-id="b4efd-167">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

<span data-ttu-id="b4efd-168">Die <xref:System.Console.WriteLine%2A>-Anweisungen zeigen die Laufzeittypen von `dyn` und `obj`.</span><span class="sxs-lookup"><span data-stu-id="b4efd-168">The <xref:System.Console.WriteLine%2A> statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="b4efd-169">Zu diesem Zeitpunkt verfügen beide denselben Typ, Integer.</span><span class="sxs-lookup"><span data-stu-id="b4efd-169">At that point, both have the same type, integer.</span></span> <span data-ttu-id="b4efd-170">Es wird die folgende Ausgabe generiert:</span><span class="sxs-lookup"><span data-stu-id="b4efd-170">The following output is produced:</span></span>

```console
System.Int32
System.Int32
```

<span data-ttu-id="b4efd-171">Um den Unterschied zwischen `dyn` und `obj` zur Kompilierzeit anzuzeigen, fügen Sie die folgenden zwei Zeilen zwischen die Deklarationen und die `WriteLine`-Anweisungen im vorherigen Beispiel ein.</span><span class="sxs-lookup"><span data-stu-id="b4efd-171">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 <span data-ttu-id="b4efd-172">Es wird ein Kompilierfehler für den Versuch, einen Integer und ein Objekt im Ausdruck `obj + 3` einzufügen, ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="b4efd-172">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="b4efd-173">Es wird jedoch kein Fehler für `dyn + 3` gemeldet.</span><span class="sxs-lookup"><span data-stu-id="b4efd-173">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="b4efd-174">Der Ausdruck, der `dyn` enthält, wird nicht zur Kompilierzeit überprüft, da der Typ von `dyn` `dynamic` ist.</span><span class="sxs-lookup"><span data-stu-id="b4efd-174">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>

<span data-ttu-id="b4efd-175">Das folgende Beispiel verwendet `dynamic` in einigen Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="b4efd-175">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="b4efd-176">Die `Main`-Methode unterscheidet auch die Typüberprüfung zur Kompilierzeit und die Laufzeittypüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="b4efd-176">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

### <a name="see-also"></a><span data-ttu-id="b4efd-177">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4efd-177">See also</span></span>

- [<span data-ttu-id="b4efd-178">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b4efd-178">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b4efd-179">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b4efd-179">C# Keywords</span></span>](../keywords/index.md)
- [<span data-ttu-id="b4efd-180">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="b4efd-180">Events</span></span>](../../programming-guide/events/index.md)
- [<span data-ttu-id="b4efd-181">Verwenden von dynamischen Typen</span><span class="sxs-lookup"><span data-stu-id="b4efd-181">Using Type dynamic</span></span>](../../programming-guide/types/using-type-dynamic.md)
- [<span data-ttu-id="b4efd-182">Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="b4efd-182">Best Practices for Using Strings</span></span>](../../../standard/base-types/best-practices-strings.md)
- [<span data-ttu-id="b4efd-183">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="b4efd-183">Basic String Operations</span></span>](../../../standard/base-types/basic-string-operations.md)
- [<span data-ttu-id="b4efd-184">Erstellen neuer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="b4efd-184">Creating New Strings</span></span>](../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="b4efd-185">Typtest- und Umwandlungsoperatoren</span><span class="sxs-lookup"><span data-stu-id="b4efd-185">Type-testing and cast operators</span></span>](../operators/type-testing-and-cast.md)
- [<span data-ttu-id="b4efd-186">Vorgehensweise: Sicheres Umwandeln mit Musterabgleich mit den Operatoren „as“ und „is“</span><span class="sxs-lookup"><span data-stu-id="b4efd-186">How to safely cast using pattern matching and the as and is operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [<span data-ttu-id="b4efd-187">Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten</span><span class="sxs-lookup"><span data-stu-id="b4efd-187">Walkthrough: creating and using dynamic objects</span></span>](../../programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
- <xref:System.Object?displayProperty=nameWithType>
- <xref:System.String?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
