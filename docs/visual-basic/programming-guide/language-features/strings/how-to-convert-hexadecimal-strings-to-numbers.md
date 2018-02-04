---
title: 'Gewusst wie: Konvertieren von Hexadezimalzeichenfolgen in Zahlen (Visual Basic)'
ms.custom: 
ms.date: 01/31/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
author: petrusha
ms.author: ronpet
ms.manager: wpickett
ms.openlocfilehash: c35ac615e3f87710f934a1cf66e6546625298bd0
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2018
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Gewusst wie: Konvertieren von Hexadezimalzeichenfolgen in Zahlen (Visual Basic)
In diesem Beispiel konvertiert eine hexadezimale Zeichenfolge in eine ganze Zahl mit der <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> Methode.  
  
## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Um eine hexadezimale Zeichenfolge in eine Zahl zu konvertieren.  
  
-   Verwenden der <xref:System.Convert.ToInt32(System.String,System.Int32)> Methode, um die Anzahl, ausgedrückt in Base-16 in eine ganze Zahl zu konvertieren.  
  
     Das erste Argument der <xref:System.Convert.ToInt32(System.String,System.Int32)> Methode ist die zu konvertierende Zeichenfolge. Das zweite Argument wird beschrieben, welche Basis der Zahl ausgedrückt ist; hexadezimale Basis 16 ist.  
  
     [!code-vb[HexConversion](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-hexadecimal-strings-to-numbers_1.vb)]  

- Beachten Sie, dass die hexadezimale Zeichenfolge die folgenden Einschränkungen:

   - Es darf keine enthalten die `&h` Präfix.
   - Es darf keine enthalten die `_` Ziffer Trennzeichen.

   Wenn das Präfix oder ein Ziffer Trennzeichen vorhanden ist, den Aufruf der <xref:System.Convert.ToInt32(System.String,System.Int32)> -Methode löst eine <xref:System.FormatException>.

## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>  
 <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
