---
title: 'Datentypen: Zusammenfassung'
ms.date: 07/20/2015
helpviewer_keywords:
- Boolean data type [Visual Basic], supported types in Visual Basic
- storage [Visual Basic], order of storage
- data types [Visual Basic], Visual Basic
- Single data type [Visual Basic], supported types in Visual Basic
- notation [Visual Basic], scientific
- memory requirements, data types
- user-defined data types [Visual Basic], Visual Basic
- Date data type [Visual Basic], Visual Basic
- Visual Basic, data types
- storage [Visual Basic], allocation
- Integer data type [Visual Basic], Visual Basic data types
- storage [Visual Basic], space
- Variant data types [Visual Basic], supported types in Visual Basic
- Char data type [Visual Basic], Visual Basic data types
- intrinsic data types [Visual Basic]
- memory consumption [Visual Basic], data types
- single-precision numbers
- data types [Visual Basic], order of storage
- Long data type [Visual Basic], supported types in Visual Basic
- String data type [Visual Basic], Visual Basic data types
- storage order, data types
- StructLayoutAttribute class, Visual Basic data type storage
- scientific notation
- Double data type [Visual Basic], Visual Basic data types
- Byte data type [Visual Basic], Visual Basic data types
- Object data type [Visual Basic], supported types in Visual Basic
- data types [Visual Basic], storage allocation
- double-precision numbers
- data types [Visual Basic], summary
- dates [Visual Basic], data types
- strings [Visual Basic], data types
- memory consumption
- storage order, controlling in Visual Basic
- data types [Visual Basic], memory requirements
ms.assetid: e975cdb6-64d8-4a4a-ae27-f3b3ed198ae0
ms.openlocfilehash: 72bd8158880c602fb2cde92a3851c4e8a702c70b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344001"
---
# <a name="data-type-summary-visual-basic"></a>Datentyp: Zusammenfassung (Visual Basic)

In der folgenden Tabelle werden die Visual Basic-Datentypen, ihre unterstützenden Common Language Runtime Typen, ihre nominale Speicher Belegung und ihre Wertebereiche angezeigt.  
  
|Visual Basic-Typ|Common Language Runtime-Typstruktur|Nominale Speicher Belegung|Gültigkeitsbereich|  
|-----------------------|--------------------------------------------|--------------------------------|-----------------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|Hängt von der implementierenden Plattform ab|`True` oder `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1 Byte|0 bis 255 (ohne Vorzeichen)|  
|[Char](../../../visual-basic/language-reference/data-types/char-data-type.md) (einzelnes Zeichen)|<xref:System.Char>|2 Bytes|0 bis 65535 (ohne Vorzeichen)|  
|[Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8 Bytes|0:00:00 (Mitternacht) am 1. Januar 0001 bis 11:59:59 Uhr am 31. Dezember 9999|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16 Bytes|0 bis +/-337 (+/-7.9...E + 28) <sup>†</sup> ohne Dezimaltrennzeichen; 0 bis +/-7.9228162514264337593543950335 mit 28 Stellen rechts vom Dezimaltrennzeichen.<br /><br /> die kleinste Zahl ungleich 0 (null) ist +/-0,0000000000000000000000000001 (+/-1E-28) <sup>†</sup>|  
|[Double](../../../visual-basic/language-reference/data-types/double-data-type.md) (Gleit Komma mit doppelter Genauigkeit)|<xref:System.Double>|8 Bytes|-1.79769313486231570 e + 308 bis-4.94065645841246544 e-324 <sup>†</sup> bei negativen Werten;<br /><br /> 4.94065645841246544 e-324 bis 1.79769313486231570 e + 308 <sup>†</sup> für positive Werte|  
|[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4 Bytes|-2.147.483.648 bis 2.147.483.647 (signiert)|  
|[Long](../../../visual-basic/language-reference/data-types/long-data-type.md) (lange ganze Zahl)|<xref:System.Int64>|8 Bytes|-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807 (9.2... E + 18 <sup>†</sup>) (signiert)|  
|[Objekt](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object> (Klasse)|4 Bytes auf 32-Bit-Plattform<br /><br /> 8 Bytes auf 64-Bit-Plattform|Jeder Typ kann in einer Variablen vom Typ gespeichert werden `Object`|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1 Byte|-128 bis 127 (signiert)|  
|[Short](../../../visual-basic/language-reference/data-types/short-data-type.md) (kurze ganze Zahl)|<xref:System.Int16>|2 Bytes|-32.768 bis 32.767 (signiert)|  
|[Single](../../../visual-basic/language-reference/data-types/single-data-type.md) (Gleit Komma mit einfacher Genauigkeit)|<xref:System.Single>|4 Bytes|-3.4028235 e + 38 bis- -1 401298E e-45 <sup>†</sup> bei negativen Werten;<br /><br /> -1 401298E e-45 bis 3.4028235 e + 38 <sup>†</sup> für positive Werte|  
|[Zeichenfolge](../../../visual-basic/language-reference/data-types/string-data-type.md) (Variable Länge)|<xref:System.String> (Klasse)|Hängt von der implementierenden Plattform ab|0 bis ungefähr 2 Milliarden Unicode-Zeichen|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4 Bytes|0 bis 4.294.967.295 (ohne Vorzeichen)|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8 Bytes|0 bis 18446744073709551615 (1.8... E + 19 <sup>†</sup>) (unsigniert)|  
|[Benutzer definiert](../../../visual-basic/language-reference/data-types/user-defined-data-type.md) (Struktur)|(erbt von <xref:System.ValueType>)|Hängt von der implementierenden Plattform ab|Jeder Member der Struktur hat einen Bereich, der durch seinen Datentyp und unabhängig von den Bereichen der anderen Member bestimmt wird.|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2 Bytes|0 bis 65.535 (ohne Vorzeichen)|  
  
 <sup>†</sup> In *wissenschaftlicher Schreib*Weise bezieht sich "E" auf eine Potenz von 10. "3,56 e + 2" steht für 3,56 x 10<sup>2</sup> oder 356, und "3,56 e-2" bedeutet 3,56/10<sup>2</sup> oder 0,0356.  
  
> [!NOTE]
> Verwenden Sie für Zeichen folgen, die Text enthalten, die <xref:Microsoft.VisualBasic.Strings.StrConv%2A>-Funktion, um ein Textformat in ein anderes zu konvertieren.  
  
 Zusätzlich zur Angabe eines Datentyps in einer Deklarations Anweisung können Sie den Datentyp einiger Programmier Elemente mithilfe eines Typzeichens erzwingen. Siehe [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="memory-consumption"></a>Speicherverbrauch  

 Beim Deklarieren eines elementaren Datentyps ist es nicht sicher anzunehmen, dass der Arbeitsspeicher Verbrauch mit der nominalen Speicher Belegung identisch ist. Dies ist auf folgende Aspekte zurückzuführen:  
  
- **Speicherzuweisung.** Der Common Language Runtime kann Speicher auf der Grundlage der aktuellen Merkmale der Plattform zuweisen, auf der die Anwendung ausgeführt wird. Wenn der Arbeitsspeicher fast voll ist, werden die deklarierten Elemente möglicherweise so nah wie möglich verpackt. In anderen Fällen kann es Ihre Speicheradressen an natürliche Hardware Grenzen ausrichten, um die Leistung zu optimieren.  
  
- **Platt Form Breite.** Die Speicherzuweisung auf einer 64-Bit-Plattform unterscheidet sich von der Zuweisung auf einer 32-Bit-Plattform.  
  
### <a name="composite-data-types"></a>Zusammengesetzte Datentypen  

 Die gleichen Überlegungen gelten für jedes Element eines zusammengesetzten Datentyps, wie z. b. eine Struktur oder ein Array. Sie können sich nicht darauf verlassen, dass Sie einfach die nominalen Speicher Belegungen der typmitglieder hinzufügen. Außerdem gibt es weitere Überlegungen, wie z. b. Folgendes:  
  
- **KV.** Einige zusammengesetzte Typen haben zusätzliche Arbeitsspeicher Anforderungen. Ein Array verwendet beispielsweise zusätzlichen Arbeitsspeicher für das Array selbst und für jede Dimension. Auf einer 32-Bit-Plattform beträgt dieser Aufwand derzeit 12 Bytes plus 8 Bytes für jede Dimension. Auf einer 64-Bit-Plattform wird diese Anforderung verdoppelt.  
  
- **Speicher Layout.** Sie können nicht sicher davon ausgehen, dass die Speicher Reihenfolge im Speicher mit der Deklarations Reihenfolge identisch ist. Sie können nicht sogar Annahmen über die Byte Ausrichtung treffen, z. b. eine 2-Byte-oder 4-Byte-Begrenzung. Wenn Sie eine Klasse oder Struktur definieren und das Speicher Layout der Member steuern müssen, können Sie das <xref:System.Runtime.InteropServices.StructLayoutAttribute>-Attribut auf die Klasse oder Struktur anwenden.  
  
### <a name="object-overhead"></a>Objekt Aufwand  

 Eine `Object`, die auf einen beliebigen elementaren oder zusammengesetzten Datentyp verweist, verwendet zusätzlich zu den im-Datentyp enthaltenen Daten 4 Bytes.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.StrConv%2A>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
