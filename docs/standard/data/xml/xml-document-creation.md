---
title: Erstellen eines XML-Dokuments
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 877e9c62-b082-4bfb-bc5b-f47297eb30ef
ms.openlocfilehash: 577d353a30c986d198140b4596ae1a7e199ddd6e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291980"
---
# <a name="xml-document-creation"></a><span data-ttu-id="4a9df-102">Erstellen eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="4a9df-102">XML Document Creation</span></span>
<span data-ttu-id="4a9df-103">Es gibt zwei Möglichkeiten, ein XML-Dokument zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a9df-103">There are two ways to create an XML document.</span></span> <span data-ttu-id="4a9df-104">Eine besteht darin, ein **XmlDocument** ohne Parameter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a9df-104">One way is to create an **XmlDocument** with no parameters.</span></span> <span data-ttu-id="4a9df-105">Die andere Möglichkeit besteht darin, ein **XmlDocument** zu erstellen und ihm eine XmlNameTable als Parameter zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="4a9df-105">The other way is to create an **XmlDocument** and pass it an XmlNameTable as a parameter.</span></span> <span data-ttu-id="4a9df-106">Das folgende Beispiel zeigt, wie Sie ein neues, leeres **XmlDocument** ohne Parameter erstellen.</span><span class="sxs-lookup"><span data-stu-id="4a9df-106">The following example shows how to create a new, empty **XmlDocument** using no parameters.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
```  
  
 <span data-ttu-id="4a9df-107">Nachdem Sie ein Dokument erstellt haben, können Sie es mithilfe der **Load**-Methode mit Daten aus einer Zeichenfolge, einem Datenstream, einer URL, einem Textreader oder einer abgeleiteten Klasse von **XmlReader** füllen.</span><span class="sxs-lookup"><span data-stu-id="4a9df-107">Once a document is created, you can load it with data from a string, stream, URL, text reader, or an **XmlReader** derived class using the **Load** method.</span></span> <span data-ttu-id="4a9df-108">Eine weitere Lademethode, die **LoadXML**-Methode, liest XML aus einer Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="4a9df-108">There is also another load method, the **LoadXML** method, which reads XML from a string.</span></span> <span data-ttu-id="4a9df-109">Weitere Informationen zu den verschiedenen **Load**-Methoden finden Sie unter [Einlesen eines XML-Dokuments in das Dokumentobjektmodell](reading-an-xml-document-into-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="4a9df-109">For more information on the various **Load** methods, see [Reading an XML Document into the DOM](reading-an-xml-document-into-the-dom.md).</span></span>  
  
 <span data-ttu-id="4a9df-110">Es gibt eine Klasse mit dem Namen **XmlNameTable**.</span><span class="sxs-lookup"><span data-stu-id="4a9df-110">There is a class called the **XmlNameTable**.</span></span> <span data-ttu-id="4a9df-111">Sie besteht aus einer Tabelle mit atomisierten Zeichenfolgenobjekten.</span><span class="sxs-lookup"><span data-stu-id="4a9df-111">This class is a table of atomized string objects.</span></span> <span data-ttu-id="4a9df-112">Diese Tabelle ist ein effizientes Instrument, mit dem der XML-Parser das gleiche Zeichenfolgenobjekt für alle wiederkehrenden Element- und Attributnamen in einem XML-Dokument verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="4a9df-112">This table provides an efficient means for the XML parser to use the same string object for all repeated element and attribute names in an XML document.</span></span> <span data-ttu-id="4a9df-113">Eine **XmlNameTable** wird automatisch generiert, wenn ein Dokument wie oben beschrieben erstellt wird, und wird mit Attribut- und Elementnamen gefüllt, wenn das Dokument geladen wird.</span><span class="sxs-lookup"><span data-stu-id="4a9df-113">An **XmlNameTable** is automatically created when a document is created as shown above and is loaded with attribute and element names when the document is loaded.</span></span> <span data-ttu-id="4a9df-114">Wenn bereits ein Dokument mit einer Namenstabelle vorhanden ist und diese Namen in einem anderen Dokument nützlich wären, können Sie mit der **Load**-Methode ein neues Dokument erstellen, das eine **XmlNameTable** als Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a9df-114">If you already have a document with a name table, and those names would be useful in another document, you can create a new document using the **Load** method that takes an **XmlNameTable** as a parameter.</span></span> <span data-ttu-id="4a9df-115">Wenn das Dokument mit dieser Methode erstellt wird, wird die bestehende **XmlNameTable** mit allen bereits aus dem anderen Dokument geladenen Attributen und Elementen verwendet.</span><span class="sxs-lookup"><span data-stu-id="4a9df-115">When the document is created with this method, it uses the existing **XmlNameTable** with all the attributes and elements already loaded into it from the other document.</span></span> <span data-ttu-id="4a9df-116">Dies dient zum effizienten Vergleichen von Element- und Attributnamen.</span><span class="sxs-lookup"><span data-stu-id="4a9df-116">It can be used for efficiently comparing element and attribute names.</span></span> <span data-ttu-id="4a9df-117">Weitere Informationen zu **XmlNameTable** finden Sie unter [Objektvergleich mit „XmlNameTable“](object-comparison-using-xmlnametable.md).</span><span class="sxs-lookup"><span data-stu-id="4a9df-117">For more information on the **XmlNameTable**, see [Object Comparison Using XmlNameTable](object-comparison-using-xmlnametable.md).</span></span> <span data-ttu-id="4a9df-118">Weitere Informationen finden Sie unter <xref:System.Xml.XmlNameTable>.</span><span class="sxs-lookup"><span data-stu-id="4a9df-118">For reference, see <xref:System.Xml.XmlNameTable>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a9df-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a9df-119">See also</span></span>

- [<span data-ttu-id="4a9df-120">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="4a9df-120">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
