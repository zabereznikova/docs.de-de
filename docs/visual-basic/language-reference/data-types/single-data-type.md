---
title: Single-Datentyp
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
ms.openlocfilehash: 60a688c510f6e36dca5809566b37a388429e18c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343917"
---
# <a name="single-data-type-visual-basic"></a>Single-Datentyp (Visual Basic)

Enthält signierte IEEE 32-Bit (4-Byte)-Gleit Komma Zahlen mit einfacher Genauigkeit, die den Wert from-3.4028235 e + 38 bis- -1 401298E e-45 für negative Werte und von -1 401298E e-45 bis 3.4028235 e + 38 für positive Werte enthalten. Zahlen mit einfacher Genauigkeit speichern eine Näherung einer reellen Zahl.  
  
## <a name="remarks"></a>Hinweise  

 Verwenden Sie den `Single`-Datentyp, um Gleit Komma Werte zu enthalten, die nicht die vollständige Daten Breite von `Double`erfordern. In einigen Fällen können die Common Language Runtime ihre `Single` Variablen eng zusammenpacken und den Speicherverbrauch sparen.  
  
 Der Standardwert von `Single` lautet 0.  
  
## <a name="programming-tips"></a>Programmiertipps  
  
- **Präziser.** Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen bestimmter Vorgänge führen, wie z. b. Wert Vergleiche und der `Mod`-Operator. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
- **Tet.** Der `Single`-Datentyp wird zu `Double`erweitert. Dies bedeutet, dass Sie `Single` in `Double` konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType> Fehler auftritt.  
  
- **Nachfolgende Nullen.** Die Gleit Komma Datentypen verfügen über keine interne Darstellung von nachfolgenden 0 Zeichen. Sie unterscheiden z. b. nicht zwischen 4,2000 und 4,2. Folglich werden nachfolgende 0 Zeichen nicht angezeigt, wenn Sie Gleit Komma Werte anzeigen oder drucken.  
  
- **Geben Sie Zeichen ein.** Durch Anhängen des Literaltypzeichens `F` an ein Literal wird der `Single`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `!` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Single`-Datentyp erzwungen.  
  
- **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Single?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Single?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Decimal-Datentyp](../../../visual-basic/language-reference/data-types/decimal-data-type.md)
- [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
- [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
