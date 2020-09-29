---
title: Erstellen benutzerdefinierter Attribute (C#)
description: Hier erfahren Sie, wie Sie benutzerdefinierte Attribute in C# erstellen, indem Sie eine Attributklasse definieren, die von der Klasse „Attribut“ abgeleitet wird.
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: 6946b707134b2bdbc245b8786f144517a5870440
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202603"
---
# <a name="creating-custom-attributes-c"></a>Erstellen benutzerdefinierter Attribute (C#)

Sie können eigene benutzerdefinierte Attribute erstellen, indem Sie eine Attributklasse definieren. Dies ist eine Klasse, die direkt oder indirekt von <xref:System.Attribute> abgeleitet wird, was es einfach macht, schnell Attributdefinitionen in Metadaten zu identifizieren. Angenommen, Sie möchten Typen mit dem Namen des Programmierers markieren, der den Typ geschrieben hat. Sie definieren möglicherweise eine benutzerdefinierte `Author`-Attributklasse:  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct)  
]  
public class AuthorAttribute : System.Attribute  
{  
    private string name;  
    public double version;  
  
    public AuthorAttribute(string name)  
    {  
        this.name = name;  
        version = 1.0;  
    }  
}  
```  
  
 Der Klassenname `AuthorAttribute` setzt sich aus dem Attributnamen `Author` und dem Suffix `Attribute` zusammen. Er ist von `System.Attribute` abgeleitet, ist also eine benutzerdefinierte Attributklasse. Die Parameter des Konstruktors sind die Positionsparameter des benutzerdefinierten Attributs. In diesem Beispiel ist `name` ein Positionsparameter. Alle öffentlichen Lese-/Schreibfelder oder -Eigenschaften werden Parameter genannt. In diesem Fall ist `version` der einzige Parameter mit Namen. Beachten Sie die Verwendung des `AttributeUsage`-Attributs, um das `Author`-Attribut ausschließlich für Klassen- und `struct`-Deklarationen gültig zu machen.  
  
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
public class AuthorAttribute : System.Attribute  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection>
- [C#-Programmierhandbuch](../../index.md)
- [Verfassen von benutzerdefinierten Attributen](../../../../standard/attributes/writing-custom-attributes.md)
- [Reflektion (C#)](../reflection.md)
- [Attribute (C#)](./index.md)
- [Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))](./accessing-attributes-by-using-reflection.md)
- [AttributeUsage (C#)](../../../language-reference/attributes/general.md)
