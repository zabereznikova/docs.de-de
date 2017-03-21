---
title: Der Ausdruck ruft rekursiv die enthaltende Eigenschaft &quot;&lt;Propertyname&gt;&quot; | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42026
- BC42026
dev_langs:
- VB
helpviewer_keywords:
- BC42026
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ca20bf1a539f2727a80f8e781c1e9ebc5a4a253d
ms.lasthandoff: 03/13/2017

---
# <a name="expression-recursively-calls-the-containing-property-39ltpropertynamegt39"></a>Der Ausdruck ruft rekursiv die enthaltende Eigenschaft '&lt;Propertyname&gt;'
Eine Anweisung in der `Set` -Prozedur einer Eigenschaftendefinition speichert einen Wert in den Namen der Eigenschaft.  
  
 Die empfohlene Vorgehensweise zum Speichern des Werts einer Eigenschaft definiert ist ein `Private` -Variable im Container der Eigenschaft und deren Verwendung in beide die `Get` und `Set` Verfahren. Die `Set` -Prozedur muss dann den eingehenden Wert in dieser speichern `Private` Variable.  
  
 Die `Get` Prozedur verhält sich wie eine `Function` Prozedur, den Eigenschaftennamen einen Wert zuzuweisen und Steuerung von auftreten zurück der `End Get` Anweisung. Jedoch wird empfohlen, enthalten die `Private` -Variable als Wert in einer [Return-Anweisung](../../../visual-basic/language-reference/statements/return-statement.md).  
  
 Die `Set` Prozedur verhält sich wie eine `Sub` Prozedur, die keinen Wert zurückgibt. Name der Prozedur oder Eigenschaft hat daher keine besondere Bedeutung innerhalb einer `Set` Prozedur, und Sie können keinen Wert darin speichern.  
  
 Das folgende Beispiel veranschaulicht die Vorgehensweise, die diesen Fehler, gefolgt von der empfohlene Ansatz.  
  
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
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42026  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Schreiben Sie die Eigenschaftsdefinition, um die empfohlene Vorgehensweise verwenden, wie im vorherigen Beispiel dargestellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Property-Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)
