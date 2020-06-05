---
title: 'Vorgehensweise: Überprüfen von Zeichenfolgen, die Datumsangaben oder Uhrzeiten darstellen'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 5d153ac29039375386b3cd5f03609b1e4bd1d5bf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410566"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Gewusst wie: Überprüfen von Zeichenfolgen, die Datumsangaben oder Uhrzeiten darstellen (Visual Basic)
Im folgenden Codebeispiel wird ein `Boolean` Wert festgelegt, der angibt, ob eine Zeichenfolge ein gültiges Datum oder eine gültige Uhrzeit darstellt.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  
 Ersetzen `("01/01/03")` `"9:30 PM"` Sie und durch das Datum und die Uhrzeit, die Sie überprüfen möchten. Sie können die Zeichenfolge durch eine andere hart codierte Zeichenfolge, durch eine `String` Variable oder durch eine Methode ersetzen, die eine Zeichenfolge zurückgibt, wie z `InputBox` . b..  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Verwenden Sie diese Methode, um die Zeichenfolge zu validieren, bevor Sie versuchen, in `String` eine Variable zu konvertieren `DateTime` . Wenn Sie das Datum oder die Uhrzeit zuerst überprüfen, können Sie verhindern, dass zur Laufzeit eine Ausnahme ausgelöst wird.  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Überprüfen von Zeichenfolgen in Visual Basic](validating-strings.md)
