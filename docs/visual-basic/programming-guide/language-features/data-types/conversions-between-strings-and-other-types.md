---
title: Konvertierungen zwischen Zeichenfolgen und anderen Typen (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 82473d59d6b6aac21f2d7f2a0c9748217a61985f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="dec53-102">Konvertierungen zwischen Zeichenfolgen und anderen Typen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dec53-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>
<span data-ttu-id="dec53-103">Sie können einen numerischen konvertieren `Boolean`, oder Datum/Uhrzeit-Wert, der eine `String`.</span><span class="sxs-lookup"><span data-stu-id="dec53-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="dec53-104">Sie können auch in umgekehrter Richtung konvertieren – aus einem Zeichenfolgenwert numerischen, `Boolean`, oder `Date` – sofern der Inhalt der Zeichenfolge als gültiger Wert des Zieldatentyps interpretiert werden können.</span><span class="sxs-lookup"><span data-stu-id="dec53-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="dec53-105">Wenn dies nicht möglich, tritt ein Laufzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="dec53-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="dec53-106">Die Konvertierungen für alle diese Zuweisungen in beide Richtungen annähernde.</span><span class="sxs-lookup"><span data-stu-id="dec53-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="dec53-107">Verwenden Sie Schlüsselwörter für die typkonvertierung (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, und `CType`).</span><span class="sxs-lookup"><span data-stu-id="dec53-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="dec53-108">Die <xref:Microsoft.VisualBasic.Strings.Format%2A> und <xref:Microsoft.VisualBasic.Conversion.Val%2A> -Funktionen geben Ihnen zusätzliche Kontrolle darüber, Konvertierungen zwischen Zeichenfolgen und Zahlen.</span><span class="sxs-lookup"><span data-stu-id="dec53-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="dec53-109">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie definieren, dass Typkonvertierungsoperatoren zwischen `String` und den Typ der Klasse oder Struktur.</span><span class="sxs-lookup"><span data-stu-id="dec53-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="dec53-110">Weitere Informationen finden Sie unter [wie: Definieren eines Konvertierungsoperators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="dec53-110">For more information, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="dec53-111">Konvertierung von Zahlen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="dec53-111">Conversion of Numbers to Strings</span></span>  
 <span data-ttu-id="dec53-112">Können Sie die `Format` Funktion, um eine Zahl in eine formatierte Zeichenfolge zu konvertieren, der nicht nur die entsprechenden Ziffern umfassen kann jedoch auch die Formatierungssymbole, z. B. ein Währungssymbol (z. B. `$`), Tausende Trennzeichen oder *Tausender Symbole* (z. B. `,`), und ein Dezimaltrennzeichen (z. B. `.`).</span><span class="sxs-lookup"><span data-stu-id="dec53-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="dec53-113">`Format` verwendet automatisch die entsprechenden Symbole gemäß der **regionale** in Windows angegebenen Einstellungen **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="dec53-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="dec53-114">Beachten Sie, dass die Verkettung (`&`)-Operator kann konvertiert eine Zahl in eine Zeichenfolge implizit, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="dec53-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="dec53-115">Konvertierung von Zeichenfolgen in Zahlen</span><span class="sxs-lookup"><span data-stu-id="dec53-115">Conversion of Strings to Numbers</span></span>  
 <span data-ttu-id="dec53-116">Sie können die `Val` Funktion explizit die Ziffern in einer Zeichenfolge in eine Zahl zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="dec53-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="dec53-117">`Val` liest die Zeichenfolge an, bis er erkennt, dass ein anderes Zeichen als ein Ziffern, Leerzeichen, Tabstopp, Line feed, Wagenrücklauf oder Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="dec53-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="dec53-118">Die Sequenzen "& O" und "& H" ändern Sie die Basis des Systems Anzahl und die Überprüfung zu beenden.</span><span class="sxs-lookup"><span data-stu-id="dec53-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="dec53-119">Bis er beendet das Lesen, wird `Val` alle entsprechende Zeichen in einen numerischen Wert konvertiert.</span><span class="sxs-lookup"><span data-stu-id="dec53-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="dec53-120">Die folgende Anweisung gibt z. B. den Wert `141.825`.</span><span class="sxs-lookup"><span data-stu-id="dec53-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="dec53-121">Visual Basic eine Zeichenfolge in einen numerischen Wert konvertiert, verwendet der **regionale** Einstellungen angegeben, die in Windows **Systemsteuerung** zum Interpretieren von Tausenden Separator, Dezimaltrennzeichen, und Währungssymbol.</span><span class="sxs-lookup"><span data-stu-id="dec53-121">When Visual Basic converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="dec53-122">Dies bedeutet, dass eine Konvertierung unter einer Einstellung, aber nicht in einer anderen erfolgreich ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="dec53-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="dec53-123">Beispielsweise `"$14.20"` akzeptabel ist in das Gebietsschema Englisch (Vereinigte Staaten), aber nicht im Gebietsschemas Französisch.</span><span class="sxs-lookup"><span data-stu-id="dec53-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dec53-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dec53-124">See Also</span></span>  
 [<span data-ttu-id="dec53-125">Konvertierungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dec53-125">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)  
 [<span data-ttu-id="dec53-126">Erweiternde und eingrenzende Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="dec53-126">Widening and Narrowing Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [<span data-ttu-id="dec53-127">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="dec53-127">Implicit and Explicit Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [<span data-ttu-id="dec53-128">Vorgehensweise: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dec53-128">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)  
 [<span data-ttu-id="dec53-129">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="dec53-129">Array Conversions</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)  
 [<span data-ttu-id="dec53-130">Datentypen</span><span class="sxs-lookup"><span data-stu-id="dec53-130">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [<span data-ttu-id="dec53-131">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="dec53-131">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [<span data-ttu-id="dec53-132">Einführung in internationale Anwendungen basierend auf .NET Framework</span><span class="sxs-lookup"><span data-stu-id="dec53-132">Introduction to International Applications Based on the .NET Framework</span></span>](/visualstudio/ide/introduction-to-international-applications-based-on-the-dotnet-framework)
