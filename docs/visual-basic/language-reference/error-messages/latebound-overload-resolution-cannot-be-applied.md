---
title: Die spät gebundene Überladungsauflösung kann nicht auf "<procedurename>" angewendet werden, da die zugreifende Instanz ein Schnittstellentyp ist.
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: 7215be3f454f4a799124620fb5db520282988035
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55272634"
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a>Spät gebundene überladungsauflösung kann nicht angewendet werden, um "\<Prozedurname >', da die Zugreifende Instanz ein Schnittstellentyp ist.
Der Compiler versucht, einen Verweis auf eine überladene Eigenschaft oder Prozedur aufzulösen, aber der Verweis schlägt fehl, weil ein Argument des Typs `Object` und das verweisende Objekt weist den Datentyp einer Schnittstelle. Die `Object` Argument erzwingt, dass der Compiler zum Auflösen des Verweises als spät gebunden.  
  
 Unter diesen Umständen löst der Compiler die Überladung durch die implementierende Klasse statt über die zugrunde liegenden Schnittstelle. Wenn die Klasse eine der überladenen Versionen umbenennt, berücksichtigt der Compiler nicht diese Version mit einer Überladung, da Sie einen anderen Namen aufweist. Dies bewirkt wiederum, dass den Compiler die umbenannte Version ignoriert, wenn sie die richtige Wahl zum Auflösen des Verweises gegangen sein könnte.  
  
 **Fehler-ID:** BC30933  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwendung `CType` umzuwandelnde das Argument vom `Object` in den Typ angegeben wird, durch die Signatur der Überladung aufgerufen werden soll.  
  
     Beachten Sie, dass es nicht hilfreich sein wird, das verweisende Objekt in der zugrunde liegenden Schnittstelle umwandeln. Sie müssen das Argument, um diesen Fehler zu vermeiden, umwandeln.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen Aufruf einer überladenen `Sub` Prozedur, die zum Zeitpunkt der Kompilierung diesen Fehler verursacht.  
  
```  
Module m1  
    Interface i1  
        Sub s1(ByVal p1 As Integer)  
        Sub s1(ByVal p1 As Double)  
    End Interface  
    Class c1  
        Implements i1  
        Public Overloads Sub s1(ByVal p1 As Integer) Implements i1.s1  
        End Sub  
        Public Overloads Sub s2(ByVal p1 As Double) Implements i1.s1  
        End Sub  
    End Class  
    Sub Main()  
        Dim refer As i1 = New c1  
        Dim o1 As Object = 3.1415  
        ' The following reference is INVALID and causes a compiler error.  
        refer.s1(o1)   
    End Sub  
End Module  
```  
  
 Im vorherigen Beispiel, wenn der Compiler den Aufruf zugelassen `s1` laut würde die Auflösung ausgeführt, über die Klasse `c1` statt die Schnittstelle `i1`. Dies bedeutet, dass der Compiler nicht berücksichtigt, `s2` da seinen Namen unterscheidet `c1`, auch wenn es sich um die richtige Wahl ist gemäß `i1`.  
  
 Sie können den Fehler korrigieren, ändern Sie den Aufruf an eines der folgenden Codezeilen:  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 Jede der vorausgehenden Zeilen Code explizit wandelt die `Object` Variable `o1` auf einen der Parametertypen für die Überladungen definiert.  
  
## <a name="see-also"></a>Siehe auch
- [Prozedurüberladung](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Überladungsauflösung](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)
- [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)
