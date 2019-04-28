---
title: Der Standardeigenschaftenzugriff ist nicht eindeutig. Es kann sich um den geerbten Schnittstellenmember "<defaultpropertyname>" der Schnittstelle "<interfacename1>" oder "<defaultpropertyname>" der Schnittstelle "<interfacename2>" handeln.
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 5f058c8e7d480b9145452ae85f186a6ac2ed0d56
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61803729"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-defaultpropertyname-of-interface-interfacename1-and-defaultpropertyname-of-interface-interfacename2"></a>Zugriff auf die Standardeigenschaft ist mehrdeutig zwischen den geerbten Schnittstellenmember\<Defaultpropertyname > "der Schnittstelle"\<schnittstellenname1 >' und '\<Defaultpropertyname > "der Schnittstelle"\< schnittstellenname2 >'
Eine Schnittstelle erbt von zwei Schnittstellen, von die jede eine Standardeigenschaft mit demselben Namen deklariert. Der Compiler kann keinen Zugriff auf diese Eigenschaft standardmäßig ohne Qualifikation aufgelöst werden. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```  
Public Interface Iface1  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface2  
    Default Property prop(ByVal arg As Integer) As Integer  
End Interface  
Public Interface Iface3  
    Inherits Iface1, Iface2  
End Interface  
Public Class testClass  
    Public Sub accessDefaultProperty()  
        Dim testObj As Iface3  
        Dim testInt As Integer = testObj(1)  
    End Sub  
End Class  
```  
  
 Beim Angeben von `testObj(1)`, der Compiler versucht, die sie in der Default-Eigenschaft aufgelöst werden. Es gibt jedoch zwei möglichen Standardeigenschaften aufgrund der geerbten Schnittstelle, damit der Compiler diesen Fehler signalisiert.  
  
 **Fehler-ID:** BC30686  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Vermeiden Sie erben keine Member mit demselben Namen. Im vorherigen Beispiel wenn `testObj` der Member ist nicht erforderlich, z. B. `Iface2`, deklarieren Sie sie wie folgt:  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     - oder -   
  
- Implementieren Sie die erbende Schnittstelle in einer Klasse. Anschließend können Sie die geerbten Eigenschaften mit unterschiedlichen Namen implementieren. Allerdings kann nur eine von ihnen die Standardeigenschaft der implementierenden Klasse sein. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
    ```  
    Public Class useIface3  
        Implements Iface3  
        Default Public Property prop1(ByVal arg As Integer) As Integer Implements Iface1.prop  
            ' Insert code to define Get and Set procedures for prop1.  
        End Property  
        Public Property prop2(ByVal arg As Integer) As Integer Implements Iface2.prop  
            ' Insert code to define Get and Set procedures for prop2.  
        End Property  
    End Class  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
