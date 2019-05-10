---
title: Der Standardeigenschaftenzugriff ist nicht eindeutig. Es kann sich um den geerbten Schnittstellenmember "<defaultpropertyname>" der Schnittstelle "<interfacename1>" oder "<defaultpropertyname>" der Schnittstelle "<interfacename2>" handeln.
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 99d5dc2e0f8389f8c9e90786c4d9d0fa037eb828
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64651417"
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
