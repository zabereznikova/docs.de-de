---
title: 'Vorgehensweise: Ermitteln des Stammelements (XPath-LINQ to XML) (C#)'
description: In diesem C#-Beispiel wird verglichen, wie XPath und LINQ to XML das Stammelement für ein XML-Beispieldokument abrufen.
ms.date: 07/20/2015
ms.assetid: 4fd824e0-4d39-429b-b092-f6a5c046ee6c
ms.openlocfilehash: 220899823210c5cd6e9834541ca87e4d8394b4ff
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87105194"
---
# <a name="how-to-find-the-root-element-xpath-linq-to-xml-c"></a><span data-ttu-id="f6e89-103">Vorgehensweise: Ermitteln des Stammelements (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="f6e89-103">How to find the root element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="f6e89-104">In diesem Thema wird gezeigt, wie Sie mit XPath und mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] das Stammelement ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="f6e89-104">This topic shows how to get the root element with XPath and [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span>  
  
 <span data-ttu-id="f6e89-105">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="f6e89-105">The XPath expression is:</span></span>  
  
 `/PurchaseOrders`  
  
## <a name="example"></a><span data-ttu-id="f6e89-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6e89-106">Example</span></span>  
 <span data-ttu-id="f6e89-107">Dieses Beispiel sucht nach dem Stammelement.</span><span class="sxs-lookup"><span data-stu-id="f6e89-107">This example finds the root element.</span></span>  
  
 <span data-ttu-id="f6e89-108">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Mehrere Bestellungen (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f6e89-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](./sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument po = XDocument.Load("PurchaseOrders.xml");  
  
// LINQ to XML query  
XElement el1 = po.Root;  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("/PurchaseOrders");  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1.Name);  
```  
  
 <span data-ttu-id="f6e89-109">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="f6e89-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
PurchaseOrders  
```  
