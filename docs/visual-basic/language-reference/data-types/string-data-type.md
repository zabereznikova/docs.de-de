---
title: String-Datentyp (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.String
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], character
- strings [Visual Basic], fixed-length
- string keyword [Visual Basic]
- fixed-length strings, string data type
- literals, string
- text [Visual Basic], String data type
- $ identifier type character
- String data type
- fixed-length strings
- string literals
- data types [Visual Basic], assigning
- String literals
- identifier type characters, $
ms.assetid: 15ac03f5-cabd-42cc-a754-1df3893c25d9
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5d7a4272169ae7b2749d038e1116818d2cfbad95
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="string-data-type-visual-basic"></a><span data-ttu-id="5aa87-102">String-Datentyp (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5aa87-102">String Data Type (Visual Basic)</span></span>
<span data-ttu-id="5aa87-103">Enthält Sequenzen vorzeichenlose 16-Bit (2-Byte)-Codepunkte Bereichs im Wert von 0 bis 65535.</span><span class="sxs-lookup"><span data-stu-id="5aa87-103">Holds sequences of unsigned 16-bit (2-byte) code points that range in value from 0 through 65535.</span></span> <span data-ttu-id="5aa87-104">Jede *Codepunkt*, oder Zeichencode stellt ein einzelnes Unicode-Zeichen dar.</span><span class="sxs-lookup"><span data-stu-id="5aa87-104">Each *code point*, or character code, represents a single Unicode character.</span></span> <span data-ttu-id="5aa87-105">Eine Zeichenfolge darf zwischen 0 und etwa zwei Milliarden (2 ^ 31) Unicode-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="5aa87-105">A string can contain from 0 to approximately two billion (2 ^ 31) Unicode characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5aa87-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5aa87-106">Remarks</span></span>  
 <span data-ttu-id="5aa87-107">Verwenden der `String` -Datentyp, um mehrere Zeichen ohne den Verwaltungsaufwand für Array speichern `Char()`, ein Array von `Char` Elemente.</span><span class="sxs-lookup"><span data-stu-id="5aa87-107">Use the `String` data type to hold multiple characters without the array management overhead of `Char()`, an array of `Char` elements.</span></span>  
  
 <span data-ttu-id="5aa87-108">Der Standardwert von `String` ist `Nothing` (ein null-Verweis).</span><span class="sxs-lookup"><span data-stu-id="5aa87-108">The default value of `String` is `Nothing` (a null reference).</span></span> <span data-ttu-id="5aa87-109">Beachten Sie, dass dies nicht dasselbe wie eine leere Zeichenfolge ist (Wert `""`).</span><span class="sxs-lookup"><span data-stu-id="5aa87-109">Note that this is not the same as the empty string (value `""`).</span></span>  
  
## <a name="unicode-characters"></a><span data-ttu-id="5aa87-110">Unicode-Zeichen</span><span class="sxs-lookup"><span data-stu-id="5aa87-110">Unicode Characters</span></span>  
 <span data-ttu-id="5aa87-111">Die ersten 128 Codepunkte (0 bis 127) von Unicode entsprechen den Buchstaben und Symbolen auf einer Standardtastatur (USA).</span><span class="sxs-lookup"><span data-stu-id="5aa87-111">The first 128 code points (0–127) of Unicode correspond to the letters and symbols on a standard U.S. keyboard.</span></span> <span data-ttu-id="5aa87-112">Diese ersten 128 Codepunkte sind identisch mit denen ASCII-Zeichensatz definiert.</span><span class="sxs-lookup"><span data-stu-id="5aa87-112">These first 128 code points are the same as those the ASCII character set defines.</span></span> <span data-ttu-id="5aa87-113">Die zweiten 128 Codepunkte (128 – 255) darstellen, Sonderzeichen, wie z. B. lateinischen Buchstaben, Akzente, Währungssymbole und Bruchzahlen.</span><span class="sxs-lookup"><span data-stu-id="5aa87-113">The second 128 code points (128–255) represent special characters, such as Latin-based alphabet letters, accents, currency symbols, and fractions.</span></span> <span data-ttu-id="5aa87-114">Unicode verwendet die übrigen Codepunkte (256 bis&65535;) für eine Vielzahl von Symbolen.</span><span class="sxs-lookup"><span data-stu-id="5aa87-114">Unicode uses the remaining code points (256-65535) for a wide variety of symbols.</span></span> <span data-ttu-id="5aa87-115">Dies schließt internationale Textzeichen, diakritische Zeichen und mathematische und technische Symbole.</span><span class="sxs-lookup"><span data-stu-id="5aa87-115">This includes worldwide textual characters, diacritics, and mathematical and technical symbols.</span></span>  
  
 <span data-ttu-id="5aa87-116">Sie verwenden die Methoden wie <xref:System.Char.IsDigit%2A>und <xref:System.Char.IsPunctuation%2A>auf ein einzelnes Zeichen in eine `String` Variable, deren Unicode-Klassifizierung ermitteln.</xref:System.Char.IsPunctuation%2A> </xref:System.Char.IsDigit%2A></span><span class="sxs-lookup"><span data-stu-id="5aa87-116">You can use methods such as <xref:System.Char.IsDigit%2A> and <xref:System.Char.IsPunctuation%2A> on an individual character in a `String` variable to determine its Unicode classification.</span></span>  
  
## <a name="format-requirements"></a><span data-ttu-id="5aa87-117">Formatanforderungen</span><span class="sxs-lookup"><span data-stu-id="5aa87-117">Format Requirements</span></span>  
 <span data-ttu-id="5aa87-118">Muss ein `String` Zeichenfolgenliteral in Anführungszeichen (`" "`).</span><span class="sxs-lookup"><span data-stu-id="5aa87-118">You must enclose a `String` literal within quotation marks (`" "`).</span></span> <span data-ttu-id="5aa87-119">Wenn Sie ein Anführungszeichen als eines der Zeichen in der Zeichenfolge einfügen müssen, verwenden Sie zwei aufeinander folgende Anführungszeichen (`""`).</span><span class="sxs-lookup"><span data-stu-id="5aa87-119">If you must include a quotation mark as one of the characters in the string, you use two contiguous quotation marks (`""`).</span></span> <span data-ttu-id="5aa87-120">Dies wird anhand des folgenden Beispiels veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="5aa87-120">The following example illustrates this.</span></span>  
  
```  
Dim j As String = "Joe said ""Hello"" to me."  
Dim h As String = "Hello"  
' The following messages all display the same thing:  
' "Joe said "Hello" to me."  
MsgBox(j)  
MsgBox("Joe said " & """" & h & """" & " to me.")  
MsgBox("Joe said """ & h & """ to me.")  
```  
  
 <span data-ttu-id="5aa87-121">Beachten Sie, dass die aufeinander folgenden Anführungszeichen, die ein Anführungszeichen in der Zeichenfolge darstellen, unabhängig von den Anführungszeichen, die Anfang und Ende der `String` literal.</span><span class="sxs-lookup"><span data-stu-id="5aa87-121">Note that the contiguous quotation marks that represent a quotation mark in the string are independent of the quotation marks that begin and end the `String` literal.</span></span>  
  
## <a name="string-manipulations"></a><span data-ttu-id="5aa87-122">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="5aa87-122">String Manipulations</span></span>  
 <span data-ttu-id="5aa87-123">Nachdem Sie eine Zeichenfolge zuweisen ein `String` , diese Zeichenfolge wird *unveränderlich*, d.h. nicht ändern, deren Größe oder den Inhalt.</span><span class="sxs-lookup"><span data-stu-id="5aa87-123">Once you assign a string to a `String` variable, that string is *immutable*, which means you cannot change its length or contents.</span></span> <span data-ttu-id="5aa87-124">Wenn Sie eine Zeichenfolge in keiner Weise ändern, wird Visual Basic eine neue Zeichenfolge erstellt und verwirft die vorhergehende.</span><span class="sxs-lookup"><span data-stu-id="5aa87-124">When you alter a string in any way, Visual Basic creates a new string and abandons the previous one.</span></span> <span data-ttu-id="5aa87-125">Die `String` -Variable zeigt dann auf die neue Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5aa87-125">The `String` variable then points to the new string.</span></span>  
  
 <span data-ttu-id="5aa87-126">Sie können den Inhalt der Bearbeiten einer `String` Variable mithilfe einer Vielzahl von Zeichenfolgenfunktionen.</span><span class="sxs-lookup"><span data-stu-id="5aa87-126">You can manipulate the contents of a `String` variable by using a variety of string functions.</span></span> <span data-ttu-id="5aa87-127">Das folgende Beispiel veranschaulicht die <xref:Microsoft.VisualBasic.Strings.Left%2A>Funktion</xref:Microsoft.VisualBasic.Strings.Left%2A></span><span class="sxs-lookup"><span data-stu-id="5aa87-127">The following example illustrates the <xref:Microsoft.VisualBasic.Strings.Left%2A> function</span></span>  
  
```  
Dim S As String = "Database"  
' The following statement sets S to a new string containing "Data".  
S = Microsoft.VisualBasic.Left(S, 4)  
```  
  
 <span data-ttu-id="5aa87-128">Eine Zeichenfolge, die von einer anderen Komponente erstellt möglicherweise mit führenden oder nachstehenden Leerzeichen aufgefüllt werden.</span><span class="sxs-lookup"><span data-stu-id="5aa87-128">A string created by another component might be padded with leading or trailing spaces.</span></span> <span data-ttu-id="5aa87-129">Wenn Sie eine solche Zeichenfolge empfangen, können Sie die <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, und <xref:Microsoft.VisualBasic.Strings.RTrim%2A>Funktionen entfernen.</xref:Microsoft.VisualBasic.Strings.RTrim%2A> </xref:Microsoft.VisualBasic.Strings.LTrim%2A> </xref:Microsoft.VisualBasic.Strings.Trim%2A></span><span class="sxs-lookup"><span data-stu-id="5aa87-129">If you receive such a string, you can use the <xref:Microsoft.VisualBasic.Strings.Trim%2A>, <xref:Microsoft.VisualBasic.Strings.LTrim%2A>, and <xref:Microsoft.VisualBasic.Strings.RTrim%2A> functions to remove these spaces.</span></span>  
  
 <span data-ttu-id="5aa87-130">Weitere Informationen über Zeichenfolgen finden Sie unter [Zeichenfolgen](../../../visual-basic/programming-guide/language-features/strings/index.md).</span><span class="sxs-lookup"><span data-stu-id="5aa87-130">For more information about string manipulations, see [Strings](../../../visual-basic/programming-guide/language-features/strings/index.md).</span></span>  
  
## <a name="programming-tips"></a><span data-ttu-id="5aa87-131">Programmiertipps</span><span class="sxs-lookup"><span data-stu-id="5aa87-131">Programming Tips</span></span>  
  
-   <span data-ttu-id="5aa87-132">**Negative Zahlen.**</span><span class="sxs-lookup"><span data-stu-id="5aa87-132">**Negative Numbers.**</span></span> <span data-ttu-id="5aa87-133">Denken Sie daran, dass die Zeichen durch gehalten `String` Vorzeichen aufweisen und keine negativen Werte darstellen.</span><span class="sxs-lookup"><span data-stu-id="5aa87-133">Remember that the characters held by `String` are unsigned and cannot represent negative values.</span></span> <span data-ttu-id="5aa87-134">In jedem Fall sollten Sie nicht verwenden `String` für numerische Werte.</span><span class="sxs-lookup"><span data-stu-id="5aa87-134">In any case, you should not use `String` to hold numeric values.</span></span>  
  
-   <span data-ttu-id="5aa87-135">**Interop-Überlegungen.**</span><span class="sxs-lookup"><span data-stu-id="5aa87-135">**Interop Considerations.**</span></span> <span data-ttu-id="5aa87-136">Wenn Sie mit nicht geschriebenen für .NET Framework-Komponenten anbinden, z. B. Automatisierungs- oder COM-Objekte, müssen Sie Zeichen der Zeichenfolge eine andere Datenbreite (8 Bit) in anderen Umgebungen.</span><span class="sxs-lookup"><span data-stu-id="5aa87-136">If you are interfacing with components not written for the .NET Framework, for example Automation or COM objects, remember that string characters have a different data width (8 bits) in other environments.</span></span> <span data-ttu-id="5aa87-137">Wenn Sie ein Zeichenfolgenargument mit 8-Bit-Zeichen an eine solche Komponente übergeben, deklarieren Sie es als `Byte()`, ein Array von `Byte` Elemente anstelle von `String` im neuen Visual Basic-Code.</span><span class="sxs-lookup"><span data-stu-id="5aa87-137">If you are passing a string argument of 8-bit characters to such a component, declare it as `Byte()`, an array of `Byte` elements, instead of `String` in your new Visual Basic code.</span></span>  
  
-   <span data-ttu-id="5aa87-138">**Typzeichen.**</span><span class="sxs-lookup"><span data-stu-id="5aa87-138">**Type Characters.**</span></span> <span data-ttu-id="5aa87-139">Durch Anhängen des Typkennzeichens `$` an einen beliebigen Bezeichner wird die `String` -Datentyp.</span><span class="sxs-lookup"><span data-stu-id="5aa87-139">Appending the identifier type character `$` to any identifier forces it to the `String` data type.</span></span> <span data-ttu-id="5aa87-140">`String`verfügt über kein Literalzeichen.</span><span class="sxs-lookup"><span data-stu-id="5aa87-140">`String` has no literal type character.</span></span> <span data-ttu-id="5aa87-141">Der Compiler behandelt jedoch Literale in Anführungszeichen eingeschlossen (`" "`) als `String`.</span><span class="sxs-lookup"><span data-stu-id="5aa87-141">However, the compiler treats literals enclosed in quotation marks (`" "`) as `String`.</span></span>  
  
-   <span data-ttu-id="5aa87-142">**Framework-Typ.**</span><span class="sxs-lookup"><span data-stu-id="5aa87-142">**Framework Type.**</span></span> <span data-ttu-id="5aa87-143">Der entsprechende Typ in .NET Framework ist die <xref:System.String?displayProperty=fullName>Klasse.</xref:System.String?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5aa87-143">The corresponding type in the .NET Framework is the <xref:System.String?displayProperty=fullName> class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa87-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5aa87-144">See Also</span></span>  
 <span data-ttu-id="5aa87-145"><xref:System.String?displayProperty=fullName></xref:System.String?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="5aa87-145"><xref:System.String?displayProperty=fullName></span></span>   
<span data-ttu-id="5aa87-146"> [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="5aa87-146"> [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="5aa87-147"> [Char-Datentyp](../../../visual-basic/language-reference/data-types/char-data-type.md) </span><span class="sxs-lookup"><span data-stu-id="5aa87-147"> [Char Data Type](../../../visual-basic/language-reference/data-types/char-data-type.md) </span></span>  
<span data-ttu-id="5aa87-148"> [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="5aa87-148"> [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="5aa87-149"> [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span><span class="sxs-lookup"><span data-stu-id="5aa87-149"> [Conversion Summary](../../../visual-basic/language-reference/keywords/conversion-summary.md) </span></span>  
<span data-ttu-id="5aa87-150"> [Gewusst wie: Aufrufen eine Windows-Funktion, die vorzeichenlose Typen akzeptiert](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md) </span><span class="sxs-lookup"><span data-stu-id="5aa87-150"> [How to: Call a Windows Function that Takes Unsigned Types](../../../visual-basic/programming-guide/com-interop/how-to-call-a-windows-function-that-takes-unsigned-types.md) </span></span>  
<span data-ttu-id="5aa87-151"> [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)</span><span class="sxs-lookup"><span data-stu-id="5aa87-151"> [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)</span></span>

