---
title: 'Vorgehensweise: Projektieren eines anonymen Typs'
ms.date: 07/20/2015
ms.assetid: 30b42987-0e0e-4b2b-adb1-5255ddfbcd7b
ms.openlocfilehash: c486fbd7ee8ae917cd0ccf57e2b04e472784b11d
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810559"
---
# <a name="how-to-project-an-anonymous-type-visual-basic"></a><span data-ttu-id="29adb-102">Gewusst wie: Projizieren eines anonymen Typs (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29adb-102">How to: Project an Anonymous Type (Visual Basic)</span></span>
<span data-ttu-id="29adb-103">Es gibt Fälle, in denen Sie eine Abfrage in einen neuen Typ projizieren möchten, obwohl Sie wissen, dass dieser Typ nur für kurze Zeit verwendet werden wird.</span><span class="sxs-lookup"><span data-stu-id="29adb-103">In some cases you might want to project a query to a new type, even though you know you will only use this type for a short while.</span></span> <span data-ttu-id="29adb-104">Das Erstellen eines neuen Typs für die Verwendung in der Projektion bedeutet viel Zusatzarbeit.</span><span class="sxs-lookup"><span data-stu-id="29adb-104">It is a lot of extra work to create a new type just to use in the projection.</span></span> <span data-ttu-id="29adb-105">Effizienter wäre es in diesem Fall, eine Projektion in einen anonymen Typ vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="29adb-105">A more efficient approach in this case is to project to an anonymous type.</span></span> <span data-ttu-id="29adb-106">Mit anonymen Typen können Sie eine Klasse definieren und dann ein Objekt dieser Klasse deklarieren und initialisieren, ohne der Klasse dazu einen Namen geben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="29adb-106">Anonymous types allow you to define a class, then declare and initialize an object of that class, without giving the class a name.</span></span>  
  
 <span data-ttu-id="29adb-107">Anonyme Typen stellen die C#-Implementierung des mathematischen Konzepts eines *Tupels* dar.</span><span class="sxs-lookup"><span data-stu-id="29adb-107">Anonymous types are the C# implementation of the mathematical concept of a *tuple*.</span></span> <span data-ttu-id="29adb-108">Der mathematische Begriff „Tupel“ bzw. „n-Tupel“ (englisch „Tuple“) leitet sich aus dem englischen Wortbestandteil „-(t)uple“ für „-fach“ (z. B. „quadruple“ für „vierfach“ und „quintuple“ für „fünffach“) ab.</span><span class="sxs-lookup"><span data-stu-id="29adb-108">The mathematical term tuple originated from the sequence single, double, triple, quadruple, quintuple, n-tuple.</span></span> <span data-ttu-id="29adb-109">Er steht für eine endliche Abfolge von Objekten, die alle von einem bestimmten Typ sind.</span><span class="sxs-lookup"><span data-stu-id="29adb-109">It refers to a finite sequence of objects, each of a specific type.</span></span> <span data-ttu-id="29adb-110">Mitunter wird dies als Liste von Name/Wert-Paaren bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="29adb-110">Sometimes this is called a list of name/value pairs.</span></span> <span data-ttu-id="29adb-111">So könnte z.B. der Inhalt einer Adresse im XML-Dokument in [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) wie folgt ausgedrückt werden:</span><span class="sxs-lookup"><span data-stu-id="29adb-111">For example, the contents of an address in the [Sample XML File: Typical Purchase Order (LINQ to XML)](sample-xml-file-typical-purchase-order-linq-to-xml.md) XML document could be expressed as follows:</span></span>  
  
```
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 <span data-ttu-id="29adb-112">Das Erstellen einer Instanz eines anonymen Typs können Sie sich wie das Erstellen eines Tupels n-ter Ordnung vorstellen.</span><span class="sxs-lookup"><span data-stu-id="29adb-112">When you create an instance of an anonymous type, it is convenient to think of it as creating a tuple of order n.</span></span> <span data-ttu-id="29adb-113">Wenn Sie eine Abfrage schreiben, die ein Tupel in der `Select`-Klausel erstellt, gibt die Abfrage eine `IEnumerable` des Tupels zurück.</span><span class="sxs-lookup"><span data-stu-id="29adb-113">If you write a query that creates a tuple in the `Select` clause, the query returns an `IEnumerable` of the tuple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29adb-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="29adb-114">Example</span></span>  
 <span data-ttu-id="29adb-115">In diesem Beispiel projiziert die `Select`-Klausel einen anonymen Typ.</span><span class="sxs-lookup"><span data-stu-id="29adb-115">In this example, the `Select` clause projects an anonymous type.</span></span> <span data-ttu-id="29adb-116">Das Beispiel verwendet dann `Dim`, um das `IEnumerable`-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="29adb-116">The example then uses `Dim` to create the `IEnumerable` object.</span></span> <span data-ttu-id="29adb-117">Innerhalb der `For Each`-Schleife wird die Iterationsvariable zu einer Instanz des im Abfrageausdruck erstellten anonymen Typs.</span><span class="sxs-lookup"><span data-stu-id="29adb-117">Within the `For Each` loop, the iteration variable becomes an instance of the anonymous type created in the query expression.</span></span>  
  
 <span data-ttu-id="29adb-118">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="29adb-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")  
Dim custList = _  
    From el In custOrd.<Customers>.<Customer> _  
    Select New With { _  
        .CustomerID = el.@<CustomerID>, _  
        .CompanyName = el.<CompanyName>.Value, _  
        .ContactName = el.<ContactName>.Value _  
    }  
For Each cust In custList  
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName)  
Next  
```  
  
 <span data-ttu-id="29adb-119">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="29adb-119">This code produces the following output:</span></span>  
  
```console  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a><span data-ttu-id="29adb-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="29adb-120">See also</span></span>

- [<span data-ttu-id="29adb-121">Projektionen und Transformationen (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29adb-121">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](projections-and-transformations-linq-to-xml.md)
