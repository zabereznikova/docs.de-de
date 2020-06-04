---
title: LINQ to XML-Ereignisse
ms.date: 07/20/2015
ms.assetid: 34923928-b99c-4004-956e-38f6db25e910
ms.openlocfilehash: d00f6f1b2a14ac73c1bcd4a1f74b9714ca304da3
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84368815"
---
# <a name="linq-to-xml-events-visual-basic"></a><span data-ttu-id="844b7-102">Ereignisse LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="844b7-102">LINQ to XML Events (Visual Basic)</span></span>
<span data-ttu-id="844b7-103">Mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Ereignissen können Sie sich benachrichtigen lassen, wenn eine XML-Struktur geändert wird.</span><span class="sxs-lookup"><span data-stu-id="844b7-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="844b7-104">Ereignisse können allen Instanzen eines <xref:System.Xml.Linq.XObject> hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="844b7-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="844b7-105">Der Ereignishandler empfängt dann Ereignisse für Änderungen an diesem <xref:System.Xml.Linq.XObject> und dessen Nachfolgern.</span><span class="sxs-lookup"><span data-stu-id="844b7-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="844b7-106">So können Sie z. B. dem Stamm der Struktur einen Ereignishandler hinzufügen und alle Änderungen an der Struktur von diesem Ereignishandler behandeln lassen.</span><span class="sxs-lookup"><span data-stu-id="844b7-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="844b7-107">Beispiele für [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Ereignisse finden Sie unter <xref:System.Xml.Linq.XObject.Changing> und <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="844b7-107">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="844b7-108">Typen und Ereignisse</span><span class="sxs-lookup"><span data-stu-id="844b7-108">Types and Events</span></span>  
 <span data-ttu-id="844b7-109">Beim Arbeiten mit Ereignissen stehen Ihnen die folgenden Typen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="844b7-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="844b7-110">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="844b7-110">Type</span></span>|<span data-ttu-id="844b7-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="844b7-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="844b7-112">Gibt den Ereignistyp an, wenn ein Ereignis für ein <xref:System.Xml.Linq.XObject> ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="844b7-112">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="844b7-113">Stellt Daten für das <xref:System.Xml.Linq.XObject.Changing>-Ereignis und das <xref:System.Xml.Linq.XObject.Changed>-Ereignis bereit.</span><span class="sxs-lookup"><span data-stu-id="844b7-113">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="844b7-114">Die folgenden Ereignisse werden ausgelöst, wenn Sie eine XML-Struktur ändern:</span><span class="sxs-lookup"><span data-stu-id="844b7-114">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="844b7-115">event</span><span class="sxs-lookup"><span data-stu-id="844b7-115">Event</span></span>|<span data-ttu-id="844b7-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="844b7-116">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="844b7-117">Tritt ein, unmittelbar bevor sich dieses <xref:System.Xml.Linq.XObject> oder eines seiner Nachfolger ändert.</span><span class="sxs-lookup"><span data-stu-id="844b7-117">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="844b7-118">Tritt ein, wenn sich ein <xref:System.Xml.Linq.XObject> oder eines seiner Nachfolger geändert hat.</span><span class="sxs-lookup"><span data-stu-id="844b7-118">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="844b7-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="844b7-119">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="844b7-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="844b7-120">Description</span></span>  
 <span data-ttu-id="844b7-121">Ereignisse erweisen sich als nützlich, wenn aggregierte Informationen in einer XML-Struktur bereitgestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="844b7-121">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="844b7-122">So können Sie auf diese Weise z. B. einen Rechnungsgesamtbetrag bereitstellen, der sich aus der Summe der Einzelpositionen der Rechnung ergibt.</span><span class="sxs-lookup"><span data-stu-id="844b7-122">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="844b7-123">Dieses Beispiel verwendet Ereignisse, um den Gesamtbetrag aller untergeordneten Elemente des komplexen Elements `Items` bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="844b7-123">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="844b7-124">Code</span><span class="sxs-lookup"><span data-stu-id="844b7-124">Code</span></span>  
  
```vb  
Module Module1  
    Dim WithEvents items As XElement = Nothing  
    Dim total As XElement = Nothing  
    Dim root As XElement = _  
            <Root>  
                <Total>0</Total>  
                <Items></Items>  
            </Root>  
  
    Private Sub XObjectChanged( _  
            ByVal sender As Object, _  
            ByVal cea As XObjectChangeEventArgs) _  
            Handles items.Changed  
        Select Case cea.ObjectChange  
            Case XObjectChange.Add  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
            Case XObjectChange.Remove  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
        End Select  
        Console.WriteLine("Changed {0} {1}", _  
                            sender.GetType().ToString(), _  
                            cea.ObjectChange.ToString())  
    End Sub  
  
    Sub Main()  
        total = root.<Total>(0)  
        items = root.<Items>(0)  
        items.SetElementValue("Item1", 25)  
        items.SetElementValue("Item2", 50)  
        items.SetElementValue("Item2", 75)  
        items.SetElementValue("Item3", 133)  
        items.SetElementValue("Item1", Nothing)  
        items.SetElementValue("Item4", 100)  
        Console.WriteLine("Total:{0}", CInt(total))  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="844b7-125">Kommentare</span><span class="sxs-lookup"><span data-stu-id="844b7-125">Comments</span></span>  
 <span data-ttu-id="844b7-126">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="844b7-126">This code produces the following output:</span></span>  
  
```console  
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
  
## <a name="see-also"></a><span data-ttu-id="844b7-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="844b7-127">See also</span></span>

- [<span data-ttu-id="844b7-128">Erweiterte LINQ to XML Programmierung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="844b7-128">Advanced LINQ to XML Programming (Visual Basic)</span></span>](advanced-linq-to-xml-programming.md)
