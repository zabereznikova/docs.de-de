---
title: LINQ to XML-Ereignisse (C#)
ms.date: 07/20/2015
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
ms.openlocfilehash: 8e0cb4519dd0fc2bed443d9a62b9a2545d10e161
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253176"
---
# <a name="linq-to-xml-events-c"></a><span data-ttu-id="0af56-102">LINQ to XML-Ereignisse (C#)</span><span class="sxs-lookup"><span data-stu-id="0af56-102">LINQ to XML Events (C#)</span></span>
<span data-ttu-id="0af56-103">Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Ereignissen können Sie sich benachrichtigen lassen, wenn eine XML-Struktur geändert wird.</span><span class="sxs-lookup"><span data-stu-id="0af56-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="0af56-104">Ereignisse können allen Instanzen eines <xref:System.Xml.Linq.XObject> hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="0af56-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="0af56-105">Der Ereignishandler empfängt dann Ereignisse für Änderungen an diesem <xref:System.Xml.Linq.XObject> und dessen Nachfolgern.</span><span class="sxs-lookup"><span data-stu-id="0af56-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="0af56-106">So können Sie z. B. dem Stamm der Struktur einen Ereignishandler hinzufügen und alle Änderungen an der Struktur von diesem Ereignishandler behandeln lassen.</span><span class="sxs-lookup"><span data-stu-id="0af56-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="0af56-107">Beispiele für [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Ereignisse finden Sie unter <xref:System.Xml.Linq.XObject.Changing> und <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="0af56-107">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="0af56-108">Typen und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="0af56-108">Types and Events</span></span>  
 <span data-ttu-id="0af56-109">Beim Arbeiten mit Ereignissen stehen Ihnen die folgenden Typen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="0af56-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="0af56-110">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="0af56-110">Type</span></span>|<span data-ttu-id="0af56-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0af56-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="0af56-112">Gibt den Ereignistyp an, wenn ein Ereignis für ein <xref:System.Xml.Linq.XObject> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0af56-112">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="0af56-113">Stellt Daten für das <xref:System.Xml.Linq.XObject.Changing>-Ereignis und das <xref:System.Xml.Linq.XObject.Changed>-Ereignis bereit.</span><span class="sxs-lookup"><span data-stu-id="0af56-113">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="0af56-114">Die folgenden Ereignisse werden ausgelöst, wenn Sie eine XML-Struktur ändern:</span><span class="sxs-lookup"><span data-stu-id="0af56-114">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="0af56-115">event</span><span class="sxs-lookup"><span data-stu-id="0af56-115">Event</span></span>|<span data-ttu-id="0af56-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0af56-116">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="0af56-117">Tritt ein, unmittelbar bevor sich dieses <xref:System.Xml.Linq.XObject> oder eines seiner Nachfolger ändert.</span><span class="sxs-lookup"><span data-stu-id="0af56-117">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="0af56-118">Tritt ein, wenn sich ein <xref:System.Xml.Linq.XObject> oder eines seiner Nachfolger geändert hat.</span><span class="sxs-lookup"><span data-stu-id="0af56-118">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0af56-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0af56-119">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0af56-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0af56-120">Description</span></span>  
 <span data-ttu-id="0af56-121">Ereignisse erweisen sich als nützlich, wenn aggregierte Informationen in einer XML-Struktur bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0af56-121">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="0af56-122">So können Sie auf diese Weise z. B. einen Rechnungsgesamtbetrag bereitstellen, der sich aus der Summe der Einzelpositionen der Rechnung ergibt.</span><span class="sxs-lookup"><span data-stu-id="0af56-122">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="0af56-123">Dieses Beispiel verwendet Ereignisse, um den Gesamtbetrag aller untergeordneten Elemente des komplexen Elements `Items` bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="0af56-123">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0af56-124">Code</span><span class="sxs-lookup"><span data-stu-id="0af56-124">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="0af56-125">Kommentare</span><span class="sxs-lookup"><span data-stu-id="0af56-125">Comments</span></span>  
 <span data-ttu-id="0af56-126">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="0af56-126">This code produces the following output:</span></span>  
  
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
  