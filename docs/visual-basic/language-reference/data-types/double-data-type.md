---
title: Double-Datentyp (Visual Basic)
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
ms.openlocfilehash: 701d10a334757a96ffd634204c1e1d5eb5418ce6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62054444"
---
# <a name="double-data-type-visual-basic"></a>Double-Datentyp (Visual Basic)
Speichert signierte IEEE-64-Bit (8 Byte) mit doppelter Genauigkeit Gleitkommazahlen, die in den Wertebereich von - 1.79769313486231570E + 308 bis - liegen 4.94065645841246544E-324 für negative Werte und 4.94065645841246544E-324 bis 1.79769313486231570E + 308 für positive Werte. Zahlen mit doppelter Genauigkeit speichern eine Approximation einer reellen Zahl.  
  
## <a name="remarks"></a>Hinweise  
 Die `Double` -Datentyp stellt die größte und kleinsten möglichen Werte für eine Reihe.  
  
 Der Standardwert von `Double` lautet 0.  
  
## <a name="programming-tips"></a>Programmiertipps  
  
- **Mit einfacher Genauigkeit.** Beim Arbeiten mit Gleitkommazahlen, denken Sie daran, dass sie nicht immer eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen führen, von der bestimmte Vorgänge, z. B. den Wertvergleich und `Mod` Operator. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
- **Nachfolgende Nullen.** Der Gleitkomma-Datentypen keine interne Darstellung für nachfolgende Nullen. Angenommen, unterscheiden sie nicht zwischen 4,2000 und 4.2. Folglich nachfolgende Nullen erscheinen nicht beim Anzeigen oder Drucken Gleitkommawerte.  
  
- **Typzeichen.** Durch Anhängen des Literaltypzeichens `R` an ein Literal wird der `Double`-Datentyp erzwungen. Wenn ein ganzzahliger Wert folgt, wird z. B. `R`, der Wert wird geändert, um eine `Double`.  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     Durch Anhängen des Typkennzeichens `#` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Double`-Datentyp erzwungen. Im folgenden Beispiel ist die Variable `num` typisiert ist, als eine `Double`:  
  
    ```  
    Dim num# = 3  
    ```  
  
- **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Double?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Double?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Decimal-Datentyp](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [Single-Datentyp](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
