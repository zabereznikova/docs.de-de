---
title: 'Vorgehensweise: Steuern des Typs einer Projektion (C#)'
ms.date: 07/20/2015
ms.assetid: e4db6b7e-4cc9-4c8f-af85-94acf32aa348
ms.openlocfilehash: cb7c272fbe67c0700b5740691befc483993f4e29
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141355"
---
# <a name="how-to-control-the-type-of-a-projection-c"></a><span data-ttu-id="92568-102">Vorgehensweise: Steuern des Typs einer Projektion (C#)</span><span class="sxs-lookup"><span data-stu-id="92568-102">How to control the type of a projection (C#)</span></span>
<span data-ttu-id="92568-103">Bei einer Projektion wird ein Satz von Daten gefiltert und in der Form und sogar im Typ geändert.</span><span class="sxs-lookup"><span data-stu-id="92568-103">Projection is the process of taking one set of data, filtering it, changing its shape, and even changing its type.</span></span> <span data-ttu-id="92568-104">Die meisten Abfrageausdrücke führen Projektionen aus.</span><span class="sxs-lookup"><span data-stu-id="92568-104">Most query expressions perform projections.</span></span> <span data-ttu-id="92568-105">Bei den meisten Abfrageausdrücken in diesem Abschnitt ist das Ergebnis der Auswertung eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement>, aber Sie können festlegen, welcher Projektionstyp verwendet werden soll, um Auflistungen eines anderen Typs zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92568-105">Most of the query expressions shown in this section evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, but you can control the type of the projection to create collections of other types.</span></span> <span data-ttu-id="92568-106">In diesem Thema wird gezeigt, wie Sie dazu vorgehen müssen.</span><span class="sxs-lookup"><span data-stu-id="92568-106">This topic shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92568-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="92568-107">Example</span></span>  
 <span data-ttu-id="92568-108">Das folgende Beispiel definiert einen neuen Typ: `Customer`.</span><span class="sxs-lookup"><span data-stu-id="92568-108">The following example defines a new type, `Customer`.</span></span> <span data-ttu-id="92568-109">Der Abfrageausdruck instanziiert dann in der `Customer`-Klausel neue `Select`-Objekte.</span><span class="sxs-lookup"><span data-stu-id="92568-109">The query expression then instantiates new `Customer` objects in the `Select` clause.</span></span> <span data-ttu-id="92568-110">Damit ist der Typ des Abfrageausdrucks eine <xref:System.Collections.Generic.IEnumerable%601> von `Customer`.</span><span class="sxs-lookup"><span data-stu-id="92568-110">This causes the type of the query expression to be <xref:System.Collections.Generic.IEnumerable%601> of `Customer`.</span></span>  
  
 <span data-ttu-id="92568-111">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="92568-111">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
public class Customer  
{  
    private string customerID;  
    public string CustomerID{ get{return customerID;} set{customerID = value;}}  
  
    private string companyName;  
    public string CompanyName{ get{return companyName;} set{companyName = value;}}  
  
    private string contactName;  
    public string ContactName { get{return contactName;} set{contactName = value;}}  
  
    public Customer(string customerID, string companyName, string contactName)  
    {  
        CustomerID = customerID;  
        CompanyName = companyName;  
        ContactName = contactName;  
    }  
  
    public override string ToString()  
    {  
        return $"{this.customerID}:{this.companyName}:{this.contactName}";
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement custOrd = XElement.Load("CustomersOrders.xml");  
        IEnumerable<Customer> custList =  
            from el in custOrd.Element("Customers").Elements("Customer")  
            select new Customer(  
                (string)el.Attribute("CustomerID"),  
                (string)el.Element("CompanyName"),  
                (string)el.Element("ContactName")  
            );  
        foreach (Customer cust in custList)  
            Console.WriteLine(cust);  
    }  
}  
```  
  
 <span data-ttu-id="92568-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="92568-112">This code produces the following output:</span></span>  
  
```output  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a><span data-ttu-id="92568-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="92568-113">See also</span></span>

- <xref:System.Linq.Enumerable.Select%2A>
