---
title: 'Vorgehensweise: Überprüfen von Zeichenfolgen, Datumsangaben oder Uhrzeiten darstellen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 1a838d9d156ad9c05a70a4d4d72db1a288731c9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54685398"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Vorgehensweise: Überprüfen von Zeichenfolgen, Datumsangaben oder Uhrzeiten darstellen (Visual Basic)
Im folgenden Codebeispiel wird eine `Boolean` Wert, der angibt, ob eine Zeichenfolge ein gültiger Datums- oder Zeitwert darstellt.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Ersetzen Sie dies `("01/01/03")` und `"9:30 PM"` mit Datum und Uhrzeit, die Sie überprüfen möchten. Können Sie die Zeichenfolge mit einer anderen Zeichenfolge, die hartcodiert und durch Ersetzen einer `String` Variablen, oder mit einer Methode, die eine Zeichenfolge zurückgibt, z. B. `InputBox`.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Mit dieser Methode können Sie um die Zeichenfolge zu überprüfen, bevor Sie versuchen, konvertieren die `String` zu einem `DateTime` Variable. Überprüfen Sie zuerst das Datum oder Uhrzeit, können Sie vermeiden, zur Laufzeit eine Ausnahme generiert.  
  
## <a name="see-also"></a>Siehe auch
- <xref:Microsoft.VisualBasic.Information.IsDate%2A>
- <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>
- [Überprüfen von Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
