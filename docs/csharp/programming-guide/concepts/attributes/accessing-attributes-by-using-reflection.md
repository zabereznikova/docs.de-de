---
title: Zugriff auf Attribute mit Reflektion (C#)
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
ms.assetid: dce3a696-4ceb-489a-b5e4-322a83052f18
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 36724c7b6a2a786aff837db5bcf2ad2ccfa39205
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="accessing-attributes-by-using-reflection-c"></a><span data-ttu-id="90cbe-102">Zugriff auf Attribute mit Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="90cbe-102">Accessing Attributes by Using Reflection (C#)</span></span>
<span data-ttu-id="90cbe-103">Die Tatsache, dass Sie benutzerdefinierte Attribute definieren und diese in Ihren Quellcode platzieren können, hätte keinen Nutzen, wenn Sie diese Informationen nicht abrufen und darauf reagieren könnten.</span><span class="sxs-lookup"><span data-stu-id="90cbe-103">The fact that you can define custom attributes and place them in your source code would be of little value without some way of retrieving that information and acting on it.</span></span> <span data-ttu-id="90cbe-104">Mithilfe der Reflektion können Sie die Informationen abrufen, die mit benutzerdefinierten Attributen definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="90cbe-104">By using reflection, you can retrieve the information that was defined with custom attributes.</span></span> <span data-ttu-id="90cbe-105">Die Schlüsselmethode ist `GetCustomAttributes`, die ein Array von Objekten zurück gibt, die die Laufzeitäquivalente der Quellcodeattribute sind.</span><span class="sxs-lookup"><span data-stu-id="90cbe-105">The key method is `GetCustomAttributes`, which returns an array of objects that are the run-time equivalents of the source code attributes.</span></span> <span data-ttu-id="90cbe-106">Diese Methode hat mehrere überladene Versionen.</span><span class="sxs-lookup"><span data-stu-id="90cbe-106">This method has several overloaded versions.</span></span> <span data-ttu-id="90cbe-107">Weitere Informationen finden Sie unter <xref:System.Attribute>.</span><span class="sxs-lookup"><span data-stu-id="90cbe-107">For more information, see <xref:System.Attribute>.</span></span>  
  
 <span data-ttu-id="90cbe-108">Eine Attributspezifikation wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="90cbe-108">An attribute specification such as:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
```  
  
 <span data-ttu-id="90cbe-109">ist mit Folgendem vergleichbar:</span><span class="sxs-lookup"><span data-stu-id="90cbe-109">is conceptually equivalent to this:</span></span>  
  
```csharp  
Author anonymousAuthorObject = new Author("P. Ackerman");  
anonymousAuthorObject.version = 1.1;  
```  
  
 <span data-ttu-id="90cbe-110">Der Code wird allerdings erst ausgeführt, wenn `SampleClass` nach Attributen abgefragt wird.</span><span class="sxs-lookup"><span data-stu-id="90cbe-110">However, the code is not executed until `SampleClass` is queried for attributes.</span></span> <span data-ttu-id="90cbe-111">Wenn `GetCustomAttributes` in `SampleClass` aufgerufen wird, führt dies zur Erstellung und Initialisierung eines `Author`-Objekt wie oben aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="90cbe-111">Calling `GetCustomAttributes` on `SampleClass` causes an `Author` object to be constructed and initialized as above.</span></span> <span data-ttu-id="90cbe-112">Wenn die Klasse andere Attribute aufweist, werden so auch andere Attributobjekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="90cbe-112">If the class has other attributes, other attribute objects are constructed similarly.</span></span> <span data-ttu-id="90cbe-113">`GetCustomAttributes` gibt anschließend das `Author`-Objekt zurück sowie jedes andere Attributobjekt eines Arrays.</span><span class="sxs-lookup"><span data-stu-id="90cbe-113">`GetCustomAttributes` then returns the `Author` object and any other attribute objects in an array.</span></span> <span data-ttu-id="90cbe-114">Dann können Sie dieses Array durchlaufen, anhand der Type der Arrayelemente feststellen, welche Attribute gelten, und Informationen jedes Attributobjekts erhalten.</span><span class="sxs-lookup"><span data-stu-id="90cbe-114">You can then iterate over this array, determine what attributes were applied based on the type of each array element, and extract information from the attribute objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90cbe-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="90cbe-115">Example</span></span>  
 <span data-ttu-id="90cbe-116">Im Folgenden sehen Sie ein vollständiges Beispiel.</span><span class="sxs-lookup"><span data-stu-id="90cbe-116">Here is a complete example.</span></span> <span data-ttu-id="90cbe-117">Ein benutzerdefiniertes Attribut wird definiert, auf mehrere Entitäten angewendet und mithilfe der Reflektion abgerufen.</span><span class="sxs-lookup"><span data-stu-id="90cbe-117">A custom attribute is defined, applied to several entities, and retrieved via reflection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="90cbe-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90cbe-118">See Also</span></span>  
 <span data-ttu-id="90cbe-119"><xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="90cbe-119"><xref:System.Reflection></span></span>   
 <span data-ttu-id="90cbe-120"><xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="90cbe-120"><xref:System.Attribute></span></span>   
 <span data-ttu-id="90cbe-121">[C#-Programmierhandbuch](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="90cbe-121">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="90cbe-122">[Abrufen von Informationen aus Attributen](../../../../standard/attributes/retrieving-information-stored-in-attributes.md) </span><span class="sxs-lookup"><span data-stu-id="90cbe-122">[Retrieving Information Stored in Attributes](../../../../standard/attributes/retrieving-information-stored-in-attributes.md) </span></span>  
 <span data-ttu-id="90cbe-123">[Reflektion (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="90cbe-123">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span></span>  
 <span data-ttu-id="90cbe-124">[Attribute (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md) </span><span class="sxs-lookup"><span data-stu-id="90cbe-124">[Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/index.md) </span></span>  
 [<span data-ttu-id="90cbe-125">Erstellen benutzerdefinierter Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="90cbe-125">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)

