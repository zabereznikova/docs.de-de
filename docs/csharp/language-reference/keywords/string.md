---
title: string (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- string
- string_CSharpKeyword
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
ms.openlocfilehash: ab2e69c60872aed19d46450f17becc918ffe2a38
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181458"
---
# <a name="string-c-reference"></a><span data-ttu-id="c2ac0-102">string (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c2ac0-102">string (C# Reference)</span></span>

<span data-ttu-id="c2ac0-103">Der Typ `string` stellt eine Sequenz von Null oder mehr Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-103">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="c2ac0-104">`string` ist ein Alias für <xref:System.String> in .NET.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-104">`string` is an alias for <xref:System.String> in .NET.</span></span>

<span data-ttu-id="c2ac0-105">Obwohl `string` ein Verweistyp ist, werden die Gleichheitsoperatoren (`==` und `!=`) zum Vergleichen der Werte von `string`-Objekten, nicht von Verweisen, definiert.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-105">Although `string` is a reference type, the equality operators (`==` and `!=`) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="c2ac0-106">Dadurch wird das Testen auf Zeichenfolgengleichheit intuitiver.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-106">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="c2ac0-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c2ac0-107">For example:</span></span>

```csharp
string a = "hello";
string b = "h";
// Append to contents of 'b'
b += "ello";
Console.WriteLine(a == b);
Console.WriteLine((object)a == (object)b);
```

<span data-ttu-id="c2ac0-108">Dies zeigt TRUE und anschließend FALSE an, weil der Inhalt der Zeichenfolgen gleich sind. Jedoch verweisen `a` und `b` nicht auf die gleiche Zeichenfolgeninstanz.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-108">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>

<span data-ttu-id="c2ac0-109">Der Operator „+“ verkettet Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="c2ac0-109">The + operator concatenates strings:</span></span>

```csharp
string a = "good " + "morning";
```

<span data-ttu-id="c2ac0-110">Dadurch wird ein Zeichenfolgenobjekt erstellt, das „Guten Morgen“ enthält.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-110">This creates a string object that contains "good morning".</span></span>

<span data-ttu-id="c2ac0-111">Zeichenfolgen sind *unveränderlich*. Die Inhalte eines Zeichenfolgenobjekts können nicht geändert werden, nachdem ein Objekt erstellt wurde, obwohl die Syntax den Eindruck erweckt, dass es machbar wäre.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-111">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="c2ac0-112">Wenn Sie z.B. diesen Code schreiben, erstellt der Compiler tatsächlich ein neues Zeichenfolgenobjekt, um die neue Zeichensequenz zu speichern. Das neue Objekt wird b zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-112">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to b.</span></span> <span data-ttu-id="c2ac0-113">Die Zeichenfolge „h“ ist anschließend für die automatische Speicherbereinigung auswählbar.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-113">The string "h" is then eligible for garbage collection.</span></span>

```csharp
string b = "h";
b += "ello";
```

<span data-ttu-id="c2ac0-114">Der []-Operator kann für schreibgeschützten Zugriff auf einzelne Zeichen eines `string` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c2ac0-114">The [] operator can be used for readonly access to individual characters of a `string`:</span></span>

```csharp
string str = "test";
char x = str[2];  // x = 's';
```

<span data-ttu-id="c2ac0-115">Zeichenfolgenliterale sind Typ `string` und können in zwei Formaten geschrieben werden: in Anführungszeichen und @-quoted.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-115">String literals are of type `string` and can be written in two forms, quoted and @-quoted.</span></span> <span data-ttu-id="c2ac0-116">Zeichenfolgenliterale in Anführungszeichen werden in doppelte Anführungszeichen (") eingeschlossen:</span><span class="sxs-lookup"><span data-stu-id="c2ac0-116">Quoted string literals are enclosed in double quotation marks ("):</span></span>

```csharp
"good morning"  // a string literal
```

<span data-ttu-id="c2ac0-117">Zeichenfolgenliterale können jeden Zeichenliteral enthalten.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-117">String literals can contain any character literal.</span></span> <span data-ttu-id="c2ac0-118">Escapesequenzen sind enthalten.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-118">Escape sequences are included.</span></span> <span data-ttu-id="c2ac0-119">Im folgenden Beispiel wird die Escapesequenz `\\` für den umgekehrten Schrägstrich, `\u0066` für den Buchstaben „f“ und `\n` für den Zeilenumbruch verwendet.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-119">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>

```csharp
string a = "\\\u0066\n";
Console.WriteLine(a);
```

> [!NOTE]
> <span data-ttu-id="c2ac0-120">Der Escapecode `\udddd` (wobei `dddd` eine vierstellige Zahl ist) stellt das Unicode-Zeichen U+`dddd` dar.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-120">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="c2ac0-121">Escapecodes aus achtstelligen Unicode werden auch erkannt: `\Udddddddd`.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-121">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>

<span data-ttu-id="c2ac0-122">Wörtliche Zeichenfolgenliterale beginnen mit `@` und sind ebenfalls in doppelte Anführungszeichen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c2ac0-122">Verbatim string literals start with `@` and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="c2ac0-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c2ac0-123">For example:</span></span>

```csharp
@"good morning"  // a string literal
```

<span data-ttu-id="c2ac0-124">Der Vorteil von wörtlichen Zeichenfolgen besteht darin, dass Escapesequenzen *nicht* verarbeitet werden, wodurch z.B. das Schreiben eines vollqualifizierten Dateinamens erleichtert wird:</span><span class="sxs-lookup"><span data-stu-id="c2ac0-124">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified file name:</span></span>

```csharp
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"
```

<span data-ttu-id="c2ac0-125">Verdoppeln Sie das doppelte Anführungszeichen, um es in einer @-quoted-Zeichenfolge aufzunehmen:</span><span class="sxs-lookup"><span data-stu-id="c2ac0-125">To include a double quotation mark in an @-quoted string, double it:</span></span>

```csharp
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.
```

<span data-ttu-id="c2ac0-126">Informationen zu anderen Verwendungsmöglichkeiten des Sonderzeichens `@` finden Sie unter [@ -- verbatim identifier (@ (wörtlicher Bezeichner))](../tokens/verbatim.md).</span><span class="sxs-lookup"><span data-stu-id="c2ac0-126">For other uses of the `@` special character, see [@ -- verbatim identifier](../tokens/verbatim.md).</span></span>

<span data-ttu-id="c2ac0-127">Weitere Informationen zu Zeichenfolgen in C# finden Sie unter [Zeichenfolgen](../../programming-guide/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="c2ac0-127">For more information about strings in C#, see [Strings](../../programming-guide/strings/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="c2ac0-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c2ac0-128">Example</span></span>

[!code-csharp[csrefKeywordsTypes#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#17)]  

## <a name="c-language-specification"></a><span data-ttu-id="c2ac0-129">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c2ac0-129">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="c2ac0-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2ac0-130">See also</span></span>

- [<span data-ttu-id="c2ac0-131">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c2ac0-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c2ac0-132">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c2ac0-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c2ac0-133">Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="c2ac0-133">Best Practices for Using Strings</span></span>](../../../standard/base-types/best-practices-strings.md)
- [<span data-ttu-id="c2ac0-134">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c2ac0-134">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c2ac0-135">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c2ac0-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c2ac0-136">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="c2ac0-136">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="c2ac0-137">Werttypen</span><span class="sxs-lookup"><span data-stu-id="c2ac0-137">Value Types</span></span>](value-types.md)
- [<span data-ttu-id="c2ac0-138">Grundlegende Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="c2ac0-138">Basic String Operations</span></span>](../../../standard/base-types/basic-string-operations.md)
- [<span data-ttu-id="c2ac0-139">Erstellen neuer Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="c2ac0-139">Creating New Strings</span></span>](../../../standard/base-types/creating-new.md)
- [<span data-ttu-id="c2ac0-140">Tabelle zur Formatierung numerischer Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="c2ac0-140">Formatting Numeric Results Table</span></span>](formatting-numeric-results-table.md)