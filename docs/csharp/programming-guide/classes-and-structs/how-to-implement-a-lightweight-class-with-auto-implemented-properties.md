---
title: 'Gewusst wie: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften – C#-Programmierhandbuch'
description: Hier erfahren Sie, wie Sie eine unveränderliche einfache Klasse in C# erstellen, die automatisch implementierte Eigenschaften kapselt. Es gibt zwei Implementierungsansätze.
ms.date: 07/20/2015
helpviewer_keywords:
- auto-implemented properties [C#]
- properties [C#], auto-implemented
ms.assetid: 1dc5a8ad-a4f7-4f32-8506-3fc6d8c8bfed
ms.openlocfilehash: de9034772bad1f28e27abe01595309dd84ddc3e7
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/21/2020
ms.locfileid: "86864565"
---
# <a name="how-to-implement-a-lightweight-class-with-auto-implemented-properties-c-programming-guide"></a>Gewusst wie: Implementieren einer einfachen Klasse mit automatisch implementierten Eigenschaften (C#-Programmierhandbuch)

In diesem Beispiel wird das Erstellen einer unveränderlichen einfachen Klasse gezeigt, die nur zum Kapseln einer Reihe von automatisch implementierten Eigenschaften dient. Verwenden Sie diese Konstruktart anstelle einer Struktur, wenn Sie eine Verweistypsemantik verwenden müssen.

Für das Erstellen einer unveränderlichen Eigenschaft gibt es zwei Möglichkeiten:

- Sie können deklarieren, dass die [set](../../language-reference/keywords/set.md)-Zugriffsmethode [privat](../../language-reference/keywords/private.md) ist.  Die Eigenschaft kann nur im Typ festgelegt werden. Kunden können sie jedoch nicht verändern.

  Beim Deklarieren eines privaten `set`-Accessors können Sie einen Objektinitialisierer nicht verwenden, um die Eigenschaft zu initialisieren. Sie müssen eine Konstruktor oder eine Factorymethode verwenden.
- Sie können einfach die [get](../../language-reference/keywords/get.md)-Zugriffsmethode deklarieren. Diese macht die Eigenschaft überall (außer im Konstruktor des Typs) unveränderlich.

Das folgende Beispiel zeigt, wie eine Eigenschaft, die nur eine get-Zugriffsmethode aufweist, sich von einer Eigenschaft mit „get“ und „private set“ unterscheidet.

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

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Möglichkeiten für die Implementierung einer unveränderlichen Klasse gezeigt, die über automatisch implementierte Eigenschaften verfügt. Mit beiden Möglichkeiten wird jeweils eine der Eigenschaften mit einer privaten `set` und eine der Eigenschaft mit einer `get` deklariert.  Die erste Klasse verwendet einen Konstruktor nur zum Initialisieren der Eigenschaften, und die zweite Klasse verwendet eine statische Factorymethode, die einen Konstruktor aufruft.

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

Der Compiler erstellt Unterstützungsfelder für jede automatisch implementierte Eigenschaft. Es ist nicht möglich, über den Quellcode direkt auf die Felder zuzugreifen.

## <a name="see-also"></a>Siehe auch

- [Eigenschaften](./properties.md)
- [struct](../../language-reference/builtin-types/struct.md)
- [Objekt- und Auflistungsinitialisierer](./object-and-collection-initializers.md)
