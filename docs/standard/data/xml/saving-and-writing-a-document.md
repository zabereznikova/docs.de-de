---
title: Speichern und Ausgeben eines Dokuments
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 097b0cb1-5743-4c3a-86ef-caf5cbe6750d
ms.openlocfilehash: 0af160b720b9eddd9e72689c920316bffdc6d21e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710218"
---
# <a name="saving-and-writing-a-document"></a><span data-ttu-id="7831b-102">Speichern und Ausgeben eines Dokuments</span><span class="sxs-lookup"><span data-stu-id="7831b-102">Saving and Writing a Document</span></span>
<span data-ttu-id="7831b-103">Ein geladenes und dann gespeichertes <xref:System.Xml.XmlDocument> kann in den folgenden Punkten vom Original abweichen:</span><span class="sxs-lookup"><span data-stu-id="7831b-103">When you load and save an <xref:System.Xml.XmlDocument>, the saved document may differ from the original in the following ways:</span></span>  
  
- <span data-ttu-id="7831b-104">Wenn die <xref:System.Xml.XmlDocument.PreserveWhitespace%2A>-Eigenschaft vor dem Aufruf der `true`-Methode auf <xref:System.Xml.XmlDocument.Save%2A> festgelegt wurde, bleibt im Dokument enthaltener Leerraum in der Ausgabe erhalten. Wenn diese Eigenschaft `false` ist, wird die Ausgabe automatisch von <xref:System.Xml.XmlDocument> eingerückt.</span><span class="sxs-lookup"><span data-stu-id="7831b-104">If the <xref:System.Xml.XmlDocument.PreserveWhitespace%2A> property is set to `true` before the <xref:System.Xml.XmlDocument.Save%2A> method is called, white space in the document is preserved in the output; if this property is `false`, <xref:System.Xml.XmlDocument> auto-indents the output.</span></span>  
  
- <span data-ttu-id="7831b-105">Der gesamte Leerraum zwischen Attributen wird zu einem einzigen Leerzeichen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="7831b-105">All the white space between attributes is reduced to a single space character.</span></span>  
  
- <span data-ttu-id="7831b-106">Leerraum zwischen Elementen wird verändert.</span><span class="sxs-lookup"><span data-stu-id="7831b-106">The white space between elements is changed.</span></span> <span data-ttu-id="7831b-107">Signifikanter Leerraum bleibt im Gegensatz zu nicht signifikantem Leerraum erhalten.</span><span class="sxs-lookup"><span data-stu-id="7831b-107">Significant white space is preserved and insignificant white space is not.</span></span> <span data-ttu-id="7831b-108">Wenn das Dokument jedoch gespeichert wird, wird **der <xref:System.Xml.XmlTextWriter> Einzugs** Modus standardmäßig verwendet, um die Ausgabe sauber zu drucken, damit Sie besser lesbar ist.</span><span class="sxs-lookup"><span data-stu-id="7831b-108">But when the document is saved, it will use the <xref:System.Xml.XmlTextWriter> **Indenting** mode by default to neatly print the output to make it more readable.</span></span>  
  
- <span data-ttu-id="7831b-109">Einfache Anführungszeichen für Attributwerte werden standardmäßig in doppelte Anführungszeichen umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="7831b-109">The quote character used around attribute values is changed to double quote by default.</span></span> <span data-ttu-id="7831b-110">Das Anführungszeichen kann mit der <xref:System.Xml.XmlTextReader.QuoteChar%2A>-Eigenschaft des <xref:System.Xml.XmlTextWriter> als einfaches oder doppeltes Anführungszeichen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="7831b-110">You can use the <xref:System.Xml.XmlTextReader.QuoteChar%2A> property on <xref:System.Xml.XmlTextWriter> to set the quote character to either double quote or single quote.</span></span>  
  
- <span data-ttu-id="7831b-111">Numerische Zeichenentitäten wie `{` werden standardmäßig erweitert.</span><span class="sxs-lookup"><span data-stu-id="7831b-111">By default, numeric character entities like `{` are expanded.</span></span>  
  
- <span data-ttu-id="7831b-112">Die Bytereihenfolgenmarkierung im Ausgangsdokument bleibt nicht erhalten.</span><span class="sxs-lookup"><span data-stu-id="7831b-112">The byte-order mark found in the input document is not preserved.</span></span> <span data-ttu-id="7831b-113">UCS-2 wird als UTF-8 gespeichert, wenn keine XML-Deklaration erstellt wird, die eine andere Codierung angibt.</span><span class="sxs-lookup"><span data-stu-id="7831b-113">UCS-2 is saved as UTF-8 unless you explicitly create an XML declaration that specifies a different encoding.</span></span>  
  
- <span data-ttu-id="7831b-114">Wenn das <xref:System.Xml.XmlDocument> als Datei oder als Stream ausgegeben wird, entspricht die Ausgabe dem Inhalt des Dokuments.</span><span class="sxs-lookup"><span data-stu-id="7831b-114">If you want to write out the <xref:System.Xml.XmlDocument> into a file or stream, the output written out is the same as the content of the document.</span></span> <span data-ttu-id="7831b-115">Eine <xref:System.Xml.XmlDeclaration> wird also nur dann ausgegeben, wenn eine solche im Dokument vorhanden ist, und die für die Ausgabe verwendete Codierung entspricht der im Deklarationsknoten angegebenen Codierung.</span><span class="sxs-lookup"><span data-stu-id="7831b-115">That is, the <xref:System.Xml.XmlDeclaration> is written out only if there is one contained in the document, and the encoding used when writing out the document is the same encoding given in the declaration node.</span></span>  
  
## <a name="writing-an-xmldeclaration"></a><span data-ttu-id="7831b-116">Schreiben einer "XmlDeclaration"</span><span class="sxs-lookup"><span data-stu-id="7831b-116">Writing an XmlDeclaration</span></span>  
 <span data-ttu-id="7831b-117">Außer der <xref:System.Xml.XmlDocument>-Methode und der <xref:System.Xml.XmlDeclaration>-Methode von <xref:System.Xml.XmlNode.OuterXml%2A> erstellen die Methoden <xref:System.Xml.XmlNode.InnerXml%2A>, <xref:System.Xml.XmlNode.WriteTo%2A> und <xref:System.Xml.XmlDocument> von <xref:System.Xml.XmlDocument.Save%2A> und <xref:System.Xml.XmlDocument.WriteContentTo%2A> eine XML-Deklaration.</span><span class="sxs-lookup"><span data-stu-id="7831b-117">The <xref:System.Xml.XmlDocument> and <xref:System.Xml.XmlDeclaration> members of <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlNode.InnerXml%2A>, and <xref:System.Xml.XmlNode.WriteTo%2A>, in addition to the <xref:System.Xml.XmlDocument> methods of <xref:System.Xml.XmlDocument.Save%2A> and <xref:System.Xml.XmlDocument.WriteContentTo%2A>, create an XML declaration.</span></span>  
  
 <span data-ttu-id="7831b-118">Bei der <xref:System.Xml.XmlDocument>-Eigenschaft und der <xref:System.Xml.XmlNode.OuterXml%2A>-Eigenschaft von <xref:System.Xml.XmlDocument.InnerXml%2A> und den Methoden <xref:System.Xml.XmlDocument.Save%2A>, <xref:System.Xml.XmlDocument.WriteTo%2A> und <xref:System.Xml.XmlDocument.WriteContentTo%2A> wird die in der XML-Deklaration ausgegebene Codierung dem <xref:System.Xml.XmlDeclaration>-Knoten entnommen.</span><span class="sxs-lookup"><span data-stu-id="7831b-118">For the <xref:System.Xml.XmlDocument> properties of <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDocument.InnerXml%2A>, and the <xref:System.Xml.XmlDocument.Save%2A>, <xref:System.Xml.XmlDocument.WriteTo%2A>, and <xref:System.Xml.XmlDocument.WriteContentTo%2A> methods, the encoding written out in the XML declaration is taken from the <xref:System.Xml.XmlDeclaration> node.</span></span> <span data-ttu-id="7831b-119">Wenn kein <xref:System.Xml.XmlDeclaration> Knoten vorhanden ist, wird <xref:System.Xml.XmlDeclaration> nicht ausgeschrieben. Wenn im <xref:System.Xml.XmlDeclaration> Knoten keine Codierung vorhanden ist, wird die Codierung nicht in die XML-Deklaration geschrieben.</span><span class="sxs-lookup"><span data-stu-id="7831b-119">If there is no <xref:System.Xml.XmlDeclaration> node, <xref:System.Xml.XmlDeclaration> is not written out. If there is no encoding in the <xref:System.Xml.XmlDeclaration> node, encoding is not written out in the XML declaration.</span></span>  
  
 <span data-ttu-id="7831b-120">Die <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType>-Methode und die <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType>-Methode schreiben immer eine <xref:System.Xml.XmlDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="7831b-120">The <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> and <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> methods always write out an <xref:System.Xml.XmlDeclaration>.</span></span> <span data-ttu-id="7831b-121">Diese Methoden übernehmen die Codierung des Writers, in den sie schreiben.</span><span class="sxs-lookup"><span data-stu-id="7831b-121">These methods take the encoding from the writer that it is writing to.</span></span> <span data-ttu-id="7831b-122">Der Codierungswert des Writers überschreibt also die Codierung im Dokument und in der <xref:System.Xml.XmlDeclaration>.</span><span class="sxs-lookup"><span data-stu-id="7831b-122">That is, the encoding value on the writer overrides the encoding on the document and in the <xref:System.Xml.XmlDeclaration>.</span></span> <span data-ttu-id="7831b-123">Bei dem folgenden Codebeispiel wird z. B. keine Codierung innerhalb der XML-Deklaration in die Ausgabedatei `out.xml` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="7831b-123">For example, the following code does not write an encoding in the XML declaration found in the output file `out.xml`.</span></span>  
  
```vb  
Dim doc As New XmlDocument()  
Dim tw As XmlTextWriter = New XmlTextWriter("out.xml", Nothing)  
doc.Load("text.xml")  
doc.Save(tw)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlTextWriter tw = new XmlTextWriter("out.xml", null);  
doc.Load("text.xml");  
doc.Save(tw);  
```  
  
 <span data-ttu-id="7831b-124">Bei der <xref:System.Xml.XmlDocument.Save%2A>-Methode wird die XML-Deklaration mit der <xref:System.Xml.XmlWriter.WriteStartDocument%2A>-Methode der <xref:System.Xml.XmlWriter>-Klasse geschrieben.</span><span class="sxs-lookup"><span data-stu-id="7831b-124">For the <xref:System.Xml.XmlDocument.Save%2A> method, the XML declaration is written out using the <xref:System.Xml.XmlWriter.WriteStartDocument%2A> method in the <xref:System.Xml.XmlWriter> class.</span></span> <span data-ttu-id="7831b-125">Ein Überschreiben der <xref:System.Xml.XmlWriter.WriteStartDocument%2A>-Methode ändert daher die Ausgabe des Dokumentanfangs.</span><span class="sxs-lookup"><span data-stu-id="7831b-125">Therefore, overwriting the <xref:System.Xml.XmlWriter.WriteStartDocument%2A> method changes how the start of the document is written.</span></span>  
  
 <span data-ttu-id="7831b-126">Wenn die <xref:System.Xml.XmlDeclaration.Encoding%2A>-Eigenschaft nicht festgelegt ist, wird für die <xref:System.Xml.XmlDeclaration> Membern von <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDeclaration.WriteTo%2A>und <xref:System.Xml.XmlNode.InnerXml%2A>keine Codierung geschrieben. Andernfalls ist die in der XML-Deklaration geschriebene Codierung mit der in der <xref:System.Xml.XmlDeclaration.Encoding%2A>-Eigenschaft gefundenen Codierung identisch.</span><span class="sxs-lookup"><span data-stu-id="7831b-126">For the <xref:System.Xml.XmlDeclaration> members of <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDeclaration.WriteTo%2A>, and <xref:System.Xml.XmlNode.InnerXml%2A>, if the <xref:System.Xml.XmlDeclaration.Encoding%2A> property is not set, no encoding is written out. Otherwise, the encoding written out in the XML declaration is the same as the encoding found in the <xref:System.Xml.XmlDeclaration.Encoding%2A> property.</span></span>  
  
## <a name="writing-document-content-using-the-outerxml-property"></a><span data-ttu-id="7831b-127">Schreiben des Dokumentinhalts mit der "OuterXml"-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7831b-127">Writing Document Content Using the OuterXml Property</span></span>  
 <span data-ttu-id="7831b-128">Die <xref:System.Xml.XmlNode.OuterXml%2A>-Eigenschaft ist eine Erweiterung von Microsoft des XML-DOM-Standards (Document Object Model) des W3C (Word Wide Web Consortium).</span><span class="sxs-lookup"><span data-stu-id="7831b-128">The <xref:System.Xml.XmlNode.OuterXml%2A> property is a Microsoft extension to the World Wide Web Consortium (W3C) XML Document Object Model (DOM) standards.</span></span> <span data-ttu-id="7831b-129">Die <xref:System.Xml.XmlNode.OuterXml%2A>-Eigenschaft wird zum Abrufen des Markups des ganzen XML-Dokuments oder eines Knotens und seiner untergeordneten Knoten verwendet.</span><span class="sxs-lookup"><span data-stu-id="7831b-129">The <xref:System.Xml.XmlNode.OuterXml%2A> property is used to get the markup of the whole XML document, or just the markup of a single node and its child nodes.</span></span> <span data-ttu-id="7831b-130"><xref:System.Xml.XmlNode.OuterXml%2A> gibt das Markup zurück, das diesen Knoten und alle ihm untergeordneten Knoten darstellt.</span><span class="sxs-lookup"><span data-stu-id="7831b-130"><xref:System.Xml.XmlNode.OuterXml%2A> returns the markup representing the given node and all its child nodes.</span></span>  
  
 <span data-ttu-id="7831b-131">Im folgenden Codebeispiel wird ein Dokument vollständig als Zeichenfolge gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7831b-131">The following code sample shows how to save a document in its entirety as a string.</span></span>  
  
```vb  
Dim mydoc As New XmlDocument()  
' Perform application needs here, like mydoc.Load("myfile");  
' Now save the entire document to a string variable called "xml".  
Dim xml As String = mydoc.OuterXml  
```  
  
```csharp  
XmlDocument mydoc = new XmlDocument();  
// Perform application needs here, like mydoc.Load("myfile");  
// Now save the entire document to a string variable called "xml".  
string xml = mydoc.OuterXml;  
```  
  
 <span data-ttu-id="7831b-132">Im folgenden Codebeispiel wird nur das Dokument-Element gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7831b-132">The following code sample shows how to save only the document element.</span></span>  
  
```vb  
' For the content of the Document Element only.  
Dim xml As String = mydoc.DocumentElement.OuterXml  
```  
  
```csharp  
// For the content of the Document Element only.  
string xml = mydoc.DocumentElement.OuterXml;  
```  
  
 <span data-ttu-id="7831b-133">Sie können dagegen die <xref:System.Xml.XmlNode.InnerText%2A>-Eigenschaft zum Speichern des Inhalts der untergeordneten Knoten verwenden.</span><span class="sxs-lookup"><span data-stu-id="7831b-133">In contrast, you can use the <xref:System.Xml.XmlNode.InnerText%2A> property if you want the content of child nodes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7831b-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7831b-134">See also</span></span>

- [<span data-ttu-id="7831b-135">XML-Dokumentobjektmodell (DOM)</span><span class="sxs-lookup"><span data-stu-id="7831b-135">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
