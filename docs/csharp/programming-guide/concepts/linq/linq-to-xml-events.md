---
title: LINQ to XML-Ereignisse (C#)
description: Fügen Sie LINQ to XML-Ereignisse in C# einer beliebigen XObject-Instanz hinzu. Der Ereignishandler empfängt Ereignisse, wenn die XML-Struktur für dieses XObject geändert wird.
ms.date: 07/20/2015
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
ms.openlocfilehash: 576b0a5d0472bddd66e01d3bef8f3affa1c9458b
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2020
ms.locfileid: "87165413"
---
# <a name="linq-to-xml-events-c"></a><span data-ttu-id="23501-104">LINQ to XML-Ereignisse (C#)</span><span class="sxs-lookup"><span data-stu-id="23501-104">LINQ to XML Events (C#)</span></span>
<span data-ttu-id="23501-105">Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Ereignissen können Sie sich benachrichtigen lassen, wenn eine XML-Struktur geändert wird.</span><span class="sxs-lookup"><span data-stu-id="23501-105">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="23501-106">Ereignisse können allen Instanzen eines <xref:System.Xml.Linq.XObject> hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="23501-106">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="23501-107">Der Ereignishandler empfängt dann Ereignisse für Änderungen an diesem <xref:System.Xml.Linq.XObject> und dessen Nachfolgern.</span><span class="sxs-lookup"><span data-stu-id="23501-107">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="23501-108">So können Sie z. B. dem Stamm der Struktur einen Ereignishandler hinzufügen und alle Änderungen an der Struktur von diesem Ereignishandler behandeln lassen.</span><span class="sxs-lookup"><span data-stu-id="23501-108">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="23501-109">Beispiele für [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Ereignisse finden Sie unter <xref:System.Xml.Linq.XObject.Changing> und <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="23501-109">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="23501-110">Typen und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="23501-110">Types and Events</span></span>  
 <span data-ttu-id="23501-111">Beim Arbeiten mit Ereignissen stehen Ihnen die folgenden Typen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="23501-111">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="23501-112">type</span><span class="sxs-lookup"><span data-stu-id="23501-112">Type</span></span>|<span data-ttu-id="23501-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23501-113">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="23501-114">Gibt den Ereignistyp an, wenn ein Ereignis für ein <xref:System.Xml.Linq.XObject> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="23501-114">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="23501-115">Stellt Daten für das <xref:System.Xml.Linq.XObject.Changing>-Ereignis und das <xref:System.Xml.Linq.XObject.Changed>-Ereignis bereit.</span><span class="sxs-lookup"><span data-stu-id="23501-115">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="23501-116">Die folgenden Ereignisse werden ausgelöst, wenn Sie eine XML-Struktur ändern:</span><span class="sxs-lookup"><span data-stu-id="23501-116">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="23501-117">Ereignis</span><span class="sxs-lookup"><span data-stu-id="23501-117">Event</span></span>|<span data-ttu-id="23501-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="23501-118">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="23501-119">Tritt ein, unmittelbar bevor sich dieses <xref:System.Xml.Linq.XObject> oder eines seiner Nachfolger ändert.</span><span class="sxs-lookup"><span data-stu-id="23501-119">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="23501-120">Tritt ein, wenn sich ein <xref:System.Xml.Linq.XObject> oder eines seiner Nachfolger geändert hat.</span><span class="sxs-lookup"><span data-stu-id="23501-120">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="23501-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="23501-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="23501-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="23501-122">Description</span></span>  
 <span data-ttu-id="23501-123">Ereignisse erweisen sich als nützlich, wenn aggregierte Informationen in einer XML-Struktur bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="23501-123">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="23501-124">So können Sie auf diese Weise z. B. einen Rechnungsgesamtbetrag bereitstellen, der sich aus der Summe der Einzelpositionen der Rechnung ergibt.</span><span class="sxs-lookup"><span data-stu-id="23501-124">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="23501-125">Dieses Beispiel verwendet Ereignisse, um den Gesamtbetrag aller untergeordneten Elemente des komplexen Elements `Items` bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="23501-125">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="23501-126">Code</span><span class="sxs-lookup"><span data-stu-id="23501-126">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="23501-127">Kommentare</span><span class="sxs-lookup"><span data-stu-id="23501-127">Comments</span></span>  
 <span data-ttu-id="23501-128">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="23501-128">This code produces the following output:</span></span>  
  
```output  
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
  