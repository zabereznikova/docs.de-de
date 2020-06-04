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
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="c6e34-102">Gewusst wie: Aufrufen einer Delegatenmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c6e34-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>

<span data-ttu-id="c6e34-103">Dieses Beispiel zeigt, wie Sie eine Methode einem Delegaten zuordnen und dann diese Methode über den Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c6e34-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>

### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="c6e34-104">Erstellen des Delegaten und der entsprechenden Prozeduren</span><span class="sxs-lookup"><span data-stu-id="c6e34-104">Create the delegate and matching procedures</span></span>

1. <span data-ttu-id="c6e34-105">Erstellen Sie einen Delegaten namens `MySubDelegate` .</span><span class="sxs-lookup"><span data-stu-id="c6e34-105">Create a delegate named `MySubDelegate`.</span></span>

    ```vb
    Delegate Sub MySubDelegate(ByVal x As Integer)
    ```

2. <span data-ttu-id="c6e34-106">Deklarieren Sie eine Klasse, die eine Methode mit der gleichen Signatur wie der Delegat enthält.</span><span class="sxs-lookup"><span data-stu-id="c6e34-106">Declare a class that contains a method with the same signature as the delegate.</span></span>

    ```vb
    Class class1
        Sub Sub1(ByVal x As Integer)
            MsgBox("The value of x is: " & CStr(x))
        End Sub
    End Class
    ```

3. <span data-ttu-id="c6e34-107">Definieren Sie eine Methode, die eine Instanz des Delegaten erstellt und die dem Delegaten zugeordnete Methode aufruft, indem Sie die integrierte `Invoke` Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c6e34-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>

    ```vb
    Protected Sub DelegateTest()
        Dim c1 As New class1
        ' Create an instance of the delegate.
        Dim msd As MySubDelegate = AddressOf c1.Sub1
        ' Call the method.
        msd.Invoke(10)
    End Sub
    ```

## <a name="see-also"></a><span data-ttu-id="c6e34-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c6e34-108">See also</span></span>

- [<span data-ttu-id="c6e34-109">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c6e34-109">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="c6e34-110">Delegaten</span><span class="sxs-lookup"><span data-stu-id="c6e34-110">Delegates</span></span>](index.md)
- [<span data-ttu-id="c6e34-111">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="c6e34-111">Events</span></span>](../events/index.md)
- [<span data-ttu-id="c6e34-112">Multithreadanwendungen</span><span class="sxs-lookup"><span data-stu-id="c6e34-112">Multithreaded Applications</span></span>](../../../../standard/threading/using-threads-and-threading.md)
