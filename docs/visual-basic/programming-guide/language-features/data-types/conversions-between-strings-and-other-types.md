---
title: Konvertierungen zwischen Zeichenfolgen und anderen Typen
ms.date: 07/20/2015
helpviewer_keywords:
- data type conversion [Visual Basic], string
- conversions [Visual Basic], type
- string conversion [Visual Basic]
- conversions [Visual Basic], data type
- type conversion [Visual Basic], string
- regional options
ms.assetid: c3a99596-f09a-44a5-81dd-1b89a094f1df
ms.openlocfilehash: 823931f7d6beb8218e8b99d4a8d45716b7214304
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077149"
---
# <a name="conversions-between-strings-and-other-types-visual-basic"></a><span data-ttu-id="1822a-102">Konvertierungen zwischen Zeichenfolgen und anderen Typen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1822a-102">Conversions Between Strings and Other Types (Visual Basic)</span></span>

<span data-ttu-id="1822a-103">Sie können einen numerischen-, `Boolean` -oder Datums-/Uhrzeitwert in einen konvertieren `String` .</span><span class="sxs-lookup"><span data-stu-id="1822a-103">You can convert a numeric, `Boolean`, or date/time value to a `String`.</span></span> <span data-ttu-id="1822a-104">Sie können auch in umgekehrter Richtung konvertieren – von einem Zeichen folgen Wert zu numeric, `Boolean` oder `Date` –, wenn der Inhalt der Zeichenfolge als gültiger Wert des Ziel Datentyps interpretiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="1822a-104">You can also convert in the reverse direction — from a string value to numeric, `Boolean`, or `Date` — provided the contents of the string can be interpreted as a valid value of the destination data type.</span></span> <span data-ttu-id="1822a-105">Wenn dies nicht möglich ist, tritt ein Laufzeitfehler auf.</span><span class="sxs-lookup"><span data-stu-id="1822a-105">If they cannot, a run-time error occurs.</span></span>  
  
 <span data-ttu-id="1822a-106">Bei den Konvertierungen für alle diese Zuweisungen in beide Richtungen handelt es sich um einschränkende Konvertierungen.</span><span class="sxs-lookup"><span data-stu-id="1822a-106">The conversions for all these assignments, in either direction, are narrowing conversions.</span></span> <span data-ttu-id="1822a-107">Verwenden Sie die Schlüsselwörter für die Typkonvertierung ( `CBool` , `CByte` , `CDate` , `CDbl` , `CDec` , `CInt` , `CLng` , `CSByte` , `CShort` , `CSng` , `CStr` , `CUInt` , `CULng` , `CUShort` und `CType` ).</span><span class="sxs-lookup"><span data-stu-id="1822a-107">You should use the type conversion keywords (`CBool`, `CByte`, `CDate`, `CDbl`, `CDec`, `CInt`, `CLng`, `CSByte`, `CShort`, `CSng`, `CStr`, `CUInt`, `CULng`, `CUShort`, and `CType`).</span></span> <span data-ttu-id="1822a-108">Mit der <xref:Microsoft.VisualBasic.Strings.Format%2A> -Funktion und der- <xref:Microsoft.VisualBasic.Conversion.Val%2A> Funktion haben Sie zusätzliche Kontrolle über Konvertierungen zwischen Zeichen folgen und Zahlen</span><span class="sxs-lookup"><span data-stu-id="1822a-108">The <xref:Microsoft.VisualBasic.Strings.Format%2A> and <xref:Microsoft.VisualBasic.Conversion.Val%2A> functions give you additional control over conversions between strings and numbers.</span></span>  
  
 <span data-ttu-id="1822a-109">Wenn Sie eine Klasse oder Struktur definiert haben, können Sie Typkonvertierungs Operatoren zwischen `String` und dem Typ der Klasse oder Struktur definieren.</span><span class="sxs-lookup"><span data-stu-id="1822a-109">If you have defined a class or structure, you can define type conversion operators between `String` and the type of your class or structure.</span></span> <span data-ttu-id="1822a-110">Weitere Informationen finden Sie unter [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span><span class="sxs-lookup"><span data-stu-id="1822a-110">For more information, see [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
## <a name="conversion-of-numbers-to-strings"></a><span data-ttu-id="1822a-111">Konvertieren von Zahlen in Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="1822a-111">Conversion of Numbers to Strings</span></span>  

 <span data-ttu-id="1822a-112">Sie können die- `Format` Funktion verwenden, um eine Zahl in eine formatierte Zeichenfolge zu konvertieren, die nicht nur die entsprechenden Ziffern enthält, sondern auch Symbole wie ein Währungszeichen (z. b. `$` ), Tausende Trennzeichen oder *zifferngruppierungssymbole* (z. b `,` .) und ein Dezimaltrennzeichen (z. b.) formatieren kann `.` .</span><span class="sxs-lookup"><span data-stu-id="1822a-112">You can use the `Format` function to convert a number to a formatted string, which can include not only the appropriate digits but also formatting symbols such as a currency sign (such as `$`), thousands separators or *digit grouping symbols* (such as `,`), and a decimal separator (such as `.`).</span></span> <span data-ttu-id="1822a-113">`Format`verwendet automatisch die entsprechenden Symbole gemäß den in der Windows- **Systemsteuerung**angegebenen Einstellungen für **regionale Optionen** .</span><span class="sxs-lookup"><span data-stu-id="1822a-113">`Format` automatically uses the appropriate symbols according to the **Regional Options** settings specified in the Windows **Control Panel**.</span></span>  
  
 <span data-ttu-id="1822a-114">Beachten Sie, dass der Concatenations ( `&` )-Operator eine Zahl implizit in eine Zeichenfolge konvertieren kann, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="1822a-114">Note that the concatenation (`&`) operator can convert a number to a string implicitly, as the following example shows.</span></span>  
  
```vb  
' The following statement converts count to a String value.  
Str = "The total count is " & count  
```  
  
## <a name="conversion-of-strings-to-numbers"></a><span data-ttu-id="1822a-115">Konvertierung von Zeichen folgen in Zahlen</span><span class="sxs-lookup"><span data-stu-id="1822a-115">Conversion of Strings to Numbers</span></span>  

 <span data-ttu-id="1822a-116">Sie können die- `Val` Funktion verwenden, um die Ziffern in einer Zeichenfolge explizit in eine Zahl zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="1822a-116">You can use the `Val` function to explicitly convert the digits in a string to a number.</span></span> <span data-ttu-id="1822a-117">`Val` liest die Zeichenfolge, bis Sie auf ein anderes Zeichen als Ziffern, Leerzeichen, Tabstopps, Zeilenvorschub oder Zeitraum trifft.</span><span class="sxs-lookup"><span data-stu-id="1822a-117">`Val` reads the string until it encounters a character other than a digit, space, tab, line feed, or period.</span></span> <span data-ttu-id="1822a-118">Die Sequenzen "&O" und "&H" ändern die Basis des Zahlen Systems und beenden das Scannen.</span><span class="sxs-lookup"><span data-stu-id="1822a-118">The sequences "&O" and "&H" alter the base of the number system and terminate the scanning.</span></span> <span data-ttu-id="1822a-119">Bis zum Beenden der Lesevorgänge `Val` konvertiert alle entsprechenden Zeichen in einen numerischen Wert.</span><span class="sxs-lookup"><span data-stu-id="1822a-119">Until it stops reading, `Val` converts all appropriate characters to a numeric value.</span></span> <span data-ttu-id="1822a-120">Beispielsweise gibt die folgende-Anweisung den-Wert zurück `141.825` .</span><span class="sxs-lookup"><span data-stu-id="1822a-120">For example, the following statement returns the value `141.825`.</span></span>  
  
 `Val("   14   1.825 miles")`  
  
 <span data-ttu-id="1822a-121">Wenn Visual Basic eine Zeichenfolge in einen numerischen Wert konvertiert, werden die in der Windows- **Systemsteuerung** angegebenen **regionalen Options** Einstellungen verwendet, um das Tausender Trennzeichen, das Dezimaltrennzeichen und das Währungssymbol zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="1822a-121">When Visual Basic converts a string to a numeric value, it uses the **Regional Options** settings specified in the Windows **Control Panel** to interpret the thousands separator, decimal separator, and currency symbol.</span></span> <span data-ttu-id="1822a-122">Dies bedeutet, dass eine Konvertierung möglicherweise unter einer Einstellung erfolgreich verläuft, aber nicht in einer anderen.</span><span class="sxs-lookup"><span data-stu-id="1822a-122">This means that a conversion might succeed under one setting but not another.</span></span> <span data-ttu-id="1822a-123">Beispielsweise `"$14.20"` ist im Gebiets Schema Englisch (USA) zulässig, jedoch nicht in einem französischen Gebiets Schema.</span><span class="sxs-lookup"><span data-stu-id="1822a-123">For example, `"$14.20"` is acceptable in the English (United States) locale but not in any French locale.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1822a-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1822a-124">See also</span></span>

- [<span data-ttu-id="1822a-125">Typkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1822a-125">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="1822a-126">Widening and Narrowing Conversions</span><span class="sxs-lookup"><span data-stu-id="1822a-126">Widening and Narrowing Conversions</span></span>](widening-and-narrowing-conversions.md)
- [<span data-ttu-id="1822a-127">Implizite und explizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="1822a-127">Implicit and Explicit Conversions</span></span>](implicit-and-explicit-conversions.md)
- [<span data-ttu-id="1822a-128">Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1822a-128">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="1822a-129">Arraykonvertierungen</span><span class="sxs-lookup"><span data-stu-id="1822a-129">Array Conversions</span></span>](array-conversions.md)
- [<span data-ttu-id="1822a-130">Datentypen</span><span class="sxs-lookup"><span data-stu-id="1822a-130">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="1822a-131">Type Conversion Functions</span><span class="sxs-lookup"><span data-stu-id="1822a-131">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="1822a-132">Entwickeln von globalisierten und lokalisierten Apps</span><span class="sxs-lookup"><span data-stu-id="1822a-132">Develop globalized and localized apps</span></span>](/visualstudio/ide/globalizing-and-localizing-applications)
