---
title: 'Gewusst wie: Aufrufen einer Delegatenmethode (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: 9fea3ddbc9fb553041671713a64e4b866ee38b50
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43392437"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Gewusst wie: Aufrufen einer Delegatenmethode (Visual Basic)
Dieses Beispiel zeigt, wie Sie eine Methode mit einem Delegaten zuweisen, und rufen danach diese Methode über den Delegaten.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Erstellen des Delegaten und die entsprechenden Verfahren  
  
1.  Erstellen Sie einen Delegaten, mit dem Namen `MySubDelegate`.  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  Deklarieren Sie eine Klasse, die eine Methode mit der gleichen Signatur wie der Delegat enthält.  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  Definieren Sie eine Methode, erstellt eine Instanz des Delegaten und ruft die Methode dem Delegaten zugeordnet sind, durch Aufrufen der integriertes `Invoke` Methode.  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [Multithreadanwendungen](https://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
