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
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="68a50-102">Gewusst wie: Aufrufen einer Delegatenmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a50-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="68a50-103">Dieses Beispiel zeigt, wie Sie eine Methode mit einem Delegaten zuweisen, und rufen danach diese Methode über den Delegaten.</span><span class="sxs-lookup"><span data-stu-id="68a50-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="68a50-104">Erstellen des Delegaten und die entsprechenden Verfahren</span><span class="sxs-lookup"><span data-stu-id="68a50-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="68a50-105">Erstellen Sie einen Delegaten, mit dem Namen `MySubDelegate`.</span><span class="sxs-lookup"><span data-stu-id="68a50-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="68a50-106">Deklarieren Sie eine Klasse, die eine Methode mit der gleichen Signatur wie der Delegat enthält.</span><span class="sxs-lookup"><span data-stu-id="68a50-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="68a50-107">Definieren Sie eine Methode, erstellt eine Instanz des Delegaten und ruft die Methode dem Delegaten zugeordnet sind, durch Aufrufen der integriertes `Invoke` Methode.</span><span class="sxs-lookup"><span data-stu-id="68a50-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="68a50-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68a50-108">See Also</span></span>  
 [<span data-ttu-id="68a50-109">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="68a50-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="68a50-110">Delegaten</span><span class="sxs-lookup"><span data-stu-id="68a50-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="68a50-111">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="68a50-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="68a50-112">Multithreadanwendungen</span><span class="sxs-lookup"><span data-stu-id="68a50-112">Multithreaded Applications</span></span>](https://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
