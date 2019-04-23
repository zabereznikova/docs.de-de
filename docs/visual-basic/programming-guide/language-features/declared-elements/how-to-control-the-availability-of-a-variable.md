---
title: 'Vorgehensweise: Steuern der Verfügbarkeit einer Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
ms.openlocfilehash: fb400b113e3f3305f5b724734b2bf9aa9425d03f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311525"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>Vorgehensweise: Steuern der Verfügbarkeit einer Variablen (Visual Basic)
Sie steuern die Verfügbarkeit einer Variablen durch Angabe der *Zugriffsebene*. Die Zugriffsebene bestimmt, welcher Code verfügt über die Berechtigung zum Lesen oder Schreiben auf die Variable.  
  
-   *Membervariablen* (definiert auf Modulebene und außerhalb einer Prozedur) standardmäßig öffentlichen Zugriff auf, d. h., jeder Code, der sie angezeigt werden kann, kann darauf zugreifen. Sie können dies ändern, indem Sie einen Zugriffsmodifizierer angeben.  
  
-   *Lokale Variablen* (innerhalb einer Prozedur definiert) nominell öffentlichen Zugriff haben, obwohl nur Code in die Prozedur darauf zugreifen kann. Die Zugriffsebene einer lokalen Variablen kann nicht geändert werden, aber Sie können ändern, die Zugriffsebene der Prozedur, die sie enthält.  
  
 Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="private-and-public-access"></a>Privater und öffentlicher Zugriff  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>Um eine Variable zu machen, die nur innerhalb der Module, Klasse oder Struktur zugegriffen werden  
  
1. Ort der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) für die Variable in das Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.  
  
2. Enthalten die [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort in der `Dim` Anweisung.  
  
     Sie Lese- oder Schreibzugriff auf die Variable an einer beliebigen Stelle innerhalb der Module, Klasse oder Struktur, jedoch nicht von außerhalb davon.  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>So auf eine Variable von einem beliebigen Code zugegriffen werden kann, die angezeigt werden können  
  
1. Platzieren Sie nach einer Membervariable der `Dim` -Anweisung für die Variable in einem Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.  
  
2. Enthalten die [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort in der `Dim` Anweisung.  
  
     Sie können lesen oder Schreiben auf die Variable aus jeder Code, der Interoperabilität mit der Assembly.  
  
 - oder -   
  
1. Platzieren Sie für eine lokale Variable, die `Dim` -Anweisung für die Variable innerhalb einer Prozedur.  
  
2. Schließen Sie nicht die `Public` -Schlüsselwort in der `Dim` Anweisung.  
  
     Sie Lese- oder Schreibzugriff auf die Variable an einer beliebigen Stelle innerhalb der Prozedur, aber nicht von außerhalb davon.  
  
## <a name="protected-and-friend-access"></a>Geschützt und Friend-Zugriff  
 Sie können die Zugriffsebene einer Variablen, die die Klasse und keine abgeleiteten Klassen, oder der Assembly einschränken. Sie können auch die Kombination dieser Einschränkungen angeben, die Zugriff von Code in einer abgeleiteten Klasse oder eine beliebige andere Stelle in der gleichen Assembly ermöglicht. Sie geben diese Union, aus der `Protected` und `Friend` Schlüsselwörter in der gleichen Deklaration.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>Um eine Variable nur innerhalb seiner Klasse und alle abgeleiteten Klassen zugänglich zu machen  
  
1. Ort der `Dim` -Anweisung für die Variable innerhalb einer Klasse, aber außerhalb einer Prozedur.  
  
2. Enthalten die [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md) -Schlüsselwort in der `Dim` Anweisung.  
  
     Sie Lese- oder Schreibzugriff auf die Variable an einer beliebigen Stelle innerhalb der Klasse sowie innerhalb eine Klasse abgeleitet, daraus, jedoch nicht von außerhalb einer Klasse in der Ableitungskette.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>Um eine Variable zu machen, die nur innerhalb der gleichen Assembly zugegriffen werden  
  
1. Ort der `Dim` -Anweisung für die Variable in einem Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.  
  
2. Enthalten die [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) -Schlüsselwort in der `Dim` Anweisung.  
  
     Sie Lese- oder Schreibzugriff auf die Variable an einer beliebigen Stelle innerhalb der Module, Klasse oder Struktur sowie von einem beliebigen Code in der gleichen Assembly, jedoch nicht von außerhalb der Assembly.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Deklarationen von Variablen mit `Public`, `Protected`, `Friend`, `Protected Friend`, und `Private` Zugriffsebenen. Hinweis: Wenn die `Dim` -Anweisung gibt eine Zugriffsebene, Sie müssen nicht enthalten die `Dim` Schlüsselwort.  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Die restriktivere die Zugriffsebene einer Variablen, desto geringer ist die Wahrscheinlichkeit, die bösartiger Code eine ungültige vornehmen können es verwenden.  
  
## <a name="see-also"></a>Siehe auch

- [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../../visual-basic/language-reference/modifiers/private.md)
