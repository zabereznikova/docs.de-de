---
title: "How to: Invoke a Delegate Method (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
ms.assetid: b56866ae-abf9-4a5a-a855-486359455e9c
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# How to: Invoke a Delegate Method (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Dieses Beispiel zeigt, wie Sie eine Methode einem Delegaten zuweisen und diese Methode anschließend über den Delegaten aufrufen.  
  
### Erstellen des Delegaten und entsprechender Prozeduren  
  
1.  Erstellen Sie einen Delegaten mit dem Namen `MySubDelegate`.  
  
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
  
3.  Definieren Sie eine Methode, die eine Instanz des Delegaten erstellt und die Methode aufruft, die dem Delegaten zugewiesen ist. Rufen Sie dazu die integrierte `Invoke`\-Methode auf.  
  
    ```  
    Protected Sub DelegateTest()  
        Dim c1 As New class1  
        ' Create an instance of the delegate.  
        Dim msd As MySubDelegate = AddressOf c1.Sub1  
        ' Call the method.  
        msd.Invoke(10)  
    End Sub  
    ```  
  
## Siehe auch  
 [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)   
 [Multithreadanwendungen](../Topic/Multithreaded%20Applications%20\(C%23%20and%20Visual%20Basic\).md)