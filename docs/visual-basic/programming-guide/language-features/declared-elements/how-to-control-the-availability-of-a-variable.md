---
title: 'Vorgehensweise: Steuern der Verfügbarkeit einer Variablen'
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
ms.openlocfilehash: e6173a0eaa0bf84abb1979711c6df932533c5ce9
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91086113"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>Gewusst wie: Steuern der Verfügbarkeit einer Variablen (Visual Basic)

Sie steuern die Verfügbarkeit einer Variablen, indem Sie Ihre *Zugriffsebene*angeben. Die Zugriffsebene bestimmt, welcher Code über die Berechtigung zum Lesen oder Schreiben der Variablen verfügt.  
  
- Element *Variablen* (auf Modulebene und außerhalb einer Prozedur definiert) werden standardmäßig auf den öffentlichen Zugriff festgelegt. Dies bedeutet, dass jeder Code, den Sie sehen können, darauf zugreifen kann. Dies kann durch Angabe eines Zugriffsmodifizierers geändert werden.  
  
- *Lokale Variablen* (definiert innerhalb einer Prozedur) weisen nominale öffentliche Zugriffe auf, obwohl nur Code in ihrer Prozedur darauf zugreifen kann. Sie können die Zugriffsebene einer lokalen Variablen nicht ändern, aber Sie können die Zugriffsebene der Prozedur ändern, in der Sie enthalten ist.  
  
 Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](access-levels.md).  
  
## <a name="private-and-public-access"></a>Privater und öffentlicher Zugriff  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>So machen Sie eine Variable nur innerhalb des Moduls, der Klasse oder der Struktur zugänglich  
  
1. Platzieren Sie die [Dim-Anweisung](../../../language-reference/statements/dim-statement.md) für die Variable innerhalb des Moduls, der Klasse oder der Struktur, aber außerhalb der Prozeduren.  
  
2. Fügen Sie das [private](../../../language-reference/modifiers/private.md) -Schlüsselwort in die `Dim` Anweisung ein.  
  
     Sie können die Variable von überall innerhalb des Moduls, der Klasse oder der Struktur lesen oder schreiben, jedoch nicht von außerhalb.  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>So machen Sie eine Variable von jedem Code aus zugänglich, der Sie sehen kann  
  
1. Platzieren Sie für eine Element Variable die- `Dim` Anweisung für die-Variable in einem Modul, einer Klasse oder einer Struktur, aber außerhalb der Prozeduren.  
  
2. Schließt das [Public](../../../language-reference/modifiers/public.md) -Schlüsselwort in die- `Dim` Anweisung ein.  
  
     Sie können in jedem Code, der mit der Assembly interagiert, Lese-oder Schreibzugriff auf die Variable erhalten.  
  
 - oder -  
  
1. Platzieren Sie für eine lokale Variable die- `Dim` Anweisung für die Variable in einer Prozedur.  
  
2. Fügen Sie das- `Public` Schlüsselwort nicht in die- `Dim` Anweisung ein.  
  
     Sie können die Variable von jedem beliebigen Ort innerhalb des Verfahrens aus lesen oder schreiben, jedoch nicht von außerhalb.  
  
## <a name="protected-and-friend-access"></a>Geschützter Zugriff und Friend-Zugriff  

 Sie können die Zugriffsebene einer Variablen auf Ihre Klasse und alle abgeleiteten Klassen oder auf Ihre Assembly beschränken. Sie können auch die Union dieser Einschränkungen angeben, die den Zugriff aus Code in einer beliebigen abgeleiteten Klasse oder an einer beliebigen anderen Stelle in derselben Assembly zulässt. Sie geben diese Union an, indem Sie die `Protected` `Friend` Schlüsselwörter und in der gleichen Deklaration kombinieren.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>So machen Sie eine Variable nur innerhalb ihrer Klasse und abgeleiteter Klassen zugänglich  
  
1. Platzieren Sie die- `Dim` Anweisung für die Variable in einer Klasse, aber außerhalb der Prozeduren.  
  
2. Schließen Sie das [geschützte](../../../language-reference/modifiers/protected.md) Schlüsselwort in die- `Dim` Anweisung ein.  
  
     Sie können die Variable von jedem beliebigen Ort innerhalb der Klasse aus lesen oder in eine beliebige Klasse schreiben, die davon abgeleitet ist, aber nicht von außerhalb einer Klasse in der Ableitung-Kette.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>So machen Sie eine Variable nur innerhalb derselben Assembly zugänglich  
  
1. Platzieren Sie die- `Dim` Anweisung für die-Variable in einem Modul, einer Klasse oder einer Struktur, aber außerhalb der Prozeduren.  
  
2. Fügen Sie das [Friend](../../../language-reference/modifiers/friend.md) -Schlüsselwort in die `Dim` Anweisung ein.  
  
     Sie können die Variable von einem beliebigen Speicherort innerhalb des Moduls, der Klasse oder Struktur sowie von einem beliebigen Code in derselben Assembly, aber nicht von außerhalb der Assembly lesen oder schreiben.  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel zeigt Deklarationen von Variablen mit den `Public` `Protected` `Friend` Zugriffsebenen,,, `Protected Friend` und `Private` . Beachten Sie, dass `Dim` Sie das-Schlüsselwort nicht einschließen müssen, wenn die-Anweisung eine Zugriffsebene angibt `Dim` .  
  
```vb  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  

 Wenn die Zugriffsebene einer Variablen restriktiver ist, desto geringer ist die Wahrscheinlichkeit, dass böswilliger Code diese nicht ordnungsgemäß verwenden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Zugriffsebenen in Visual Basic](access-levels.md)
- [Dim-Anweisung](../../../language-reference/statements/dim-statement.md)
- [Öffentlich](../../../language-reference/modifiers/public.md)
- [Gebieten](../../../language-reference/modifiers/protected.md)
- [Friend](../../../language-reference/modifiers/friend.md)
- [Privat](../../../language-reference/modifiers/private.md)
