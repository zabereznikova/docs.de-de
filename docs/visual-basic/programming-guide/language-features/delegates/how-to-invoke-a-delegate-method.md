---
title: 'Gewusst wie: Aufrufen einer Delegatenmethode (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 060a60da16a0032850b0a45822c8fd24b4622b83
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-invoke-a-delegate-method-visual-basic"></a><span data-ttu-id="39236-102">Gewusst wie: Aufrufen einer Delegatenmethode (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="39236-102">How to: Invoke a Delegate Method (Visual Basic)</span></span>
<span data-ttu-id="39236-103">Dieses Beispiel zeigt, wie Sie eine Methode mit einem Delegaten zuweisen und dann diese Methode über den Delegaten aufrufen.</span><span class="sxs-lookup"><span data-stu-id="39236-103">This example shows how to associate a method with a delegate and then invoke that method through the delegate.</span></span>  
  
### <a name="create-the-delegate-and-matching-procedures"></a><span data-ttu-id="39236-104">Erstellen des Delegaten und entsprechender Prozeduren</span><span class="sxs-lookup"><span data-stu-id="39236-104">Create the delegate and matching procedures</span></span>  
  
1.  <span data-ttu-id="39236-105">Erstellen Sie einen Delegaten mit dem Namen `MySubDelegate`.</span><span class="sxs-lookup"><span data-stu-id="39236-105">Create a delegate named `MySubDelegate`.</span></span>  
  
    ```  
    Delegate Sub MySubDelegate(ByVal x As Integer)  
    ```  
  
2.  <span data-ttu-id="39236-106">Deklarieren Sie eine Klasse, die eine Methode mit der gleichen Signatur wie der Delegat enthält.</span><span class="sxs-lookup"><span data-stu-id="39236-106">Declare a class that contains a method with the same signature as the delegate.</span></span>  
  
    ```  
    Class class1  
        Sub Sub1(ByVal x As Integer)  
            MsgBox("The value of x is: " & CStr(x))  
        End Sub  
    End Class  
    ```  
  
3.  <span data-ttu-id="39236-107">Definieren Sie eine Methode, die eine Instanz des Delegaten erstellt und ruft die Methode, die dem Delegaten zugeordnet sind, durch Aufrufen der integriertes `Invoke` Methode.</span><span class="sxs-lookup"><span data-stu-id="39236-107">Define a method that creates an instance of the delegate and invokes the method associated with the delegate by calling the built-in `Invoke` method.</span></span>  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="39236-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39236-108">See Also</span></span>  
 <span data-ttu-id="39236-109">[Delegate-Anweisung](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span><span class="sxs-lookup"><span data-stu-id="39236-109">[Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md) </span></span>  
<span data-ttu-id="39236-110"> [Delegaten](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span><span class="sxs-lookup"><span data-stu-id="39236-110"> [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/index.md) </span></span>  
<span data-ttu-id="39236-111"> [Ereignisse](../../../../visual-basic/programming-guide/language-features/events/index.md) </span><span class="sxs-lookup"><span data-stu-id="39236-111"> [Events](../../../../visual-basic/programming-guide/language-features/events/index.md) </span></span>  
<span data-ttu-id="39236-112"> [Multithreadanwendungen](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)</span><span class="sxs-lookup"><span data-stu-id="39236-112"> [Multithreaded Applications](http://msdn.microsoft.com/library/a06a1a56-dd16-44e8-bc01-2c2255511bc6)</span></span>
