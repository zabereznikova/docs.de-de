---
title: 'Vorgehensweise: Überprüfen von Zeichenfolgen, Datumsangaben oder Uhrzeiten darstellen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: f24ff05e48327c21c02eb92b07db17266f743a80
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62024611"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Vorgehensweise: Überprüfen von Zeichenfolgen, Datumsangaben oder Uhrzeiten darstellen (Visual Basic)
Im folgenden Codebeispiel wird eine `Boolean` Wert, der angibt, ob eine Zeichenfolge ein gültiger Datums- oder Zeitwert darstellt.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbcnRegEx#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnRegEx/VB/Class1.vb#2)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Ersetzen Sie dies `("01/01/03")` und `"9:30 PM"` mit Datum und Uhrzeit, die Sie überprüfen möchten. Können Sie die Zeichenfolge mit einer anderen Zeichenfolge, die hartcodiert und durch Ersetzen einer `String` Variablen, oder mit einer Methode, die eine Zeichenfolge zurückgibt, z. B. `InputBox`.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Mit dieser Methode können Sie um die Zeichenfolge zu überprüfen, bevor Sie versuchen, konvertieren die `String` zu einem `DateTime` Variable. Überprüfen Sie zuerst das Datum oder Uhrzeit, können Sie vermeiden, zur Laufzeit eine Ausnahme generiert.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Überprüfen von Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
