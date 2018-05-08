---
title: Spät gebundene überladungsauflösung. kann nicht angewendet werden, um &#39; &lt;Prozedurname&gt; &#39; , da die Instanz beim Zugriff auf ein Schnittstellentyp ist.
ms.date: 07/20/2015
f1_keywords:
- vbc30933
- bc30933
helpviewer_keywords:
- overload resolution [Visual Basic], with late-bound argument
- BC30933
ms.assetid: 8182eea0-dd34-4d6e-9ca0-41d8713e9dc4
ms.openlocfilehash: e41cbf30f06547ef39553e31542e4e8b6df49a3b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="latebound-overload-resolution-cannot-be-applied-to-39ltprocedurenamegt39-because-the-accessing-instance-is-an-interface-type"></a>Spät gebundene überladungsauflösung. kann nicht angewendet werden, um &#39; &lt;Prozedurname&gt; &#39; , da die Instanz beim Zugriff auf ein Schnittstellentyp ist.
Der Compiler versucht, einen Verweis auf eine überladene Eigenschaft oder Prozedur aufzulösen, aber der Verweis schlägt fehl, da ein Argument des Typs ist `Object` und das verweisende Objekt weist den Datentyp einer Schnittstelle. Die `Object` Argument zwingt den Compiler zum Auflösen des Verweises als spät gebunden.  
  
 Unter diesen Umständen löst der Compiler die Überladung über die implementierende Klasse anstelle von über die zugrunde liegenden Schnittstelle. Wenn die Klasse mit einer der überladenen Versionen umbenennt, berücksichtigt der Compiler nicht diese Version mit einer Überladung, da Sie einen anderen Namen aufweist. Dies Compiler wiederum der die umbenannte Version ignoriert, wenn sie die richtige Auswahl den Verweis aufgelöst gegangen sein könnte.  
  
 **Fehler-ID:** BC30933  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwendung `CType` das Argument aus umwandeln `Object` in den angegebenen, durch die Signatur der Überladung, die Sie aufrufen möchten.  
  
     Beachten Sie, dass er nicht behoben wird, das verweisende Objekt, das die zugrunde liegende Schnittstelle umwandeln. Das Argument, um diesen Fehler vermeiden, müssen Sie eine Umwandlung.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen Aufruf einer überladenen `Sub` Prozedur, die diesen Fehler zur Kompilierzeit verursacht.  
  
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
  
 Im vorherigen Beispiel, wenn der Compiler den Aufruf zugelassen `s1` geschrieben, die Auflösung erfolgt über die Klasse `c1` anstelle der Schnittstelle `i1`. Dies bedeutet, dass der Compiler nicht berücksichtigt, `s2` weil dieser Name in verschiedenen ist `c1`, auch wenn es sich um die richtige Wahl ist gemäß der Definition von `i1`.  
  
 Sie können den Fehler behoben, durch den Aufruf an einen der folgenden Codezeilen ändern:  
  
```  
refer.s1(CType(o1, Integer))  
refer.s1(CType(o1, Double))  
```  
  
 Jede der vorangehenden Zeilen des Codes explizit wandelt die `Object` Variable `o1` auf einen der Parametertypen für die Überladungen definiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Prozedurüberladung](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)  
 [Überladungsauflösung](../../../visual-basic/programming-guide/language-features/procedures/overload-resolution.md)  
 [CType-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)
