---
title: Konvertierungen zwischen Zeichenfolgen und anderen Typen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- data type conversion, string
- conversions, type
- string conversion
- conversions, data type
- type conversion, string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
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
ms.openlocfilehash: 34eb32cb6e640d681db6853aaa164d84acca7e4f
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="7dd9c-102">Konvertierungen zwischen Zeichenfolgen und anderen Typen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7dd9c-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>
<span data-ttu-id="7dd9c-103">Sie können eine numerische konvertieren `Boolean`, oder Datum/Uhrzeit-Wert, der eine `String`.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="7dd9c-104">Sie können auch in umgekehrter Richtung konvertieren – aus einem Zeichenfolgenwert numerischen, `Boolean`, oder `Date` – sofern der Inhalt der Zeichenfolge als gültiger Wert des Zieldatentyps interpretiert werden können.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="7dd9c-105">Ist dies nicht möglich, tritt ein Laufzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="7dd9c-106">Die Konvertierungen für alle diese Aufgaben in beide Richtungen annähernde.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="7dd9c-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span><span class="sxs-lookup"><span data-stu-id="7dd9c-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="7dd9c-108">Die <xref:Microsoft.VisualBasic.Strings.Format%2A>und <xref:Microsoft.VisualBasic.Conversion.Val%2A>Funktionen erhalten Sie zusätzliche Kontrolle über Konvertierungen zwischen Zeichenfolgen und Zahlen.</xref:Microsoft.VisualBasic.Conversion.Val%2A> </xref:Microsoft.VisualBasic.Strings.Format%2A></span><span class="sxs-lookup"><span data-stu-id="7dd9c-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="7dd9c-109">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie definieren, dass Typkonvertierungsoperatoren zwischen `String` und den Typ der Klasse bzw. Struktur.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="7dd9c-110">Weitere Informationen finden Sie unter [Gewusst wie: Definieren eines Konvertierungsoperators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="7dd9c-110">For more information, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="7dd9c-111">Konvertieren von Zahlen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="7dd9c-111">Conversion of Numbers to Strings</span></span>  
 <span data-ttu-id="7dd9c-112">Können Sie die `Format` -Funktion zum Umwandeln einer Zahl in eine formatierte Zeichenfolge, die nicht nur die entsprechenden Ziffern enthalten, können jedoch auch die Formatierungssymbole, wie Währungszeichen (z. B. `$`), Tausende Trennzeichen oder *Ziffer gruppieren Symbole* (z. B. `,`), und ein Dezimaltrennzeichen (z. B. `.`).</span><span class="sxs-lookup"><span data-stu-id="7dd9c-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="7dd9c-113">`Format`verwendet automatisch die entsprechenden Symbole gemäß der **regionale** Einstellungen in Windows **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="7dd9c-114">Beachten Sie, dass die Verkettung (`&`) konvertieren kann eine Zahl in eine Zeichenfolge implizit, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="7dd9c-115">Konvertierung von Zeichenfolgen in Zahlen</span><span class="sxs-lookup"><span data-stu-id="7dd9c-115">Conversion of Strings to Numbers</span></span>  
 <span data-ttu-id="7dd9c-116">Sie können die `Val` Funktion, die Ziffern in einer Zeichenfolge explizit in eine Zahl zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="7dd9c-117">`Val`liest die Zeichenfolge, bis ein anderes Zeichen als eine Ziffer, Leerzeichen, Tabstoppzeichen, Line feed, oder Zeitraum auftritt.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="7dd9c-118">Die Sequenzen "& O" und "& H" ändern die Basis des Systems Anzahl und beenden die Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="7dd9c-119">Bis sie gelesen wird, stoppt `Val` alle entsprechende Zeichen in einen numerischen Wert konvertiert.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="7dd9c-120">Die folgende Anweisung gibt z. B. den Wert `141.825`.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="7dd9c-121">Wenn [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] konvertiert eine Zeichenfolge in einen numerischen Wert, verwendet der **regionale** Einstellungen in Windows **Systemsteuerung** Tausendertrennzeichen interpretiert Trennzeichen, Dezimaltrennzeichen und Währungssymbol.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-121">When [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="7dd9c-122">Dies bedeutet, dass eine Konvertierung möglicherweise unter einem, jedoch nicht in einer anderen Einstellung erfolgreich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="7dd9c-123">Z. B. `"$14.20"` akzeptabel ist in Englisch (USA) jedoch nicht in Gebietsschemas Französisch.</span><span class="sxs-lookup"><span data-stu-id="7dd9c-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dd9c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dd9c-124">See Also</span></span>  
 <span data-ttu-id="7dd9c-125">[Typumwandlungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7dd9c-125">[Type Conversions in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="7dd9c-126"> [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7dd9c-126"> [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) </span></span>  
<span data-ttu-id="7dd9c-127"> [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7dd9c-127"> [Implicit and Explicit Conversions](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) </span></span>  
<span data-ttu-id="7dd9c-128"> [Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span><span class="sxs-lookup"><span data-stu-id="7dd9c-128"> [How to: Convert an Object to Another Type in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md) </span></span>  
<span data-ttu-id="7dd9c-129"> [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7dd9c-129"> [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md) </span></span>  
<span data-ttu-id="7dd9c-130"> [Datentypen](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span><span class="sxs-lookup"><span data-stu-id="7dd9c-130"> [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md) </span></span>  
<span data-ttu-id="7dd9c-131"> [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span><span class="sxs-lookup"><span data-stu-id="7dd9c-131"> [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md) </span></span>  
<span data-ttu-id="7dd9c-132"> [Einführung in internationale Anwendungen basierend auf .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)</span><span class="sxs-lookup"><span data-stu-id="7dd9c-132"> [Introduction to International Applications Based on the .NET Framework](https://docs.microsoft.com/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)</span></span>
