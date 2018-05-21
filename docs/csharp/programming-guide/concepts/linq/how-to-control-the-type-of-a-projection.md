---
title: 'Vorgehensweise: Steuern des Typs einer Projektion (C#)'
ms.date: 07/20/2015
ms.assetid: e4db6b7e-4cc9-4c8f-af85-94acf32aa348
ms.openlocfilehash: 67ca04d9f3412def8d8c940c9ed932bf9da3287b
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-control-the-type-of-a-projection-c"></a><span data-ttu-id="2f954-102">Vorgehensweise: Steuern des Typs einer Projektion (C#)</span><span class="sxs-lookup"><span data-stu-id="2f954-102">How to: Control the Type of a Projection (C#)</span></span>
<span data-ttu-id="2f954-103">Bei einer Projektion wird ein Satz von Daten gefiltert und in der Form und sogar im Typ geändert.</span><span class="sxs-lookup"><span data-stu-id="2f954-103">Projection is the process of taking one set of data, filtering it, changing its shape, and even changing its type.</span></span> <span data-ttu-id="2f954-104">Die meisten Abfrageausdrücke führen Projektionen aus.</span><span class="sxs-lookup"><span data-stu-id="2f954-104">Most query expressions perform projections.</span></span> <span data-ttu-id="2f954-105">Bei den meisten Abfrageausdrücken in diesem Abschnitt ist das Ergebnis der Auswertung eine <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement>, aber Sie können festlegen, welcher Projektionstyp verwendet werden soll, um Auflistungen eines anderen Typs zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2f954-105">Most of the query expressions shown in this section evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, but you can control the type of the projection to create collections of other types.</span></span> <span data-ttu-id="2f954-106">In diesem Thema wird gezeigt, wie Sie dazu vorgehen müssen.</span><span class="sxs-lookup"><span data-stu-id="2f954-106">This topic shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f954-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f954-107">Example</span></span>  
 <span data-ttu-id="2f954-108">Das folgende Beispiel definiert einen neuen Typ: `Customer`.</span><span class="sxs-lookup"><span data-stu-id="2f954-108">The following example defines a new type, `Customer`.</span></span> <span data-ttu-id="2f954-109">Der Abfrageausdruck instanziiert dann in der `Customer`-Klausel neue `Select`-Objekte.</span><span class="sxs-lookup"><span data-stu-id="2f954-109">The query expression then instantiates new `Customer` objects in the `Select` clause.</span></span> <span data-ttu-id="2f954-110">Damit ist der Typ des Abfrageausdrucks eine <xref:System.Collections.Generic.IEnumerable%601> von `Customer`.</span><span class="sxs-lookup"><span data-stu-id="2f954-110">This causes the type of the query expression to be <xref:System.Collections.Generic.IEnumerable%601> of `Customer`.</span></span>  
  
 <span data-ttu-id="2f954-111">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="2f954-111">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
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
        return String.Format("{0}:{1}:{2}", this.customerID, this.companyName, this.contactName);  
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
  
 <span data-ttu-id="2f954-112">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="2f954-112">This code produces the following output:</span></span>  
  
```  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f954-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f954-113">See Also</span></span>  
 <xref:System.Linq.Enumerable.Select%2A>  
 [<span data-ttu-id="2f954-114">Projektionen und Transformationen (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2f954-114">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
