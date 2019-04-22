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
ms.openlocfilehash: 3e87dc6527b4351467b1155439ee8266157c16ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58842290"
---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="8a35c-102">String-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a35c-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="8a35c-103">Enthält Sequenzen von unsignierten 16-Bit (2-Byte)-Codepunkte dieses Bereichs im Wert von 0 bis 65535 an.</span><span class="sxs-lookup"><span data-stu-id="8a35c-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="8a35c-104">Jede *Codepunkt*, oder Zeichencode ein einzelnes Unicodezeichens darstellt.</span><span class="sxs-lookup"><span data-stu-id="8a35c-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="8a35c-105">Eine Zeichenfolge kann zwischen 0 und etwa zwei Milliarden enthalten (2 ^ 31) Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="8a35c-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a35c-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8a35c-106">Remarks</span></span>  
 <span data-ttu-id="8a35c-107">Verwenden der `String` -Datentyp, um mehrere Zeichen, ohne den Aufwand des Array-Verwaltung von aufzunehmen `Char()`, ein Array von `Char` Elemente.</span><span class="sxs-lookup"><span data-stu-id="8a35c-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="8a35c-108">Der Standardwert von `String` ist `Nothing` (ein null-Verweis).</span><span class="sxs-lookup"><span data-stu-id="8a35c-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="8a35c-109">Beachten Sie, dass dies nicht identisch mit der leeren Zeichenfolge ist (Wert `""`).</span><span class="sxs-lookup"><span data-stu-id="8a35c-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="8a35c-110">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="8a35c-110">Unicode Characters</span></span>  
 <span data-ttu-id="8a35c-111">Die ersten 128 Codepunkte (0 bis 127) von Unicode entsprechen den Buchstaben und Symbolen, die auf einer US-Standardtastatur.</span><span class="sxs-lookup"><span data-stu-id="8a35c-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="8a35c-112">Diese ersten 128 Codepunkte sind identisch mit denen ASCII-Zeichensatz definiert.</span><span class="sxs-lookup"><span data-stu-id="8a35c-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="8a35c-113">Die zweite 128 Codepunkte (128 – 255) stellen die Sonderzeichen enthält, z. B. lateinische Buchstaben, Akzenten, Währungssymbole und Bruchzahlen dar.</span><span class="sxs-lookup"><span data-stu-id="8a35c-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="8a35c-114">Unicode verwendet die übrigen Codepunkte (256-65535) für eine Vielzahl von Symbolen.</span><span class="sxs-lookup"><span data-stu-id="8a35c-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="8a35c-115">Dies schließt weltweit Textzeichen, diakritische Zeichen und mathematischen und technischen Symbole.</span><span class="sxs-lookup"><span data-stu-id="8a35c-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="8a35c-116">Können Sie Methoden wie z. B. <xref:System.Char.IsDigit%2A> und <xref:System.Char.IsPunctuation%2A> auf ein einzelnes Zeichen in einem `String` Variable, um zu bestimmen, die Unicode-Klassifizierung.</span><span class="sxs-lookup"><span data-stu-id="8a35c-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="8a35c-117">Formatanforderungen</span><span class="sxs-lookup"><span data-stu-id="8a35c-117">Format Requirements</span></span>  
 <span data-ttu-id="8a35c-118">Sie setzen eine `String` Zeichenfolgenliteral in Anführungszeichen (`" "`).</span><span class="sxs-lookup"><span data-stu-id="8a35c-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="8a35c-119">Wenn Sie ein Anführungszeichen als eines der Zeichen in der Zeichenfolge einfügen müssen, verwenden Sie zwei aufeinander folgende Anführungszeichen (`""`).</span><span class="sxs-lookup"><span data-stu-id="8a35c-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="8a35c-120">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8a35c-120">The following example illustrates this.</span></span>  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="8a35c-121">Beachten Sie, dass die aufeinander folgenden Anführungszeichen, die ein Anführungszeichen in der Zeichenfolge darstellen, unabhängig von der Anführungszeichen, das Starten und Beenden der `String` literal.</span><span class="sxs-lookup"><span data-stu-id="8a35c-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="8a35c-122">Zeichenfolgenbearbeitungen</span><span class="sxs-lookup"><span data-stu-id="8a35c-122">String Manipulations</span></span>  
 <span data-ttu-id="8a35c-123">Nachdem Sie eine Zeichenfolge, die zugewiesen eine `String` -Variablen Zeichenfolge ist *unveränderliche*, das bedeutet, dass nicht ändern, deren Größe oder den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="8a35c-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="8a35c-124">Wenn Sie eine Zeichenfolge in keiner Weise ändern, wird Visual Basic erstellt eine neue Zeichenfolge, und bricht ab dem vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="8a35c-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="8a35c-125">Die `String` Variable verweist dann auf die neue Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8a35c-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="8a35c-126">Sie können den Inhalt bearbeiten einer `String` Variable, indem Sie mithilfe einer Vielzahl von Funktionen für Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="8a35c-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="8a35c-127">Das folgende Beispiel veranschaulicht die <xref:Microsoft.VisualBasic.Strings.Left%2A> Funktion</span><span class="sxs-lookup"><span data-stu-id="8a35c-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="8a35c-128">Eine Zeichenfolge, die von einer anderen Komponente erstellt, möglicherweise mit voran- oder nachgestellten Leerzeichen aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="8a35c-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="8a35c-129">Wenn Sie eine solche Zeichenfolge erhalten haben, können Sie die <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, und <xref:Microsoft.VisualBasic.Strings.RTrim%2A> Funktionen diese Leerzeichen entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8a35c-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="8a35c-130">Weitere Informationen zu zeichenfolgenbearbeitungen, finden Sie unter [Zeichenfolgen](../../../visual-basic/programming-guide/language-features/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="8a35c-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="8a35c-131">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="8a35c-131">Programming Tips</span></span>  
  
-   <span data-ttu-id="8a35c-132">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="8a35c-132">**Negative Numbers.**</span></span> <span data-ttu-id="8a35c-133">Beachten Sie, dass die Zeichen von gehalten `String` nicht signiert sind und keine negativen Werte darstellen.</span><span class="sxs-lookup"><span data-stu-id="8a35c-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="8a35c-134">In jedem Fall sollten Sie nicht verwenden `String` für numerische Werte.</span><span class="sxs-lookup"><span data-stu-id="8a35c-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="8a35c-135">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="8a35c-135">**Interop Considerations.**</span></span> <span data-ttu-id="8a35c-136">Wenn die Komponenten, die nicht für .NET Framework geschrieben wurden verbunden ist z. B. Automatisierungs- oder COM-Objekte, denken Sie daran, dass Zeichen der Zeichenfolge eine andere Datenbreite (8 Bit) verfügen in anderen Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="8a35c-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="8a35c-137">Wenn Sie ein Zeichenfolgenargument von 8-Bit-Zeichen an eine solche Komponente übergeben, deklarieren Sie sie als `Byte()`, ein Array von `Byte` Elemente anstelle von `String` im neuen Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="8a35c-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="8a35c-138">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="8a35c-138">**Type Characters.**</span></span> <span data-ttu-id="8a35c-139">Der Bezeichner-Typzeichen Anfügen `$` an einen beliebigen Bezeichner wird die `String` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="8a35c-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="8a35c-140">`String` hat kein literal-Typzeichen.</span><span class="sxs-lookup"><span data-stu-id="8a35c-140">`String` has no literal type character.</span></span> <span data-ttu-id="8a35c-141">Der Compiler behandelt jedoch Literale, die in Anführungszeichen eingeschlossen (`" "`) als `String`.</span><span class="sxs-lookup"><span data-stu-id="8a35c-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
-   <span data-ttu-id="8a35c-142">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="8a35c-142">**Framework Type.**</span></span> <span data-ttu-id="8a35c-143">Der entsprechende Typ in .NET Framework ist die <xref:System.String?displayProperty=nameWithType> Klasse.</span><span class="sxs-lookup"><span data-stu-id="8a35c-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=nameWithType> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a35c-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8a35c-144">See also</span></span>

- <xref:System.String?displayProperty=nameWithType>
- [<span data-ttu-id="8a35c-145">Datentypen</span><span class="sxs-lookup"><span data-stu-id="8a35c-145">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="8a35c-146">Char-Datentyp</span><span class="sxs-lookup"><span data-stu-id="8a35c-146">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)
- [<span data-ttu-id="8a35c-147">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="8a35c-147">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="8a35c-148">Konvertierung: Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="8a35c-148">Conversion Summary</span></span>](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [<span data-ttu-id="8a35c-149">Vorgehensweise: Aufrufen einer Windows-Funktion, die vorzeichenlose Typen akzeptiert</span><span class="sxs-lookup"><span data-stu-id="8a35c-149">How to: Call a Windows Function that Takes Unsigned Types</span></span>](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md)
- [<span data-ttu-id="8a35c-150">Effiziente Verwendung von Datentypen</span><span class="sxs-lookup"><span data-stu-id="8a35c-150">Efficient Use of Data Types</span></span>](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
