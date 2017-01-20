---
title: "Default property access is ambiguous between the inherited interface members &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename1&gt;&#39; and &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename2&gt;&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30686"
  - "bc30686"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30686"
ms.assetid: 784fefec-ef57-48cf-b960-957df419b439
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Default property access is ambiguous between the inherited interface members &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename1&gt;&#39; and &#39;&lt;defaultpropertyname&gt;&#39; of interface &#39;&lt;interfacename2&gt;&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Eine Schnittstelle erbt von zwei Schnittstellen, von denen jede eine Standardeigenschaft mit dem gleichen Namen deklariert.  Der Compiler kann einen Zugriff auf diese Standardeigenschaft ohne Qualifikation nicht auflösen.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
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
  
 Wenn Sie `testObj(1)` angeben, versucht der Compiler, es in die Standardeigenschaft aufzulösen.  Aufgrund der geerbten Schnittstellen gibt es jedoch zwei mögliche Standardeigenschaften. Der Compiler signalisiert deshalb diesen Fehler.  
  
 **Fehler\-ID:** BC30686  
  
### So beheben Sie diesen Fehler  
  
-   Vermeiden Sie das Vererben von Membern mit dem gleichen Namen.  Wenn `testObj` im obigen Beispiel keinen der Member beispielsweise von `Iface2` benötigt, deklarieren Sie es folgendermaßen:  
  
    ```  
    Dim testObj As Iface1  
    ```  
  
     \- oder \-  
  
-   Implementieren Sie die erbende Schnittstelle in einer Klasse.  Anschließend können Sie jede der geerbten Eigenschaften mit unterschiedlichen Namen implementieren.  Allerdings kann nur eine Eigenschaft die Standardeigenschaft der implementierenden Klasse sein.  Dies wird anhand des folgenden Beispiels veranschaulicht:  
  
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
  
## Siehe auch  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)