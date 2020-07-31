---
title: Zugriff auf Attribute mit Reflektion (C#)
description: Verwenden Sie die Reflexion, um mithilfe der GetCustomAttributes-Methode mit benutzerdefinierten Attributen definierte Informationen in C# zu erhalten.
ms.date: 07/20/2015
ms.assetid: dce3a696-4ceb-489a-b5e4-322a83052f18
ms.openlocfilehash: 9425141d64fd061d0c1f628228693cce02f7bfa0
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925097"
---
# <a name="accessing-attributes-by-using-reflection-c"></a>Zugriff auf Attribute mit Reflektion (C#)
Die Tatsache, dass Sie benutzerdefinierte Attribute definieren und diese in Ihren Quellcode platzieren können, hätte keinen Nutzen, wenn Sie diese Informationen nicht abrufen und darauf reagieren könnten. Mithilfe der Reflektion können Sie die Informationen abrufen, die mit benutzerdefinierten Attributen definiert wurden. Die Schlüsselmethode ist `GetCustomAttributes`, die ein Array von Objekten zurück gibt, die die Laufzeitäquivalente der Quellcodeattribute sind. Diese Methode hat mehrere überladene Versionen. Weitere Informationen finden Sie unter <xref:System.Attribute>.  
  
 Eine Attributspezifikation wie z.B.:  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
```  
  
 ist mit Folgendem vergleichbar:  
  
```csharp  
Author anonymousAuthorObject = new Author("P. Ackerman");  
anonymousAuthorObject.version = 1.1;  
```  
  
 Der Code wird allerdings erst ausgeführt, wenn `SampleClass` nach Attributen abgefragt wird. Wenn `GetCustomAttributes` in `SampleClass` aufgerufen wird, führt dies zur Erstellung und Initialisierung eines `Author`-Objekt wie oben aufgeführt. Wenn die Klasse andere Attribute aufweist, werden so auch andere Attributobjekte erstellt. `GetCustomAttributes` gibt anschließend das `Author`-Objekt zurück sowie jedes andere Attributobjekt eines Arrays. Dann können Sie dieses Array durchlaufen, anhand der Type der Arrayelemente feststellen, welche Attribute gelten, und Informationen jedes Attributobjekts erhalten.  
  
## <a name="example"></a>Beispiel  
 Im Folgenden sehen Sie ein vollständiges Beispiel. Ein benutzerdefiniertes Attribut wird definiert, auf mehrere Entitäten angewendet und mithilfe der Reflektion abgerufen.  
  
```csharp  
// Multiuse attribute.  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // Multiuse attribute.  
]  
public class Author : System.Attribute  
{  
    string name;  
    public double version;  
  
    public Author(string name)  
    {  
        this.name = name;  
  
        // Default value.  
        version = 1.0;  
    }  
  
    public string GetName()  
    {  
        return name;  
    }  
}  
  
// Class with the Author attribute.  
[Author("P. Ackerman")]  
public class FirstClass  
{  
    // ...  
}  
  
// Class without the Author attribute.  
public class SecondClass  
{  
    // ...  
}  
  
// Class with multiple Author attributes.  
[Author("P. Ackerman"), Author("R. Koch", version = 2.0)]  
public class ThirdClass  
{  
    // ...  
}  
  
class TestAuthorAttribute  
{  
    static void Test()  
    {  
        PrintAuthorInfo(typeof(FirstClass));  
        PrintAuthorInfo(typeof(SecondClass));  
        PrintAuthorInfo(typeof(ThirdClass));  
    }  
  
    private static void PrintAuthorInfo(System.Type t)  
    {  
        System.Console.WriteLine("Author information for {0}", t);  
  
        // Using reflection.  
        System.Attribute[] attrs = System.Attribute.GetCustomAttributes(t);  // Reflection.  
  
        // Displaying output.  
        foreach (System.Attribute attr in attrs)  
        {  
            if (attr is Author)  
            {  
                Author a = (Author)attr;  
                System.Console.WriteLine("   {0}, version {1:f}", a.GetName(), a.version);  
            }  
        }  
    }  
}  
/* Output:  
    Author information for FirstClass  
       P. Ackerman, version 1.00  
    Author information for SecondClass  
    Author information for ThirdClass  
       R. Koch, version 2.00  
       P. Ackerman, version 1.00  
*/  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Reflection>
- <xref:System.Attribute>
- [C#-Programmierhandbuch](../../index.md)
- [Abrufen von Informationen aus Attributen](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)
- [Reflektion (C#)](../reflection.md)
- [Attribute (C#)](./index.md)
- [Erstellen benutzerdefinierter Attribute (C#)](./creating-custom-attributes.md)
