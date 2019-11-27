---
title: 'Gewusst wie: Konvertieren von Hexadezimalzeichenfolgen in Zahlen'
ms.date: 01/31/2018
helpviewer_keywords:
- numbers [Visual Basic], hexadecimals
- hexadecimals [Visual Basic], decimals
- examples [Visual Basic], string conversion
- decimals [Visual Basic], hexadecimals
- string conversion [Visual Basic], hexadecimal to numbers
ms.assetid: 76675807-eadb-4c08-bd50-e6c6ff4b8ced
ms.openlocfilehash: f0a97a0c212a64bfa4db4606ee526b666f07877a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347174"
---
# <a name="how-to-convert-hexadecimal-strings-to-numbers-visual-basic"></a>Gewusst wie: Konvertieren von Hexadezimalzeichenfolgen in Zahlen (Visual Basic)

In diesem Beispiel wird eine hexadezimale Zeichenfolge mithilfe der <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>-Methode in eine ganze Zahl konvertiert.

## <a name="to-convert-a-hexadecimal-string-to-a-number"></a>So konvertieren Sie eine hexadezimale Zeichenfolge in eine Zahl

- Verwenden Sie die <xref:System.Convert.ToInt32(System.String,System.Int32)>-Methode, um die in Base-16 ausgedrückte Zahl in eine ganze Zahl zu konvertieren.

  Das erste Argument der <xref:System.Convert.ToInt32(System.String,System.Int32)>-Methode ist die Zeichenfolge, die konvertiert werden soll. Das zweite Argument beschreibt die Basis, in der die Zahl ausgedrückt wird. Hexadezimalwert ist Basis 16.

  [!code-vb[VbVbalrStrings#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#62)]

- Beachten Sie, dass für die hexadezimale Zeichenfolge die folgenden Einschränkungen gelten:

  - Das `&h` Präfix darf nicht enthalten sein.
  - Das `_` Ziffern Trennzeichen kann nicht enthalten sein.

  Wenn das Präfix oder ein Ziffern Trennzeichen vorhanden ist, löst der aufzurufende <xref:System.Convert.ToInt32(System.String,System.Int32)> Methode eine <xref:System.FormatException>aus.

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:System.Convert.ToInt32%2A?displayProperty=nameWithType>
