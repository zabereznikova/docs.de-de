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
ms.openlocfilehash: 6d2fd226735622de5cd7197060c05b8ac12b69f1
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696843"
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="ca2e3-102">String-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ca2e3-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="ca2e3-103">Enthält Sequenzen von 16-Bit-Code Punkten (2 Bytes) ohne Vorzeichen, die den Wert zwischen 0 und 65535 liegen.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="ca2e3-104">Jeder *Codepunkt*oder Zeichencode stellt ein einzelnes Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="ca2e3-105">Eine Zeichenfolge kann zwischen 0 und ungefähr 2 Milliarden (2 ^ 31) Unicode-Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca2e3-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ca2e3-106">Remarks</span></span>  
 <span data-ttu-id="ca2e3-107">Verwenden Sie den `String`-Datentyp, um mehrere Zeichen ohne den zusätzlichen Verwaltungsaufwand `Char()`, ein Array von `Char`-Elementen, zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="ca2e3-108">Der Standardwert von `String` ist `Nothing` (ein NULL-Verweis).</span><span class="sxs-lookup"><span data-stu-id="ca2e3-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="ca2e3-109">Beachten Sie, dass dies nicht mit der leeren Zeichenfolge (Wert `""`) identisch ist.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="ca2e3-110">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="ca2e3-110">Unicode Characters</span></span>  
 <span data-ttu-id="ca2e3-111">Die ersten 128-Code Punkte (0 – 127) von Unicode entsprechen den Buchstaben und Symbolen in einer standardmäßigen US-Tastatur.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="ca2e3-112">Diese ersten 128-Code Punkte sind identisch mit denen, die der ASCII-Zeichensatz definiert.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="ca2e3-113">Die zweiten 128-Code Punkte (128 – 255) stellen Sonderzeichen dar, wie z. b. lateinische, Buchstaben, Akzente, Währungssymbole und Bruchteile.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="ca2e3-114">Unicode verwendet die verbleibenden Code Punkte (256-65535) für eine Vielzahl von Symbolen.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="ca2e3-115">Dies schließt weltweite Textzeichen, Diakritik und mathematische und technische Symbole ein.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="ca2e3-116">Sie können Methoden, wie z. b. <xref:System.Char.IsDigit%2A> und <xref:System.Char.IsPunctuation%2A>, für ein einzelnes Zeichen in einer `String`-Variablen verwenden, um die Unicode-Klassifizierung zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="ca2e3-117">Formatanforderungen</span><span class="sxs-lookup"><span data-stu-id="ca2e3-117">Format Requirements</span></span>  
 <span data-ttu-id="ca2e3-118">Sie müssen ein `String`-Literale in Anführungszeichen (`" "`) einschließen.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="ca2e3-119">Wenn Sie ein Anführungszeichen als eines der Zeichen in die Zeichenfolge einschließen müssen, verwenden Sie zwei zusammenhängende Anführungszeichen (`""`).</span><span class="sxs-lookup"><span data-stu-id="ca2e3-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="ca2e3-120">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-120">The following example illustrates this.</span></span>  
  
```vb  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="ca2e3-121">Beachten Sie, dass die zusammenhängenden Anführungszeichen, die ein Anführungszeichen in der Zeichenfolge darstellen, unabhängig von den Anführungszeichen sind, die das Literalzeichen "`String`" starten und beenden.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="ca2e3-122">Zeichen folgen Manipulationen</span><span class="sxs-lookup"><span data-stu-id="ca2e3-122">String Manipulations</span></span>  
 <span data-ttu-id="ca2e3-123">Wenn Sie einer `String`-Variablen eine Zeichenfolge zuweisen, ist diese Zeichenfolge *unveränderlich*. Dies bedeutet, dass Sie Ihre Länge oder ihren Inhalt nicht ändern können.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="ca2e3-124">Wenn Sie eine Zeichenfolge in irgendeiner Weise ändern, erstellt Visual Basic eine neue Zeichenfolge und gibt die vorherige zurück.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="ca2e3-125">Die Variable `String` zeigt dann auf die neue Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="ca2e3-126">Sie können den Inhalt einer `String`-Variablen bearbeiten, indem Sie eine Vielzahl von Zeichen folgen Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="ca2e3-127">Im folgenden Beispiel wird die Funktion "<xref:Microsoft.VisualBasic.Strings.Left%2A>" veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```vb  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="ca2e3-128">Eine von einer anderen Komponente erstellte Zeichenfolge kann mit führenden oder nachfolgenden Leerzeichen aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="ca2e3-129">Wenn Sie eine solche Zeichenfolge erhalten, können Sie die Funktionen <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A> und <xref:Microsoft.VisualBasic.Strings.RTrim%2A> verwenden, um diese Leerzeichen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="ca2e3-130">Weitere Informationen zu Zeichen folgen Manipulationen finden Sie unter Zeichen [folgen.](../../../visual-basic/programming-guide/language-features/strings/index.md)</span><span class="sxs-lookup"><span data-stu-id="ca2e3-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="ca2e3-131">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="ca2e3-131">Programming Tips</span></span>  
  
- <span data-ttu-id="ca2e3-132">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="ca2e3-132">**Negative Numbers.**</span></span> <span data-ttu-id="ca2e3-133">Beachten Sie, dass die von `String` gehaltenen Zeichen nicht signiert sind und keine negativen Werte darstellen können.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="ca2e3-134">In jedem Fall sollten Sie nicht `String` verwenden, um numerische Werte zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
- <span data-ttu-id="ca2e3-135">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="ca2e3-135">**Interop Considerations.**</span></span> <span data-ttu-id="ca2e3-136">Wenn Sie mit Komponenten verbunden sind, die nicht für die .NET Framework geschrieben wurden (z. b. Automatisierungs-oder COM-Objekte), beachten Sie, dass Zeichen folgen Zeichen in anderen Umgebungen eine andere Daten Breite (8 Bits) aufweisen.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="ca2e3-137">Wenn Sie ein Zeichen folgen Argument von 8-Bit-Zeichen an eine solche Komponente übergeben, deklarieren Sie es als `Byte()`, ein Array von `Byte`-Elementen anstelle von `String` im neuen Visual Basic Code.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
- <span data-ttu-id="ca2e3-138">**Geben Sie Zeichen ein.**</span><span class="sxs-lookup"><span data-stu-id="ca2e3-138">**Type Characters.**</span></span> <span data-ttu-id="ca2e3-139">Wenn Sie den Bezeichnertyp Zeichen `$` an einen beliebigen Bezeichner anfügen, wird er in den `String`-Datentyp erzwungen.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="ca2e3-140">`String` hat kein Literalzeichen.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-140">`String` has no literal type character.</span></span> <span data-ttu-id="ca2e3-141">Der Compiler behandelt jedoch Literale, die in Anführungszeichen (`" "`) eingeschlossen sind, als `String`.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
- <span data-ttu-id="ca2e3-142">**Frameworktyp.**</span><span class="sxs-lookup"><span data-stu-id="ca2e3-142">**Framework Type.**</span></span> <span data-ttu-id="ca2e3-143">Der entsprechende Typ in der .NET Framework ist die <xref:System.String?displayProperty=nameWithType>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="ca2e3-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca2e3-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca2e3-144">See also</span></span>

- <xref:System.String?displayProperty=nameWithType>
- [<span data-ttu-id="ca2e3-145">Datentypen</span><span class="sxs-lookup"><span data-stu-id="ca2e3-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="ca2e3-146">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="ca2e3-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="ca2e3-147">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="ca2e3-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="ca2e3-148">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="ca2e3-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="ca2e3-149">Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="ca2e3-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="ca2e3-150">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="ca2e3-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
