---
title: 'Vorgehensweise: Aufrufen einer Delegatenmethode'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: f319727c007b93c7b334af0598f1b9f7c034144d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410720"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a>Gewusst wie: Aufrufen einer Delegatenmethode (Visual Basic)

Dieses Beispiel zeigt, wie Sie eine Methode einem Delegaten zuordnen und dann diese Methode über den Delegaten aufrufen.

### <a name="create-the-delegate-and-matching-procedures"></a>Erstellen des Delegaten und der entsprechenden Prozeduren

1. Erstellen Sie einen Delegaten namens `MySubDelegate` .

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

3. Definieren Sie eine Methode, die eine Instanz des Delegaten erstellt und die dem Delegaten zugeordnete Methode aufruft, indem Sie die integrierte `Invoke` Methode aufrufen.

    ```vb
    Protected Sub DelegateTest()
        Dim c1 As New class1
        ' Create an instance of the delegate.
        Dim msd As MySubDelegate = AddressOf c1.Sub1
        ' Call the method.
        msd.Invoke(10)
    End Sub
    ```

## <a name="see-also"></a>Weitere Informationen

- [Delegate-Anweisung](../../../language-reference/statements/delegate-statement.md)
- [Delegaten](index.md)
- [Ereignisse](../events/index.md)
- [Multithreadanwendungen](../../../../standard/threading/using-threads-and-threading.md)
