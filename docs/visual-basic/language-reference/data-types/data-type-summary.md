---
title: "Data Type Summary (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Boolean data type, supported types in Visual Basic"
  - "storage, order of storage"
  - "data types [Visual Basic], Visual Basic"
  - "Single data type, supported types in Visual Basic"
  - "notation, scientific"
  - "memory requirements, data types"
  - "user-defined data types, Visual Basic"
  - "Date data type, Visual Basic"
  - "Visual Basic, data types"
  - "storage, allocation"
  - "Integer data type, Visual Basic data types"
  - "storage, space"
  - "Variant data types, supported types in Visual Basic"
  - "Char data type, Visual Basic data types"
  - "intrinsic data types"
  - "memory consumption, data types"
  - "single-precision numbers"
  - "data types [Visual Basic], order of storage"
  - "Long data type, supported types in Visual Basic"
  - "String data type, Visual Basic data types"
  - "storage order, data types"
  - "StructLayoutAttribute class, Visual Basic data type storage"
  - "scientific notation"
  - "Double data type, Visual Basic data types"
  - "Byte data type, Visual Basic data types"
  - "Object data type, supported types in Visual Basic"
  - "data types [Visual Basic], storage allocation"
  - "double-precision numbers"
  - "data types [Visual Basic], summary"
  - "dates [Visual Basic], data types"
  - "strings [Visual Basic], data types"
  - "memory consumption"
  - "storage order, controlling in Visual Basic"
  - "data types [Visual Basic], memory requirements"
ms.assetid: e975cdb6-64d8-4a4a-ae27-f3b3ed198ae0
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Data Type Summary (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

In der folgenden Tabelle sind die Datentypen von Visual Basic, die Typen der Common Language Runtime, die sie unterstützen, und die entsprechenden nominalen Speicherbelegungen und Wertbereiche aufgeführt.  
  
|Visual Basic\-Datentyp|Common Language Runtime\-Typstruktur|Nominale Speicherbelegung|Wertbereich|  
|----------------------------|------------------------------------------|-------------------------------|-----------------|  
|[Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<xref:System.Boolean>|Abhängig von Implementierungsplattform|`True` oder `False`|  
|[Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<xref:System.Byte>|1 Byte|0 bis 255 \(ohne Vorzeichen\)|  
|[Char](../../../visual-basic/language-reference/data-types/char-data-type.md) \(einzelnes Zeichen\)|<xref:System.Char>|2 Bytes|0 bis 65535 \(ohne Vorzeichen\).|  
|[Datum](../../../visual-basic/language-reference/data-types/date-data-type.md)|<xref:System.DateTime>|8 Bytes|0:00:00 \(Mitternacht\), 1. Januar 0001 bis 23:59:59, 31. Dezember 9999.|  
|[Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<xref:System.Decimal>|16 Bytes|0 bis \+\/\-79.228.162.514.264.337.593.543.950.335 \(\+\/\-7,9...E\+28\) <sup>†</sup> ohne Dezimalzeichen; 0 bis \+\/\-7,9228162514264337593543950335 mit 28 Stellen rechts vom Dezimalzeichen;<br /><br /> kleinste Zahl ungleich 0 \(null\) ist \+\/\-0,0000000000000000000000000001 \(\+\/\-1E\-28\) <sup>†</sup>|  
|[Double](../../../visual-basic/language-reference/data-types/double-data-type.md) \(Gleitkommawert mit doppelter Genauigkeit\)|<xref:System.Double>|8 Bytes|\-1,79769313486231570E\+308 bis \-4,94065645841246544E\-324 <sup>†</sup> für negative Werte;<br /><br /> 4,94065645841246544E\-324 bis 1,79769313486231570E\+308 <sup>†</sup> für positive Werte|  
|[Ganze Zahl](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<xref:System.Int32>|4 Bytes|\-2.147.483.648 bis 2.147.483.647 \(mit Vorzeichen\)|  
|[Long](../../../visual-basic/language-reference/data-types/long-data-type.md) \(lange ganze Zahl\)|<xref:System.Int64>|8 Bytes|\-9.223.372.036.854.775.808 bis 9.223.372.036.854.775.807 \(9,2... E\+18 <sup>†</sup>\) \(mit Vorzeichen\)|  
|[Objekt](../../../visual-basic/language-reference/data-types/object-data-type.md)|<xref:System.Object> \(Klasse\)|4 Bytes auf 32\-Bit\-Plattform<br /><br /> 8 Bytes auf 64\-Bit\-Plattform|In einer Variablen vom Typ `Object` kann jeder beliebige Typ gespeichert werden.|  
|[SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<xref:System.SByte>|1 Byte|\-128 bis 127 \(mit Vorzeichen\)|  
|[Short](../../../visual-basic/language-reference/data-types/short-data-type.md) \(kurze ganze Zahl\)|<xref:System.Int16>|2 Bytes|\-32.768 bis 32.767 \(mit Vorzeichen\)|  
|[Single](../../../visual-basic/language-reference/data-types/single-data-type.md) \(Gleitkommawert mit einfacher Genauigkeit\)|<xref:System.Single>|4 Bytes|\-3,4028235E\+38 bis \-1,401298E\-45 <sup>†</sup> für negative Werte;<br /><br /> 1,401298E\-45 bis 3,4028235E\+38 <sup>†</sup> für positive Werte|  
|[String](../../../visual-basic/language-reference/data-types/string-data-type.md) \(variable Länge\)|<xref:System.String> \(Klasse\)|Abhängig von Implementierungsplattform|0 bis ungefähr 2 Milliarden Unicode\-Zeichen|  
|[UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<xref:System.UInt32>|4 Bytes|0 bis 4.294.967.295 \(ohne Vorzeichen\)|  
|[ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<xref:System.UInt64>|8 Bytes|0 bis 18.446.744.073.709.551.615 \(1,8... E\+19 <sup>†</sup>\) \(ohne Vorzeichen\)|  
|[Benutzerdefiniert](../../../visual-basic/language-reference/data-types/user-defined-data-type.md) \(Struktur\)|\(erbt von <xref:System.ValueType>\)|Abhängig von Implementierungsplattform|Jeder Member in der Struktur hat einen Wertbereich, der von seinem Datentyp bestimmt wird. Dieser ist unabhängig von den Wertbereichen der anderen Member.|  
|[UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<xref:System.UInt16>|2 Bytes|0 bis 65.535 \(ohne Vorzeichen\)|  
  
 <sup>†</sup> In *wissenschaftlicher Schreibweise* verweist "E" auf eine Leistung von 10.  Dementsprechend bezeichnet 3.56E\+2 3.56 x 10<sup>2</sup> oder 356 und 3.56E\-2 3.56 \/ 10<sup>2</sup> oder 0,0356 an.  
  
> [!NOTE]
>  Bei Zeichenfolgen mit Text verwenden Sie die <xref:Microsoft.VisualBasic.Strings.StrConv%2A>\-Funktion zum Konvertieren zwischen verschiedenen Textformaten.  
  
 Zusätzlich zur Angabe eines Datentyps in einer Deklarationsanweisung, können Sie den Datentyp einiger Programmierelemente erzwingen, indem Sie ein Typzeichen verwenden.  Siehe [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## Speicherverbrauch  
 Wenn ein elementarer Datentyp deklariert wird, können Sie nicht davon ausgehen, dass sein Speicherverbrauch dem seiner nominalen Speicherbelegung entspricht.  Dies lässt sich wie folgt begründen:  
  
-   **Speicherzuweisung.** Die Speicherzuweisung durch die Common Language Runtime geschieht auf der Grundlage der Merkmale der Plattform, auf der die Anwendung ausgeführt wird.  Wenn der Arbeitsspeicher beinahe erschöpft ist, werden die deklarierten Elemente u. U. möglichst eng zusammengepackt.  In anderen Fällen werden die Speicheradressen möglicherweise an den gegebenen Hardwarebegrenzungen ausgerichtet, um die Leistung zu optimieren.  
  
-   **Plattformbreite.** Die Speicherzuweisung auf einer 64\-Bit\-Plattform unterscheidet sich von der Speicherzuweisung auf einer 32\-Bit\-Plattform.  
  
### Zusammengesetzte Datentypen  
 Dasselbe gilt für die einzelnen Member zusammengesetzter Datentypen, wie Strukturen und Arrays.  Die einfache Addition der nominalen Speicherbelegungen aller Member des Datentyps liefert kein zuverlässiges Ergebnis.  Überdies sind andere Dinge zu berücksichtigen, z. B. Folgendes:  
  
-   **Zusatzaufwand.** Bestimmte zusammengesetzte Typen erfordern darüber hinaus zusätzlichen Speicher.  Arrays verwenden beispielsweise zusätzlichen Speicher für das Array selbst und die einzelnen Dimensionen.  Auf einer 32\-Bit\-Plattform beträgt diese zusätzliche Kapazität derzeit 12 Bytes plus 8 Bytes pro Dimension.  Auf einer 64\-Bit\-Plattform verdoppeln sich die Anforderungen.  
  
-   **Speicherlayout.** Sie können nicht davon ausgehen, dass die Member im Speicher in der gleichen Reihenfolge wie in der Deklaration angeordnet sind.  Sie können nicht einmal Vorhersagen über die Byteausrichtung \(z. B. 2\-Byte\- oder 4\-Byte\-Grenze\) treffen.  Wenn Sie eine Klasse oder Struktur definieren und das Speicherlayout deren Member steuern müssen, können Sie das <xref:System.Runtime.InteropServices.StructLayoutAttribute>\-Attribut auf die Klasse oder Struktur anwenden.  
  
### Zusatzaufwand für den Object\-Datentyp  
 Ein `Object`, das auf einen elementaren oder zusammengesetzten Datentyp verweist, verwendet zusätzlich zu den im Datentyp enthaltenen Daten weitere 4 Bytes.  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Strings.StrConv%2A>   
 <xref:System.Runtime.InteropServices.StructLayoutAttribute>   
 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)   
 [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)   
 [Efficient Use of Data Types](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)