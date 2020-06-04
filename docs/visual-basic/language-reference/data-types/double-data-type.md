---
title: Double-Datentyp
ms.date: 07/20/2015
f1_keywords:
- vb.Double
helpviewer_keywords:
- 'identifier type characters [Visual Basic], #'
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- 0 characters [Visual Basic], trailing
- literal type characters [Visual Basic], R
- data types [Visual Basic], assigning
- Double data type [Visual Basic]
- '# identifier type character'
- double-precision numbers
- floating-point numbers [Visual Basic], Double data type
- R literal type character [Visual Basic]
- zeros, trailing
- Double data type
ms.assetid: 0c5670f7-fcb1-453a-bef1-374730cd38fd
ms.openlocfilehash: 899554f427ac77ead465752c35e51ca88d045763
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84415633"
---
# <a name="double-data-type-visual-basic"></a>Double-Datentyp (Visual Basic)

Enthält signierte IEEE 64-Bit (8-Byte)-Gleit Komma Zahlen mit doppelter Genauigkeit, die im Wert von-1.79769313486231570 e + 308 bis-4.94065645841246544 e-324 für negative Werte und von 4.94065645841246544 e-324 bis 1.79769313486231570 e + 308 für positive Werte liegen. Zahlen mit doppelter Genauigkeit speichern eine Näherung einer reellen Zahl.

## <a name="remarks"></a>Bemerkungen

Der `Double` -Datentyp bietet die größte und kleinste mögliche Vergrößerung für eine Zahl.

Der Standardwert von `Double` lautet 0.

## <a name="programming-tips"></a>Programmiertipps

- **Präziser.** Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen bei bestimmten Vorgängen führen, wie z. b. Werte Vergleich und `Mod` Operator. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).

- **Nachfolgende Nullen.** Die Gleit Komma Datentypen verfügen über keine interne Darstellung von nachfolgenden NULL-Zeichen. Sie unterscheiden z. b. nicht zwischen 4,2000 und 4,2. Folglich werden nachfolgende NULL-Zeichen nicht angezeigt, wenn Sie Gleit Komma Werte anzeigen oder drucken.

- **Geben Sie Zeichen ein.** Durch Anhängen des Literaltypzeichens `R` an ein Literal wird der `Double`-Datentyp erzwungen. Wenn z. b. auf einen ganzzahligen Wert folgt `R` , wird der Wert in einen geändert `Double` .

  ```vb
  ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:
  Dim dub As Double = 4.0R
  ```

  Durch Anhängen des Typkennzeichens `#` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Double`-Datentyp erzwungen. Im folgenden Beispiel wird die-Variable `num` als typisiert `Double` :

  ```vb
  Dim num# = 3
  ```

- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Double?displayProperty=nameWithType>-Struktur.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Double?displayProperty=nameWithType>
- [Datentypen](index.md)
- [Decimal-Datentyp](decimal-data-type.md)
- [Single-Datentyp](single-data-type.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Problembehandlung bei Datentypen](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Typzeichen](../../programming-guide/language-features/data-types/type-characters.md)
