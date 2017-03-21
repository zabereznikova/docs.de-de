---
title: AttributeUsage (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 48757216-c21d-4051-86d5-8a3e03c39d2c
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bf56f40033f9d1547d63fccd25e3c0561bb62cb1
ms.lasthandoff: 03/13/2017

---
# <a name="attributeusage-visual-basic"></a>AttributeUsage (Visual Basic)
Bestimmt, wie eine benutzerdefinierte Attributklasse verwendet werden kann. `AttributeUsage`ist ein Attribut, die angewendet werden kann, um benutzerdefinierte Attributdefinitionen zu steuern, wie das neue Attribut angewendet werden kann. Die Standardeinstellungen aussehen wie folgt, wenn Sie explizit angewendet:  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All,   
                   AllowMultiple:=False,   
                   Inherited:=True)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 In diesem Beispiel die `NewAttribute` -Klasse kann auf jede Codeentität Attribut kann angewendet, aber kann nur einmal für jede Entität angewendet werden. Es wird von abgeleiteten Klassen bei Anwendung auf eine Basisklasse geerbt.  
  
 Die `AllowMultiple` und `Inherited` Argumente sind optional, damit dieser Code die gleiche Wirkung hat:  
  
```vb  
<System.AttributeUsage(System.AttributeTargets.All)>   
Class NewAttribute  
    Inherits System.Attribute  
End Class  
```  
  
 Die erste `AttributeUsage` Argument muss ein oder mehrere Elemente von der <xref:System.AttributeTargets>-Enumeration.</xref:System.AttributeTargets> Mehrere Zieltypen können zusammen mit dem OR-Operator, wie folgt verknüpft:  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Property Or AttributeTargets.Field)>   
Class NewPropertyOrFieldAttribute  
    Inherits Attribute  
End Class  
```  
  
 Wenn die `AllowMultiple` Argument auf festgelegt ist `true`, und klicken Sie dann das resultierende Attribut mehr als einmal kann, können Sie für eine einzelne Entität, wie folgt angewendet werden:  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=True)>   
Class MultiUseAttr  
    Inherits Attribute  
End Class  
  
<MultiUseAttr(), MultiUseAttr()>   
Class Class1  
End Class  
```  
  
 In diesem Fall `MultiUseAttr` kann mehrmals angewendet werden, da `AllowMultiple` Wert `true`. Beide Formate wie für das Anwenden von mehreren Attributen sind gültig.  
  
 Wenn `Inherited` Wert `false`, und klicken Sie dann das Attribut nicht von Klassen geerbt wird, die von einer Klasse abgeleitet werden, die zugeordnet wird. Beispiel:  
  
```vb  
Imports System  
```  
  
```vb  
<AttributeUsage(AttributeTargets.Class, Inherited:=False)>   
Class Attr1  
    Inherits Attribute  
End Class  
  
<Attr1()>   
Class BClass  
  
End Class    
  
Class DClass  
    Inherits BClass  
End Class  
```  
  
 In diesem Fall `Attr1` gilt nicht für `DClass` über Vererbung.  
  
## <a name="remarks"></a>Hinweise  
 Das `AttributeUsage` -Attribut ist ein Attribut – es kann nicht auf die gleiche Klasse mehr als einmal angewendet werden. `AttributeUsage`ist ein Alias für <xref:System.AttributeUsageAttribute>.</xref:System.AttributeUsageAttribute>  
  
 Weitere Informationen finden Sie unter [Zugriff auf Attribute mithilfe von Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Auswirkung der `Inherited` und `AllowMultiple` Argumente für die `AttributeUsage` -Attribut, und wie die benutzerdefinierten Attribute auf eine Klasse angewendet aufgelistet werden können.  
  
```vb  
Imports System  
```  
  
```vb  
' Create some custom attributes:  
<AttributeUsage(System.AttributeTargets.Class, Inherited:=False)>   
Class A1  
    Inherits System.Attribute  
End Class  
  
<AttributeUsage(System.AttributeTargets.Class)>   
Class A2  
    Inherits System.Attribute  
End Class      
  
<AttributeUsage(System.AttributeTargets.Class, AllowMultiple:=True)>   
Class A3  
    Inherits System.Attribute  
End Class  
  
' Apply custom attributes to classes:  
<A1(), A2()>   
Class BaseClass  
  
End Class  
  
<A3(), A3()>   
Class DerivedClass  
    Inherits BaseClass  
End Class  
  
Public Class TestAttributeUsage  
    Sub Main()  
        Dim b As New BaseClass  
        Dim d As New DerivedClass  
        ' Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:")  
        Dim attrs() As Object = b.GetType().GetCustomAttributes(True)  
  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next  
  
        Console.WriteLine("Attributes on Derived Class:")  
        attrs = d.GetType().GetCustomAttributes(True)  
        For Each attr In attrs  
            Console.WriteLine(attr)  
        Next              
    End Sub  
End Class  
```  
  
## <a name="sample-output"></a>Beispielausgabe  
  
```  
Attributes on Base Class:  
A1  
A2  
Attributes on Derived Class:  
A3  
A3  
A2  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Attribute></xref:System.Attribute>   
 <xref:System.Reflection></xref:System.Reflection>   
 [Visual Basic-Programmierhandbuch](../../../../visual-basic/programming-guide/index.md)   
 [Attribute](https://msdn.microsoft.com/library/5x6cd29c)   
 [Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)   
 [Attribute (Visual Basic)](../../../../visual-basic/language-reference/attributes.md)   
 [Erstellen von benutzerdefinierten Attributen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)   
 [Zugriff auf Attribute mit Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
