---
title: LINQ to XML-Ereignisse (C#)
ms.date: 07/20/2015
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
ms.openlocfilehash: 6308d81eac830e11b6d58f8e460dfa377663cd21
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44261472"
---
# <a name="linq-to-xml-events-c"></a><span data-ttu-id="bf3d5-102">LINQ to XML-Ereignisse (C#)</span><span class="sxs-lookup"><span data-stu-id="bf3d5-102">LINQ to XML Events (C#)</span></span>
<span data-ttu-id="bf3d5-103">Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Ereignissen können Sie sich benachrichtigen lassen, wenn eine XML-Struktur geändert wird.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="bf3d5-104">Ereignisse können allen Instanzen eines <xref:System.Xml.Linq.XObject> hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="bf3d5-105">Der Ereignishandler empfängt dann Ereignisse für Änderungen an diesem <xref:System.Xml.Linq.XObject> und dessen Nachfolgern.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="bf3d5-106">So können Sie z. B. dem Stamm der Struktur einen Ereignishandler hinzufügen und alle Änderungen an der Struktur von diesem Ereignishandler behandeln lassen.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="bf3d5-107">Beispiele für [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Ereignisse finden Sie unter <xref:System.Xml.Linq.XObject.Changing> und <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-107">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="bf3d5-108">Typen und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="bf3d5-108">Types and Events</span></span>  
 <span data-ttu-id="bf3d5-109">Beim Arbeiten mit Ereignissen stehen Ihnen die folgenden Typen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="bf3d5-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="bf3d5-110">Typ</span><span class="sxs-lookup"><span data-stu-id="bf3d5-110">Type</span></span>|<span data-ttu-id="bf3d5-111">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="bf3d5-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="bf3d5-112">Gibt den Ereignistyp an, wenn ein Ereignis für ein <xref:System.Xml.Linq.XObject> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-112">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="bf3d5-113">Stellt Daten für das <xref:System.Xml.Linq.XObject.Changing>-Ereignis und das <xref:System.Xml.Linq.XObject.Changed>-Ereignis bereit.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-113">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="bf3d5-114">Die folgenden Ereignisse werden ausgelöst, wenn Sie eine XML-Struktur ändern:</span><span class="sxs-lookup"><span data-stu-id="bf3d5-114">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="bf3d5-115">event</span><span class="sxs-lookup"><span data-stu-id="bf3d5-115">Event</span></span>|<span data-ttu-id="bf3d5-116">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="bf3d5-116">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="bf3d5-117">Tritt ein, unmittelbar bevor sich dieses <xref:System.Xml.Linq.XObject> oder eines seiner Nachfolger ändert.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-117">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="bf3d5-118">Tritt ein, wenn sich ein <xref:System.Xml.Linq.XObject> oder eines seiner Nachfolger geändert hat.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-118">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="bf3d5-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bf3d5-119">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="bf3d5-120">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="bf3d5-120">Description</span></span>  
 <span data-ttu-id="bf3d5-121">Ereignisse erweisen sich als nützlich, wenn aggregierte Informationen in einer XML-Struktur bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-121">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="bf3d5-122">So können Sie auf diese Weise z. B. einen Rechnungsgesamtbetrag bereitstellen, der sich aus der Summe der Einzelpositionen der Rechnung ergibt.</span><span class="sxs-lookup"><span data-stu-id="bf3d5-122">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="bf3d5-123">Dieses Beispiel verwendet Ereignisse, um den Gesamtbetrag aller untergeordneten Elemente des komplexen Elements `Items` bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="bf3d5-123">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bf3d5-124">Code</span><span class="sxs-lookup"><span data-stu-id="bf3d5-124">Code</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Total", "0"),  
    new XElement("Items")  
);  
XElement total = root.Element("Total");  
XElement items = root.Element("Items");  
items.Changed += (object sender, XObjectChangeEventArgs cea) =>  
{  
    switch (cea.ObjectChange)  
    {  
        case XObjectChange.Add:  
            if (sender is XElement)  
                total.Value = ((int)total + (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total + (int)((XText)sender).Parent).ToString();  
            break;  
        case XObjectChange.Remove:  
            if (sender is XElement)  
                total.Value = ((int)total - (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total - Int32.Parse(((XText)sender).Value)).ToString();  
            break;  
    }  
    Console.WriteLine("Changed {0} {1}",  
      sender.GetType().ToString(), cea.ObjectChange.ToString());  
};  
items.SetElementValue("Item1", 25);  
items.SetElementValue("Item2", 50);  
items.SetElementValue("Item2", 75);  
items.SetElementValue("Item3", 133);  
items.SetElementValue("Item1", null);  
items.SetElementValue("Item4", 100);  
Console.WriteLine("Total:{0}", (int)total);  
Console.WriteLine(root);  
```  
  
### <a name="comments"></a><span data-ttu-id="bf3d5-125">Kommentare</span><span class="sxs-lookup"><span data-stu-id="bf3d5-125">Comments</span></span>  
 <span data-ttu-id="bf3d5-126">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bf3d5-126">This code produces the following output:</span></span>  
  
```  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf3d5-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf3d5-127">See Also</span></span>

- [<span data-ttu-id="bf3d5-128">Advanced LINQ to XML Programming (C#) (Erweiterte LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="bf3d5-128">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
