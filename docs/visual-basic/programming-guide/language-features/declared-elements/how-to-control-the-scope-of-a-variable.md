---
title: 'Vorgehensweise: Steuern des Gültigkeitsbereichs einer Variablen (Visual Basic)'
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
ms.openlocfilehash: 7f1d671f6657c7810ec605533493a340baac39c9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64610344"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>Vorgehensweise: Steuern des Gültigkeitsbereichs einer Variablen (Visual Basic)
In der Regel wird eine Variable *Bereich*, oder als Referenz in der Region, in dem Sie wurde deklariert, sichtbar. In einigen Fällen die Variable des *Zugriffsebene* können ihren Bereich beeinflussen.  
  
 Weitere Informationen finden Sie unter [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## <a name="scope-at-block-or-procedure-level"></a>Gültigkeitsbereich der Block- oder Prozedurebene  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>Um eine Variable nur innerhalb eines Blocks sichtbar zu machen  
  
- Ort der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) für die Variable zwischen der initiiert und beendet die deklarationsanweisungen dieses Blocks, z. B. zwischen den `For` und `Next` Anweisungen eine `For` Schleife.  
  
     Sie können auf die Variable nur von innerhalb des Blocks verweisen.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>Um eine Variable nur innerhalb einer Prozedur sichtbar zu machen  
  
- Ort der `Dim` -Anweisung für die Variable in der Prozedur, aber außerhalb aller Blöcke (z. B. eine `With`... `End With` Block).  
  
     Sie können auf die Variable nur von innerhalb der Prozedur, einschließlich innerhalb eines beliebigen Blocks enthalten sind, in der Prozedur verweisen.  
  
## <a name="scope-at-module-or-namespace-level"></a>Bereich auf Namespace-Ebene oder Moduls  
 Der Einfachheit halber einen einzelnen Ausdruck *auf Modulebene* gilt gleichermaßen für Module, Klassen und Strukturen. Die Zugriffsebene der einer Modulvariablen Ebene bestimmt den Gültigkeitsbereich. Der Namespace, der das Modul, Klasse oder Struktur enthält, wirkt sich auch auf den Bereich aus.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>Um eine Variable in einem Modul, Klasse oder Struktur sichtbar zu machen  
  
1. Ort der `Dim` -Anweisung für die Variable in das Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.  
  
2. Enthalten die [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort in der `Dim` Anweisung.  
  
3. Sehen Sie sich die Variable aus einer beliebigen Position innerhalb der Module, Klasse oder Struktur, jedoch nicht von außerhalb davon.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>Um eine Variable in einem Namespace sichtbar zu machen  
  
1. Ort der `Dim` -Anweisung für die Variable in das Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.  
  
2. Enthalten die [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) oder [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort in der `Dim` Anweisung.  
  
3. Sie können auf die Variable verweisen, von überall aus innerhalb des Namespaces, die das Modul, Klasse oder Struktur enthält.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine Variable auf Modulebene und schränkt die Sichtbarkeit für Code innerhalb des Moduls.  
  
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
  
 Im vorherigen Beispiel werden alle Prozeduren in Modul definierten `demonstrateScope` können, finden Sie in der `String` Variable `strMsg`. Wenn die `usePrivateVariable` Prozedur aufgerufen wird, wird es zeigt den Inhalt der Zeichenfolgenvariablen `strMsg` in einem Dialogfeld.  
  
 Durch die folgende Änderung zum vorherigen Beispiel die Zeichenfolgenvariable `strMsg` kann vom Code an einer beliebigen Stelle in den Namespace der Deklaration verwiesen werden.  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Je schmaler der Gültigkeitsbereich einer Variablen, die weniger Möglichkeiten haben Sie bei der es versehentlich anstelle einer anderen Variablen mit dem gleichen Namen auf. Sie können auch Probleme mit übereinstimmenden verweisen minimieren.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Je schmaler des Gültigkeitsbereichs einer Variablen, verwendet der geringer ist die Wahrscheinlichkeit, die bösartiger Code eine ungültige vornehmen können.  
  
## <a name="see-also"></a>Siehe auch

- [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)
