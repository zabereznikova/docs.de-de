---
title: Funktionen für die Typkonvertierung (Visual Basic)
ms.date: 10/24/2018
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
ms.openlocfilehash: ea7cc2c7f988617de67bf0ea46aeb3396acdf4b1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980619"
---
# <a name="type-conversion-functions-visual-basic"></a>Funktionen für die Typkonvertierung (Visual Basic)
Diese Funktionen sind kompilierte Inline, was bedeutet, dass der Konvertierungscode Teil des Codes ist die Auswertung des Ausdrucks. In manchen sind Situationen kein Aufruf an eine Prozedur zum Durchführen der Konvertierung wird die Leistung verbessert. Jede Funktion wandelt einen Ausdruck, der einen bestimmten Datentyp.  
  
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
 Erforderlich. Ein Ausdruck des Typs der Daten.  
  
## <a name="return-value-data-type"></a>Datentyp des Rückgabewerts  
 Den Namen der Funktion bestimmt den Datentyp des Werts, den sie zurückgibt, wie in der folgenden Tabelle gezeigt.  
  
|Funktionsname|Rückgabedatentyp|Der Bereich für `expression` Argument|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[Boolean-Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|Eine beliebige gültige `Char` oder `String` oder numerischer Ausdruck.|  
|`CByte`|[Byte-Datentyp](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte.MinValue?displayProperty=nameWithType> (0) über <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsignierten); Nachkommastellen gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in bytekonvertierung mit der `CByte` funktionieren, finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.|  
|`CChar`|[Char-Datentyp](../../../visual-basic/language-reference/data-types/char-data-type.md)|Eine beliebige gültige `Char` oder `String` Ausdruck; nur die ersten Zeichen der ein `String` konvertiert wird; Wert kann 0 bis 65535 (ohne Vorzeichen) sein.|  
|`CDate`|[Date-Datentyp](../../../visual-basic/language-reference/data-types/date-data-type.md)|Jede gültige Darstellung von Datum und Uhrzeit.|  
|`CDbl`|[Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)|-1.79769313486231570E + 308 bis - 4.94065645841246544E-324 für negative Werte; 4.94065645841246544E-324 bis 1.79769313486231570E + 308 für positive Werte.|  
|`CDec`|[Decimal-Datentyp](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|+ / – 79.228.162.514.264.337.593.543.950.335 für die Skalierung von 0 (null) Zahlen, also ohne Dezimalstellen. Ist der Bereich für Zahlen mit 28 Dezimalstellen + / – 7,9228162514264337593543950335. Die kleinste mögliche Zahl ungleich NULL ist – 0,0000000000000000000000000001 (+/-1E-28).|  
|`CInt`|[Integer-Datentyp](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32.MinValue?displayProperty=nameWithType> (-2.147.483.648) bis <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2.147.483.647); Nachkommastellen gerundet.<sup> 1</sup> <br/><br/>Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in ganze Zahl Konvertierung mit dem `CInt` funktionieren, finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel. |  
|`CLng`|[Long-Datentyp](../../../visual-basic/language-reference/data-types/long-data-type.md)|<xref:System.Int64.MinValue?displayProperty=nameWithType> (-9.223.372.036.854.775.808) bis <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9.223.372.036.854.775.807); Nachkommastellen gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in 64-Bit-Ganzzahl-Konvertierung mit dem `CLng` funktionieren, finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.|  
|`CObj`|[Object-Datentyp](../../../visual-basic/language-reference/data-types/object-data-type.md)|Jeder gültige Ausdruck.|  
|`CSByte`|[SByte-Datentyp](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) über <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); Nachkommastellen gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in Byte mit Vorzeichen Konvertierung mit dem `CSByte` funktionieren, finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.|  
|`CShort`|[Short-Datentyp](../../../visual-basic/language-reference/data-types/short-data-type.md)|<xref:System.Int16.MinValue?displayProperty=nameWithType> (-32.768) bis <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32.767); Nachkommastellen gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in ganze 16-Bit-Konvertierung mit den `CShort` funktionieren, finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.|  
|`CSng`|[Single-Datentyp](../../../visual-basic/language-reference/data-types/single-data-type.md)|-3, 402823e + 38 bis - 1.401298E-45 für negative Werte; 1.401298E-45 bis 3, 402823e + 38 für positive Werte.|  
|`CStr`|[String-Datentyp](../../../visual-basic/language-reference/data-types/string-data-type.md)|Gibt für `CStr` richten sich nach der `expression` Argument. Finden Sie unter [Werte zurück, für die CStr-Funktion](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).|  
|`CUInt`|[UInteger-Datentyp](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) über <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4.294.967.295) (unsignierten); Nachkommastellen gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in ganze Zahl ohne Vorzeichen Konvertierung mit dem `CUInt` funktionieren, finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.|  
|`CULng`|[ULong-Datentyp](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) über <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18.446.744.073.709.551.615) (unsignierten); Nachkommastellen gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkommazahl in unsigned long integer-Wert-Konvertierung mit dem `CULng` funktionieren, finden Sie unter der ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.|  
|`CUShort`|[UShort-Datentyp](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) über <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65.535) (unsignierten); Nachkommastellen gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic-15.8, Visual Basic optimiert die Leistung von Gleitkomma, um die Konvertierung von 16-Bit-Ganzzahl ohne Vorzeichen mit der `CUShort` funktionieren, finden Sie unter den ["Hinweise"](#remarks) Abschnitt, um weitere Informationen. Finden Sie unter den [CInt-Beispiel](#cint-example) -Abschnitt für ein Beispiel.|  
  
 <sup>1</sup> Nachkommastellen können eine besondere Art der Rundung aufgerufene unterliegen *Banker rounding*. Weitere Informationen finden Sie unter "Hinweise".  
  
## <a name="remarks"></a>Hinweise  
 Als Faustregel gilt, sollten Sie z. B. die Typkonvertierungsfunktionen von Visual Basic .NET Framework-Methoden verwenden `ToString()`, entweder auf die <xref:System.Convert> Klasse oder auf einem einzelnen Typstruktur oder Klasse. Visual Basic-Funktionen sind für eine optimale Interaktion mit Visual Basic-Code vorgesehen, und sie machen auch den Quellcode kürzer und leichter zu lesen. Darüber hinaus die .NET Framework-Konvertierungsmethoden immer erzeugen nicht die gleichen Ergebnisse wie Visual Basic-Funktionen, z. B. bei der Konvertierung `Boolean` zu `Integer`. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  


Ab Visual Basic-15.8, ist die Leistung der Konvertierung von Gleitkomma-point-in Ganzzahlwerte beim übergeben optimiert die <xref:System.Single> oder <xref:System.Double> mithilfe der folgenden Methoden auf einen der die Funktionen zurückgegebene Wert (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

Diese Optimierung können Code, der eine große Anzahl von Konvertierungen von ganzzahligen auf doppelt so schnell ausgeführt werden, um. Das folgende Beispiel veranschaulicht diese optimierte Gleitkomma-point-in Ganzzahlwerte Konvertierungen:

```vb
Dim s As Single = 173.7619
Dim d As Double = s 

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a>Verhalten  
  
-   **Umwandlung.** Die Funktionen für die typkonvertierung Daten können Sie in der Regel das Ergebnis eines Vorgangs auf einen bestimmten Datentyp anstelle des Standarddatentyps umgewandelt werden soll. Verwenden Sie z. B. `CDec` gezwungen dezimale arithmetische Operationen in Fällen, in denen mit einfacher Genauigkeit, mit doppelter Genauigkeit oder Ganzzahlarithmetik würde normalerweise stattfinden.  
  
-   **Fehlgeschlagene Konvertierungen.** Wenn die `expression` liegt außerhalb des Bereichs des Datentyps auf den er konvertiert werden, werden an die Funktion übergeben eine <xref:System.OverflowException> auftritt.  
  
-   **Nachkommastellen.** Wenn Sie einen nicht ganzzahligen Wert in eine Ganzzahlkonstante konvertieren eingeben, die Funktionen (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, und `CUShort`) entfernen Sie die Sekundenbruchteile Teil, und den Wert, der die nächste ganze Zahl gerundet.  
  
     Wenn der Bruchteil exakt 0,5, die Konvertierungsfunktionen ganze Zahl aufgerundet auf die nächste gerade ganze Zahl. 0 (null) und 1.5 und 2.5, die auf 2 gerundet wird z. B. 0,5 abgerundet. Dies wird mitunter bezeichnet *Banker rounding*, und die darin besteht, die für ein Bias zu kompensieren, die sich ansammeln könnten, wenn Sie viele derartige Zahlen zusammenführen.  
  
     `CInt` und `CLng` unterscheiden sich von der <xref:Microsoft.VisualBasic.Conversion.Int%2A> und <xref:Microsoft.VisualBasic.Conversion.Fix%2A> -Funktionen, die den Bruchteil einer Zahl zu runden, sondern abgeschnitten. Darüber hinaus `Fix` und `Int` wie Sie übergeben immer den Wert des gleichen Datentyps zurück.  
  
-   **Datum/Uhrzeit-Konvertierungen.** Verwenden der <xref:Microsoft.VisualBasic.Information.IsDate%2A> Funktion, um zu bestimmen, ob ein Wert in ein Datum und eine Uhrzeit konvertiert werden kann. `CDate` erkennt Datums- und Uhrzeitliterale aber keine numerischen Werte. Konvertieren Sie eine Visual Basic 6.0 `Date` -Werts in einen `Date` Wert in Visual Basic 2005 oder höher, können Sie die <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> Methode.  
  
-   **Neutral Datum/Uhrzeit-Werten.** Die [Date-Datentyps](../../../visual-basic/language-reference/data-types/date-data-type.md) immer sowohl Datums-und Uhrzeitinformationen enthält. Für Zwecke der typkonvertierung berücksichtigt Visual Basic 1/1/0001 (1. Januar des Jahres 1), werden eine *neutrale Wert* für das Datum und 00:00:00 (Mitternacht) einen neutralen Wert für die Zeit sein. Wenn Sie konvertieren ein `Date` Wert in eine Zeichenfolge, `CStr` enthält keine neutralen Werte in der Ergebniszeichenfolge. Wenn Sie konvertieren, z. B. `#January 1, 0001 9:30:00#` in eine Zeichenfolge, das Ergebnis "9:30:00 Uhr"; die Datumsinformationen unterdrückt wird. Die Datumsinformationen ist jedoch weiterhin vorhanden, in der ursprünglichen `Date` Wert und kann mit Funktionen wiederhergestellt werden, z. B. <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> Funktion.  
  
-   **Berücksichtigung der Kultur.** Die Zeichenfolgen mit Funktionen für die typkonvertierung führen Konvertierungen, die basierend auf den Einstellungen der aktuellen Kultur für die Anwendung aus. Z. B. `CDate` erkennt Datums-und Uhrzeitformate gemäß der gebietsschemaeinstellung des Systems. Sie müssen den Tag, Monat und Jahr in der richtigen Reihenfolge für Ihr Gebietsschema angeben, oder das Datum möglicherweise nicht ordnungsgemäß interpretiert werden. Ein langes Datumsformat wird nicht erkannt werden, wenn es sich um einen Tag der Woche-Zeichenfolge, z. B. "Wednesday" enthält.  
  
     Wenn Sie in oder aus einer Zeichenfolgendarstellung eines Werts in einem anderen Format als dem vom Gebietsschema angegeben konvertiert werden müssen, können nicht Sie die Funktionen für die typkonvertierung Visual Basic verwenden. Verwenden Sie hierzu die `ToString(IFormatProvider)` und `Parse(String, IFormatProvider)` Methoden der Typ des Werts. Verwenden Sie z. B. <xref:System.Double.Parse%2A?displayProperty=nameWithType> beim Konvertieren einer Zeichenfolge zu einer `Double`, und verwenden Sie <xref:System.Double.ToString%2A?displayProperty=nameWithType> beim Konvertieren eines Werts vom Typ `Double` in eine Zeichenfolge.  
  
## <a name="ctype-function"></a>CType Function  
 Die [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md) nimmt ein zweites Argument, `typename`, und wandelt `expression` zu `typename`, wobei `typename` kann-Datentyp, Struktur, Klasse oder Schnittstelle, eine gültige Konvertierung vorhanden, sein.  
  
 Einen Vergleich der `CType` mit anderen Schlüsselwörter für die typkonvertierung, finden Sie unter [DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) und [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).  
  
## <a name="cbool-example"></a>CBool-Beispiel  
 Im folgenden Beispiel wird die `CBool` Funktion, um Ausdrücke für konvertiert `Boolean` Werte. Wenn ein Ausdruck einen Wert ungleich null ergibt `CBool` gibt `True`ist, andernfalls gibt `False`.  
  
 [!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]  
  
## <a name="cbyte-example"></a>CByte-Beispiel  
 Im folgenden Beispiel wird die `CByte` Funktion, um einen Ausdruck zum Konvertieren einer `Byte`.  
  
 [!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]  
  
## <a name="cchar-example"></a>CChar-Beispiel  
 Im folgenden Beispiel wird die `CChar` Funktion konvertiert das erste Zeichen einer `String` Ausdruck, der eine `Char` Typ.  
  
 [!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]  
  
 Das Eingabeargument für `CChar` muss der Datentyp `Char` oder `String`. Sie können keine `CChar` , eine Zahl in ein Zeichen zu konvertieren, da `CChar` nicht akzeptieren einen numerischen Datentyp aufweisen. Im folgenden Beispiel ruft eine Zahl, die einen Codepunkt (Zeichencode) und konvertiert ihn in das entsprechende Zeichen. Er verwendet den <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> Funktion zum Abrufen der Zeichenfolge der Ziffern, `CInt` zum Konvertieren der Zeichenfolge in den Typ `Integer`, und `ChrW` um die Anzahl in den Typ zu konvertieren `Char`.  
  
 [!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]  
  
## <a name="cdate-example"></a>CDate-Beispiel  
 Im folgenden Beispiel wird die `CDate` Funktion zum Konvertieren von Zeichenfolgen, die `Date` Werte. Im Allgemeinen wird ein hartcodieren Datums- und Uhrzeitangaben als Zeichenfolgen (wie im folgenden Beispiel gezeigt) nicht empfohlen. Verwenden von Datums- und Uhrzeitliterale, z. B. #Feb 12, 1969 # und # 4:45:23 Uhr #. stattdessen.  
  
 [!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]  
  
## <a name="cdbl-example"></a>CDbl-Beispiel  
 [!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]  
  
## <a name="cdec-example"></a>CDec-Beispiel  
 Im folgenden Beispiel wird die `CDec` Funktion, um einen numerischen Wert konvertieren `Decimal`.  
  
 [!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]  
  
## <a name="cint-example"></a>CInt-Beispiel  
 Im folgenden Beispiel wird die `CInt` Funktion zum Konvertieren eines Werts zu `Integer`.  
  
 [!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]  

## <a name="clng-example"></a>CLng-Beispiel
 Im folgenden Beispiel wird die `CLng` Funktion zum Konvertieren `Long`.  
  
 [!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]  
  
## <a name="cobj-example"></a>"CObj"-Beispiel  
 Im folgenden Beispiel wird die `CObj` Funktion, um einen numerischen Wert konvertieren `Object`. Die `Object` Variable sich selbst enthält nur einen 4-Byte-Zeiger, die auf verweist die `Double` Wert zugewiesen.  
  
 [!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]  
  
## <a name="csbyte-example"></a>CSByte-Beispiel  
 Im folgenden Beispiel wird die `CSByte` Funktion, um einen numerischen Wert konvertieren `SByte`.  
  
 [!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]  
  
## <a name="cshort-example"></a>Beispiel für CShort  
 Im folgenden Beispiel wird die `CShort` Funktion, um einen numerischen Wert konvertieren `Short`.  
  
 [!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]  
  
## <a name="csng-example"></a>CSng-Beispiel  
 Im folgenden Beispiel wird die `CSng` Funktion zum Konvertieren `Single`.  
  
 [!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]  
  
## <a name="cstr-example"></a>CStr-Beispiel  
 Im folgenden Beispiel wird die `CStr` Funktion, um einen numerischen Wert konvertieren `String`.  
  
 [!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]  
  
 Im folgenden Beispiel wird die `CStr` Funktion konvertiert `Date` Werte `String` Werte.  
  
 [!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]  
  
 `CStr` stellt immer eine `Date` Wert in der standardmäßigen Kurzformat für das aktuelle Gebietsschema, z. B. "6/15/2003 4:35:47 PM". Allerdings `CStr` unterdrückt die *neutralen Werte* von 1/1/0001 für das Datum und die 00:00:00, für die Zeit.  
  
 Weitere Informationen zu der vom zurückgegebenen Werte `CStr`, finden Sie unter [Werte zurückgeben, für die CStr-Funktion](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).  
  
## <a name="cuint-example"></a>CUInt-Beispiel  
 Im folgenden Beispiel wird die `CUInt` Funktion, um einen numerischen Wert konvertieren `UInteger`.  
  
 [!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]  
  
## <a name="culng-example"></a>CULng-Beispiel  
 Im folgenden Beispiel wird die `CULng` Funktion, um einen numerischen Wert konvertieren `ULong`.  
  
 [!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]  
  
## <a name="cushort-example"></a>CUShort-Beispiel  
 Im folgenden Beispiel wird die `CUShort` Funktion, um einen numerischen Wert konvertieren `UShort`.  
  
 [!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [Konvertierungsfunktionen](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [Typkonvertierung in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
