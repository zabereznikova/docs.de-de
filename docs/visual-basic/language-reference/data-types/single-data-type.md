---
title: Single-Datentyp (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Single
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c91dbdf73ed1e26393518001ec8651557e5b780f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="single-data-type-visual-basic"></a>Single-Datentyp (Visual Basic)
Speichert signierte IEEE-32-Bit (4-Byte) einzelne Gleitkommazahlen mit doppelter Genauigkeit im Bereich von - 3,4028235E + 38 bis - 1.401298E-45 für negative Werte und 1.401298E-45 bis 3,4028235E + 38 für positive Werte zulässig sind. Zahlen mit einfacher Genauigkeit Näherung eine einer reellen Zahl.  
  
## <a name="remarks"></a>Hinweise  
 Verwenden der `Single` -Datentyp, um Gleitkommawerte enthalten, die nicht die gesamten Datenbreite des erfordern `Double`. In einigen Fällen die common Language Runtime möglicherweise pack Ihre `Single` Variablen eng zusammen, und speichern Sie den Arbeitsspeicherverbrauch.  
  
 Der Standardwert von `Single` lautet 0.  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Mit einfacher Genauigkeit.** Beim Arbeiten mit Gleitkommazahlen, sollten Sie bedenken, dass sie nicht immer eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen führen, über bestimmte Vorgänge, z. B. Wertvergleich und `Mod` Operator. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Widening.** Die `Single` -Datentyp zu `Double`. Dies bedeutet, dass Sie Sie konvertieren können `Single` auf `Double` ohne dass eine <xref:System.OverflowException?displayProperty=nameWithType> Fehler.  
  
-   **Nachfolgende Nullen.** Der Gleitkomma-Datentypen keine interne Darstellung für nachfolgende 0 Zeichen. Angenommen, unterscheiden sie nicht zwischen 4,2000 und 4.2. Folglich werden nachfolgende 0 Zeichen nicht angezeigt, wenn Sie anzeigen oder Drucken von Gleitkommawerten.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `F` an ein Literal wird der `Single`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `!` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Single`-Datentyp erzwungen.  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Single?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Single?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Decimal-Datentyp](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
