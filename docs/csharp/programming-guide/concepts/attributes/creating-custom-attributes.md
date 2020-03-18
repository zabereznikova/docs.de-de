---
title: Erstellen benutzerdefinierter Attribute (C#)
ms.date: 07/20/2015
ms.assetid: 500e1977-c6de-462d-abce-78a0eb1eda22
ms.openlocfilehash: c0f25adf0d562b659edaa8f36e72332fd0c1ee7e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "69595409"
---
# <a name="creating-custom-attributes-c"></a><span data-ttu-id="df9d5-102">Erstellen benutzerdefinierter Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="df9d5-102">Creating Custom Attributes (C#)</span></span>
<span data-ttu-id="df9d5-103">Sie können eigene benutzerdefinierte Attribute erstellen, indem Sie eine Attributklasse definieren. Dies ist eine Klasse, die direkt oder indirekt von <xref:System.Attribute> abgeleitet wird, was es einfach macht, schnell Attributdefinitionen in Metadaten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="df9d5-103">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="df9d5-104">Angenommen, Sie möchten Typen mit dem Namen des Programmierers markieren, der den Typ geschrieben hat.</span><span class="sxs-lookup"><span data-stu-id="df9d5-104">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="df9d5-105">Sie definieren möglicherweise eine benutzerdefinierte `Author`-Attributklasse:</span><span class="sxs-lookup"><span data-stu-id="df9d5-105">You might define a custom `Author` attribute class:</span></span>  
  
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
  
 <span data-ttu-id="df9d5-106">Der Klassenname ist der Attributname, `Author`.</span><span class="sxs-lookup"><span data-stu-id="df9d5-106">The class name is the attribute's name, `Author`.</span></span> <span data-ttu-id="df9d5-107">Er ist von `System.Attribute` abgeleitet, ist also eine benutzerdefinierte Attributklasse.</span><span class="sxs-lookup"><span data-stu-id="df9d5-107">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="df9d5-108">Die Parameter des Konstruktors sind die Positionsparameter des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="df9d5-108">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="df9d5-109">In diesem Beispiel ist `name` ein Positionsparameter.</span><span class="sxs-lookup"><span data-stu-id="df9d5-109">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="df9d5-110">Alle öffentlichen Lese-/Schreibfelder oder -Eigenschaften werden Parameter genannt.</span><span class="sxs-lookup"><span data-stu-id="df9d5-110">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="df9d5-111">In diesem Fall ist `version` der einzige Parameter mit Namen.</span><span class="sxs-lookup"><span data-stu-id="df9d5-111">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="df9d5-112">Beachten Sie die Verwendung des `AttributeUsage`-Attributs, um das `Author`-Attribut ausschließlich für Klassen- und `struct`-Deklarationen gültig zu machen.</span><span class="sxs-lookup"><span data-stu-id="df9d5-112">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `struct` declarations.</span></span>  
  
 <span data-ttu-id="df9d5-113">Sie könnten dieses neue Attribut wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="df9d5-113">You could use this new attribute as follows:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 <span data-ttu-id="df9d5-114">`AttributeUsage` verfügt über einen Parameter, `AllowMultiple`, mit dem Sie ein benutzerdefiniertes Attribut zur einmaligen oder mehrfachen Nutzung erstellen können.</span><span class="sxs-lookup"><span data-stu-id="df9d5-114">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="df9d5-115">Im folgenden Codebeispiel wird ein mehrfach verwendbares Attribut erstellt.</span><span class="sxs-lookup"><span data-stu-id="df9d5-115">In the following code example, a multiuse attribute is created.</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class Author : System.Attribute  
```  
  
 <span data-ttu-id="df9d5-116">Im folgenden Codebeispiel werden mehrere Attribute desselben Typs auf eine Klasse angewendet.</span><span class="sxs-lookup"><span data-stu-id="df9d5-116">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="df9d5-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="df9d5-117">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="df9d5-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="df9d5-118">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="df9d5-119">Verfassen von benutzerdefinierten Attributen</span><span class="sxs-lookup"><span data-stu-id="df9d5-119">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="df9d5-120">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="df9d5-120">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="df9d5-121">Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="df9d5-121">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="df9d5-122">Zugriff auf Attribute mit Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="df9d5-122">Accessing Attributes by Using Reflection (C#)</span></span>](./accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="df9d5-123">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="df9d5-123">AttributeUsage (C#)</span></span>](./attributeusage.md)
