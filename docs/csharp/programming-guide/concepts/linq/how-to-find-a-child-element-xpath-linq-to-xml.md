---
title: 'Vorgehensweise: Suchen eines untergeordneten Elements (XPath-LINQ to XML) (C#)'
description: Erfahren Sie, wie Sie ein untergeordnetes Element suchen, indem Sie die Achse der untergeordneten XPath-Elemente mit der LINQ to XML Element-Methode vergleichen.
ms.date: 07/20/2015
ms.assetid: 4fa6182d-6196-4ed1-9c9e-82949ff89c71
ms.openlocfilehash: 57d1a4e636e3443512020129a76cc2de7bb3f244
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301735"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="f71ce-103">Vorgehensweise: Suchen eines untergeordneten Elements (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="f71ce-103">How to find a child element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="f71ce-104">In diesem Thema wird die Achse der untergeordneten XPath-Elemente mit der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A>-Methode verglichen.</span><span class="sxs-lookup"><span data-stu-id="f71ce-104">This topic compares the XPath child element axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  
  
 <span data-ttu-id="f71ce-105">Der XPath-Ausdruck lautet `DeliveryNotes`.</span><span class="sxs-lookup"><span data-stu-id="f71ce-105">The XPath expression is `DeliveryNotes`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f71ce-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f71ce-106">Example</span></span>  
 <span data-ttu-id="f71ce-107">Dieses Beispiel ermittelt das untergeordnete Element `DeliveryNotes`.</span><span class="sxs-lookup"><span data-stu-id="f71ce-107">This example finds the child element `DeliveryNotes`.</span></span>  
  
 <span data-ttu-id="f71ce-108">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f71ce-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument cpo = XDocument.Load("PurchaseOrders.xml");  
XElement po = cpo.Root.Element("PurchaseOrder");  
  
// LINQ to XML query  
XElement el1 = po.Element("DeliveryNotes");  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("DeliveryNotes");  
// same as "child::DeliveryNotes"  
// same as "./DeliveryNotes"  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 <span data-ttu-id="f71ce-109">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="f71ce-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  