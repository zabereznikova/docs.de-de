---
title: Erstellen eines XML-Dokuments
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5a0806e34cfbf7c8e0b5ba995ca4876b8d10405e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xml-document-creation"></a><span data-ttu-id="24ae4-102">Erstellen eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="24ae4-102">XML Document Creation</span></span>
<span data-ttu-id="24ae4-103">Es gibt zwei Möglichkeiten, ein XML-Dokument zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="24ae4-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="24ae4-104">Eine Möglichkeit besteht im Erstellen einer **XmlDocument** ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="24ae4-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="24ae4-105">Eine andere Möglichkeit besteht im Erstellen einer **XmlDocument** und ihm eine XmlNameTable als Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="24ae4-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="24ae4-106">Im folgende Beispiel wird gezeigt, wie ein neues, leeres erstellen **XmlDocument** ohne Parameter.</span><span class="sxs-lookup"><span data-stu-id="24ae4-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="24ae4-107">Sobald ein Dokument erstellt wird, können Sie es mit Daten aus einer Zeichenfolge laden Datenstream, einer URL, Text-Reader oder ein **XmlReader** abgeleiteten Klasse von der **laden** Methode.</span><span class="sxs-lookup"><span data-stu-id="24ae4-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="24ae4-108">Es gibt auch eine andere Load-Methode, die **LoadXML** -Methode, die XML aus einer Zeichenfolge liest.</span><span class="sxs-lookup"><span data-stu-id="24ae4-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="24ae4-109">Weitere Informationen zu den verschiedenen **laden** Methoden, finden Sie unter [Lesen eines XML-Dokuments in das DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="24ae4-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="24ae4-110">Es wird eine Klasse mit dem Namen der **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="24ae4-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="24ae4-111">Sie besteht aus einer Tabelle mit atomisierten Zeichenfolgenobjekten.</span><span class="sxs-lookup"><span data-stu-id="24ae4-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="24ae4-112">Diese Tabelle ist ein effizientes Instrument, mit dem der XML-Parser das gleiche Zeichenfolgenobjekt für alle wiederkehrenden Element- und Attributnamen in einem XML-Dokument verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="24ae4-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="24ae4-113">Ein **XmlNameTable** wird automatisch erstellt, wenn ein Dokument erstellt wird, wie oben dargestellt und wird mit Attribut- und Elementnamen geladen, wenn das Dokument geladen wird.</span><span class="sxs-lookup"><span data-stu-id="24ae4-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="24ae4-114">Wenn Sie bereits über ein Dokument mit einer Namenstabelle verfügen und diese Namen in einem anderen Dokument nützlich wären, können Sie erstellen, ein neues Dokument mit der **laden** Methode, eine **XmlNameTable** als Parameter.</span><span class="sxs-lookup"><span data-stu-id="24ae4-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="24ae4-115">Wenn das Dokument mit dieser Methode erstellt wird, verwendet die vorhandene **XmlNameTable** mit allen Attributen und Elementen, die bereits geladenen aus dem anderen Dokument.</span><span class="sxs-lookup"><span data-stu-id="24ae4-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="24ae4-116">Dies dient zum effizienten Vergleichen von Element- und Attributnamen.</span><span class="sxs-lookup"><span data-stu-id="24ae4-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="24ae4-117">Weitere Informationen zu den **XmlNameTable**, finden Sie unter [Objekt Vergleich mit "XmlNameTable"](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span><span class="sxs-lookup"><span data-stu-id="24ae4-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="24ae4-118">Weitere Informationen finden Sie <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="24ae4-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24ae4-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24ae4-119">See Also</span></span>  
 [<span data-ttu-id="24ae4-120">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="24ae4-120">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
