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
# <a name="accessing-attributes-by-using-reflection-c"></a><span data-ttu-id="ca65c-103">Zugriff auf Attribute mit Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="ca65c-103">Accessing Attributes by Using Reflection (C#)</span></span>
<span data-ttu-id="ca65c-104">Die Tatsache, dass Sie benutzerdefinierte Attribute definieren und diese in Ihren Quellcode platzieren können, hätte keinen Nutzen, wenn Sie diese Informationen nicht abrufen und darauf reagieren könnten.</span><span class="sxs-lookup"><span data-stu-id="ca65c-104">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="ca65c-105">Mithilfe der Reflektion können Sie die Informationen abrufen, die mit benutzerdefinierten Attributen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ca65c-105">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="ca65c-106">Die Schlüsselmethode ist `GetCustomAttributes`, die ein Array von Objekten zurück gibt, die die Laufzeitäquivalente der Quellcodeattribute sind.</span><span class="sxs-lookup"><span data-stu-id="ca65c-106">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="ca65c-107">Diese Methode hat mehrere überladene Versionen.</span><span class="sxs-lookup"><span data-stu-id="ca65c-107">This method has several overloaded versions.</span></span> <span data-ttu-id="ca65c-108">Weitere Informationen finden Sie unter <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="ca65c-108">For more information, see <xref:System.Attribute>.</span></span>  
  
 <span data-ttu-id="ca65c-109">Eine Attributspezifikation wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="ca65c-109">An attribute specification such as:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
```  
  
 <span data-ttu-id="ca65c-110">ist mit Folgendem vergleichbar:</span><span class="sxs-lookup"><span data-stu-id="ca65c-110">is conceptually equivalent to this:</span></span>  
  
```csharp  
Author anonymousAuthorObject = new Author("P. Ackerman");  
anonymousAuthorObject.version = 1.1;  
```  
  
 <span data-ttu-id="ca65c-111">Der Code wird allerdings erst ausgeführt, wenn `SampleClass` nach Attributen abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="ca65c-111">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="ca65c-112">Wenn `GetCustomAttributes` in `SampleClass` aufgerufen wird, führt dies zur Erstellung und Initialisierung eines `Author`-Objekt wie oben aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ca65c-112">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="ca65c-113">Wenn die Klasse andere Attribute aufweist, werden so auch andere Attributobjekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="ca65c-113">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="ca65c-114">`GetCustomAttributes` gibt anschließend das `Author`-Objekt zurück sowie jedes andere Attributobjekt eines Arrays.</span><span class="sxs-lookup"><span data-stu-id="ca65c-114">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="ca65c-115">Dann können Sie dieses Array durchlaufen, anhand der Type der Arrayelemente feststellen, welche Attribute gelten, und Informationen jedes Attributobjekts erhalten.</span><span class="sxs-lookup"><span data-stu-id="ca65c-115">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ca65c-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ca65c-116">Example</span></span>  
 <span data-ttu-id="ca65c-117">Im Folgenden sehen Sie ein vollständiges Beispiel.</span><span class="sxs-lookup"><span data-stu-id="ca65c-117">Here is a complete example.</span></span> <span data-ttu-id="ca65c-118">Ein benutzerdefiniertes Attribut wird definiert, auf mehrere Entitäten angewendet und mithilfe der Reflektion abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ca65c-118">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ca65c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca65c-119">See also</span></span>

- <xref:System.Reflection>
- <xref:System.Attribute>
- [<span data-ttu-id="ca65c-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ca65c-120">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="ca65c-121">Abrufen von Informationen aus Attributen</span><span class="sxs-lookup"><span data-stu-id="ca65c-121">Retrieving Information Stored in Attributes</span></span>](../../../../standard/attributes/retrieving-information-stored-in-attributes.md)
- [<span data-ttu-id="ca65c-122">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="ca65c-122">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="ca65c-123">Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="ca65c-123">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="ca65c-124">Erstellen benutzerdefinierter Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="ca65c-124">Creating Custom Attributes (C#)</span></span>](./creating-custom-attributes.md)
