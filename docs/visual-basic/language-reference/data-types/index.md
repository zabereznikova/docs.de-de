---
title: 'Datentyp: Zusammenfassung (Visual Basic)'
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
ms.openlocfilehash: 29e5cbe09026dd52811c6c5fb88e940b45b7c0bb
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58821971"
---
# <a name="data-type-summary-visual-basic"></a>Datentyp: Zusammenfassung (Visual Basic)
Die folgende Tabelle zeigt die Visual Basic-Datentypen, die unterstützenden Typen common Language Runtime, die nominale Speicherzuordnung und ihre Wertebereiche.  
  
|Visual Basic-Typ|Common Language Runtime-Typ-Struktur|Speicherzuweisung nominale|Wertebereich|  
|-----------------------|--------------------------------------------|--------------------------------|-----------------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|Abhängig von der Plattform|`True` oder `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1 Byte|0 bis 255 (ohne Vorzeichen)|  
|[Char](../../../visual-basic/language-reference/data-types/char-data-type.md) (einzelnes Zeichen)|<xref:System.Char>|2 Bytes|0 bis 65535 (ohne Vorzeichen)|  
|[Date](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8 Bytes|0:00:00 (Mitternacht) am 1. Januar 0001 bis 23:59:59 Uhr am 31. Dezember 9999|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16 Bytes|0 bis + / – 79.228.162.514.264.337.593.543.950.335 (+/-7.9... E + 28) <sup>†</sup> ohne Dezimaltrennzeichen; 0 bis + / – 7,9228162514264337593543950335 mit 28 Stellen rechts vom Dezimalkomma;<br /><br /> kleinste Zahl ungleich NULL ist + / – 0,0000000000000000000000000001 (+/-1E-28) <sup>†</sup>|  
|[Doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md) (Gleitkommazahl mit doppelter Genauigkeit)|<xref:System.Double>|8 Bytes|-1.79769313486231570E + 308 bis - 4.94065645841246544E-324 <sup>†</sup> für negative Werte;<br /><br /> 4.94065645841246544E-324 bis 1.79769313486231570E + 308 <sup>†</sup> für positive Werte|  
|[Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4 Bytes|zwischen – 2.147.483.648 und 2.147.483.647 sein (mit Vorzeichen)|  
|[Lange](../../../visual-basic/language-reference/data-types/long-data-type.md) (lange ganze Zahl)|<xref:System.Int64>|8 Bytes|9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807 (9.2... E + 18 <sup>†</sup>) (mit Vorzeichen)|  
|[Objekt](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object> (Klasse)|4 Byte für 32-Bit-Plattform<br /><br /> 8 Bytes auf 64-Bit-Plattform|Jede Art kann in einer Variablen des Typs gespeichert werden `Object`|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1 Byte|-128 bis 127 (mit Vorzeichen)|  
|[Kurze](../../../visual-basic/language-reference/data-types/short-data-type.md) (kurze ganze Zahl)|<xref:System.Int16>|2 Bytes|32.768 bis 32.767 (mit Vorzeichen)|  
|[Einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md) (Gleitkommazahl mit einfacher Genauigkeit)|<xref:System.Single>|4 Bytes|-3,4028235E + 38 bis - 1.401298E-45 <sup>†</sup> für negative Werte;<br /><br /> 1.401298E-45 bis 3,4028235E + 38 <sup>†</sup> für positive Werte|  
|[Zeichenfolge](../../../visual-basic/language-reference/data-types/string-data-type.md) (mit variabler Länge)|<xref:System.String> (Klasse)|Abhängig von der Plattform|0 bis ca. 2 Milliarden Unicode-Zeichen|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4 Bytes|0 bis 4.294.967.295 (ohne Vorzeichen)|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8 Bytes|0 bis 18.446.744.073.709.551.615 (1.8... E + 19 <sup>†</sup>) (ohne Vorzeichen)|  
|[Eine benutzerdefinierte](../../../visual-basic/language-reference/data-types/user-defined-data-type.md) (Struktur)|(erbt von <xref:System.ValueType>)|Abhängig von der Plattform|Jedes Element der Struktur weist einen Bereich, der durch den Datentyp und unabhängig von den Wertbereichen der anderen Member bestimmt|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2 Bytes|0 bis 65.535 (ohne Vorzeichen)|  
  
 <sup>†</sup> In *wissenschaftliche Schreibweise*, "E" bezieht sich auf eine Potenz von 10. Dementsprechend bezeichnet 3.56E + 2 3.56 x 10<sup>2</sup> oder 356 und bezeichnet 3.56E-2 Gibt an, 3.56 / 10<sup>2</sup> oder 0,0356.  
  
> [!NOTE]
>  Für Zeichenfolgen, die Text enthält, verwenden die <xref:Microsoft.VisualBasic.Strings.StrConv%2A> Funktion, die aus einem Text-Format in einen anderen konvertieren.  
  
 Zusätzlich zum Angeben eines Datentyps in einer deklarationsanweisung, können Sie den Datentyp der einige Programmierelemente erzwingen, mit einem Typzeichen. Finden Sie unter [-Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="memory-consumption"></a>Speicherverbrauch  
 Wenn Sie einen elementarer Datentyp deklarieren, ist es nicht davon ausgehen, dass der Speicherverbrauch die Zuordnung von nominalen identisch ist. Dies liegt an die folgenden Überlegungen:  
  
-   **Speicherzuweisung.** Die common Language Runtime kann Speicher, die basierend auf den aktuellen Merkmalen der Plattform, auf dem die Anwendung ausgeführt wird, zugewiesen. Wenn Arbeitsspeicher fast voll ist, können sie Ihre deklarierte Elemente so weit zusammen, wie möglich pack. In anderen Fällen kann es die Speicheradressen natürlichen hardwarebeschränkungen gelten zum Optimieren der Leistung auszurichten.  
  
-   **Breite der Plattform.** Speicherzuweisung auf einer 64-Bit-Plattform unterscheidet sich von der Zuweisung auf einer 32-Bit-Plattform.  
  
### <a name="composite-data-types"></a>Zusammengesetzte Datentypen  
 Die gleichen Überlegungen gelten für jedes Element einen zusammengesetzten Datentyp, z. B. eine Struktur oder ein Array. Sie können nicht auf die einfach Membern des Typs der nominalen speicherbelegungen addieren basieren. Darüber hinaus stehen auch andere Aspekte, z. B. Folgendes:  
  
-   **Aufwand.** Einige zusammengesetzten Typen haben Anforderungen an den zusätzlichen Arbeitsspeicher. Ein Array verwendet beispielsweise zusätzlichen Speicherplatz für das Array selbst sowie für jede Dimension. Auf einer 32-Bit-Plattform befindet sich dieser Aufwand derzeit 12 Byte plus 8 Bytes für jede Dimension. Auf einer 64-Bit-Plattform wird diese Anforderung verdoppelt.  
  
-   **Speicherlayout.** Sie können nicht davon ausgehen, dass die Reihenfolge der im Speicher in der Reihenfolge der Deklaration identisch ist. Sie können nicht selbst Annahmen zu Byte-Ausrichtung, wie z. B. eine 2-Byte- oder 4-Byte-Grenze. Wenn Sie eine Klasse oder Struktur definieren, und Sie das Speicherlayout Membern steuern müssen, können Sie die <xref:System.Runtime.InteropServices.StructLayoutAttribute> -Attribut auf die Klasse oder Struktur.  
  
### <a name="object-overhead"></a>Objekt-Mehraufwand  
 Ein `Object` verweisen auf alle elementaren oder zusammengesetzten Daten Typ verwendet 4 Bytes zusätzlich zu den Daten, die in den Datentyp enthalten.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Strings.StrConv%2A>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
