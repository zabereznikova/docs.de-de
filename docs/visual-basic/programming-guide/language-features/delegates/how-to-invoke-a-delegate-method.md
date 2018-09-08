---
title: 'Gewusst wie: Aufrufen einer Delegatenmethode (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
ms.openlocfilehash: c50a32d300aaf52efe0c55cef69d5793a98305ac
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44129211"
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="21fc8-102">Gewusst wie: Aufrufen einer Delegatenmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="21fc8-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="21fc8-103">Dieses Beispiel zeigt, wie Sie eine Methode mit einem Delegaten zuweisen, und rufen danach diese Methode über den Delegaten.</span><span class="sxs-lookup"><span data-stu-id="21fc8-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="21fc8-104">Erstellen des Delegaten und die entsprechenden Verfahren</span><span class="sxs-lookup"><span data-stu-id="21fc8-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="21fc8-105">Erstellen Sie einen Delegaten, mit dem Namen `MySubDelegate`.</span><span class="sxs-lookup"><span data-stu-id="21fc8-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="21fc8-106">Deklarieren Sie eine Klasse, die eine Methode mit der gleichen Signatur wie der Delegat enthält.</span><span class="sxs-lookup"><span data-stu-id="21fc8-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="21fc8-107">Definieren Sie eine Methode, erstellt eine Instanz des Delegaten und ruft die Methode dem Delegaten zugeordnet sind, durch Aufrufen der integriertes `Invoke` Methode.</span><span class="sxs-lookup"><span data-stu-id="21fc8-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="21fc8-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21fc8-108">See also</span></span>

- [<span data-ttu-id="21fc8-109">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="21fc8-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
- [<span data-ttu-id="21fc8-110">Delegaten</span><span class="sxs-lookup"><span data-stu-id="21fc8-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
- [<span data-ttu-id="21fc8-111">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="21fc8-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
- [<span data-ttu-id="21fc8-112">Multithreadanwendungen</span><span class="sxs-lookup"><span data-stu-id="21fc8-112">Multithreaded Applications</span></span>](../../../../standard/threading/using-threads-and-threading.md)
