---
title: Erstellen benutzerdefinierter Attribute (C#) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 346a5311a100e75adacea6100d6e5f1f893812ff
ms.contentlocale: de-de
ms.lasthandoff: 05/10/2017

---
# <a name="creating-custom-attributes-c"></a>Erstellen benutzerdefinierter Attribute (C#)
Sie können eigene benutzerdefinierte Attribute erstellen, indem Sie eine Attributklasse definieren. Dies ist eine Klasse, die direkt oder indirekt von <xref:System.Attribute> abgeleitet wird, was es einfach macht, schnell Attributdefinitionen in Metadaten zu identifizieren. Angenommen, Sie möchten Typen mit dem Namen des Programmierers markieren, der den Typ geschrieben hat. Sie definieren möglicherweise eine benutzerdefinierte `Author`-Attributklasse:  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class Author : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 Der Klassenname ist der Attributname, `Author`. Er ist von `System.Attribute` abgeleitet, ist also eine benutzerdefinierte Attributklasse. Die Parameter des Konstruktors sind die Positionsparameter des benutzerdefinierten Attributs. In diesem Beispiel ist `name` ein Positionsparameter. Alle öffentlichen Lese-/Schreibfelder oder -Eigenschaften werden Parameter genannt. In diesem Fall ist `version` der einzige Parameter mit Namen. Beachten Sie die Verwendung des `AttributeUsage`-Attributs, um das `Author`-Attribut ausschließlich für Klassen- und `struct`-Deklarationen gültig zu machen.  
  
 Sie könnten dieses neue Attribut wie folgt verwenden:  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 `AttributeUsage` verfügt über einen Parameter, `AllowMultiple`, mit dem Sie ein benutzerdefiniertes Attribut zur einmaligen oder mehrfachen Nutzung erstellen können. Im folgenden Codebeispiel wird ein mehrfach verwendbares Attribut erstellt.  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class Author : System.Attribute  
```  
  
 Im folgenden Codebeispiel werden mehrere Attribute desselben Typs auf eine Klasse angewendet.  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
> [!NOTE]
>  Wenn die Attributklasse eine Eigenschaft enthält, muss die Eigenschaft Lese- und Schreibberechtigung aufweisen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Reflection>   
 [C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md)   
 [Verfassen von benutzerdefinierten Attributen](../../../../standard/attributes/writing-custom-attributes.md)   
 [Reflektion (C#)](../../../../csharp/programming-guide/concepts/reflection.md)   
 [Attribute (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md)   
 [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)   
 [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md)
