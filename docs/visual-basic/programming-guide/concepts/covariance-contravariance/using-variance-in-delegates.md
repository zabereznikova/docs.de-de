---
title: Verwenden von Varianz in Delegaten (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 7b5c20f1-6416-46a3-94b6-f109c31c842c
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 5bd3e60031eac713cee3dee1399af8c6b83e6656
ms.lasthandoff: 03/13/2017

---
# <a name="using-variance-in-delegates-visual-basic"></a>Verwenden von Varianz in Delegaten (Visual Basic)
Wenn Sie einen Delegaten eine Methode zuweisen *Kovarianz* und *Kontravarianz* bieten Flexibilität für den Abgleich eines Delegattyps mit einer Methodensignatur. Kovarianz unterstützt eine Methode Rückgabetyp aufweisen, stärker abgeleiteten, als im Delegaten definiert ist. Kontravarianz unterstützt eine Methode mit Parametertypen, die weniger stark abgeleitet sind als die in der Delegattyp.  
  
## <a name="example-1-covariance"></a>Beispiel 1: Kovarianz  
  
### <a name="description"></a>Beschreibung  
 In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, deren Rückgabetypen von dem Rückgabetyp in der Signatur des Delegaten abgeleitet werden. Der zurückgegebene Datentyp `DogsHandler` ist vom Typ `Dogs`, die abgeleitet wird von der `Mammals` Typ, der in der Delegat definiert ist.  
  
### <a name="code"></a>Code  
  
```vb  
Class Mammals  
End Class  
  
Class Dogs  
    Inherits Mammals  
End Class  
Class Test  
    Public Delegate Function HandlerMethod() As Mammals  
    Public Shared Function MammalsHandler() As Mammals  
        Return Nothing  
    End Function  
    Public Shared Function DogsHandler() As Dogs  
        Return Nothing  
    End Function  
    Sub Test()  
        Dim handlerMammals As HandlerMethod = AddressOf MammalsHandler  
        ' Covariance enables this assignment.  
        Dim handlerDogs As HandlerMethod = AddressOf DogsHandler  
    End Sub  
End Class  
```  
  
## <a name="example-2-contravariance"></a>Beispiel 2: Kontravarianz  
  
### <a name="description"></a>Beschreibung  
 In diesem Beispiel wird veranschaulicht, wie Delegaten mit Methoden verwendet werden können, deren Parameter Basistypen des Delegattyps Signatur-Parameter. Mithilfe von Kontravarianz können Sie einen Ereignishandler statt separate Handler. Sie können z. B. einen Ereignishandler, der akzeptiert erstellen ein `EventArgs` Eingabeparameter, und verwenden Sie es mit eine `Button.MouseClick` -Ereignis, das gesendet ein `MouseEventArgs` Typ als Parameter und mit ein `TextBox.KeyDown` -Ereignis, das gesendet ein `KeyEventArgs` Parameter.  
  
### <a name="code"></a>Code  
  
```vb  
' Event hander that accepts a parameter of the EventArgs type.  
Private Sub MultiHandler(ByVal sender As Object,  
                         ByVal e As System.EventArgs)  
    Label1.Text = DateTime.Now  
End Sub  
  
Private Sub Form1_Load(ByVal sender As System.Object,  
    ByVal e As System.EventArgs) Handles MyBase.Load  
  
    ' You can use a method that has an EventArgs parameter,  
    ' although the event expects the KeyEventArgs parameter.  
    AddHandler Button1.KeyDown, AddressOf MultiHandler  
  
    ' You can use the same method   
    ' for the event that expects the MouseEventArgs parameter.  
    AddHandler Button1.MouseClick, AddressOf MultiHandler  
End Sub  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)   
 [Verwenden von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
