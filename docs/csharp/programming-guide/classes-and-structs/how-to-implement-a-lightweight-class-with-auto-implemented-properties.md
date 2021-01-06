---
title: 'Gewusst wie: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie eine unveränderliche einfache Klasse in C# erstellen, die automatisch implementierte Eigenschaften kapselt. Es gibt zwei Implementierungsansätze.
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.topic: how-to
ms.custom: contperf-fy21q2
ms.assetid: 1dc5a8ad-a4f7-4f32-8506-3fc6d8c8bfed
ms.openlocfilehash: 4b28ee17f4be2b933373cce0d3670cbfa9a12895
ms.sourcegitcommit: d0990c1c1ab2f81908360f47eafa8db9aa165137
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "97513041"
---
# <a name="how-to-implement-a-lightweight-class-with-auto-implemented-properties-c-programming-guide"></a><span data-ttu-id="9f17b-104">Gewusst wie: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="9f17b-104">How to implement a lightweight class with auto-implemented properties (C# Programming Guide)</span></span>

<span data-ttu-id="9f17b-105">In diesem Beispiel wird das Erstellen einer unveränderlichen einfachen Klasse gezeigt, die nur zum Kapseln einer Reihe von automatisch implementierten Eigenschaften dient.</span><span class="sxs-lookup"><span data-stu-id="9f17b-105">This example shows how to create an immutable lightweight class that serves only to encapsulate a set of auto-implemented properties.</span></span> <span data-ttu-id="9f17b-106">Verwenden Sie diese Konstruktart anstelle einer Struktur, wenn Sie eine Verweistypsemantik verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="9f17b-106">Use this kind of construct instead of a struct when you must use reference type semantics.</span></span>

<span data-ttu-id="9f17b-107">Für das Erstellen einer unveränderlichen Eigenschaft gibt es zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="9f17b-107">You can make an immutable property in two ways:</span></span>

- <span data-ttu-id="9f17b-108">Sie können deklarieren, dass die [set](../../language-reference/keywords/set.md)-Zugriffsmethode [privat](../../language-reference/keywords/private.md) ist.</span><span class="sxs-lookup"><span data-stu-id="9f17b-108">You can declare the [set](../../language-reference/keywords/set.md) accessor to be [private](../../language-reference/keywords/private.md).</span></span>  <span data-ttu-id="9f17b-109">Die Eigenschaft kann nur im Typ festgelegt werden. Kunden können sie jedoch nicht verändern.</span><span class="sxs-lookup"><span data-stu-id="9f17b-109">The property is only settable within the type, but it is immutable to consumers.</span></span>

  <span data-ttu-id="9f17b-110">Beim Deklarieren eines privaten `set`-Accessors können Sie einen Objektinitialisierer nicht verwenden, um die Eigenschaft zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="9f17b-110">When you declare a private `set` accessor, you cannot use an object initializer to initialize the property.</span></span> <span data-ttu-id="9f17b-111">Sie müssen eine Konstruktor oder eine Factorymethode verwenden.</span><span class="sxs-lookup"><span data-stu-id="9f17b-111">You must use a constructor or a factory method.</span></span>
- <span data-ttu-id="9f17b-112">Sie können einfach die [get](../../language-reference/keywords/get.md)-Zugriffsmethode deklarieren. Diese macht die Eigenschaft überall (außer im Konstruktor des Typs) unveränderlich.</span><span class="sxs-lookup"><span data-stu-id="9f17b-112">You can declare only the [get](../../language-reference/keywords/get.md) accessor, which makes the property immutable everywhere except in the type's constructor.</span></span>

<span data-ttu-id="9f17b-113">Das folgende Beispiel zeigt, wie eine Eigenschaft, die nur eine get-Zugriffsmethode aufweist, sich von einer Eigenschaft mit „get“ und „private set“ unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="9f17b-113">The following example shows how a property with only get accessor differs than one with get and private set.</span></span>

```csharp
class Contact
{
    public string Name { get; }
    public string Address { get; private set; }

    public Contact(string contactName, string contactAddress)
    {
        // Both properties are accessible in the constructor.
        Name = contactName;
        Address = contactAddress;
    }

    // Name isn't assignable here. This will generate a compile error.
    //public void ChangeName(string newName) => Name = newName;

    // Address is assignable here.
    public void ChangeAddress(string newAddress) => Address = newAddress
}
```

## <a name="example"></a><span data-ttu-id="9f17b-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9f17b-114">Example</span></span>

<span data-ttu-id="9f17b-115">Im folgenden Beispiel werden zwei Möglichkeiten für die Implementierung einer unveränderlichen Klasse gezeigt, die über automatisch implementierte Eigenschaften verfügt.</span><span class="sxs-lookup"><span data-stu-id="9f17b-115">The following example shows two ways to implement an immutable class that has auto-implemented properties.</span></span> <span data-ttu-id="9f17b-116">Mit beiden Möglichkeiten wird jeweils eine der Eigenschaften mit einer privaten `set` und eine der Eigenschaft mit einer `get` deklariert.</span><span class="sxs-lookup"><span data-stu-id="9f17b-116">Each way declares one of the properties with a private `set` and one of the properties with a `get` only.</span></span>  <span data-ttu-id="9f17b-117">Die erste Klasse verwendet einen Konstruktor nur zum Initialisieren der Eigenschaften, und die zweite Klasse verwendet eine statische Factorymethode, die einen Konstruktor aufruft.</span><span class="sxs-lookup"><span data-stu-id="9f17b-117">The first class uses a constructor only to initialize the properties, and the second class uses a static factory method that calls a constructor.</span></span>

```csharp
// This class is immutable. After an object is created,
// it cannot be modified from outside the class. It uses a
// constructor to initialize its properties.
class Contact
{
    // Read-only property.
    public string Name { get; }

    // Read-write property with a private set accessor.
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
    // Read-write property with a private set accessor.
    public string Name { get; private set; }

    // Read-only property.
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

<span data-ttu-id="9f17b-118">Der Compiler erstellt Unterstützungsfelder für jede automatisch implementierte Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9f17b-118">The compiler creates backing fields for each auto-implemented property.</span></span> <span data-ttu-id="9f17b-119">Es ist nicht möglich, über den Quellcode direkt auf die Felder zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9f17b-119">The fields are not accessible directly from source code.</span></span>

## <a name="see-also"></a><span data-ttu-id="9f17b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f17b-120">See also</span></span>

- [<span data-ttu-id="9f17b-121">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9f17b-121">Properties</span></span>](./properties.md)
- [<span data-ttu-id="9f17b-122">struct</span><span class="sxs-lookup"><span data-stu-id="9f17b-122">struct</span></span>](../../language-reference/builtin-types/struct.md)
- [<span data-ttu-id="9f17b-123">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="9f17b-123">Object and Collection Initializers</span></span>](./object-and-collection-initializers.md)
