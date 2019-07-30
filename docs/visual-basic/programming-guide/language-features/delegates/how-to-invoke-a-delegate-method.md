---
title: 'Vorgehensweise: Delegatmethode aufrufen (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: c2bdb65c9d060e854db3319e4aa5b2e93b9681af
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68629589"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Vorgehensweise: Delegatmethode aufrufen (Visual Basic)

Dieses Beispiel zeigt, wie Sie eine Methode einem Delegaten zuordnen und dann diese Methode über den Delegaten aufrufen.

### <a name="create-the-delegate-and-matching-procedures"></a>Erstellen des Delegaten und der entsprechenden Prozeduren

1. Erstellen Sie einen Delegaten namens `MySubDelegate`.

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. Deklarieren Sie eine Klasse, die eine Methode mit der gleichen Signatur wie der Delegat enthält.

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. Definieren Sie eine Methode, die eine Instanz des Delegaten erstellt und die dem Delegaten zugeordnete Methode aufruft, indem Sie `Invoke` die integrierte Methode aufrufen.

    ```vb
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
