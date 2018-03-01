---
title: Double-Datentyp (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ad0e8082edfb7b7d96b0ca2019da88514e5b3b09
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="double-data-type-visual-basic"></a>Double-Datentyp (Visual Basic)
Speichert signierte IEEE-64-Bit (8 Byte) mit doppelter Genauigkeit Gleitkommazahlen, die von - 1.79769313486231570E + 308 bis - Wertebereich 4.94065645841246544E-324 für negative Werte und 4.94065645841246544E-324 bis 1.79769313486231570E + 308 für positive Werte zulässig sind. Zahlen mit doppelter Genauigkeit Näherung eine einer reellen Zahl.  
  
## <a name="remarks"></a>Hinweise  
 Die `Double` -Datentyp stellt den größten und kleinsten möglichen Werte für einige.  
  
 Der Standardwert von `Double` lautet 0.  
  
## <a name="programming-tips"></a>Programmiertipps  
  
-   **Mit einfacher Genauigkeit.** Wenn Sie mit Gleitkommazahlen arbeiten, denken Sie daran, dass sie nicht immer eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen führen, über bestimmte Vorgänge, z. B. Wertvergleich und `Mod` Operator. Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
-   **Nachfolgende Nullen.** Der Gleitkomma-Datentypen keine interne Darstellung des Nachstellen von 0 (null) Zeichen. Angenommen, unterscheiden sie nicht zwischen 4,2000 und 4.2. Folglich Nachstellen von 0 (null) Zeichen erscheinen nicht beim Anzeigen oder Drucken Gleitkommawerte.  
  
-   **Typzeichen.** Durch Anhängen des Literaltypzeichens `R` an ein Literal wird der `Double`-Datentyp erzwungen. Wenn Sie ein ganzzahligen Wert folgt, wird z. B. `R`, der Wert wird geändert, um eine `Double`.  
  
    ```  
    ' Visual Basic expands the 4 in the statement Dim dub As Double = 4R to 4.0:  
    Dim dub As Double = 4.0R  
    ```  
  
     Durch Anhängen des Typkennzeichens `#` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Double`-Datentyp erzwungen. Im folgenden Beispiel wird die Variable `num` als typisiert ist, eine `Double`:  
  
    ```  
    Dim num# = 3  
    ```  
  
-   **Framework-Typ.** Der entsprechende Typ in .NET Framework ist die <xref:System.Double?displayProperty=nameWithType>-Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Double?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Decimal-Datentyp](../../../visual-basic/language-reference/data-types/decimal-data-type.md)  
 [Single-Datentyp](../../../visual-basic/language-reference/data-types/single-data-type.md)  
 [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)  
 [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)  
 [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)  
 [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
