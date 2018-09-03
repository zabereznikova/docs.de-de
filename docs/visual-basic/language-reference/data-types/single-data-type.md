---
title: Single-Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Single
helpviewer_keywords:
- Single data type
- F literal type character [Visual Basic]
- trailing zeros
- real numbers
- literal type characters [Visual Basic], F
- trailing 0 characters [Visual Basic]
- identifier type characters [Visual Basic], !
- single-precision numbers
- '! identifier type character'
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- floating-point numbers [Visual Basic], Single data type
- numbers [Visual Basic], real
- zeros, trailing
- numbers [Visual Basic], floating point
ms.assetid: 224a2795-4cd5-496c-8f7a-a4f05a06d45d
ms.openlocfilehash: 98433c0f1d1008664bb994f3b43fe48a753a432c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483644"
---
# <a name="single-data-type-visual-basic"></a>Single-Datentyp (Visual Basic)
Speichert signierte IEEE-32-Bit (4-Byte) mit einfacher Genauigkeit Gleitkommazahlen im Bereich von - 3,4028235E + 38 bis - 1.401298E-45 für negative Werte und 1.401298E-45 bis 3,4028235E + 38 für positive Werte. Zahlen mit einfacher Genauigkeit speichern eine Approximation einer reellen Zahl.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `Single` Datentyp in Gleitkommazahlen-Punktwerte enthalten, die nicht die gesamten Datenbreite des erfordern `Double`. In einigen Fällen die common Language Runtime kann in der Lage, Packen Ihrer `Single` Variablen, die eng zusammen und Arbeitsspeicher belegt.  
  
 Der Standardwert von `Single` lautet 0.  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Mit einfacher Genauigkeit.** Beim Arbeiten mit Gleitkommazahlen, Bedenken Sie, dass sie nicht immer eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen führen, von der bestimmte Vorgänge, z. B. den Wertvergleich und `Mod` Operator. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Erweiternde.** Die `Single` -Datentyp wird zu `Double`. Dies bedeutet, Sie können konvertieren `Single` zu `Double` unabhängig vom eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
-   **Nachfolgende Nullen.** Der Gleitkomma-Datentypen keine interne Darstellung für nachfolgende 0 Zeichen. Angenommen, unterscheiden sie nicht zwischen 4,2000 und 4.2. Nachfolgende 0 Zeichen werden daher nicht angezeigt, wenn Sie anzeigen oder Drucken von Gleitkommazahlen-Punktwerte.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `F` an ein Literal wird der `Single`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `!` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Single`-Datentyp erzwungen.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Single?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Single?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/index.md)  
 [Decimal-Datentyp](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
