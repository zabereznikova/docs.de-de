---
title: 'Vorgehensweise: Konvertieren von Hexadezimalzeichenfolgen in Zahlen (Visual Basic)'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: ddb7b39f7a47234c003ca16e1d7ea013e113c108
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59773687"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Vorgehensweise: Konvertieren von Hexadezimalzeichenfolgen in Zahlen (Visual Basic)

In diesem Beispiel wird eine hexadezimale Zeichenfolge konvertiert, um eine ganze Zahl mit dem <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType> Methode.

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>Zum Konvertieren einer hexadezimalen Zeichenfolge in eine Zahl

- Verwenden der <xref:System.Convert.ToInt32(System.String,System.Int32)> Methode, um die Anzahl, ausgedrückt in Base-16 in eine ganze Zahl zu konvertieren.

  Das erste Argument von der <xref:System.Convert.ToInt32(System.String,System.Int32)> Methode ist die zu konvertierende Zeichenfolge. Das zweite Argument wird beschrieben, welche Basis der Zahl ausgedrückt wird; hexadezimale Basis 16 ist.

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- Beachten Sie, dass die hexadezimale Zeichenfolge die folgenden Einschränkungen:

  - Es darf keine enthalten die `&h` Präfix.
  - Es darf keine enthalten die `_` Zifferntrennzeichen.

  Wenn das Präfix oder Zifferntrennzeichen vorhanden ist, den Aufruf der <xref:System.Convert.ToInt32(System.String,System.Int32)> -Methode löst eine <xref:System.FormatException>.

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
