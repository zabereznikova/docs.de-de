---
title: AttributeUsage (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 22c45568-9a6a-4c2f-8480-f38c1caa0a99
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 81e7440279a2d7dfa801394ee0e9af6181da3c13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="attributeusage-c"></a>AttributeUsage (C#)
Bestimmt, wie eine benutzerdefinierte Attributklasse verwendet werden kann. `AttributeUsage` ist ein Attribut, dass auf benutzerdefinierte Attributdefinitionen zur Steuerung der Anwendung neuer Attribute angewendet werden kann. Die Standardeinstellungen sehen wie folgt aus, wenn Sie explizit angewendet werden:  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All,  
                   AllowMultiple = false,  
                   Inherited = true)]  
class NewAttribute : System.Attribute { }  
```  
  
 In diesem Beispiel kann die Klasse `NewAttribute` auf jede attributfähige Codeentität angewendet werden; allerdings nur einmal pro Entität. Wenn sie auf eine Basisklasse angewendet wird, wird sie an eine abgeleitete Klasse vererbt.  
  
 Die Argumente `AllowMultiple` und `Inherited` sind optional, sodass dieser Code die gleiche Wirkung hat:  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.All)]  
class NewAttribute : System.Attribute { }  
```  
  
 Das erste `AttributeUsage`-Argument muss mindestens ein Element der <xref:System.AttributeTargets>-Enumeration sein. Mehrere Zieltypen können mithilfe des OR-Operator wie folgt verknüpft werden:  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Property | AttributeTargets.Field)]  
class NewPropertyOrFieldAttribute : Attribute { }  
```  
  
 Wenn das `AllowMultiple`-Argument auf `true` festgelegt ist, kann das daraus entstehende Attribut wie folgt mehr als einmal auf eine einzelne Entität angewendet werden:  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, AllowMultiple = true)]  
class MultiUseAttr : Attribute { }  
  
[MultiUseAttr]  
[MultiUseAttr]  
class Class1 { }  
  
[MultiUseAttr, MultiUseAttr]  
class Class2 { }  
```  
  
 In diesem Fall kann `MultiUseAttr` wiederholt angewendet werden, da `AllowMultiple` auf `true` festgelegt ist. Beide gezeigten Formate für das Anwenden von mehreren Attributen sind gültig.  
  
 Wenn `Inherited` auf `false` festgelegt ist, wird das Attribut nicht an die von der attribuierten Klasse abgeleiteten Klassen vererbt. Zum Beispiel:  
  
```csharp  
using System;  

[AttributeUsage(AttributeTargets.Class, Inherited = false)]  
class Attr1 : Attribute { }  
  
[Attr1]  
class BClass { }  
  
class DClass : BClass { }  
```  
  
 In diesem Fall wird `Attr1` nicht durch Vererbung auf `DClass` angewendet.  
  
## <a name="remarks"></a>Hinweise  
 Das `AttributeUsage`-Attribut ist für die einmalige Nutzung bestimmt; es kann nicht mehr als einmal auf dieselbe Klasse angewendet werden. `AttributeUsage` ist ein Alias für <xref:System.AttributeUsageAttribute>.  
  
 Weitere Informationen finden Sie unter [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).  
  
## <a name="example"></a>Beispiel  
 In folgendem Beispiel wird die Wirkung der Argumente `Inherited` und `AllowMultiple` auf das Attribut `AttributeUsage` und die Enumeration benutzerdefinierter Attribute veranschaulicht, die auf eine Klasse angewendet wurden.  
  
```csharp  
using System;  

// Create some custom attributes:  
[AttributeUsage(System.AttributeTargets.Class, Inherited = false)]  
class A1 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class)]  
class A2 : System.Attribute { }  
  
[AttributeUsage(System.AttributeTargets.Class, AllowMultiple = true)]  
class A3 : System.Attribute { }  
  
// Apply custom attributes to classes:  
[A1, A2]  
class BaseClass { }  
  
[A3, A3]  
class DerivedClass : BaseClass { }  
  
public class TestAttributeUsage  
{  
    static void Main()  
    {  
        BaseClass b = new BaseClass();  
        DerivedClass d = new DerivedClass();  
  
        // Display custom attributes for each class.  
        Console.WriteLine("Attributes on Base Class:");  
        object[] attrs = b.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
  
        Console.WriteLine("Attributes on Derived Class:");  
        attrs = d.GetType().GetCustomAttributes(true);  
        foreach (Attribute attr in attrs)  
        {  
            Console.WriteLine(attr);  
        }  
    }  
}  
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
 <xref:System.Attribute>  
 <xref:System.Reflection>  
 [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)  
 [Attribute](https://msdn.microsoft.com/library/5x6cd29c)  
 [Reflektion (C#)](../../../../csharp/programming-guide/concepts/reflection.md)  
 [Attribute](../../../../csharp/programming-guide/concepts/attributes/index.md)  
 [Erstellen benutzerdefinierter Attribute (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
 [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
