---
title: 'Vorgehensweise: Projektieren eines anonymen Typs (C#)'
description: Informationen zum Projizieren einer Abfrage ab einen anonymen Typ in C# Es kann einfacher sein, einen anonymen Typ zu verwenden, als einen neuen Typ zu erstellen, der nur kurz verwendet wird.
ms.date: 07/20/2015
ms.assetid: 5cb9be13-5ac4-4373-a034-b3520a5b2dec
ms.openlocfilehash: 6598796a4ba95362340f2551b1da6ac6d857eaae
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104624"
---
# <a name="how-to-project-an-anonymous-type-c"></a><span data-ttu-id="807a0-104">Vorgehensweise: Projektieren eines anonymen Typs (C#)</span><span class="sxs-lookup"><span data-stu-id="807a0-104">How to project an anonymous type (C#)</span></span>
<span data-ttu-id="807a0-105">Es gibt Fälle, in denen Sie eine Abfrage in einen neuen Typ projizieren möchten, obwohl Sie wissen, dass dieser Typ nur für kurze Zeit verwendet werden wird.</span><span class="sxs-lookup"><span data-stu-id="807a0-105">In some cases you might want to project a query to a new type, even though you know you will only use this type for a short while.</span></span> <span data-ttu-id="807a0-106">Das Erstellen eines neuen Typs für die Verwendung in der Projektion bedeutet viel Zusatzarbeit.</span><span class="sxs-lookup"><span data-stu-id="807a0-106">It is a lot of extra work to create a new type just to use in the projection.</span></span> <span data-ttu-id="807a0-107">Effizienter wäre es in diesem Fall, eine Projektion in einen anonymen Typ vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="807a0-107">A more efficient approach in this case is to project to an anonymous type.</span></span> <span data-ttu-id="807a0-108">Mit anonymen Typen können Sie eine Klasse definieren und dann ein Objekt dieser Klasse deklarieren und initialisieren, ohne der Klasse dazu einen Namen geben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="807a0-108">Anonymous types allow you to define a class, then declare and initialize an object of that class, without giving the class a name.</span></span>  
  
 <span data-ttu-id="807a0-109">Anonyme Typen stellen die C#-Implementierung des mathematischen Konzepts eines *Tupels* dar.</span><span class="sxs-lookup"><span data-stu-id="807a0-109">Anonymous types are the C# implementation of the mathematical concept of a *tuple*.</span></span> <span data-ttu-id="807a0-110">Der mathematische Begriff „Tupel“ bzw. „n-Tupel“ (englisch „Tuple“) leitet sich aus dem englischen Wortbestandteil „-(t)uple“ für „-fach“ (z. B. „quadruple“ für „vierfach“ und „quintuple“ für „fünffach“) ab.</span><span class="sxs-lookup"><span data-stu-id="807a0-110">The mathematical term tuple originated from the sequence single, double, triple, quadruple, quintuple, n-tuple.</span></span> <span data-ttu-id="807a0-111">Er steht für eine endliche Abfolge von Objekten, die alle von einem bestimmten Typ sind.</span><span class="sxs-lookup"><span data-stu-id="807a0-111">It refers to a finite sequence of objects, each of a specific type.</span></span> <span data-ttu-id="807a0-112">Mitunter wird dies als Liste von Name/Wert-Paaren bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="807a0-112">Sometimes this is called a list of name/value pairs.</span></span> <span data-ttu-id="807a0-113">So könnte z.B. der Inhalt einer Adresse im XML-Dokument in [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) wie folgt ausgedrückt werden:</span><span class="sxs-lookup"><span data-stu-id="807a0-113">For example, the contents of an address in the [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md) XML document could be expressed as follows:</span></span>  
  
```text  
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 <span data-ttu-id="807a0-114">Das Erstellen einer Instanz eines anonymen Typs können Sie sich wie das Erstellen eines Tupels n-ter Ordnung vorstellen.</span><span class="sxs-lookup"><span data-stu-id="807a0-114">When you create an instance of an anonymous type, it is convenient to think of it as creating a tuple of order n.</span></span> <span data-ttu-id="807a0-115">Wenn Sie eine Abfrage schreiben, die ein Tupel in der `select`-Klausel erstellt, gibt die Abfrage eine `IEnumerable` des Tupels zurück.</span><span class="sxs-lookup"><span data-stu-id="807a0-115">If you write a query that creates a tuple in the `select` clause, the query returns an `IEnumerable` of the tuple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="807a0-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="807a0-116">Example</span></span>  
 <span data-ttu-id="807a0-117">In diesem Beispiel projiziert die `select`-Klausel einen anonymen Typ.</span><span class="sxs-lookup"><span data-stu-id="807a0-117">In this example, the `select` clause projects an anonymous type.</span></span> <span data-ttu-id="807a0-118">Das Beispiel verwendet dann `var`, um das `IEnumerable`-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="807a0-118">The example then uses `var` to create the `IEnumerable` object.</span></span> <span data-ttu-id="807a0-119">Innerhalb der `foreach`-Schleife wird die Iterationsvariable zu einer Instanz des im Abfrageausdruck erstellten anonymen Typs.</span><span class="sxs-lookup"><span data-stu-id="807a0-119">Within the `foreach` loop, the iteration variable becomes an instance of the anonymous type created in the query expression.</span></span>  
  
 <span data-ttu-id="807a0-120">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="807a0-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement custOrd = XElement.Load("CustomersOrders.xml");  
var custList =  
    from el in custOrd.Element("Customers").Elements("Customer")  
    select new {  
        CustomerID = (string)el.Attribute("CustomerID"),  
        CompanyName = (string)el.Element("CompanyName"),  
        ContactName = (string)el.Element("ContactName")  
    };  
foreach (var cust in custList)  
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName);  
```  
  
 <span data-ttu-id="807a0-121">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="807a0-121">This code produces the following output:</span></span>  
  
```output  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  