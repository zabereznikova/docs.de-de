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
# <a name="creating-custom-attributes-c"></a><span data-ttu-id="2fdd8-103">Erstellen benutzerdefinierter Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="2fdd8-103">Creating Custom Attributes (C#)</span></span>

<span data-ttu-id="2fdd8-104">Sie können eigene benutzerdefinierte Attribute erstellen, indem Sie eine Attributklasse definieren. Dies ist eine Klasse, die direkt oder indirekt von <xref:System.Attribute> abgeleitet wird, was es einfach macht, schnell Attributdefinitionen in Metadaten zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="2fdd8-104">You can create your own custom attributes by defining an attribute class, a class that derives directly or indirectly from <xref:System.Attribute>, which makes identifying attribute definitions in metadata fast and easy.</span></span> <span data-ttu-id="2fdd8-105">Angenommen, Sie möchten Typen mit dem Namen des Programmierers markieren, der den Typ geschrieben hat.</span><span class="sxs-lookup"><span data-stu-id="2fdd8-105">Suppose you want to tag types with the name of the programmer who wrote the type.</span></span> <span data-ttu-id="2fdd8-106">Sie definieren möglicherweise eine benutzerdefinierte `Author`-Attributklasse:</span><span class="sxs-lookup"><span data-stu-id="2fdd8-106">You might define a custom `Author` attribute class:</span></span>  
  
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
  
 <span data-ttu-id="2fdd8-107">Der Klassenname `AuthorAttribute` setzt sich aus dem Attributnamen `Author` und dem Suffix `Attribute` zusammen.</span><span class="sxs-lookup"><span data-stu-id="2fdd8-107">The class name `AuthorAttribute` is the attribute's name, `Author`, plus the `Attribute` suffix.</span></span> <span data-ttu-id="2fdd8-108">Er ist von `System.Attribute` abgeleitet, ist also eine benutzerdefinierte Attributklasse.</span><span class="sxs-lookup"><span data-stu-id="2fdd8-108">It is derived from `System.Attribute`, so it is a custom attribute class.</span></span> <span data-ttu-id="2fdd8-109">Die Parameter des Konstruktors sind die Positionsparameter des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="2fdd8-109">The constructor's parameters are the custom attribute's positional parameters.</span></span> <span data-ttu-id="2fdd8-110">In diesem Beispiel ist `name` ein Positionsparameter.</span><span class="sxs-lookup"><span data-stu-id="2fdd8-110">In this example, `name` is a positional parameter.</span></span> <span data-ttu-id="2fdd8-111">Alle öffentlichen Lese-/Schreibfelder oder -Eigenschaften werden Parameter genannt.</span><span class="sxs-lookup"><span data-stu-id="2fdd8-111">Any public read-write fields or properties are named parameters.</span></span> <span data-ttu-id="2fdd8-112">In diesem Fall ist `version` der einzige Parameter mit Namen.</span><span class="sxs-lookup"><span data-stu-id="2fdd8-112">In this case, `version` is the only named parameter.</span></span> <span data-ttu-id="2fdd8-113">Beachten Sie die Verwendung des `AttributeUsage`-Attributs, um das `Author`-Attribut ausschließlich für Klassen- und `struct`-Deklarationen gültig zu machen.</span><span class="sxs-lookup"><span data-stu-id="2fdd8-113">Note the use of the `AttributeUsage` attribute to make the `Author` attribute valid only on class and `struct` declarations.</span></span>  
  
 <span data-ttu-id="2fdd8-114">Sie könnten dieses neue Attribut wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="2fdd8-114">You could use this new attribute as follows:</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
}  
```  
  
 <span data-ttu-id="2fdd8-115">`AttributeUsage` verfügt über einen Parameter, `AllowMultiple`, mit dem Sie ein benutzerdefiniertes Attribut zur einmaligen oder mehrfachen Nutzung erstellen können.</span><span class="sxs-lookup"><span data-stu-id="2fdd8-115">`AttributeUsage` has a named parameter, `AllowMultiple`, with which you can make a custom attribute single-use or multiuse.</span></span> <span data-ttu-id="2fdd8-116">Im folgenden Codebeispiel wird ein mehrfach verwendbares Attribut erstellt.</span><span class="sxs-lookup"><span data-stu-id="2fdd8-116">In the following code example, a multiuse attribute is created.</span></span>  
  
```csharp  
[System.AttributeUsage(System.AttributeTargets.Class |  
                       System.AttributeTargets.Struct,  
                       AllowMultiple = true)  // multiuse attribute  
]  
public class AuthorAttribute : System.Attribute  
```  
  
 <span data-ttu-id="2fdd8-117">Im folgenden Codebeispiel werden mehrere Attribute desselben Typs auf eine Klasse angewendet.</span><span class="sxs-lookup"><span data-stu-id="2fdd8-117">In the following code example, multiple attributes of the same type are applied to a class.</span></span>  
  
```csharp  
[Author("P. Ackerman", version = 1.1)]  
[Author("R. Koch", version = 1.2)]  
class SampleClass  
{  
    // P. Ackerman's code goes here...  
    // R. Koch's code goes here...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2fdd8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fdd8-118">See also</span></span>

- <xref:System.Reflection>
- [<span data-ttu-id="2fdd8-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="2fdd8-119">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="2fdd8-120">Verfassen von benutzerdefinierten Attributen</span><span class="sxs-lookup"><span data-stu-id="2fdd8-120">Writing Custom Attributes</span></span>](../../../../standard/attributes/writing-custom-attributes.md)
- [<span data-ttu-id="2fdd8-121">Reflektion (C#)</span><span class="sxs-lookup"><span data-stu-id="2fdd8-121">Reflection (C#)</span></span>](../reflection.md)
- [<span data-ttu-id="2fdd8-122">Attribute (C#)</span><span class="sxs-lookup"><span data-stu-id="2fdd8-122">Attributes (C#)</span></span>](./index.md)
- [<span data-ttu-id="2fdd8-123">Accessing Attributes by Using Reflection (C#) (Zugriff auf Attribute mit Reflektion (C#))</span><span class="sxs-lookup"><span data-stu-id="2fdd8-123">Accessing Attributes by Using Reflection (C#)</span></span>](./accessing-attributes-by-using-reflection.md)
- [<span data-ttu-id="2fdd8-124">AttributeUsage (C#)</span><span class="sxs-lookup"><span data-stu-id="2fdd8-124">AttributeUsage (C#)</span></span>](../../../language-reference/attributes/general.md)
