---
title: Funktionen für die Typkonvertierung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: c9222bdb31f4fd7c792d5a50c100067e29e9d537
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33605081"
---
# <a name="type-conversion-functions-visual-basic"></a>Funktionen für die Typkonvertierung (Visual Basic)
Diese Funktionen sind Inline kompiliert, was bedeutet, dass der Konvertierungscode Bestandteil des Codes ist die Auswertung des Ausdrucks. Manchmal ist kein Aufruf einer Prozedur zum Durchführen der Konvertierung zur Verbesserung, die Leistung beiträgt. Jede Funktion wandelt einen Ausdruck in einen bestimmten Datentyp.  
  
## <a name="syntax"></a>Syntax  
  
```  
CBool(expression)  
CByte(expression)  
CChar(expression)  
CDate(expression)  
CDbl(expression)  
CDec(expression)  
CInt(expression)  
CLng(expression)  
CObj(expression)  
CSByte(expression)  
CShort(expression)  
CSng(expression)  
CStr(expression)  
CUInt(expression)  
CULng(expression)  
CUShort(expression)  
```  
  
## <a name="part"></a>Segment  
 `expression`  
 Erforderlich. Jeder Ausdruck mit dem Quelldatentyp.  
  
## <a name="return-value-data-type"></a>Datentyp des Rückgabewerts  
 Der Funktionsname bestimmt den Datentyp des Werts, den sie zurückgibt, wie in der folgenden Tabelle gezeigt.  
  
|Funktionsname|Rückgabedatentyp|Der Bereich für `expression` Argument|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Jeder gültige `Char` oder `String` oder numerische Ausdruck.|  
|`CByte`|[Byte-Datentyp](../../../visual-basic/language-reference/data-types/byte-data-type.md)|0 bis 255 (ohne Vorzeichen); werden die Nachkommastellen gerundet. <sup>1</sup>|  
|`CChar`|[Char-Datentyp](../../../visual-basic/language-reference/data-types/char-data-type.md)|Jeder gültige `Char` oder `String` Ausdruck; nur die ersten Zeichen des eine `String` konvertiert; Wert kann zwischen 0 und 65535 (ohne Vorzeichen) liegen.|  
|`CDate`|[Date-Datentyp](../../../visual-basic/language-reference/data-types/date-data-type.md)|Jede gültige Darstellung einer Datums- und Uhrzeitangabe.|  
|`CDbl`|[Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)|-1.79769313486231570E + 308 bis - 4.94065645841246544E-324 für negative Werte; 4.94065645841246544E-324 bis 1.79769313486231570E + 308 für positive Werte zulässig sind.|  
|`CDec`|[Decimal-Datentyp](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|+/-Wert 79,228,162,514,264,337,593,543,950,335 für Skalierung von 0 (null) Zahlen, also ohne Dezimalstellen an. Für Zahlen mit 28 Dezimalstellen wird der Bereich +/-7,9228162514264337593543950335 ist. Die kleinstmögliche Zahl ungleich 0 (null) ist 0,0000000000000000000000000001 (+/-1E-28).|  
|`CInt`|[Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)|2.147.483.648 bis 2.147.483.647; werden die Nachkommastellen gerundet. <sup>1</sup>|  
|`CLng`|[Long-Datentyp](../../../visual-basic/language-reference/data-types/long-data-type.md)|-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807; werden die Nachkommastellen gerundet. <sup>1</sup>|  
|`CObj`|[Object-Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md)|Jeder gültige Ausdruck.|  
|`CSByte`|[SByte-Datentyp](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|-128 bis 127; werden die Nachkommastellen gerundet. <sup>1</sup>|  
|`CShort`|[Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)|32.768 bis 32.767; werden die Nachkommastellen gerundet. <sup>1</sup>|  
|`CSng`|[Single-Datentyp](../../../visual-basic/language-reference/data-types/single-data-type.md)|-3, 402823e + 38 bis - 1.401298E-45 für negative Werte; 1.401298E-45 bis 3, 402823e + 38 für positive Werte zulässig sind.|  
|`CStr`|[String-Datentyp](../../../visual-basic/language-reference/data-types/string-data-type.md)|Gibt für `CStr` richten sich nach der `expression` Argument. Finden Sie unter [Rückgabewerte für die CStr-Funktion](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).|  
|`CUInt`|[UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|0 bis 4.294.967.295 (ohne Vorzeichen); werden die Nachkommastellen gerundet. <sup>1</sup>|  
|`CULng`|[ULong-Datentyp](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|0 bis 18.446.744.073.709.551.615 (ohne Vorzeichen); werden die Nachkommastellen gerundet. <sup>1</sup>|  
|`CUShort`|[UShort-Datentyp](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|0 bis 65.535 (ohne Vorzeichen); werden die Nachkommastellen gerundet. <sup>1</sup>|  
  
 <sup>1</sup> Bruchteile unterliegen eine besondere Art von Rundung aufgerufen werden können *Banker rounding*. Weitere Informationen finden Sie unter "Hinweise".  
  
## <a name="remarks"></a>Hinweise  
 In der Regel sollten Sie z. B. die Typkonvertierungsfunktionen von Visual Basic .NET Framework-Methoden verwenden `ToString()`, entweder auf die <xref:System.Convert> Klasse oder eine Struktur vom Typ einzeln oder -Klasse. Visual Basic-Funktionen sind für eine optimale Interaktion mit Visual Basic-Code vorgesehen, und diese bilden auch des Quellcodes kürzer und leichter zu lesen. Darüber hinaus die .NET Framework-Konvertierungsmethoden nicht immer erzeugen die gleichen Ergebnisse wie die Visual Basic-Funktionen, z. B. beim Konvertieren von `Boolean` auf `Integer`. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="behavior"></a>Verhalten  
  
-   **Umwandlung.** Die Datentypkonvertierungsfunktionen können Sie im Allgemeinen das Ergebnis eines Vorgangs an einen bestimmten Datentyp anstelle des Standarddatentyps umgewandelt werden. Verwenden Sie z. B. `CDec` gezwungen dezimale arithmetische Operationen in Fällen, in denen mit einfacher Genauigkeit, mit doppelter Genauigkeit oder Ganzzahlarithmetik würde normalerweise stattfinden.  
  
-   **Fehlgeschlagene Konvertierungen.** Wenn die `expression` liegt außerhalb des Bereichs des Datentyps auf das konvertiert werden, werden an die Funktion übergebene ein <xref:System.OverflowException> auftritt.  
  
-   **Bruchteile.** Wenn Sie einen nicht ganzzahligen Wert in eine ganze Zahl konvertieren Typkonvertierungsfunktionen, die ganze Zahl (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, und `CUShort`) entfernen Sie die Sekundenbruchteile Teil und den Wert auf die nächste Ganzzahl gerundet.  
  
     Wenn der Bruchteil exakt 0,5 die Konvertierungsfunktionen ganze Zahl gerundet wird, damit die nächste gerade ganze Zahl. Rundet z. B. 0,5 auf 0 (null) und 1,5 und 2.5 auf 2 gerundet. Dies wird manchmal als bezeichnet *Banker rounding*, und der Zweck eines Bias zu kompensieren, die sich ansammeln könnten, wenn Sie viele diese Zahlen zusammenführen ist.  
  
     `CInt` und `CLng` unterscheiden sich von der <xref:Microsoft.VisualBasic.Conversion.Int%2A> und <xref:Microsoft.VisualBasic.Conversion.Fix%2A> -Funktionen, die den Bruchteil einer Zahl zu runden, sondern abgeschnitten. Darüber hinaus `Fix` und `Int` wie Sie übergeben immer den Wert des gleichen Datentyps zurück.  
  
-   **Datum/Uhrzeit-Konvertierungen.** Verwenden der <xref:Microsoft.VisualBasic.Information.IsDate%2A> Funktion, um zu bestimmen, ob ein Wert in ein Datum und eine Uhrzeit konvertiert werden kann. `CDate` erkennt Datumsliterale und Zeitliterale, aber keine numerischen Werte. Konvertieren Sie eine Visual Basic 6.0 `Date` -Wert in einen `Date` Wert in Visual Basic 2005 oder höher können Sie die <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> Methode.  
  
-   **Neutrale Datum/Uhrzeit-Werte.** Die [Datumsdatentyp](../../../visual-basic/language-reference/data-types/date-data-type.md) enthält immer die Datums-und Uhrzeitinformationen. Zwecken Typumwandlung berücksichtigt Visual Basic 1/1/0001 (1. Januar des Jahres 1), werden eine *neutrale Wert* für das Datum und 00:00:00 (Mitternacht) für die Zeit ein neutrale Wert sein. Konvertieren einer `Date` Wert in eine Zeichenfolge `CStr` neutralen Werte nicht in der Ergebniszeichenfolge enthalten ist. Angenommen, Sie konvertieren `#January 1, 0001 9:30:00#` in eine Zeichenfolge das Ergebnis "9:30:00 AM"; die Datumsinformationen unterdrückt wird. Die Datumsinformationen ist jedoch weiterhin vorhanden, in der ursprünglichen `Date` Wert und können mit Funktionen wie z. B. wiederhergestellt werden <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> Funktion.  
  
-   **Berücksichtigung der Kultur.** Typkonvertierungsfunktionen, die im Zusammenhang mit Zeichenfolgen führen Konvertierungen, die auf Grundlage der aktuellen kultureinstellungen für die Anwendung aus. Beispielsweise `CDate` erkennt Datumsformate gemäß dem Gebietsschema Ihres Systems. Sie müssen den Tag, Monat und Jahr in der richtigen Reihenfolge für Ihr Gebietsschema angeben, oder das Datum möglicherweise nicht ordnungsgemäß interpretiert werden. Ein langes Datumsformat wird nicht erkannt, wenn sie eine Day of Week-Zeichenfolge, z. B. "Mittwoch" enthält.  
  
     Wenn Sie in oder aus einer Zeichenfolgendarstellung eines Werts in einem anderen Format als dem vom Gebietsschema angegeben konvertiert werden müssen, können nicht Sie die Visual Basic-Typkonvertierungsfunktionen verwenden. Verwenden Sie hierzu die `ToString(IFormatProvider)` und `Parse(String, IFormatProvider)` Methoden vom Typ des Werts. Verwenden Sie z. B. <xref:System.Double.Parse%2A?displayProperty=nameWithType> beim Konvertieren einer Zeichenfolge zu einer `Double`, und verwenden Sie <xref:System.Double.ToString%2A?displayProperty=nameWithType> beim Konvertieren eines Werts vom Typ `Double` in eine Zeichenfolge.  
  
## <a name="ctype-function"></a>CType Function  
 Die [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) nimmt ein zweites Argument `typename`, und wandelt `expression` auf `typename`, wobei `typename` kann-Datentyp, Struktur, Klasse oder Schnittstelle, eine gültige Konvertierung vorhanden, sein.  
  
 Einen Vergleich der `CType` mit anderen Schlüsselwörter für die typkonvertierung, finden Sie unter [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) und [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
## <a name="cbool-example"></a>CBool-Beispiel  
 Im folgenden Beispiel wird die `CBool` Funktion, um Ausdrücke, die zu konvertierende `Boolean` Werte. Wenn ein Ausdruck einen Wert ungleich null ergibt `CBool` gibt `True`ist, andernfalls gibt `False`.  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## <a name="cbyte-example"></a>CByte-Beispiel  
 Im folgenden Beispiel wird die `CByte` Funktion, um einen Ausdruck zum Konvertieren einer `Byte`.  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## <a name="cchar-example"></a>CChar-Beispiel  
 Im folgenden Beispiel wird die `CChar` Funktion konvertiert das erste Zeichen einer `String` Ausdruck, der eine `Char` Typ.  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 Das Eingabeargument für `CChar` muss der Datentyp `Char` oder `String`. Sie können keine `CChar` , eine Zahl in ein Zeichen zu konvertieren, da `CChar` kann keine akzeptieren einen numerischen Datentyp aufweisen. Im folgenden Beispiel wird eine Zahl, die einen Codepunkt (Zeichencode) abgerufen und in das entsprechende Zeichen konvertiert. Er verwendet die <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> -Funktion abrufen die Zeichenfolge aus Ziffern, `CInt` zum Konvertieren der Zeichenfolge in den Typ `Integer`, und `ChrW` zu konvertieren `Char`.  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## <a name="cdate-example"></a>CDate-Beispiel  
 Im folgenden Beispiel wird die `CDate` Funktion zum Konvertieren von Zeichenfolgen in `Date` Werte. Im Allgemeinen wird ein Hardcodieren Datumsangaben und Uhrzeiten als Zeichenfolgen (wie im folgenden Beispiel gezeigt) nicht empfohlen. Verwenden von Datums- und Zeitliterale, z. B. #Feb 12, 1969 # und # 4:45:23 Uhr # stattdessen.  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## <a name="cdbl-example"></a>CDbl-Beispiel  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## <a name="cdec-example"></a>CDec-Beispiel  
 Im folgenden Beispiel wird die `CDec` Funktion, um einen numerischen Wert konvertieren `Decimal`.  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## <a name="cint-example"></a>CInt-Beispiel  
 Im folgenden Beispiel wird die `CInt` Funktion, um einen Wert zu konvertieren `Integer`.  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## <a name="clng-example"></a>CLng-Beispiel  
 Im folgenden Beispiel wird die `CLng` Funktion, um Werte zu konvertieren `Long`.  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## <a name="cobj-example"></a>CObj-Beispiel  
 Im folgenden Beispiel wird die `CObj` Funktion, um einen numerischen Wert konvertieren `Object`. Die `Object` Variable selbst enthält nur einen 4-Byte-Zeiger, die auf verweist die `Double` Wert zugewiesen.  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## <a name="csbyte-example"></a>CSByte-Beispiel  
 Im folgenden Beispiel wird die `CSByte` Funktion, um einen numerischen Wert konvertieren `SByte`.  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## <a name="cshort-example"></a>Beispiel für CShort  
 Im folgenden Beispiel wird die `CShort` Funktion, um einen numerischen Wert konvertieren `Short`.  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## <a name="csng-example"></a>CSng-Beispiel  
 Im folgenden Beispiel wird die `CSng` Funktion, um Werte zu konvertieren `Single`.  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## <a name="cstr-example"></a>CStr-Beispiel  
 Im folgenden Beispiel wird die `CStr` Funktion, um einen numerischen Wert konvertieren `String`.  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 Im folgenden Beispiel wird die `CStr` Funktion konvertiert `Date` Werte `String` Werte.  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 `CStr` Rendert immer eine `Date` Wert in der standardmäßigen Kurzformat für das aktuelle Gebietsschema, z. B. "6/15/2003 4:35:47 PM". Allerdings `CStr` unterdrückt die *neutralen Werte* von 1/1/0001 für das Datum und die 00:00:00 für die Zeit.  
  
 Weitere Informationen über die Rückgabewerte `CStr`, finden Sie unter [Rückgabewerte für die CStr-Funktion](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).  
  
## <a name="cuint-example"></a>CUInt-Beispiel  
 Im folgenden Beispiel wird die `CUInt` Funktion, um einen numerischen Wert konvertieren `UInteger`.  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## <a name="culng-example"></a>CULng-Beispiel  
 Im folgenden Beispiel wird die `CULng` Funktion, um einen numerischen Wert konvertieren `ULong`.  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## <a name="cushort-example"></a>CUShort-Beispiel  
 Im folgenden Beispiel wird die `CUShort` Funktion, um einen numerischen Wert konvertieren `UShort`.  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.Asc%2A>  
 <xref:Microsoft.VisualBasic.Strings.AscW%2A>  
 <xref:Microsoft.VisualBasic.Strings.Chr%2A>  
 <xref:Microsoft.VisualBasic.Strings.ChrW%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>  
 <xref:Microsoft.VisualBasic.Strings.Format%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Oct%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Str%2A>  
 <xref:Microsoft.VisualBasic.Conversion.Val%2A>  
 [Konvertierungsfunktionen](../../../visual-basic/language-reference/functions/conversion-functions.md)  
 [Konvertierungen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
