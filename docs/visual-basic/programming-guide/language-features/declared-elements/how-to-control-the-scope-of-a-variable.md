---
title: 'Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 6e8d1178398711226b88fee7e6defd5162b91fcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen (Visual Basic)
In der Regel wird eine Variable ist *Bereich*, sichtbar zu Referenzzwecken innerhalb der Region, in dem Sie wurde deklariert. In einigen Fällen die Variable des *Zugriffsebene* Bereich beeinflussen können.  
  
 Weitere Informationen finden Sie unter [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="scope-at-block-or-procedure-level"></a>Gültigkeitsbereich der-Block oder Prozedurebene  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>Um eine Variable nur innerhalb eines Blocks sichtbar zu machen  
  
-   Ort der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) für die Variable zwischen der Initiierung und Beenden des Blocks, deklarationsanweisungen z. B. zwischen der `For` und `Next` -Anweisungen eine `For` Schleife.  
  
     Sie können auf die Variable nur innerhalb des Blocks verweisen.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>Um eine Variable nur innerhalb einer Prozedur sichtbar zu machen  
  
-   Ort der `Dim` -Anweisung für die Variable in der Prozedur, aber außerhalb aller Blöcke (z. B. eine `With`... `End With` Block).  
  
     Sie können auf die Variable nur innerhalb der Prozedur, einschließlich der in einen beliebigen TextBlock enthalten sind, in der Prozedur verweisen.  
  
## <a name="scope-at-module-or-namespace-level"></a>Gültigkeitsbereich Modul oder einen Namespace-Ebene  
 Der Einfachheit halber einen einzelnen Ausdruck *Modulebene* gilt gleichermaßen für Module, Klassen und Strukturen. Die Zugriffsebene einer Variablen auf der Modulebene bestimmt den Gültigkeitsbereich. Der Namespace, der das Modul, Klasse oder Struktur enthält, wirkt sich auch auf den Bereich aus.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>Um eine Variable in einem Modul, Klasse oder Struktur sichtbar zu machen  
  
1.  Ort der `Dim` -Anweisung für die Variable in das Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.  
  
2.  Enthalten die [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort in der `Dim` Anweisung.  
  
3.  Sie verweisen auf die Variable an einer beliebigen Stelle innerhalb das Modul, Klasse oder Struktur, jedoch nicht von außerhalb davon.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>Um eine Variable in einem Namespace sichtbar zu machen  
  
1.  Ort der `Dim` -Anweisung für die Variable in das Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.  
  
2.  Enthalten die ["Friend"](../../../../visual-basic/language-reference/modifiers/friend.md) oder [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort in der `Dim` Anweisung.  
  
3.  Sie können auf die Variable verweisen, von überall innerhalb des Namespaces, die das Modul, Klasse oder Struktur enthält.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Variable auf Modulebene deklariert und schränkt die Sichtbarkeit für Code innerhalb des Moduls.  
  
```  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 Im vorherigen Beispiel, alle Prozeduren, die im Modul definiert `demonstrateScope` können finden Sie in der `String` Variable `strMsg`. Wenn die `usePrivateVariable` Prozedur aufgerufen wird, es zeigt den Inhalt der Zeichenfolgenvariablen `strMsg` in einem Dialogfeld.  
  
 Mit der folgenden Änderung im vorhergehenden Beispiel, die Zeichenfolgenvariable `strMsg` können von Code an einer beliebigen Stelle in den Namespace der Deklaration bezeichnet werden.  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Umso schmaler der Gültigkeitsbereich einer Variablen, die weniger Möglichkeiten für versehentlich verweisen darauf anstelle einer anderen Variablen mit dem gleichen Namen haben. Sie können auch Probleme mit übereinstimmenden verweisen minimieren.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Umso schmaler Gültigkeitsbereich einer Variablen verwenden desto geringer ist die Wahrscheinlichkeit, die bösartiger Code falsche vornehmen können.  
  
## <a name="see-also"></a>Siehe auch  
 [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)
