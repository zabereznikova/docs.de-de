---
title: String-Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.String
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings [Visual Basic], string data type
- literals [Visual Basic], string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals [Visual Basic]
- data types [Visual Basic], assigning
- String literals [Visual Basic]
- identifier type characters [Visual Basic], $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
ms.openlocfilehash: 894638bbe50dad2cae1f74a2f7b7fe006f029d1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="2d1fb-102">String-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d1fb-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="2d1fb-103">Enthält Sequenzen vorzeichenlose 16-Bit (2-Byte)-Codepunkte dieses Bereichs liegt im Bereich zwischen 0 und 65535 an.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="2d1fb-104">Jede *Codepunkt*, oder Zeichencode stellt ein einzelnes Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="2d1fb-105">Eine Zeichenfolge darf zwischen 0 und etwa zwei Milliarden (2 ^ 31) Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d1fb-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d1fb-106">Remarks</span></span>  
 <span data-ttu-id="2d1fb-107">Verwenden der `String` Datentyps zum Speichern von mehreren Zeichen ohne den Arrayverwaltungsaufwand `Char()`, ein Array von `Char` Elemente.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="2d1fb-108">Der Standardwert von `String` ist `Nothing` (ein null-Verweis).</span><span class="sxs-lookup"><span data-stu-id="2d1fb-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="2d1fb-109">Beachten Sie, dass dies nicht mit der leeren Zeichenfolge identisch ist (Wert `""`).</span><span class="sxs-lookup"><span data-stu-id="2d1fb-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="2d1fb-110">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="2d1fb-110">Unicode Characters</span></span>  
 <span data-ttu-id="2d1fb-111">Die ersten 128 Codepunkte (0 bis 127) von Unicode entsprechen den Buchstaben und Symbolen auf eine US-Standardtastatur.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="2d1fb-112">Diese ersten 128 Codepunkte sind identisch mit denen ASCII-Zeichensatz definiert.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="2d1fb-113">Die zweite 128 Codepunkte (128 bis 255) darstellen Sonderzeichen enthält, z. B. lateinische Buchstaben, Akzente, Währungssymbole und Sekundenbruchteilen.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="2d1fb-114">Unicode verwendet die übrigen Codepunkte (256-65535) für eine Vielzahl von Symbolen.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="2d1fb-115">Dies schließt weltweite Textzeichen, diakritische Zeichen und mathematische und technische Symbole.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="2d1fb-116">Sie verwenden die Methoden wie z. B. <xref:System.Char.IsDigit%2A> und <xref:System.Char.IsPunctuation%2A> auf ein einzelnes Zeichen in einer `String` Variable, deren Unicode-Klassifizierung ermitteln.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="2d1fb-117">Formatanforderungen</span><span class="sxs-lookup"><span data-stu-id="2d1fb-117">Format Requirements</span></span>  
 <span data-ttu-id="2d1fb-118">Sie setzen eine `String` Zeichenfolgenliteral in Anführungszeichen (`" "`).</span><span class="sxs-lookup"><span data-stu-id="2d1fb-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="2d1fb-119">Wenn Sie als eines der Zeichen in der Zeichenfolge ein Anführungszeichen einschließen müssen, verwenden Sie zwei aufeinander folgende Anführungszeichen (`""`).</span><span class="sxs-lookup"><span data-stu-id="2d1fb-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="2d1fb-120">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-120">The following example illustrates this.</span></span>  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="2d1fb-121">Beachten Sie, dass die aufeinander folgenden Anführungszeichen, die ein Anführungszeichen in der Zeichenfolge darstellen von Anführungszeichen unabhängig sind, das Starten und Beenden der `String` literal.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="2d1fb-122">Zeichenfolgenmanipulationen</span><span class="sxs-lookup"><span data-stu-id="2d1fb-122">String Manipulations</span></span>  
 <span data-ttu-id="2d1fb-123">Nachdem Sie eine Zeichenfolge zum Zuweisen eine `String` Variable, diese Zeichenfolge wird *unveränderlichen*, das bedeutet, dass seine Länge oder den Inhalt ändern kann nicht.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="2d1fb-124">Wenn Sie eine Zeichenfolge in irgendeiner Weise ändern, Visual Basic erstellt eine neue Zeichenfolge, und die vorherige Abfrage abbricht.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="2d1fb-125">Die `String` Variable verweist dann auf die neue Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="2d1fb-126">Sie können den Inhalt bearbeiten eine `String` Variable, indem Sie mithilfe einer Vielzahl von String-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="2d1fb-127">Das folgende Beispiel veranschaulicht die <xref:Microsoft.VisualBasic.Strings.Left%2A> Funktion</span><span class="sxs-lookup"><span data-stu-id="2d1fb-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="2d1fb-128">Eine Zeichenfolge, die von einer anderen Komponente erstellt möglicherweise mit führende oder nachfolgende Leerzeichen aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="2d1fb-129">Wenn Sie solch eine Zeichenfolge empfangen, können Sie die <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, und <xref:Microsoft.VisualBasic.Strings.RTrim%2A> Funktionen diese Leerzeichen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="2d1fb-130">Weitere Informationen zu zeichenfolgenmanipulationen, finden Sie unter [Zeichenfolgen](../../../visual-basic/programming-guide/language-features/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="2d1fb-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="2d1fb-131">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="2d1fb-131">Programming Tips</span></span>  
  
-   <span data-ttu-id="2d1fb-132">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="2d1fb-132">**Negative Numbers.**</span></span> <span data-ttu-id="2d1fb-133">Denken Sie daran, dass die Zeichen vom reservierten `String` ohne Vorzeichen sind, und keine negativen Werte darstellen.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="2d1fb-134">In jedem Fall sollten Sie nicht verwenden `String` für numerische Werte.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="2d1fb-135">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="2d1fb-135">**Interop Considerations.**</span></span> <span data-ttu-id="2d1fb-136">Wenn Sie Komponenten, die nicht für .NET Framework geschrieben wurden Datenbreite z. B. Automatisierungs- oder COM-Objekte, denken Sie daran Zeichen der Zeichenfolge eine andere Datenbreite (8 Bit) in anderen Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="2d1fb-137">Wenn Sie ein Argument für eine 8-Bit-Zeichen an eine solche Komponente übergeben, deklarieren Sie es als `Byte()`, ein Array von `Byte` Elemente, anstelle von `String` im neuen Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="2d1fb-138">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="2d1fb-138">**Type Characters.**</span></span> <span data-ttu-id="2d1fb-139">Die Typkennzeichen Anfügen `$` an einen beliebigen Bezeichner wird die `String` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="2d1fb-140">`String` hat kein literal-Typzeichen.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-140">`String` has no literal type character.</span></span> <span data-ttu-id="2d1fb-141">Der Compiler behandelt jedoch Literale, die in Anführungszeichen eingeschlossen (`" "`) als `String`.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
-   <span data-ttu-id="2d1fb-142">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="2d1fb-142">**Framework Type.**</span></span> <span data-ttu-id="2d1fb-143">Der entsprechende Typ in .NET Framework ist die <xref:System.String?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="2d1fb-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d1fb-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d1fb-144">See Also</span></span>  
 <xref:System.String?displayProperty=nameWithType>  
 [<span data-ttu-id="2d1fb-145">Datentypen</span><span class="sxs-lookup"><span data-stu-id="2d1fb-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="2d1fb-146">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="2d1fb-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [<span data-ttu-id="2d1fb-147">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="2d1fb-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="2d1fb-148">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="2d1fb-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [<span data-ttu-id="2d1fb-149">Gewusst wie: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="2d1fb-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)  
 [<span data-ttu-id="2d1fb-150">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="2d1fb-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
