---
title: Zugriff auf die Standardeigenschaft ist nicht die geerbten Schnittstellenmember eindeutig &#39; &lt;Defaultpropertyname&gt; &#39; Schnittstelle &#39; &lt;schnittstellenname1&gt; &#39; und &#39; &lt;Defaultpropertyname&gt; &#39; Schnittstelle &#39; &lt;schnittstellenname2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc30686
- bc30686
helpviewer_keywords:
- BC30686
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
ms.openlocfilehash: 65a10067284cad3bf56ecdc441ebefa0a740ef53
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590854"
---
# <a name="default-property-access-is-ambiguous-between-the-inherited-interface-members-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename1gt39-and-39ltdefaultpropertynamegt39-of-interface-39ltinterfacename2gt39"></a>Zugriff auf die Standardeigenschaft ist nicht die geerbten Schnittstellenmember eindeutig &#39; &lt;Defaultpropertyname&gt; &#39; Schnittstelle &#39; &lt;schnittstellenname1&gt; &#39; und &#39; &lt;Defaultpropertyname&gt; &#39; Schnittstelle &#39; &lt;schnittstellenname2&gt;&#39;
Eine Schnittstelle erbt von zwei Schnittstellen, von die jede eine Standardeigenschaft mit demselben Namen deklariert. Der Compiler kann keinen Zugriff auf diese Eigenschaft standardmäßig ohne Qualifizierung aufgelöst werden. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
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
  
 Geben Sie bei `testObj(1)`, versucht der Compiler, es in die Standardeigenschaft aufzulösen. Es gibt jedoch zwei möglichen Standardeigenschaften aufgrund der geerbten Schnittstellen, damit der Compiler diesen Fehler signalisiert.  
  
 **Fehler-ID:** BC30686  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Vermeiden Sie erbt alle Member mit demselben Namen. Im vorherigen Beispiel wenn `testObj` benötigt keine von, z. B. `Iface2`, deklarieren Sie es wie folgt:  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     - oder -   
  
-   Implementieren Sie die erbende Schnittstelle in einer Klasse. Anschließend können Sie jede der geerbten Eigenschaften mit unterschiedlichen Namen implementieren. Allerdings kann nur eine davon die Standardeigenschaft der implementierenden Klasse sein. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
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
 [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
