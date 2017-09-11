---
title: string (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- string
- string_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- strings [C#], reference
- '@ string literal'
- string literals [C#]
- string keyword [C#]
ms.assetid: 3037e558-fb22-494d-bca1-a15ade11b11a
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 56847aad4cb8b0427594a299df2306d21675506b
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="string-c-reference"></a><span data-ttu-id="c225b-102">string (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c225b-102">string (C# Reference)</span></span>
<span data-ttu-id="c225b-103">Der Typ `string` stellt eine Sequenz von Null oder mehr Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="c225b-103">The `string` type represents a sequence of zero or more Unicode characters.</span></span> <span data-ttu-id="c225b-104">`string` ist ein Alias für <xref:System.String> in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c225b-104">`string` is an alias for <xref:System.String> in the .NET Framework.</span></span>  
  
 <span data-ttu-id="c225b-105">Obwohl `string` ein Verweistyp ist, werden die Gleichheitsoperatoren (`==` und `!=`) zum Vergleichen der Werte von `string`-Objekten, nicht von Verweisen, definiert.</span><span class="sxs-lookup"><span data-stu-id="c225b-105">Although `string` is a reference type, the equality operators (`==` and `!=`) are defined to compare the values of `string` objects, not references.</span></span> <span data-ttu-id="c225b-106">Dadurch wird das Testen auf Zeichenfolgengleichheit intuitiver.</span><span class="sxs-lookup"><span data-stu-id="c225b-106">This makes testing for string equality more intuitive.</span></span> <span data-ttu-id="c225b-107">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c225b-107">For example:</span></span>  
  
```csharp  
string a = "hello";  
string b = "h";  
// Append to contents of 'b'  
b += "ello";  
Console.WriteLine(a == b);  
Console.WriteLine((object)a == (object)b);  
```  
  
 <span data-ttu-id="c225b-108">Dies zeigt TRUE und anschließend FALSE an, weil der Inhalt der Zeichenfolgen gleich sind. Jedoch verweisen `a` und `b` nicht auf die gleiche Zeichenfolgeninstanz.</span><span class="sxs-lookup"><span data-stu-id="c225b-108">This displays "True" and then "False" because the content of the strings are equivalent, but `a` and `b` do not refer to the same string instance.</span></span>  
  
 <span data-ttu-id="c225b-109">Der Operator „+“ verkettet Zeichenfolgen:</span><span class="sxs-lookup"><span data-stu-id="c225b-109">The + operator concatenates strings:</span></span>  
  
```csharp  
string a = "good " + "morning";  
```  
  
 <span data-ttu-id="c225b-110">Dadurch wird ein Zeichenfolgenobjekt erstellt, das „Guten Morgen“ enthält.</span><span class="sxs-lookup"><span data-stu-id="c225b-110">This creates a string object that contains "good morning".</span></span>  
  
 <span data-ttu-id="c225b-111">Zeichenfolgen sind *unveränderlich*. Die Inhalte eines Zeichenfolgenobjekts können nicht geändert werden, nachdem ein Objekt erstellt wurde, obwohl die Syntax den Eindruck erweckt, dass es machbar wäre.</span><span class="sxs-lookup"><span data-stu-id="c225b-111">Strings are *immutable*--the contents of a string object cannot be changed after the object is created, although the syntax makes it appear as if you can do this.</span></span> <span data-ttu-id="c225b-112">Wenn Sie z.B. diesen Code schreiben, erstellt der Compiler tatsächlich ein neues Zeichenfolgenobjekt, um die neue Zeichensequenz zu speichern. Das neue Objekt wird b zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="c225b-112">For example, when you write this code, the compiler actually creates a new string object to hold the new sequence of characters, and that new object is assigned to b.</span></span> <span data-ttu-id="c225b-113">Die Zeichenfolge „h“ ist anschließend für die automatische Speicherbereinigung auswählbar.</span><span class="sxs-lookup"><span data-stu-id="c225b-113">The string "h" is then eligible for garbage collection.</span></span>  
  
```csharp
string b = "h";  
b += "ello";  
```  
  
 <span data-ttu-id="c225b-114">Der []-Operator kann für schreibgeschützten Zugriff auf einzelne Zeichen eines `string` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="c225b-114">The [] operator can be used for readonly access to individual characters of a `string`:</span></span>  
  
```csharp  
string str = "test";  
char x = str[2];  // x = 's';  
```  
  
 <span data-ttu-id="c225b-115">Zeichenfolgenliterale sind Typ `string` und können in zwei Formaten geschrieben werden: in Anführungszeichen und @-quoted.</span><span class="sxs-lookup"><span data-stu-id="c225b-115">String literals are of type `string` and can be written in two forms, quoted and @-quoted.</span></span> <span data-ttu-id="c225b-116">Zeichenfolgenliterale in Anführungszeichen werden in doppelte Anführungszeichen (") eingeschlossen:</span><span class="sxs-lookup"><span data-stu-id="c225b-116">Quoted string literals are enclosed in double quotation marks ("):</span></span>  
  
```csharp  
"good morning"  // a string literal  
```  
  
 <span data-ttu-id="c225b-117">Zeichenfolgenliterale können jeden Zeichenliteral enthalten.</span><span class="sxs-lookup"><span data-stu-id="c225b-117">String literals can contain any character literal.</span></span> <span data-ttu-id="c225b-118">Escapesequenzen sind enthalten.</span><span class="sxs-lookup"><span data-stu-id="c225b-118">Escape sequences are included.</span></span> <span data-ttu-id="c225b-119">Im folgenden Beispiel wird die Escapesequenz `\\` für den umgekehrten Schrägstrich, `\u0066` für den Buchstaben „f“ und `\n` für den Zeilenumbruch verwendet.</span><span class="sxs-lookup"><span data-stu-id="c225b-119">The following example uses escape sequence `\\` for backslash, `\u0066` for the letter f, and `\n` for newline.</span></span>  
  
```  
string a = "\\\u0066\n";  
Console.WriteLine(a);  
```  
  
> [!NOTE]
>  <span data-ttu-id="c225b-120">Der Escapecode `\udddd` (wobei `dddd` eine vierstellige Zahl ist) stellt das Unicode-Zeichen U+`dddd` dar.</span><span class="sxs-lookup"><span data-stu-id="c225b-120">The escape code `\udddd` (where `dddd` is a four-digit number) represents the Unicode character U+`dddd`.</span></span> <span data-ttu-id="c225b-121">Escapecodes aus achtstelligen Unicode werden auch erkannt: `\Udddddddd`.</span><span class="sxs-lookup"><span data-stu-id="c225b-121">Eight-digit Unicode escape codes are also recognized: `\Udddddddd`.</span></span>  
  
 <span data-ttu-id="c225b-122">Wörtliche Zeichenfolgenliterale beginnen mit @ und sind ebenfalls in doppelte Anführungszeichen eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="c225b-122">Verbatim string literals start with @ and are also enclosed in double quotation marks.</span></span> <span data-ttu-id="c225b-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c225b-123">For example:</span></span>  
  
```csharp  
@"good morning"  // a string literal  
```  
  
 <span data-ttu-id="c225b-124">Der Vorteil von wörtlichen Zeichenfolgen besteht darin, dass Escapesequenzen *nicht* verarbeitet werden, wodurch z.B. das Schreiben eines vollqualifizierten Dateinamens erleichtert wird:</span><span class="sxs-lookup"><span data-stu-id="c225b-124">The advantage of verbatim strings is that escape sequences are *not* processed, which makes it easy to write, for example, a fully qualified file name:</span></span>  
  
```csharp  
@"c:\Docs\Source\a.txt"  // rather than "c:\\Docs\\Source\\a.txt"  
```  
  
 <span data-ttu-id="c225b-125">Verdoppeln Sie das doppelte Anführungszeichen, um es in einer @-quoted-Zeichenfolge aufzunehmen:</span><span class="sxs-lookup"><span data-stu-id="c225b-125">To include a double quotation mark in an @-quoted string, double it:</span></span>  
  
```csharp  
@"""Ahoy!"" cried the captain." // "Ahoy!" cried the captain.  
```  
  
 <span data-ttu-id="c225b-126">Eine andere Verwendung des @-Symbols besteht darin, verwiesene ([/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)) Bezeichner zu verwenden, die C#-Schlüsselwörter sind.</span><span class="sxs-lookup"><span data-stu-id="c225b-126">Another use of the @ symbol is to use referenced ([/reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md)) identifiers that are C# keywords.</span></span>  
  
 <span data-ttu-id="c225b-127">Weitere Informationen zu Zeichenfolgen in C# finden Sie unter [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="c225b-127">For more information about strings in C#, see [Strings](../../../csharp/programming-guide/strings/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c225b-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c225b-128">Example</span></span>  
 <span data-ttu-id="c225b-129">[!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="c225b-129">[!code-cs[csrefKeywordsTypes#17](../../../csharp/language-reference/keywords/codesnippet/CSharp/string_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="c225b-130">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="c225b-130">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c225b-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c225b-131">See Also</span></span>  
 <span data-ttu-id="c225b-132">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c225b-132">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c225b-133">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c225b-133">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c225b-134">[Empfohlene Vorgehensweisen für die Verwendung von Zeichenfolgen](../../../standard/base-types/best-practices-strings.md) </span><span class="sxs-lookup"><span data-stu-id="c225b-134">[Best Practices for Using Strings](../../../standard/base-types/best-practices-strings.md) </span></span>  
 <span data-ttu-id="c225b-135">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c225b-135">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c225b-136">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c225b-136">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c225b-137">[Verweistypen](../../../csharp/language-reference/keywords/reference-types.md) </span><span class="sxs-lookup"><span data-stu-id="c225b-137">[Reference Types](../../../csharp/language-reference/keywords/reference-types.md) </span></span>  
 <span data-ttu-id="c225b-138">[Werttypen](../../../csharp/language-reference/keywords/value-types.md) </span><span class="sxs-lookup"><span data-stu-id="c225b-138">[Value Types](../../../csharp/language-reference/keywords/value-types.md) </span></span>  
 <span data-ttu-id="c225b-139">[Grundlegende Zeichenfolgenoperationen](../../../standard/base-types/basic-string-operations.md) </span><span class="sxs-lookup"><span data-stu-id="c225b-139">[Basic String Operations](../../../standard/base-types/basic-string-operations.md) </span></span>  
 <span data-ttu-id="c225b-140">[Erstellen neuer Zeichenfolgen](../../../standard/base-types/creating-new.md) </span><span class="sxs-lookup"><span data-stu-id="c225b-140">[Creating New Strings](../../../standard/base-types/creating-new.md) </span></span>  
 [<span data-ttu-id="c225b-141">Tabelle zur Formatierung numerischer Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="c225b-141">Formatting Numeric Results Table</span></span>](../../../csharp/language-reference/keywords/formatting-numeric-results-table.md)

