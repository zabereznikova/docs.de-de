---
title: "Type Conversion Functions (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.CUShort"
  - "vb.csng"
  - "vb.CDate"
  - "CByte"
  - "CSng"
  - "vb.CDec"
  - "CBool"
  - "CStr"
  - "vb.CULng"
  - "CDec"
  - "CVErr"
  - "CDbl"
  - "CShort"
  - "vb.CObj"
  - "vb.CVErr"
  - "CULng"
  - "vb.cdbl"
  - "vb.cbool"
  - "CObj"
  - "CDate"
  - "CLng"
  - "vb.cstr"
  - "vb.cbyte"
  - "vb.clng"
  - "vb.CChar"
  - "CUShort"
  - "vb.CUInt"
  - "vb.cint"
  - "vb.CShort"
  - "CInt"
  - "CUInt"
  - "CChar"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "CDate function"
  - "CByte function"
  - "Integer data type, converting"
  - "string conversion, conversion functions"
  - "fractions"
  - "data types [Visual Basic], converting"
  - "text, converting"
  - "CDec function"
  - "Char data type, converting"
  - "type conversion, functions for"
  - "Single data type, converting"
  - "numbers, rounding"
  - "rounding numbers, type conversion"
  - "CUShort function"
  - "Long data type, converting"
  - "return values, data types"
  - "single-precision numbers, converting"
  - "data type conversion, functions for"
  - "CStr function"
  - "times, converting"
  - "CSng function"
  - "conversions, type conversion functions"
  - "CBool function"
  - "CDbl function"
  - "CUInt function"
  - "Currency data type, conversion functions"
  - "numbers, converting"
  - "Double data type, converting"
  - "CLng function"
  - "CSByte function"
  - "double-precision numbers"
  - "Decimal data type, converting"
  - "Boolean data type, converting"
  - "integers, type conversion functions"
  - "dates, converting"
  - "CULng function"
  - "CInt function"
  - "Date data type, converting"
  - "Byte data type, converting"
  - "String data type, converting"
  - "CChar function"
  - "banker's rounding"
  - "Short data type, converting"
  - "rounding numbers, banker's rounding"
  - "type conversion, Visual Basic vs. .NET Framework"
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type Conversion Functions (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Diese Funktionen werden inline kompiliert. Dies bedeutet, dass der Konvertierungscode Bestandteil des Codes für die Auswertung des Ausdrucks ist.  Manchmal gibt es keinen Aufruf einer Prozedur zum Durchführen der Konvertierung. Das erhöht die Leistung.  Jede Funktion erzwingt für einen Ausdruck einen bestimmten Datentyp.  
  
## Syntax  
  
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
  
## Bestandteil  
 `expression`  
 Erforderlich.  Beliebiger Ausdruck des Quelldatentyps.  
  
## Datentyp des Rückgabewerts  
 Der Funktionsname bestimmt den Datentyp des von der Funktion zurückgegebenen Werts wie in der folgenden Tabelle gezeigt.  
  
|Funktionsname|Rückgabedatentyp|Bereich für das `expression`\-Argument|  
|-------------------|----------------------|--------------------------------------------|  
|`CBool`|[Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Ein beliebiger gültiger `Char`\-Ausdruck, `String`\-Ausdruck oder numerischer Ausdruck.|  
|`CByte`|[Byte Data Type](../../../visual-basic/language-reference/data-types/byte-data-type.md)|0 \(null\) bis 255 \(ohne Vorzeichen\); Nachkommastellen werden gerundet.<sup>1</sup>|  
|`CChar`|[Char Data Type](../../../visual-basic/language-reference/data-types/char-data-type.md)|Jeder gültige `Char`\-Ausdruck oder `String`\-Ausdruck; nur das erste Zeichen von `String` wird konvertiert; Wert kann 0 \(null\) bis 65535 \(ohne Vorzeichen\) sein.|  
|`CDate`|[Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md)|Eine beliebige gültige Darstellung eines Datums und einer Uhrzeit.|  
|`CDbl`|[Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md)|\-1,79769313486231570E\+308 bis \-4,94065645841246544E–324 für negative Werte; 4,94065645841246544E–324 bis 1,79769313486231570E\+308 für positive Werte.|  
|`CDec`|[Decimal Data Type](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|\+\/–79.228.162.514.264.337.593.543.950.335 für skalierte ganze Zahlen, d. h. Zahlen ohne Dezimalstellen.  Für Zahlen mit 28 Dezimalstellen ist der gültige Bereich \+\/\-7,9228162514264337593543950335.  Die kleinste mögliche Zahl ungleich 0 \(null\) ist 0,0000000000000000000000000001 \(\+\/\-1E\-28\).|  
|`CInt`|[Integer Data Type](../../../visual-basic/language-reference/data-types/integer-data-type.md)|\-2.147.483.648 bis 2.147.483.647; Nachkommastellen werden gerundet.<sup>1</sup>|  
|`CLng`|[Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md)|\-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807; Nachkommastellen werden gerundet.<sup>1</sup>|  
|`CObj`|[Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md)|Jeder gültige Ausdruck.|  
|`CSByte`|[SByte Data Type](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|\-128 bis 127; Nachkommastellen werden gerundet.<sup>1</sup>|  
|`CShort`|[Short Data Type](../../../visual-basic/language-reference/data-types/short-data-type.md)|\-32.768 bis 32.767; Nachkommastellen werden gerundet.<sup>1</sup>|  
|`CSng`|[Single Data Type](../../../visual-basic/language-reference/data-types/single-data-type.md)|–3,402823E\+38 bis –1,401298E–45 für negative Werte; 1,401298E–45 bis 3,402823E\+38 für positive Werte.|  
|`CStr`|[String Data Type](../../../visual-basic/language-reference/data-types/string-data-type.md)|Die Rückgabe für `CStr` hängt vom `expression`\-Argument ab.  Weitere Informationen finden Sie unter [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).|  
|`CUInt`|[UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|0 \(null\) bis 4.294.967.295 \(ohne Vorzeichen\); Nachkommastellen werden gerundet.<sup>1</sup>|  
|`CULng`|[ULong Data Type](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|0 \(null\) bis 18.446.744.073.709.551.615 \(ohne Vorzeichen\); Nachkommastellen werden gerundet.<sup>1</sup>|  
|`CUShort`|[UShort Data Type](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|0 \(null\) bis 65.535 \(ohne Vorzeichen\); Nachkommastellen werden gerundet.<sup>1</sup>|  
  
 <sup>1</sup> Nachkommastellen können der *unverzerrten Rundung \(Banker's Rounding\)* unterliegen, einem besonderen Rundungstyp.  Weitere Informationen finden Sie unter "Hinweise".  
  
## Hinweise  
 Grundsätzlich sollten Sie die Typkonvertierungsfunktionen von Visual Basic den .NET Framework\-Methoden wie `ToString()` entweder für die <xref:System.Convert>\-Klasse oder eine individuelle Typstruktur oder \-klasse vorziehen.  Die Visual Basic\-Funktionen sind auf eine optimale Interaktion mit Visual Basic\-Code ausgerichtet. Außerdem wird Ihr Quellcode dadurch kürzer und besser lesbar.  Darüber hinaus erzeugen die .NET Framework\-Konvertierungsmethoden nicht immer die gleichen Ergebnisse wie die Visual Basic\-Funktionen. Dies ist z. B. bei der Konvertierung von `Boolean` in `Integer` der Fall.  Weitere Informationen finden Sie unter [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## Verhalten  
  
-   **Konvertierung.** Die Funktionen zum Konvertieren von Datentypen können dazu verwendet werden, das Ergebnis einer Operation in einen bestimmten Datentyp anstatt in den Standarddatentyp umzuwandeln.  Mit `CDec` können Sie beispielsweise Berechnungen explizit im Dezimalformat durchführen, bei denen normalerweise ganzzahlige Werte oder Werte mit einfacher oder doppelter Genauigkeit verwendet würden.  
  
-   **Fehlgeschlagene Konvertierungen.** Wenn das an die Funktion weitergegebene `expression`\-Argument außerhalb des Bereichs des Datentyps liegt, in den es konvertiert werden soll, tritt eine <xref:System.OverflowException> auf.  
  
-   **Nachkommastellen.** Wenn Sie einen Wert, der keine ganze Zahl ist, in einen ganzzahligen Typ konvertieren, entfernen die Funktionen zum Konvertieren von ganzen Zahlen \(`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng` und `CUShort`\) den Teil mit den Dezimalstellen. Der Wert wird dann auf die nächste ganze Zahl gerundet.  
  
     Wenn der Teil mit den Dezimalstellen genau 0,5 ist, runden die Funktionen zum Konvertieren von ganzen Zahlen den Wert auf die nächste gerade ganze Zahl.  Beispielsweise wird 0,5 auf 0 gerundet, und 1,5 und 2,5 werden beide auf 2 gerundet.  Dies wird manchmal als *unverzerrte Rundung \(Banker's Rounding\)* bezeichnet. Ziel dieser Rundungsmethode ist es, die Abweichung zu kompensieren, die sich beim Addieren vieler solcher Zahlen aufbauen könnte.  
  
     `CInt` und `CLng` unterscheiden sich von den Funktionen <xref:Microsoft.VisualBasic.Conversion.Int%2A> und <xref:Microsoft.VisualBasic.Conversion.Fix%2A>, die den Teil mit den Dezimalstellen einer Zahl abschneiden und nicht runden.  Außerdem entspricht der Rückgabetyp von `Fix` und `Int` immer dem Typ des an sie übergebenen Werts.  
  
-   **Konvertierung von Datum\/Zeit.** Verwenden Sie die <xref:Microsoft.VisualBasic.Information.IsDate%2A>\-Funktion, um festzustellen, ob ein Wert in ein Datum und eine Uhrzeit konvertiert werden kann.  `CDate` erkennt Datumsliterale und Uhrzeitliterale, aber keine numerischen Werte.  Um einen `Date`\-Wert von Visual Basic 6.0 in einen  `Date`\-Wert unter Visual Basic 2005 oder höher zu konvertieren, können Sie die <xref:System.DateTime.FromOADate%2A?displayProperty=fullName>\-Methode verwenden.  
  
-   **Neutrale Datums\-\/Zeitwerte.** Der [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) enthält immer sowohl Datums\- als auch Zeitinformationen.  Für die Typkonvertierung verwendet Visual Basic 1\/1\/0001 \(1. Januar des Jahres 1\) als *neutralen Wert* für das Datum und 00:00:00 \(Mitternacht\) als neutralen Wert für die Uhrzeit.  Wenn ein `Date`\-Wert in eine Zeichenfolge umgewandelt wird, nimmt `CStr` in die resultierende Zeichenfolge keine neutralen Werte auf.  Wenn beispielsweise `#January 1, 0001 9:30:00#` in eine Zeichenfolge umgewandelt wird, lautet das Ergebnis "9:30:00 AM"; die Datumsinformationen werden unterdrückt.  Die Datumsangaben sind aber weiterhin im `Date`\-Wert enthalten und können mit Funktionen wie der <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>\-Funktion wiederhergestellt werden.  
  
-   **Berücksichtigung der Kultur.** Die Typkonvertierungsfunktionen, die Zeichenfolgen betreffen, führen Konvertierungen auf der Grundlage der aktuellen Kultureinstellungen für die Anwendung aus.  `CDate` z. B. erkennt Datumsformate gemäß den im System festgelegten Gebietsschemaeinstellungen.  Sie müssen Tag, Monat und Jahr für das Gebietsschema in der richtigen Reihenfolge angeben, sonst wird das Datum nicht richtig interpretiert.  Außerdem wird ein langes Datumsformat nicht erkannt, wenn es auch eine Zeichenfolge für den Wochentag, wie "Mittwoch" enthält.  
  
     Wenn Sie in eine oder aus einer Zeichenfolgendarstellung eines Werts in ein anderes Format als das von Ihrem Gebietsschema angegebene Format konvertieren müssen, können Sie die Typkonvertierungsfunktionen von Visual Basic nicht verwenden.  Verwenden Sie in diesem Fall die `ToString(IFormatProvider)`\-Methode und die `Parse(String, IFormatProvider)`\-Methode für den Typ dieses Werts.  Verwenden Sie z. B. <xref:System.Double.Parse%2A?displayProperty=fullName>, wenn Sie eine Zeichenfolge in `Double` konvertieren, und <xref:System.Double.ToString%2A?displayProperty=fullName>, wenn Sie einen Wert vom Typ `Double` in eine Zeichenfolge konvertieren.  
  
## CType\-Funktion  
 Die [CType\-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) nimmt ein zweites Argument \(`typename`\) an und wandelt `expression` in `typename` um. Dabei kann `typename` ein beliebiger Datentyp oder eine beliebige Struktur, Klasse oder Schnittstelle sein, für die es eine gültige Konvertierung gibt.  
  
 Einen Vergleich von `CType` mit den anderen Typkonvertierungsschlüsselwörtern finden Sie unter [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) und [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
## Beispiel für CBool  
 In diesem Beispiel wird die `CBool`\-Funktion dazu verwendet, Ausdrücke in `Boolean`\-Werte zu konvertieren.  Wenn ein Ausdruck einen Wert ungleich 0 \(null\) ergibt, gibt `CBool` den Wert `True` zurück; andernfalls wird `False` zurückgegeben.  
  
 [!code-vb[VbVbalrFunctions#1](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_1.vb)]  
  
## Beispiel für CByte  
 Im folgenden Beispiel wird die `CByte`\-Funktion dazu verwendet, einen Ausdruck in `Byte` zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#2](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_2.vb)]  
  
## Beispiel für CChar  
 Im folgenden Beispiel wird die `CChar`\-Funktion dazu verwendet, das erste Zeichen eines `String`\-Ausdrucks in einen `Char`\-Typ zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#3](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_3.vb)]  
  
 Das Eingabeargument für `CChar` muss dem Datentyp `Char` oder `String` angehören.  `CChar` kann nicht dazu verwendet werden, eine Zahl in ein Zeichen zu konvertieren, da `CChar` einen numerischen Datentyp nicht akzeptieren kann.  Im folgenden Beispiel wird eine Zahl abgerufen, die einen Codepunkt \(Zeichencode\) repräsentiert und anschließend in das entsprechende Zeichen konvertiert.  Dabei wird die <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>\-Funktion verwendet, um die Zeichenfolge von Ziffern zu erhalten; `CInt` wird eingesetzt, um die Zeichenfolge in den Typ `Integer` zu konvertieren, und `ChrW`, um die Zahl in den Typ `Char` zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#4](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_4.vb)]  
  
## Beispiel für CDate  
 Im folgenden Beispiel wird die `CDate`\-Funktion dazu verwendet, Zeichenfolgen in `Date`\-Werte zu konvertieren.  Im Allgemeinen wird davon abgeraten, Datums\- und Zeitangaben fest als Zeichenfolgen zu programmieren \(siehe Beispiel\).  Verwenden Sie stattdessen Datums\- und Zeitliterale, wie \#Feb 12, 1969\# und \#4:45:23 PM\#.  
  
 [!code-vb[VbVbalrFunctions#5](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_5.vb)]  
  
## Beispiel für CDbl  
 [!code-vb[VbVbalrFunctions#6](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_6.vb)]  
  
## Beispiel für CDec  
 Im folgenden Beispiel wird die `CDec`\-Funktion dazu verwendet, einen numerischen Wert in `Decimal` zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#7](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_7.vb)]  
  
## Beispiel für CInt  
 Im folgenden Beispiel wird die `CInt`\-Funktion dazu verwendet, einen Wert in `Integer` zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_8.vb)]  
  
## Beispiel für CLng  
 Im folgenden Beispiel wird die `CLng`\-Funktion dazu verwendet, Werte in `Long` zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#9](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_9.vb)]  
  
## Beispiel für CObj  
 Im folgenden Beispiel wird die `CObj`\-Funktion dazu verwendet, einen numerischen Wert in `Object` zu konvertieren.  Die `Object`\-Variable selbst enthält nur einen 4\-Byte\-Zeiger, der auf den ihm zugewiesenen `Double`\-Wert zeigt.  
  
 [!code-vb[VbVbalrFunctions#10](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_10.vb)]  
  
## CSByte\-Beispiel  
 Im folgenden Beispiel wird die `CSByte`\-Funktion dazu verwendet, einen numerischen Wert in `SByte` zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#11](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_11.vb)]  
  
## Beispiel für CShort  
 Im folgenden Beispiel wird die `CShort`\-Funktion dazu verwendet, einen numerischen Wert in `Short` zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#12](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_12.vb)]  
  
## Beispiel für CSng  
 Im folgenden Beispiel wird die `CSng`\-Funktion dazu verwendet, Werte in `Single` zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#13](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_13.vb)]  
  
## Beispiel für CStr  
 Im folgenden Beispiel wird die `CStr`\-Funktion dazu verwendet, einen numerischen Wert in `String` zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#14](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_14.vb)]  
  
 Im folgenden Beispiel wird die `CStr`\-Funktion dazu verwendet, `Date`\-Werte in `String`\-Werte zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#15](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_15.vb)]  
  
 `CStr` stellt einen `Date`\-Wert immer im standardmäßigen Kurzformat für das aktuelle Gebietsschema dar, z. B. "6\/15\/2003 4:35:47 PM".  `CStr` unterdrückt jedoch die *neutralen Werte* von 1\/1\/0001 für das Datum und 00:00:00 für die Zeit.  
  
 Weitere Informationen über die Werte, die von `CStr` zurückgegeben werden, finden Sie unter [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).  
  
## CUInt\-Beispiel  
 Im folgenden Beispiel wird die `CUInt`\-Funktion dazu verwendet, einen numerischen Wert in `UInteger` zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#16](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_16.vb)]  
  
## CULng\-Beispiel  
 Im folgenden Beispiel wird die `CULng`\-Funktion dazu verwendet, einen numerischen Wert in `ULong` zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_17.vb)]  
  
## CUShort\-Beispiel  
 Im folgenden Beispiel wird die `CUShort`\-Funktion dazu verwendet, einen numerischen Wert in `UShort` zu konvertieren.  
  
 [!code-vb[VbVbalrFunctions#18](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/type-conversion-functions_18.vb)]  
  
## Siehe auch  
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
 [Conversion Functions](../../../visual-basic/language-reference/functions/conversion-functions.md)   
 [Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)