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
ms.openlocfilehash: 090ec6f3bbf56350fda2ab15c974b0bc6b15e3d3
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162517"
---
# <a name="bc30933-latebound-overload-resolution-cannot-be-applied-to-procedurename-because-the-accessing-instance-is-an-interface-type"></a>BC30933: die lategebundene Überladungs Auflösung kann nicht auf "" angewendet werden, \<procedurename> da die Zugriffs Instanz ein Schnittstellentyp ist.

Der Compiler versucht, einen Verweis auf eine überladene Eigenschaft oder Prozedur aufzulösen, aber der Verweis schlägt fehl, da ein Argument vom Typ ist `Object` und das verweisende Objekt den Datentyp einer Schnittstelle aufweist. Das- `Object` Argument zwingt den Compiler, den Verweis als spät gebunden aufzulösen.

In diesen Fällen löst der Compiler die Überladung durch die implementierende Klasse anstelle der zugrunde liegenden Schnittstelle auf. Wenn die Klasse eine der überladenen Versionen umbenennt, betrachtet der Compiler diese Version nicht als Überladung, da der Name anders ist. Dies bewirkt wiederum, dass der Compiler die umbenannte Version ignoriert, wenn es möglicherweise die richtige Wahl war, den Verweis aufzulösen.

**Fehler-ID:** BC30933

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

- Verwenden `CType` Sie, um das-Argument von `Object` in den Typ umzuwandeln, der von der Signatur der aufzurufenden Überladung angegeben wird.

  Beachten Sie, dass es nicht hilfreich ist, das verweisende Objekt in die zugrunde liegende-Schnittstelle umzuwandeln. Sie müssen das-Argument umwandeln, um diesen Fehler zu vermeiden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein Aufruf einer überladenen `Sub` Prozedur veranschaulicht, die diesen Fehler zur Kompilierzeit verursacht.

```vb
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

Wenn der Compiler im vorherigen Beispiel den-Aufrufvorgang `s1` als geschrieben hat, würde die Auflösung durch die-Klasse `c1` anstelle der-Schnittstelle stattfinden `i1` . Dies bedeutet, dass der Compiler nicht in Erwägung zieht `s2` , weil der Name in anders ist `c1` , obwohl er die richtige Wahl ist, wie durch definiert `i1` .

Sie können den Fehler beheben, indem Sie den-Befehl in einer der folgenden Codezeilen ändern:

```vb
refer.s1(CType(o1, Integer))
refer.s1(CType(o1, Double))
```

Jede der vorangehenden Codezeilen wandelt die Variable explizit `Object` `o1` in einen der für die über Ladungen definierten Parametertypen um.

## <a name="see-also"></a>Siehe auch

- [Prozedurüberladung](../../programming-guide/language-features/procedures/procedure-overloading.md)
- [Overload Resolution](../../programming-guide/language-features/procedures/overload-resolution.md)
- [CType Function](../functions/ctype-function.md)
