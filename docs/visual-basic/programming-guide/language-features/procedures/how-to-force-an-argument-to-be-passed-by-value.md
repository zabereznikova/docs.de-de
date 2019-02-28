---
title: 'Vorgehensweise: Erzwingen, dass ein Argument als Wert (Visual Basic) übergeben werden'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- procedures [Visual Basic], calling
- arguments [Visual Basic], in parentheses
- procedure arguments [Visual Basic], in parentheses
- arguments [Visual Basic], changing value
ms.assetid: 77b4f2d2-1055-4c2f-a521-874d1db86946
ms.openlocfilehash: 7bd78772b35e3f336f49c1d39b5f56a3a2076c30
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970284"
---
# <a name="how-to-force-an-argument-to-be-passed-by-value-visual-basic"></a>Vorgehensweise: Erzwingen, dass ein Argument als Wert (Visual Basic) übergeben werden
Den Übergabemechanismus der Prozedurdeklaration. Wenn ein Parameter deklariert wird [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic geht davon aus, das entsprechende Argument als Verweis übergeben. Dadurch wird das Verfahren zum Ändern des Werts des zugrunde liegenden Arguments im aufrufenden Code Programmierelements. Wenn Sie das zugrunde liegende Element für eine solche Änderung schützen möchten, können Sie überschreiben die `ByRef` Übergabemechanismus in der Prozedur aufrufen, indem der Name des Arguments in Klammern einschließen. Diese Klammern sind zusätzlich zu den Klammern einschließen der Liste der Argumente im Aufruf.  
  
 Der aufrufende Code kann nicht überschrieben. eine [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) Mechanismus.  
  
### <a name="to-force-an-argument-to-be-passed-by-value"></a>Erzwingen Sie ein Argument als Wert übergeben werden  
  
-   Wenn der entsprechende Parameter deklariert wird `ByVal` in der Prozedur, Sie müssen keine weiteren Schritte. Visual Basic erwartet, dass bereits das Argument als Wert übergeben.  
  
-   Wenn der entsprechende Parameter deklariert wird `ByRef` setzen Sie in der Prozedur das Argument im Aufruf Prozedur in Klammern.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `ByRef` Parameterdeklaration. Im Aufruf, die erzwingt, dass `ByVal`, beachten Sie die zwei Ebenen von Klammern.  
  
 [!code-vb[VbVbcnProcedures#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#39)]  
  
 [!code-vb[VbVbcnProcedures#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#40)]  
  
 Wenn `str` in der Argumentliste in zusätzlichen Klammern eingeschlossen ist die `setNewString` Prozedur Wert im aufrufenden Code nicht ändern kann und `MsgBox` zeigt "Kann nicht ersetzt werden, wenn ByVal übergeben". Wenn `str` ist nicht eingeschlossen in zusätzlichen Klammern kann die Prozedur ändern, und `MsgBox` zeigt "Dies ist es sich um einen neuen Wert für das Argument InString."  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Wenn Sie eine Variable als Verweis übergeben, müssen Sie verwenden die `ByRef` Schlüsselwort, um diesen Mechanismus angeben.  
  
 Der Standardwert in Visual Basic ist, Argumente als Wert übergeben. Allerdings ist es guter Programmierstil, auch die [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) oder [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) Schlüsselwort für jeden deklarierten Parameter. Dadurch wird Ihr Code einfacher zu lesen.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Wenn eine Prozedur einen Parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), die richtige Ausführung des Codes abhängen, wird das zugrunde liegende Element im aufrufenden Code ändern können. Wenn der aufrufende Code diesen Mechanismus aufrufen, überschreibt indem Sie das Argument in Klammern einschließen, oder wenn ein nicht änderbarer Argument übergeben, kann die Prozedur nicht das zugrunde liegende Element ändern. Dies kann unerwartete Ergebnisse im aufrufenden Code erzeugen.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Es ist immer ein potenzielles Risiko einer Prozedur zum Ändern des Werts, der ein Argument im aufrufenden Code zugrunde liegt. Stellen Sie sicher, dass Sie erwarten, dass dieser Wert geändert werden, und auf Gültigkeit überprüft werden vor der Verwendung vorbereitet werden.  
  
## <a name="see-also"></a>Siehe auch
- [Verfahren](./index.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Vorgehensweise: Übergeben von Argumenten an eine Prozedur](./how-to-pass-arguments-to-a-procedure.md)
- [Übergeben von Argumenten als Wert und als Verweis](./passing-arguments-by-value-and-by-reference.md)
- [Unterschiede zwischen veränderbaren und nicht veränderbaren Argumenten](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [Unterschiede zwischen dem Übergeben von Argumenten als Wert und als Verweis](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [Vorgehensweise: Ändern des Werts eines Prozedurarguments](./how-to-change-the-value-of-a-procedure-argument.md)
- [Vorgehensweise: Schützen eines Prozedurarguments gegen Wertänderungen](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [Übergeben von Argumenten nach Position und Name](./passing-arguments-by-position-and-by-name.md)
- [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
