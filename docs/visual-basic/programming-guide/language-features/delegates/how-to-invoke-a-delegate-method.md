---
title: 'Vorgehensweise: Aufrufen einer Delegatenmethode (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: ac3e32010e7c20ba76e39915d694b11ab3a65d40
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59319611"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Vorgehensweise: Aufrufen einer Delegatenmethode (Visual Basic)
Dieses Beispiel zeigt, wie Sie eine Methode mit einem Delegaten zuweisen, und rufen danach diese Methode über den Delegaten.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>Erstellen des Delegaten und die entsprechenden Verfahren  
  
1. Erstellen Sie einen Delegaten, mit dem Namen `MySubDelegate`.  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2. Deklarieren Sie eine Klasse, die eine Methode mit der gleichen Signatur wie der Delegat enthält.  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3. Definieren Sie eine Methode, erstellt eine Instanz des Delegaten und ruft die Methode dem Delegaten zugeordnet sind, durch Aufrufen der integriertes `Invoke` Methode.  
  
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

- [Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md)
- [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md)
- [Multithreadanwendungen](../../../../standard/threading/using-threads-and-threading.md)
