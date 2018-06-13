---
title: 'Gewusst wie: Überprüfen von Zeichenfolgen, die Datumsangaben oder Uhrzeiten darstellen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], validating
- String data type [Visual Basic], validation
ms.assetid: ae7d4b29-3436-4032-bdbf-4650eb1c8e19
ms.openlocfilehash: 411c8517783421b2472c3e4aa77287f8252f179b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647861"
---
# <a name="how-to-validate-strings-that-represent-dates-or-times-visual-basic"></a>Gewusst wie: Überprüfen von Zeichenfolgen, die Datumsangaben oder Uhrzeiten darstellen (Visual Basic)
Im folgenden Codebeispiel wird eine `Boolean` -Wert, der angibt, ob eine Zeichenfolge ein gültiges Datum oder Uhrzeit darstellt.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbVbcnRegEx#2](../../../../visual-basic/programming-guide/language-features/strings/codesnippet/VisualBasic/how-to-validate-strings-that-represent-dates-or-times_1.vb)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Ersetzen Sie `("01/01/03")` und `"9:30 PM"` mit Datum und Uhrzeit, die Sie überprüfen möchten. Können Sie die Zeichenfolge mit einer anderen hartcodierte Zeichenfolge durch Ersetzen einer `String` -Variable ist, oder mit einer Methode, die eine Zeichenfolge zurückgibt, z. B. `InputBox`.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Mit dieser Methode können Sie um die Zeichenfolge zu überprüfen, bevor Sie versuchen, konvertieren die `String` zu einem `DateTime` Variable. Überprüfen Sie zunächst die Datums- oder Zeitangabe, können Sie vermeiden, zur Laufzeit eine Ausnahme generiert.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.Information.IsDate%2A>  
 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A>  
 [Überprüfen von Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
