---
title: 'Gewusst wie: Aufrufen einer Delegatenmethode (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ea94d4bb26e168667fd75c6928e52261f230c85e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="8668c-102">Gewusst wie: Aufrufen einer Delegatenmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8668c-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="8668c-103">Dieses Beispiel zeigt, wie eine Methode mit einem Delegaten zuordnen und anschließend diese Methode über den Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="8668c-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="8668c-104">Erstellen des Delegaten und dem entsprechenden Verfahren</span><span class="sxs-lookup"><span data-stu-id="8668c-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="8668c-105">Erstellen Sie einen Delegaten mit dem Namen `MySubDelegate`.</span><span class="sxs-lookup"><span data-stu-id="8668c-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="8668c-106">Deklarieren Sie eine Klasse, die eine Methode mit der gleichen Signatur wie der Delegat enthält.</span><span class="sxs-lookup"><span data-stu-id="8668c-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="8668c-107">Definieren Sie eine Methode, erstellt eine Instanz des Delegaten und ruft die Methode, die der Delegat durch Aufrufen der integriertes zugeordneten `Invoke` Methode.</span><span class="sxs-lookup"><span data-stu-id="8668c-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8668c-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8668c-108">See Also</span></span>  
 [<span data-ttu-id="8668c-109">Delegate-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8668c-109">Delegate Statement</span></span>](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [<span data-ttu-id="8668c-110">Delegaten</span><span class="sxs-lookup"><span data-stu-id="8668c-110">Delegates</span></span>](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [<span data-ttu-id="8668c-111">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="8668c-111">Events</span></span>](../../../../visual-basic/programming-guide/language-features/events/index.md)  
 [<span data-ttu-id="8668c-112">Multithreadanwendungen</span><span class="sxs-lookup"><span data-stu-id="8668c-112">Multithreaded Applications</span></span>](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)
