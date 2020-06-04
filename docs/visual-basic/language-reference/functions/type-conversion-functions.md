---
title: Type Conversion Functions
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
ms.openlocfilehash: 5c0cfae01da02222d0827e81ec1ed35ce353ead1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415374"
---
# <a name="type-conversion-functions-visual-basic"></a>Funktionen für die Typkonvertierung (Visual Basic)

Diese Funktionen werden Inline kompiliert. Dies bedeutet, dass der Konvertierungs Code Teil des Codes ist, der den Ausdruck auswertet. Manchmal gibt es keinen aufzurufenden Vorgang zum Durchführen der Konvertierung, wodurch die Leistung verbessert wird. Jede Funktion wandelt einen Ausdruck in einen bestimmten Datentyp um.

## <a name="syntax"></a>Syntax

```vb
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

## <a name="part"></a>Teil

`expression`  
Erforderlich. Ein beliebiger Ausdruck des Quell Datentyps.

## <a name="return-value-data-type"></a>Rückgabewert Datentyp

Der Funktionsname bestimmt den Datentyp des zurückgegebenen Werts, wie in der folgenden Tabelle dargestellt.

|Funktionsname|Rückgabedatentyp|Bereich für `expression` Argument|
|-------------------|----------------------|-------------------------------------|
|`CBool`|[Boolean-Datentyp](../data-types/boolean-data-type.md)|Ein beliebiger gültiger-Ausdruck oder ein `Char` `String` numerischer Ausdruck.|
|`CByte`|[Byte-Datentyp](../data-types/byte-data-type.md)|<xref:System.Byte.MinValue?displayProperty=nameWithType>(0) bis <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigniert); Bruchteile werden gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic 15,8 optimiert Visual Basic die Leistung der Gleit Komma-zu-Byte-Konvertierung mit der- `CByte` Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ". Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .|
|`CChar`|[Char-Datentyp](../data-types/char-data-type.md)|Jeder gültige `Char` - `String` Ausdruck oder-Ausdruck; nur das erste Zeichen einer `String` wird konvertiert. der Wert kann zwischen 0 und 65535 (unsigned) liegen.|
|`CDate`|[Date-Datentyp](../data-types/date-data-type.md)|Eine beliebige gültige Darstellung eines Datums und einer Uhrzeit.|
|`CDbl`|[Double-Datentyp](../data-types/double-data-type.md)|-1.79769313486231570 e + 308 bis-4.94065645841246544 e-324 für negative Werte; 4.94065645841246544 e-324 bis 1.79769313486231570 e + 308 für positive Werte.|
|`CDec`|[Decimal-Datentyp](../data-types/decimal-data-type.md)|+/-337 für Zahlen mit NULL Skalierung, d. h. Zahlen ohne Dezimalstellen. Für Zahlen mit 28 Dezimalstellen beträgt der Bereich +/-7.9228162514264337593543950335. Die kleinstmögliche Zahl ungleich 0 (null) ist 0,0000000000000000000000000001 (+/-1E-28).|
|`CInt`|[Integer-Datentyp](../data-types/integer-data-type.md)|<xref:System.Int32.MinValue?displayProperty=nameWithType>(-2.147.483.648) bis <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2.147.483.647); Bruchteile werden gerundet.<sup> 1</sup> <br/><br/>Ab Visual Basic 15,8 optimiert Visual Basic die Leistung der Gleit Komma-zu-ganzzahligen Konvertierung mit der- `CInt` Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ". Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) . |
|`CLng`|[Long-Datentyp](../data-types/long-data-type.md)|<xref:System.Int64.MinValue?displayProperty=nameWithType>(-9.223.372.036.854.775.808) bis <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9.223.372.036.854.775.807); Bruchteile werden gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic 15,8 optimiert Visual Basic die Leistung der Konvertierung von Gleit Komma-auf 64-Bit-Ganzzahl mit der- `CLng` Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ". Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .|
|`CObj`|[Object Data Type](../data-types/object-data-type.md)|Beliebiger gültiger Ausdruck.|
|`CSByte`|[SByte-Datentyp](../data-types/sbyte-data-type.md)|<xref:System.SByte.MinValue?displayProperty=nameWithType>(-128) bis <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); Bruchteile werden gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic 15,8 optimiert Visual Basic die Leistung der Konvertierung von Gleit Komma-und signierten Bytes mit der- `CSByte` Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ". Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .|
|`CShort`|[Short-Datentyp](../data-types/short-data-type.md)|<xref:System.Int16.MinValue?displayProperty=nameWithType>(-32.768) bis <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32.767); Bruchteile werden gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic 15,8 optimiert Visual Basic die Leistung von Gleit Komma-zu-16-Bit-ganzzahligen Konvertierungen mit der- `CShort` Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ". Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .|
|`CSng`|[Single-Datentyp](../data-types/single-data-type.md)|-3.402823 e + 38 bis- -1 401298E e-45 für negative Werte; -1 401298E e-45 bis 3.402823 e + 38 für positive Werte.|
|`CStr`|[String-Datentyp](../data-types/string-data-type.md)|Gibt für `CStr` abhängig vom- `expression` Argument zurück. Weitere Informationen finden Sie [unter Rückgabewerte für die CStr-Funktion](return-values-for-the-cstr-function.md).|
|`CUInt`|[UInteger-Datentyp](../data-types/uinteger-data-type.md)|<xref:System.UInt32.MinValue?displayProperty=nameWithType>(0) bis <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4.294.967.295) (unsigniert); Bruchteile werden gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic 15,8 optimiert Visual Basic die Leistung von Gleit Komma Zahlen in ganz Zahl Konvertierungen ohne Vorzeichen mit der- `CUInt` Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ". Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .|
|`CULng`|[ULong-Datentyp](../data-types/ulong-data-type.md)|<xref:System.UInt64.MinValue?displayProperty=nameWithType>(0) bis <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18446744073709551615) (unsigniert); Bruchteile werden gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic 15,8 optimiert Visual Basic die Leistung von Gleit Komma Zahlen in eine lange ganzzahlige Konvertierung ohne Vorzeichen mit der- `CULng` Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ". Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .|
|`CUShort`|[UShort-Datentyp](../data-types/ushort-data-type.md)|<xref:System.UInt16.MinValue?displayProperty=nameWithType>(0) bis <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65.535) (unsigniert); Bruchteile werden gerundet.<sup> 1</sup><br/><br/>Ab Visual Basic 15,8 optimiert Visual Basic die Leistung von Gleit Komma Zahlen in eine 16-Bit-Ganzzahl ohne Vorzeichen mit der- `CUShort` Funktion. Weitere Informationen finden Sie im Abschnitt " [Hinweise](#remarks) ". Ein Beispiel finden Sie im Abschnitt [CInt-Beispiel](#cint-example) .|

<sup>1</sup> Bruchteile können einer besonderen Art von Rundung unterliegen, die als " *Banker Rundung*" bezeichnet wird. Weitere Informationen finden Sie unter "Hinweise".

## <a name="remarks"></a>Bemerkungen

Als Regel sollten Sie die Visual Basic Typkonvertierungs Funktionen für die .NET Framework Methoden wie verwenden, z. b `ToString()` . für die <xref:System.Convert> Klasse oder für eine einzelne Typstruktur oder-Klasse. Die Visual Basic Funktionen sind für eine optimale Interaktion mit Visual Basic Code konzipiert. Außerdem wird der Quellcode kürzer und leichter lesbar. Außerdem erzielen die .NET Framework Konvertierungs Methoden nicht immer dieselben Ergebnisse wie die Visual Basic Funktionen, z. b. bei der Konvertierung `Boolean` in `Integer` . Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).

Ab Visual Basic 15,8 wird die Leistung der Konvertierung von Gleit Komma-zu-ganzzahligen Daten optimiert, wenn Sie den- <xref:System.Single> oder- <xref:System.Double> Wert, der von den folgenden Methoden zurückgegeben wird, an eine der ganzzahligen Konvertierungs Funktionen übergeben ( `CByte` , `CShort` , `CInt` , `CLng` , `CSByte` , `CUShort` , `CUInt` , `CULng` ):

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

Diese Optimierung ermöglicht, dass Code, der eine große Anzahl von ganzzahligen Konvertierungen durchführt, bis zu doppelt so schnell ausgeführt wird. Das folgende Beispiel veranschaulicht diese optimierten Konvertierungen von Gleit Komma-und ganzzahligen Zeichen folgen:

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

- **Nötigung.** Im Allgemeinen können Sie die Datentyp-Konvertierungs Funktionen verwenden, um das Ergebnis eines Vorgangs in einen bestimmten Datentyp und nicht in den Standard Datentyp umzuwandeln. Verwenden `CDec` Sie z. b., um die Dezimal Arithmetik in Fällen zu erzwingen, in denen normale Genauigkeit, doppelte Genauigkeit oder ganzzahlige Arithmetik normalerweise stattfinden würde.

- **Fehlerhafte Konvertierungen.** Wenn die `expression` , die an die Funktion übertragen wird, außerhalb des Bereichs des Datentyps liegt, in den Sie konvertiert werden soll, tritt ein auf <xref:System.OverflowException> .

- **Bruchteile.** Wenn Sie einen nicht ganzzahligen Wert in einen ganzzahligen Typ konvertieren, entfernen die ganzzahligen Konvertierungs Funktionen ( `CByte` ,, `CInt` `CLng` , `CSByte` , `CShort` , `CUInt` , `CULng` und `CUShort` ) den Bruch Teil und runden den Wert auf die nächste ganze Zahl auf.

     Wenn der Bruchteil der Dezimalstellen genau 0,5 ist, runden die ganzzahligen Konvertierungs Funktionen diese auf die nächste gerade ganze Zahl auf. 0,5 rundet beispielsweise auf 0 und 1,5 und 2,5 beide Runden auf 2. Dies wird auch als *die Rundung von Bankiers*bezeichnet, und der Zweck besteht darin, einen Bias auszugleichen, der sich beim Hinzufügen von zahlreichen derartigen Zahlen ansammeln könnte.

     `CInt`und `CLng` unterscheiden sich von der <xref:Microsoft.VisualBasic.Conversion.Int%2A> -Funktion und der- <xref:Microsoft.VisualBasic.Conversion.Fix%2A> Funktion, die den Bruch Teil einer Zahl abschneiden, anstatt Sie zu runden. Außerdem `Fix` geben und `Int` immer einen Wert desselben Datentyps zurück, den Sie übergeben.

- **Datums-/Uhrzeit-Konvertierungen** Verwenden Sie die- <xref:Microsoft.VisualBasic.Information.IsDate%2A> Funktion, um zu bestimmen, ob ein Wert in ein Datum und eine Uhrzeit konvertiert werden kann. `CDate`erkennt Datums Literale und Zeit Literale, aber keine numerischen Werte. Wenn Sie einen Visual Basic 6,0- `Date` Wert in einen- `Date` Wert in Visual Basic 2005 oder höher konvertieren möchten, können Sie die- <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> Methode verwenden.

- **Neutrale Datums-/Uhrzeitwerte.** Der [Date-Datentyp](../data-types/date-data-type.md) enthält immer Datums-und Uhrzeit Informationen. Für den Zweck der Typkonvertierung berücksichtigt Visual Basic 1/1/0001 (1. Januar des Jahres 1) als *neutralen Wert* für das Datum und 00:00:00 (Mitternacht) als neutralen Wert für die Zeit. Wenn Sie einen `Date` Wert in eine Zeichenfolge konvertieren, `CStr` schließt keine neutralen Werte in die resultierende Zeichenfolge ein. Wenn Sie z `#January 1, 0001 9:30:00#` . b. in eine Zeichenfolge konvertieren, ist das Ergebnis "9:30:00 am"; die Datumsinformationen werden unterdrückt. Die Datumsinformationen sind jedoch weiterhin im ursprünglichen `Date` Wert vorhanden und können mit Funktionen wie "Function" wieder hergestellt werden <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> .

- **Kultur Sensitivität.** Die Typkonvertierungs Funktionen, die Zeichen folgen einschließen, führen Konvertierungen auf Grundlage der aktuellen Kultur Einstellungen für die Anwendung aus. `CDate`Erkennt z. b. Datumsformate gemäß der Gebiets Schema Einstellung Ihres Systems. Sie müssen den Tag, den Monat und das Jahr in der richtigen Reihenfolge für Ihr Gebiets Schema angeben, oder das Datum wird möglicherweise nicht richtig interpretiert. Ein langes Datumsformat wird nicht erkannt, wenn es eine Wochentag-Zeichenfolge, z. b. "Mittwoch", enthält.

     Wenn Sie in eine oder aus einer Zeichen folgen Darstellung eines Werts in einem anderen Format als dem durch das Gebiets Schema angegebenen Format konvertieren müssen, können Sie die Visual Basic Typkonvertierungs Funktionen nicht verwenden. Verwenden Sie hierzu die `ToString(IFormatProvider)` -Methode und die `Parse(String, IFormatProvider)` -Methode des Typs dieses Werts. Verwenden Sie z. b., <xref:System.Double.Parse%2A?displayProperty=nameWithType> Wenn Sie eine Zeichenfolge in eine-Zeichenfolge umrechnen `Double` , und verwenden <xref:System.Double.ToString%2A?displayProperty=nameWithType> Sie, wenn Sie einen Wert vom Typ `Double` in eine

## <a name="ctype-function"></a>CType Function

Die [CType-Funktion](ctype-function.md) nimmt ein zweites Argument, `typename` , und `expression` in ein `typename` , wobei `typename` jeder Datentyp, jede Struktur, Klasse oder Schnittstelle sein kann, auf die eine gültige Konvertierung vorhanden ist.

Einen Vergleich von `CType` mit den anderen Schlüsselwörtern für die Typkonvertierung finden Sie unter [DirectCast-Operator](../operators/directcast-operator.md) und [TryCast-Operator](../operators/trycast-operator.md).

## <a name="cbool-example"></a>CBool-Beispiel

Im folgenden Beispiel wird die- `CBool` Funktion verwendet, um Ausdrücke in-Werte zu konvertieren `Boolean` . Wenn ein Ausdruck zu einem Wert ungleich 0 (null) ausgewertet wird, wird `CBool` zurückgegeben `True` ; andernfalls wird zurückgegeben `False` .

[!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]

## <a name="cbyte-example"></a>CByte-Beispiel

Im folgenden Beispiel wird die- `CByte` Funktion verwendet, um einen Ausdruck in eine zu konvertieren `Byte` .

[!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]

## <a name="cchar-example"></a>CChar-Beispiel

Im folgenden Beispiel wird die- `CChar` Funktion verwendet, um das erste Zeichen eines- `String` Ausdrucks in einen-Typ zu konvertieren `Char` .

[!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]

Das Eingabe Argument für `CChar` muss vom Datentyp `Char` oder sein `String` . Sie können nicht verwenden, `CChar` um eine Zahl in ein Zeichen zu konvertieren, da `CChar` einen numerischen Datentyp nicht annehmen kann. Im folgenden Beispiel wird eine Zahl abgerufen, die einen Codepunkt darstellt (Zeichencode) und in das entsprechende Zeichen konvertiert. Es verwendet die <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> -Funktion, um die Zeichenfolge zu erhalten, `CInt` die Zeichenfolge in den-Typ zu konvertieren `Integer` und `ChrW` die Zahl in den-Typ zu konvertieren `Char` .

[!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]

## <a name="cdate-example"></a>CDate-Beispiel

Im folgenden Beispiel wird die- `CDate` Funktion verwendet, um Zeichen folgen in-Werte zu konvertieren `Date` . Im Allgemeinen wird das hart codieren von Datums-und Uhrzeitangaben als Zeichen folgen (wie in diesem Beispiel gezeigt) nicht empfohlen. Verwenden Sie stattdessen Datums Literale und Zeit Literale, wie z. b. #Feb 12, 1969 # und #4:45:23 pm #.

[!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]

## <a name="cdbl-example"></a>CDbl-Beispiel

[!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]

## <a name="cdec-example"></a>CDec-Beispiel

Im folgenden Beispiel wird die- `CDec` Funktion verwendet, um einen numerischen Wert in zu konvertieren `Decimal` .

[!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]

## <a name="cint-example"></a>CInt-Beispiel

Im folgenden Beispiel wird die- `CInt` Funktion verwendet, um einen-Wert in zu konvertieren `Integer` .

[!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]

## <a name="clng-example"></a>CLng-Beispiel

Im folgenden Beispiel wird die- `CLng` Funktion verwendet, um Werte in zu konvertieren `Long` .

[!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]

## <a name="cobj-example"></a>CObj-Beispiel

Im folgenden Beispiel wird die- `CObj` Funktion verwendet, um einen numerischen Wert in zu konvertieren `Object` . Die `Object` Variable selbst enthält nur einen 4-Byte-Zeiger, der auf den `Double` zugewiesenen Wert zeigt.

[!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]

## <a name="csbyte-example"></a>CSByte-Beispiel

Im folgenden Beispiel wird die- `CSByte` Funktion verwendet, um einen numerischen Wert in zu konvertieren `SByte` .

[!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]

## <a name="cshort-example"></a>CShort-Beispiel

Im folgenden Beispiel wird die- `CShort` Funktion verwendet, um einen numerischen Wert in zu konvertieren `Short` .

[!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]

## <a name="csng-example"></a>CSng-Beispiel

Im folgenden Beispiel wird die- `CSng` Funktion verwendet, um Werte in zu konvertieren `Single` .

[!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]

## <a name="cstr-example"></a>CStr-Beispiel

Im folgenden Beispiel wird die- `CStr` Funktion verwendet, um einen numerischen Wert in zu konvertieren `String` .

[!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]

Im folgenden Beispiel wird die- `CStr` Funktion verwendet, um `Date` Werte in-Werte zu konvertieren `String` .

[!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]

`CStr`Rendert immer einen `Date` Wert im Standard Kurzformat für das aktuelle Gebiets Schema, z. b. "6/15/2003 4:35:47 pm". Unter `CStr` drückt jedoch die *neutralen Werte* von 1/1/0001 für das Datum und 00:00:00 für die Zeit.

Weitere Details zu den Werten, die von zurückgegeben `CStr` werden, finden Sie unter [Rückgabewerte für die CStr-Funktion](return-values-for-the-cstr-function.md).

## <a name="cuint-example"></a>CUInt-Beispiel

Im folgenden Beispiel wird die- `CUInt` Funktion verwendet, um einen numerischen Wert in zu konvertieren `UInteger` .

[!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]

## <a name="culng-example"></a>CULng-Beispiel

Im folgenden Beispiel wird die- `CULng` Funktion verwendet, um einen numerischen Wert in zu konvertieren `ULong` .

[!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]

## <a name="cushort-example"></a>CUShort-Beispiel

Im folgenden Beispiel wird die- `CUShort` Funktion verwendet, um einen numerischen Wert in zu konvertieren `UShort` .

[!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]

## <a name="see-also"></a>Weitere Informationen

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
- [Konvertierungsfunktionen](conversion-functions.md)
- [Typkonvertierung in Visual Basic](../../programming-guide/language-features/data-types/type-conversions.md)
