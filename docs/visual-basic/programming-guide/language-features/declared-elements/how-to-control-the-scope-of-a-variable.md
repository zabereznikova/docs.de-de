---
title: 'Vorgehensweise: Steuern des Gültigkeitsbereichs einer Variablen'
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
ms.openlocfilehash: 2ce7c1700eec54542719e6e0880466ca136e86f6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91095432"
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen (Visual Basic)

Normalerweise befindet sich eine Variable im Gültigkeits *Bereich*oder in der Region, in der Sie Sie deklarieren, als Verweis sichtbar. In einigen Fällen kann sich die *Zugriffsebene* der Variablen auf den Gültigkeitsbereich auswirken.  
  
 Weitere Informationen finden Sie unter [Scope in Visual Basic](scope.md).  
  
## <a name="scope-at-block-or-procedure-level"></a>Bereich auf Block-oder Prozedur Ebene  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>So machen Sie eine Variable nur innerhalb eines Blocks sichtbar  
  
- Platzieren Sie die [Dim-Anweisung](../../../language-reference/statements/dim-statement.md) für die Variable zwischen den initiierenden und abschließenden Deklarations Anweisungen dieses Blocks, z. b. zwischen der-Anweisung `For` und der-Anweisung `Next` einer- `For` Schleife.  
  
     Sie können nur innerhalb des-Blocks auf die-Variable verweisen.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>So machen Sie eine Variable nur innerhalb einer Prozedur sichtbar  
  
- Platzieren Sie die- `Dim` Anweisung für die Variable innerhalb der Prozedur, aber außerhalb eines Blocks (z `With` . b. eines...- `End With` Blocks).  
  
     Sie können auf die Variable nur innerhalb der Prozedur verweisen, einschließlich der in der Prozedur enthaltenen Blöcke.  
  
## <a name="scope-at-module-or-namespace-level"></a>Bereich auf Modul-oder Namespace Ebene  

 Der Vorteil ist, dass die einzelne Begriffs *Modulebene* gleichermaßen auf Module, Klassen und Strukturen angewendet wird. Die Zugriffsebene einer Variablen auf Modulebene bestimmt ihren Bereich. Der Namespace, der das Modul, die Klasse oder die Struktur enthält, wirkt sich auch auf den Bereich aus.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>So machen Sie eine Variable in einem Modul, einer Klasse oder einer Struktur sichtbar  
  
1. Platzieren Sie die- `Dim` Anweisung für die Variable innerhalb des Moduls, der Klasse oder der Struktur, aber außerhalb der Prozeduren.  
  
2. Fügen Sie das [private](../../../language-reference/modifiers/private.md) -Schlüsselwort in die `Dim` Anweisung ein.  
  
3. Sie können auf die Variable von einer beliebigen Stelle innerhalb des Moduls, der Klasse oder Struktur verweisen, jedoch nicht von außerhalb.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>So machen Sie eine Variable in einem Namespace sichtbar  
  
1. Platzieren Sie die- `Dim` Anweisung für die Variable innerhalb des Moduls, der Klasse oder der Struktur, aber außerhalb der Prozeduren.  
  
2. Fügen Sie das [Friend](../../../language-reference/modifiers/friend.md) -oder [Public](../../../language-reference/modifiers/public.md) -Schlüsselwort in die `Dim` Anweisung ein.  
  
3. Sie können innerhalb des Namespace, der das Modul, die Klasse oder Struktur enthält, auf die Variable verweisen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine Variable auf Modulebene deklariert und deren Sichtbarkeit auf den Code im Modul beschränkt.  
  
```vb  
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
  
 Im vorherigen Beispiel können alle im Modul definierten Prozeduren `demonstrateScope` auf die Variable verweisen `String` `strMsg` . Wenn die `usePrivateVariable` Prozedur aufgerufen wird, wird der Inhalt der Zeichen folgen Variablen `strMsg` in einem Dialogfeld angezeigt.  
  
 Mit der folgenden Änderung am vorangehenden Beispiel kann auf die Zeichen folgen Variable an `strMsg` beliebiger Stelle im Namespace der zugehörigen Deklaration verwiesen werden.  
  
```vb  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>Stabile Programmierung  

 Je geringer der Gültigkeitsbereich einer Variablen ist, desto weniger Möglichkeiten haben Sie, um versehentlich auf diese anstelle einer anderen Variablen mit demselben Namen zu verweisen. Sie können auch Probleme bei der Verweis Übereinstimmung minimieren.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  

 Je geringer der Gültigkeitsbereich einer Variablen ist, desto geringer ist die Wahrscheinlichkeit, dass böswilliger Code diese nicht ordnungsgemäß verwenden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Gültigkeitsbereich in Visual Basic](scope.md)
- [Lebensdauer in Visual Basic](lifetime.md)
- [Zugriffsebenen in Visual Basic](access-levels.md)
- [Variablen](../variables/index.md)
- [Variablen Deklaration](../variables/variable-declaration.md)
- [Dim-Anweisung](../../../language-reference/statements/dim-statement.md)
