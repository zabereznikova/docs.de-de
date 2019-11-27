---
title: 'Gewusst wie: Überprüfen von Zeichenfolgen, die Datumsangaben oder Uhrzeiten darstellen'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 34af6dffeb0d05eaeed38354f8007554b60e91b0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344355"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Gewusst wie: Überprüfen von Zeichenfolgen, die Datumsangaben oder Uhrzeiten darstellen (Visual Basic)
Im folgenden Codebeispiel wird ein `Boolean` Wert festgelegt, der angibt, ob eine Zeichenfolge ein gültiges Datum oder eine gültige Uhrzeit darstellt.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Ersetzen Sie `("01/01/03")` und `"9:30 PM"` durch das Datum und die Uhrzeit, die Sie überprüfen möchten. Sie können die Zeichenfolge durch eine andere hart codierte Zeichenfolge ersetzen, durch eine `String` Variable oder durch eine Methode, die eine Zeichenfolge zurückgibt, wie z. b. `InputBox`.  
  
## <a name="robust-programming"></a>Robuste Programmierung  
 Verwenden Sie diese Methode, um die Zeichenfolge zu validieren, bevor Sie die `String` in eine `DateTime` Variable konvertieren. Wenn Sie das Datum oder die Uhrzeit zuerst überprüfen, können Sie verhindern, dass zur Laufzeit eine Ausnahme ausgelöst wird.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Überprüfen von Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
