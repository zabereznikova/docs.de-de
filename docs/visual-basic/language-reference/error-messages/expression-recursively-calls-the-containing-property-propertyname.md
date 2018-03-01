---
title: Der Ausdruck ruft rekursiv den enthaltenden Eigenschaft &#39; &lt;Propertyname&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42026
- BC42026
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47de3c2d25336962168f01a4c8717274de7c9aad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a>Der Ausdruck ruft rekursiv den enthaltenden Eigenschaft &#39; &lt;Propertyname&gt;&#39;
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
