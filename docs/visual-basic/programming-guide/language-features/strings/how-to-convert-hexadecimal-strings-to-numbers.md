---
title: 'Gewusst wie: Konvertieren von Hexadezimalzeichenfolgen in Zahlen (Visual Basic)'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af0e6c1e30c116709ed98240de7bf3471fa842d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648641"
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
