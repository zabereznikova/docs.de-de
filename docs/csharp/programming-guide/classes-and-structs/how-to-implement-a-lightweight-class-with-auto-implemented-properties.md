---
title: 'Vorgehensweise: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: 1dc5a8ad-a4f7-4f32-8506-3fc6d8c8bfed
ms.openlocfilehash: be4d7e5cf4d2f7c117766858dbba9c7c59c74b73
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267685"
---
# <a name="how-to-implement-a-lightweight-class-with-auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="62a63-102">Vorgehensweise: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="62a63-102">How to: Implement a Lightweight Class with Auto-Implemented Properties (C# Programming Guide)</span></span>
<span data-ttu-id="62a63-103">In diesem Beispiel wird das Erstellen einer unveränderlichen einfachen Klasse gezeigt, die nur zum Kapseln einer Reihe von automatisch implementierten Eigenschaften dient.</span><span class="sxs-lookup"><span data-stu-id="62a63-103">This example shows how to create an immutable lightweight class that serves only to encapsulate a set of auto-implemented properties.</span></span> <span data-ttu-id="62a63-104">Verwenden Sie diese Konstruktart anstelle einer Struktur, wenn Sie eine Verweistypsemantik verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="62a63-104">Use this kind of construct instead of a struct when you must use reference type semantics.</span></span>  
  
 <span data-ttu-id="62a63-105">Für das Erstellen einer unveränderlichen Eigenschaft gibt es zwei Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="62a63-105">You can make an immutable property in two ways.</span></span>  <span data-ttu-id="62a63-106">Sie können deklarieren, dass die [set](../../../csharp/language-reference/keywords/set.md)-Zugriffsmethode [privat](../../../csharp/language-reference/keywords/private.md) ist.</span><span class="sxs-lookup"><span data-stu-id="62a63-106">You can declare the [set](../../../csharp/language-reference/keywords/set.md) accessor to be [private](../../../csharp/language-reference/keywords/private.md).</span></span>  <span data-ttu-id="62a63-107">Die Eigenschaft kann nur im Typ festgelegt werden. Kunden können sie jedoch nicht verändern.</span><span class="sxs-lookup"><span data-stu-id="62a63-107">The property is only settable within the type, but it is immutable to consumers.</span></span>  <span data-ttu-id="62a63-108">Sie können stattdessen einfach die [Get](../../../csharp/language-reference/keywords/get.md)-Zugriffsmethode deklarieren. Dieser macht die Eigenschaft mit Ausnahme im Konstruktor des Typs überall unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="62a63-108">You can instead declare only the [get](../../../csharp/language-reference/keywords/get.md) accessor, which makes the property immutable everywhere except in the type’s constructor.</span></span>  
  
 <span data-ttu-id="62a63-109">Beim Deklarieren eines privaten `set`-Accessors können Sie einen Objektinitialisierer nicht verwenden, um die Eigenschaft zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="62a63-109">When you declare a private `set` accessor, you cannot use an object initializer to initialize the property.</span></span> <span data-ttu-id="62a63-110">Sie müssen eine Konstruktor oder eine Factorymethode verwenden.</span><span class="sxs-lookup"><span data-stu-id="62a63-110">You must use a constructor or a factory method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="62a63-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="62a63-111">Example</span></span>  
 <span data-ttu-id="62a63-112">Im folgenden Beispiel werden zwei Möglichkeiten für die Implementierung einer unveränderlichen Klasse gezeigt, die über automatisch implementierte Eigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="62a63-112">The following example shows two ways to implement an immutable class that has auto-implemented properties.</span></span> <span data-ttu-id="62a63-113">Mit beiden Möglichkeiten wird jeweils eine der Eigenschaften mit einer privaten `set` und eine der Eigenschaft mit einer `get` deklariert.</span><span class="sxs-lookup"><span data-stu-id="62a63-113">Each way declares one of the properties with a private `set` and one of the properties with a `get` only.</span></span>  <span data-ttu-id="62a63-114">Die erste Klasse verwendet einen Konstruktor nur zum Initialisieren der Eigenschaften, und die zweite Klasse verwendet eine statische Factorymethode, die einen Konstruktor aufruft.</span><span class="sxs-lookup"><span data-stu-id="62a63-114">The first class uses a constructor only to initialize the properties, and the second class uses a static factory method that calls a constructor.</span></span>  
  
```csharp  
// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// constructor to initialize its properties.
class Contact
{
    // Read-only properties.
    public string Name { get; }
    public string Address { get; private set; }

    // Public constructor.
    public Contact(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }
}

// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// static method and private constructor to initialize its properties.
public class Contact2
{
    // Read-only properties.
    public string Name { get; private set; }
    public string Address { get; }

    // Private constructor.
    private Contact2(string contactName, string contactAddress)
    {
        Name = contactName;
        Address = contactAddress;
    }

    // Public factory method.
    public static Contact2 CreateContact(string name, string address)
    {
        return new Contact2(name, address);
    }
}

public class Program
{
    static void Main()
    {
        // Some simple data sources.
        string[] names = {"Terry Adams","Fadi Fakhouri", "Hanying Feng",
                            "Cesar Garcia", "Debra Garcia"};
        string[] addresses = {"123 Main St.", "345 Cypress Ave.", "678 1st Ave",
                                "12 108th St.", "89 E. 42nd St."};

        // Simple query to demonstrate object creation in select clause.
        // Create Contact objects by using a constructor.
        var query1 = from i in Enumerable.Range(0, 5)
                    select new Contact(names[i], addresses[i]);

        // List elements cannot be modified by client code.
        var list = query1.ToList();
        foreach (var contact in list)
        {
            Console.WriteLine("{0}, {1}", contact.Name, contact.Address);
        }

        // Create Contact2 objects by using a static factory method.
        var query2 = from i in Enumerable.Range(0, 5)
                        select Contact2.CreateContact(names[i], addresses[i]);

        // Console output is identical to query1.
        var list2 = query2.ToList();

        // List elements cannot be modified by client code.
        // CS0272:
        // list2[0].Name = "Eugene Zabokritski";

        // Keep the console open in debug mode.
        Console.WriteLine("Press any key to exit.");
        Console.ReadKey();
    }
}
  
/* Output:  
    Terry Adams, 123 Main St.  
    Fadi Fakhouri, 345 Cypress Ave.  
    Hanying Feng, 678 1st Ave  
    Cesar Garcia, 12 108th St.  
    Debra Garcia, 89 E. 42nd St.  
*/  
```  
  
 <span data-ttu-id="62a63-115">Der Compiler erstellt Unterstützungsfelder für jede automatisch implementierte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="62a63-115">The compiler creates backing fields for each auto-implemented property.</span></span> <span data-ttu-id="62a63-116">Es ist nicht möglich, über den Quellcode direkt auf die Felder zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="62a63-116">The fields are not accessible directly from source code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62a63-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62a63-117">See also</span></span>

- [<span data-ttu-id="62a63-118">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="62a63-118">Properties</span></span>](../../../csharp/programming-guide/classes-and-structs/properties.md)
- [<span data-ttu-id="62a63-119">struct</span><span class="sxs-lookup"><span data-stu-id="62a63-119">struct</span></span>](../../../csharp/language-reference/keywords/struct.md)
- [<span data-ttu-id="62a63-120">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="62a63-120">Object and Collection Initializers</span></span>](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)
