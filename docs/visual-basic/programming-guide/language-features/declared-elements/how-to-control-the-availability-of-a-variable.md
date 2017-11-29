---
title: "Gewusst wie: Steuern der Verfügbarkeit einer Variablen (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 004fb101661fadeaee084e1f9374ca8332ac7234
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>Gewusst wie: Steuern der Verfügbarkeit einer Variablen (Visual Basic)
Sie steuern die Verfügbarkeit einer Variablen durch Angabe seiner *Zugriffsebene*. Die Zugriffsebene bestimmt, welcher Code verfügt über die Berechtigung zum Lesen oder Schreiben auf die Variable.  
  
-   *Membervariablen* (auf Modulebene und außerhalb einer Prozedur definiert) standardmäßig öffentlichen Zugriff auf, d. h. jeglicher Code, der sie angezeigt werden kann darauf zugreifen kann. Sie können dies ändern, indem Sie einen Zugriffsmodifizierer angeben.  
  
-   *Lokale Variablen* (innerhalb einer Prozedur definiert) nominell öffentlichen Zugriff haben, obwohl nur Code innerhalb ihrer Prozedur darauf zugreifen kann. Die Zugriffsebene einer lokalen Variablen kann nicht geändert werden, aber Sie können die Zugriffsebene der Prozedur, die es enthält ändern.  
  
 Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="private-and-public-access"></a>Privater und öffentlicher Zugriff  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>Eine Variable nur innerhalb seiner-Modul, Klasse oder Struktur zugänglich gemacht  
  
1.  Ort der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) für die Variable in das Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.  
  
2.  Enthalten die [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort in der `Dim` Anweisung.  
  
     Sie Lese- oder Schreibzugriff auf die Variable an einer beliebigen Stelle innerhalb das Modul, Klasse oder Struktur, jedoch nicht von außerhalb davon.  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>Um eine Variable von einem beliebigen Code verfügbar, die sie anzeigen können  
  
1.  Platzieren Sie nach einer Membervariable der `Dim` -Anweisung für die Variable in einem Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.  
  
2.  Enthalten die [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort in der `Dim` Anweisung.  
  
     Sie können lesen oder Schreiben auf die Variable von einem beliebigen Code, die Interoperabilität mit der Assembly.  
  
 - oder -   
  
1.  Platzieren Sie für eine lokale Variable, die `Dim` -Anweisung für die Variable innerhalb einer Prozedur.  
  
2.  Schließen Sie nicht die `Public` -Schlüsselwort in der `Dim` Anweisung.  
  
     Sie Lese- oder Schreibzugriff auf die Variable an einer beliebigen Stelle innerhalb der Prozedur, jedoch nicht von außerhalb davon.  
  
## <a name="protected-and-friend-access"></a>Geschützte und Friend-Zugriff  
 Sie können die Zugriffsebene einer Variablen auf ihre Klasse und keine abgeleiteten Klassen oder in einer Assembly einschränken. Sie können auch die Kombination dieser Einschränkungen angeben, die Zugriff von Code in einer abgeleiteten Klasse oder in eine beliebige andere Stelle in der gleichen Assembly erlaubt. Sie geben diese Union kombinierten der `Protected` und `Friend` Schlüsselwörter in der gleichen Deklaration.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>Um eine Variable nur innerhalb der Klasse und alle abgeleiteten Klassen zugänglich zu machen  
  
1.  Ort der `Dim` -Anweisung für die Variable innerhalb einer Klasse, aber außerhalb einer Prozedur.  
  
2.  Enthalten die [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md) -Schlüsselwort in der `Dim` Anweisung.  
  
     Sie Lese- oder Schreibzugriff auf die Variable an einer beliebigen Stelle innerhalb der Klasse sowie innerhalb eine Klasse abgeleitet, jedoch nicht von außerhalb einer Klasse in der Ableitungskette.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>Eine Variable kann nur zugegriffen werden innerhalb der gleichen Assembly vornehmen.  
  
1.  Ort der `Dim` -Anweisung für die Variable in einem Modul, Klasse oder Struktur, aber außerhalb einer Prozedur.  
  
2.  Enthalten die ["Friend"](../../../../visual-basic/language-reference/modifiers/friend.md) -Schlüsselwort in der `Dim` Anweisung.  
  
     Sie Lese- oder Schreibzugriff auf die Variable an einer beliebigen Stelle in das Modul, Klasse oder Struktur, sowie von einem beliebigen Code in derselben Assembly, jedoch nicht von außerhalb der Assembly.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Deklarationen von Variablen mit `Public`, `Protected`, `Friend`, `Protected Friend`, und `Private` Zugriffsebenen. Beachten Sie, dass bei der `Dim` -Anweisung gibt eine Zugriffsebene, müssen Sie nicht einschließen der `Dim` Schlüsselwort.  
  
```  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Die restriktivere Zugriffsebene einer Variablen, desto geringer ist die Wahrscheinlichkeit, die bösartiger Code falsche vornehmen können verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [Public](../../../../visual-basic/language-reference/modifiers/public.md)  
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../../visual-basic/language-reference/modifiers/private.md)
