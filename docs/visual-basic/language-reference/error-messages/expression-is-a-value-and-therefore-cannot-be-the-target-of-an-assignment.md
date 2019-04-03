---
title: Der Ausdruck ist ein Wert und kann nicht als Ziel einer Zuweisung verwendet werden
ms.date: 07/20/2015
f1_keywords:
- bc30068
- vbc30068
helpviewer_keywords:
- BC30068
ms.assetid: d65141e1-f31e-4ac5-a3b8-0b2e02a71ebf
ms.openlocfilehash: 3027be6ee4ed3664b81c661b6a086a3604573833
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826131"
---
# <a name="expression-is-a-value-and-therefore-cannot-be-the-target-of-an-assignment"></a>Der Ausdruck ist ein Wert und kann nicht als Ziel einer Zuweisung verwendet werden
Eine Anweisung versucht, ein Ausdruck einen Wert zuweisen. Sie können einen Wert nur auf eine schreibbare Variable, eine Eigenschaft oder ein Arrayelement zur Laufzeit zuweisen. Im folgende Beispiel wird veranschaulicht, wie dieser Fehler kann auftreten.  
  
```  
Dim yesterday As Integer  
ReadOnly maximum As Integer = 45  
yesterday + 1 = DatePart(DateInterval.Day, Now)  
' The preceding line is an ERROR because of an expression on the left.  
maximum = 50  
' The preceding line is an ERROR because maximum is declared ReadOnly.  
```  
  
 Ähnliche Beispiele können auf Eigenschaften und Elemente des Arrays anwenden.  
  
 **Indirekten Zugriff.** Dieser Fehler kann auch von Indirekter Zugriff über einen Werttyp generiert werden. Beachten Sie im folgenden Codebeispiel wird, der versucht, den Wert festlegen <xref:System.Drawing.Point> von indirekten Zugriff über <xref:System.Windows.Forms.Control.Location%2A>.  
  
```  
' Assume this code runs inside Form1.  
Dim exitButton As New System.Windows.Forms.Button()  
exitButton.Text = "Exit this form"  
exitButton.Location.X = 140  
' The preceding line is an ERROR because of no storage for Location.  
```  
  
 Die letzte Anweisung im obigen Beispiel schlägt fehl, da nur eine temporäre Zuordnung für erstellt die <xref:System.Drawing.Point> vom zurückgegebene Struktur der <xref:System.Windows.Forms.Control.Location%2A> Eigenschaft. Eine Struktur ein Werttyp ist, und die temporäre Struktur wird nicht beibehalten, nachdem die Anweisung ausgeführt wird. Das Problem ist behoben, durch Deklarieren und verwenden eine Variable für <xref:System.Windows.Forms.Control.Location%2A>, erstellt eine permanente Zuordnung für die <xref:System.Drawing.Point> Struktur. Das folgende Beispiel zeigt Code, der die letzte Anweisung der im vorherigen Beispiel ersetzen kann.  
  
```  
Dim exitLocation as New System.Drawing.Point(140, exitButton.Location.Y)  
exitButton.Location = exitLocation  
```  
  
 **Fehler-ID:** BC30068  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn die Anweisung ein Ausdruck einen Wert zuweist, ersetzen Sie den Ausdruck durch eine einzelne schreibbare Variable, eine Eigenschaft oder ein Arrayelement aus.  
  
-   Wenn die Anweisung indirekten Zugriff über einen Werttyp (in der Regel eine Struktur) ist, erstellen Sie eine Variable für den Werttyp.  
  
-   Weisen Sie die entsprechende Struktur (oder anderen Werttyp) auf die Variable an.  
  
-   Verwenden Sie die Variable, um Zugriff auf die Eigenschaft es sich um einen Wert zuzuweisen.  
  
## <a name="see-also"></a>Siehe auch

- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
- [Problembehandlung bei Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/troubleshooting-procedures.md)
