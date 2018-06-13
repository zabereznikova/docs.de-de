---
title: Der Ausdruck ruft rekursiv den enthaltende Eigenschaft &#39; &lt;Propertyname&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: f14e2645772b22a8f6ff2385dcd316a42d1d5cf0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588842"
---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a>Der Ausdruck ruft rekursiv den enthaltende Eigenschaft &#39; &lt;Propertyname&gt;&#39;
Eine Anweisung in der `Set` Prozedur mit einer Eigenschaftendefinition speichert einen Wert in den Namen der Eigenschaft.  
  
 Die empfohlene Vorgehensweise zum Speichern des Werts einer Eigenschaft besteht darin zu definieren eine `Private` -Variable im Container der Eigenschaft und deren Verwendung in sowohl die `Get` und `Set` Prozeduren. Die `Set` Prozedur muss dann den eingehenden Wert in dieser speichern `Private` Variable.  
  
 Die `Get` Prozedur verhält sich wie ein `Function` Prozedur, damit weisen Sie einen Wert des Eigenschaftennamens und Steuerung von auftreten zurückgegeben werden kann die `End Get` Anweisung. Die empfohlene Vorgehensweise ist jedoch enthalten die `Private` -Variable als Wert in einer [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Die `Set` Prozedur verhält sich wie ein `Sub` -Prozedur, die keinen Wert zurückgibt. Daher den Namen der Prozedur oder Eigenschaft hat keine besondere Bedeutung innerhalb einer `Set` Prozedur, und Sie keinen Wert darin gespeichert.  
  
 Das folgende Beispiel veranschaulicht die Vorgehensweise, die diesen Fehler, gefolgt von den empfohlenen Ansatz verursachen kann.  
  
```  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42026  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Schreiben Sie die Eigenschaftsdefinition, um die empfohlene Vorgehensweise verwenden, wie im vorherigen Beispiel dargestellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)
