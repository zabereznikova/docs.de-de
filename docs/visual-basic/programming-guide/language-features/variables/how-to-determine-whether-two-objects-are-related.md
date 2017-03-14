---
title: "How to: Determine Whether Two Objects Are Related (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "inheritance, Visual Basic objects"
  - "objects [Visual Basic], inheritance"
  - "object variables, determining relation"
ms.assetid: da002e3f-6616-4bad-a229-f842d06652bb
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# How to: Determine Whether Two Objects Are Related (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie können zwei Objekte miteinander vergleichen, um ggf. die Beziehung zwischen den Klassen zu ermitteln, aus denen sie erstellt wurden.  Die <xref:System.Type.IsInstanceOfType%2A>\-Methode der <xref:System.Type?displayProperty=fullName>\-Klasse gibt `True` zurück, wenn die angegebene Klasse von der aktuellen Klasse erbt oder wenn der aktuelle Typ eine Schnittstelle ist, die von der angegebenen Klasse unterstützt wird.  
  
### So stellen Sie fest, ob ein Objekt von der Klasse oder Schnittstelle eines anderen Objekts erbt  
  
1.  Rufen Sie für das Objekt, das Sie für eine Instanz des Basistyps halten, die <xref:System.Object.GetType%2A>\-Methode auf.  
  
2.  Rufen Sie für das von <xref:System.Object.GetType%2A> zurückgegebene <xref:System.Type?displayProperty=fullName>\-Objekt die <xref:System.Type.IsInstanceOfType%2A>\-Methode auf.  
  
3.  Geben Sie in der Argumentliste für <xref:System.Type.IsInstanceOfType%2A> das Objekt an, das Sie für eine Instanz des abgeleiteten Typs halten.  
  
     <xref:System.Type.IsInstanceOfType%2A> gibt `True` zurück, wenn dessen Argumenttyp vom <xref:System.Type?displayProperty=fullName>\-Objekttyp erbt.  
  
## Beispiel  
 Im folgenden Beispiel wird festgestellt, ob ein Objekt eine Klasse repräsentiert, die aus der Klasse eines anderen Objekts abgeleitet wurde:  
  
```  
Public Class baseClass  
End Class  
Public Class derivedClass : Inherits baseClass  
End Class  
Public Class testTheseClasses  
    Public Sub seeIfRelated()  
        Dim baseObj As Object = New baseClass()  
        Dim derivedObj As Object = New derivedClass()  
        Dim related As Boolean  
        related = baseObj.GetType().IsInstanceOfType(derivedObj)  
        MsgBox(CStr(related))  
    End Sub  
End Class  
```  
  
 Beachten Sie die unerwartete Platzierung der beiden Objektvariablen im Aufruf von <xref:System.Type.IsInstanceOfType%2A>.  Der angenommene Basistyp wird zum Generieren der <xref:System.Type?displayProperty=fullName>\-Klasse verwendet, und der angenommene abgeleitete Typ wird als Argument der <xref:System.Type.IsInstanceOfType%2A>\-Methode übergeben.  
  
## Siehe auch  
 <xref:System.Object.GetType%2A>   
 <xref:System.Type?displayProperty=fullName>   
 <xref:System.Type.IsInstanceOfType%2A>   
 [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Values](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [How to: Determine Whether Two Objects Are Identical](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-identical.md)