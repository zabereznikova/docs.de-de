---
title: Der Ausdruck ruft rekursiv die enthaltende <propertyname>-Eigenschaft auf.
ms.date: 07/20/2015
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
ms.openlocfilehash: a758d05cca5ca71943b0ef08184aef5b2c457739
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58836843"
---
# <a name="expression-recursively-calls-the-containing-property-propertyname"></a>Der Ausdruck ruft rekursiv die enthaltende Eigenschaft '\<Propertyname >'
Eine Anweisung in der `Set` Definition einer Prozedur speichert einen Wert in den Namen der Eigenschaft.  
  
 Der empfohlene Ansatz zum Speichern des Werts einer Eigenschaft wird zum definieren eine `Private` -Variable im Container der Eigenschaft und verwenden in beiden die `Get` und `Set` Verfahren. Die `Set` Prozedur muss dann den eingehenden Wert in dieser speichern `Private` Variable.  
  
 Die `Get` Prozedur verhält sich wie ein `Function` Prozedur, damit Namen der Eigenschaft einen Wert zuzuweisen und die Steuerung, durch die auftreten zurück können die `End Get` Anweisung. Allerdings wird empfohlen, sollen die `Private` -Variable als den Wert in eine [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Die `Set` Prozedur verhält sich wie ein `Sub` -Prozedur, die keinen Wert zurückgibt. Aus diesem Grund hat der Prozedur oder Eigenschaft Name keine besondere Bedeutung innerhalb einer `Set` Prozedur, und Sie können keinen Wert darin speichern.  
  
 Das folgende Beispiel veranschaulicht den Ansatz, der diesen Fehler, gefolgt von der empfohlene Ansatz verursachen kann.  
  
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
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42026  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Schreiben Sie die Eigenschaftsdefinition, um die empfohlene Vorgehensweise verwenden, wie im vorherigen Beispiel gezeigt.  
  
## <a name="see-also"></a>Siehe auch

- [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)
