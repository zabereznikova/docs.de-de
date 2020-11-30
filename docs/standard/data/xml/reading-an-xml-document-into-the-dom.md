---
title: Einlesen eines XML-Dokuments in das DOM
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4fb291f-5630-49ba-a49a-5b66c3b71e49
ms.openlocfilehash: 61275e9232b3d9e516636869d7153f33133cbd03
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686864"
---
# <a name="reading-an-xml-document-into-the-dom"></a><span data-ttu-id="031b8-102">Einlesen eines XML-Dokuments in das DOM</span><span class="sxs-lookup"><span data-stu-id="031b8-102">Reading an XML Document into the DOM</span></span>

<span data-ttu-id="031b8-103">XML-Daten werden aus verschiedenen Formaten in den Speicher eingelesen.</span><span class="sxs-lookup"><span data-stu-id="031b8-103">XML information is read into memory from different formats.</span></span> <span data-ttu-id="031b8-104">Dies kann z. B. aus einer Zeichenfolge, einem Datenstream, einer URL, einem Textreader oder einer von <xref:System.Xml.XmlReader> abgeleiteten Klasse erfolgen.</span><span class="sxs-lookup"><span data-stu-id="031b8-104">It can be read from a string, stream, URL, text reader, or a class derived from the <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="031b8-105">Die <xref:System.Xml.XmlDocument.Load%2A>-Methode lädt das Dokument in den Speicher. Sie verfügt über überladene Methoden, die Daten aus den unterschiedlichen Formaten einlesen.</span><span class="sxs-lookup"><span data-stu-id="031b8-105">The <xref:System.Xml.XmlDocument.Load%2A> method brings the document into memory and has overloaded methods available to take data from each of the different formats.</span></span> <span data-ttu-id="031b8-106">Eine weitere Methode, die <xref:System.Xml.XmlDocument.LoadXml%2A>-Methode, liest XML aus einer Zeichenfolge ein.</span><span class="sxs-lookup"><span data-stu-id="031b8-106">There is also a <xref:System.Xml.XmlDocument.LoadXml%2A> method that reads XML from a string.</span></span>  
  
 <span data-ttu-id="031b8-107">Die unterschiedlichen <xref:System.Xml.XmlDocument.Load%2A>-Methoden beeinflussen, welche Knoten beim Laden des XML-DOM ( Document Object Model) erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="031b8-107">Different <xref:System.Xml.XmlDocument.Load%2A> methods affect which nodes are created when the XML Document Object Model (DOM) is loaded.</span></span> <span data-ttu-id="031b8-108">In der folgenden Tabelle werden die Unterschiede zwischen einigen <xref:System.Xml.XmlDocument.Load%2A>-Methoden sowie die zugehörigen Themen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="031b8-108">The following table lists the differences between some of the <xref:System.Xml.XmlDocument.Load%2A> methods and topics that address them.</span></span>  
  
|<span data-ttu-id="031b8-109">Betreff</span><span class="sxs-lookup"><span data-stu-id="031b8-109">Subject</span></span>|<span data-ttu-id="031b8-110">Thema</span><span class="sxs-lookup"><span data-stu-id="031b8-110">Topic</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="031b8-111">Erstellen von Leerraumknoten</span><span class="sxs-lookup"><span data-stu-id="031b8-111">Creation of white space nodes</span></span>|<span data-ttu-id="031b8-112">Das zum Laden des DOM verwendete Objekt beeinflusst die Leerraum- und die signifikanten Leerraumknoten, die im DOM erzeugt werden.</span><span class="sxs-lookup"><span data-stu-id="031b8-112">The object used to load the DOM has an affect on the white space and significant white space nodes generated in the DOM.</span></span> <span data-ttu-id="031b8-113">Weitere Informationen finden Sie unter [Behandlung von Leerräumen und signifikanten Leerräumen beim Laden des DOM](white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="031b8-113">For more information, see [White Space and Significant White Space Handling when Loading the DOM](white-space-and-significant-white-space-handling-when-loading-the-dom.md).</span></span>|  
|<span data-ttu-id="031b8-114">Laden von XML, beginnend an einem bestimmten Knoten, oder Laden des gesamten XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="031b8-114">Loading XML starting from a specific node or loading the entire XML document</span></span>|<span data-ttu-id="031b8-115">Mithilfe der <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType>-Methode können Daten aus einem bestimmten Knoten in das DOM geladen werden.</span><span class="sxs-lookup"><span data-stu-id="031b8-115">Using the <xref:System.Xml.XmlDocument.Load%2A?displayProperty=nameWithType> method data can be loaded from a specific node into the DOM.</span></span> <span data-ttu-id="031b8-116">Weitere Informationen finden Sie unter [Laden von Daten aus einem Reader](load-data-from-a-reader.md).</span><span class="sxs-lookup"><span data-stu-id="031b8-116">For more information, see [Load Data from a Reader](load-data-from-a-reader.md).</span></span>|  
|<span data-ttu-id="031b8-117">Validieren des geladenen XML</span><span class="sxs-lookup"><span data-stu-id="031b8-117">Validating the XML as it is loaded</span></span>|<span data-ttu-id="031b8-118">Die XML-Daten, die in das DOM geladen werden, können beim Laden validiert werden.</span><span class="sxs-lookup"><span data-stu-id="031b8-118">The XML data loaded into the DOM can be validated as it is loaded.</span></span> <span data-ttu-id="031b8-119">Dies erfolgt mit dem Validierungs-<xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="031b8-119">This is accomplished using a validating <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="031b8-120">Weitere Informationen zum Validieren von XML beim Ladevorgang finden Sie unter [Validieren eines XML-Dokuments im DOM](validating-an-xml-document-in-the-dom.md).</span><span class="sxs-lookup"><span data-stu-id="031b8-120">For more information about validating XML as it is loaded, see [Validating an XML Document in the DOM](validating-an-xml-document-in-the-dom.md).</span></span>|  
  
 <span data-ttu-id="031b8-121">Im folgenden Beispiel wird veranschaulicht, wie XML mithilfe der <xref:System.Xml.XmlDocument.LoadXml%2A>-Methode geladen wird, und wie die Daten anschließend in der Textdatei `data.xml` gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="031b8-121">The following example shows XML being loaded with the <xref:System.Xml.XmlDocument.LoadXml%2A> method and the data subsequently saved to a text file called `data.xml`.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Xml  
  
Public Class Sample  
  
    Public Shared Sub Main()  
        ' Create the XmlDocument.  
        Dim doc As New XmlDocument()  
        doc.LoadXml(("<book genre='novel' ISBN='1-861001-57-5'>" & _  
                    "<title>Pride And Prejudice</title>" & _  
                    "</book>"))  
        ' Save the document to a file.  
        doc.Save("data.xml")  
    End Sub 'Main  
End Class 'Sample  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
  
public class Sample  
{  
    public static void Main()  
    {  
        // Create the XmlDocument.  
        XmlDocument doc = new XmlDocument();  
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5'>" +  
                    "<title>Pride And Prejudice</title>" +  
                    "</book>");  
  
        // Save the document to a file.  
        doc.Save("data.xml");  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="031b8-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="031b8-122">See also</span></span>

- [<span data-ttu-id="031b8-123">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="031b8-123">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
