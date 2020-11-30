---
title: Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5711b225-6aa2-4e4f-9898-19f2d518ad1a
ms.openlocfilehash: 8ffd03d1a9915bade6c4d421d5fad096a4784fb8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686786"
---
# <a name="reading-xml-data-using-xpathdocument-and-xmldocument"></a><span data-ttu-id="405a8-102">Lesen von XML-Daten mithilfe von XPathDocument und XmlDocument</span><span class="sxs-lookup"><span data-stu-id="405a8-102">Reading XML Data using XPathDocument and XmlDocument</span></span>

<span data-ttu-id="405a8-103">Es gibt zwei Möglichkeiten, wie ein XML-Dokument in einem <xref:System.Xml.XPath?displayProperty=nameWithType>-Namespace gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="405a8-103">There are two ways to read an XML document in the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="405a8-104">Zum einem kann ein XML-Dokument mithilfe der schreibgeschützten <xref:System.Xml.XPath.XPathDocument>-Klasse und zum anderen mithilfe der editierbaren <xref:System.Xml.XmlDocument>-Klasse im <xref:System.Xml?displayProperty=nameWithType>-Namespace gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="405a8-104">One is to read an XML document using the read-only <xref:System.Xml.XPath.XPathDocument> class and the other is to read an XML document using the editable <xref:System.Xml.XmlDocument> class in the <xref:System.Xml?displayProperty=nameWithType> namespace.</span></span>  
  
## <a name="reading-xml-documents-using-the-xpathdocument-class"></a><span data-ttu-id="405a8-105">Lesen von XML-Dokumenten mithilfe der XPathDocument-Klasse</span><span class="sxs-lookup"><span data-stu-id="405a8-105">Reading XML Documents using the XPathDocument Class</span></span>  

 <span data-ttu-id="405a8-106">Die <xref:System.Xml.XPath.XPathDocument>-Klasse bietet eine schnelle, schreibgeschützte Darstellung eines XML-Dokuments im Speicher mithilfe des XPath-Datenmodells.</span><span class="sxs-lookup"><span data-stu-id="405a8-106">The <xref:System.Xml.XPath.XPathDocument> class provides a fast, read-only, in-memory representation of an XML document using the XPath data model.</span></span> <span data-ttu-id="405a8-107">Instanzen der <xref:System.Xml.XPath.XPathDocument>-Klasse werden mithilfe einer ihrer sechs Konstruktoren erstellt.</span><span class="sxs-lookup"><span data-stu-id="405a8-107">Instances of the <xref:System.Xml.XPath.XPathDocument> class are created using one of its six constructors.</span></span> <span data-ttu-id="405a8-108">Diese Konstruktoren ermöglichen das Lesen eines XML-Dokuments mithilfe eines der Objekte <xref:System.IO.Stream>, <xref:System.IO.TextReader> oder <xref:System.Xml.XmlReader> sowie des `string`-Pfads zu einer XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="405a8-108">These constructors allow you to read an XML document using a <xref:System.IO.Stream>, <xref:System.IO.TextReader>, or <xref:System.Xml.XmlReader> object, as well as the `string` path to an XML file.</span></span>  
  
 <span data-ttu-id="405a8-109">Im folgenden Beispiel wird die Verwendung des <xref:System.Xml.XPath.XPathDocument>-Konstruktors der `string`-Klasse zum Lesen eines XML-Dokuments veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="405a8-109">The following example illustrates using the <xref:System.Xml.XPath.XPathDocument> class's `string` constructor to read an XML document.</span></span>  
  
```vb  
Dim document As XPathDocument = New XPathDocument("books.xml")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("books.xml");  
```  
  
## <a name="reading-xml-documents-using-the-xmldocument-class"></a><span data-ttu-id="405a8-110">Lesen von XML-Dokumenten mithilfe der XmlDocument-Klasse</span><span class="sxs-lookup"><span data-stu-id="405a8-110">Reading XML Documents using the XmlDocument Class</span></span>  

 <span data-ttu-id="405a8-111">Die <xref:System.Xml.XmlDocument>-Klasse ist eine editierbare speicherresidente Darstellung eines XML-Dokuments, die das DOM Level 1 Core und das DOM Level 2 Core des W3C implementiert.</span><span class="sxs-lookup"><span data-stu-id="405a8-111">The <xref:System.Xml.XmlDocument> class is an editable in-memory representation of an XML document implementing W3C Document Object Model (DOM) Level 1 Core and Core DOM Level 2.</span></span> <span data-ttu-id="405a8-112">Instanzen der <xref:System.Xml.XmlDocument>-Klasse werden mithilfe einer ihrer drei Konstruktoren erstellt.</span><span class="sxs-lookup"><span data-stu-id="405a8-112">Instances of the <xref:System.Xml.XmlDocument> class are created using one of its three constructors.</span></span> <span data-ttu-id="405a8-113">Sie können ein neues, leeres <xref:System.Xml.XmlDocument>-Objekt erstellen, indem Sie den Konstruktor der <xref:System.Xml.XmlDocument>-Klasse ohne Parameter aufrufen.</span><span class="sxs-lookup"><span data-stu-id="405a8-113">You can create a new, empty <xref:System.Xml.XmlDocument> object by calling the <xref:System.Xml.XmlDocument> class constructor with no parameters.</span></span> <span data-ttu-id="405a8-114">Verwenden Sie nach dem Aufrufen des Konstruktors die <xref:System.Xml.XmlDocument.Load%2A>-Methode, um XML-Daten aus einem der Objekte <xref:System.Xml.XmlDocument>, <xref:System.IO.Stream> oder <xref:System.IO.TextReader> sowie aus dem <xref:System.Xml.XmlReader>-Pfad zu einer XML-Datei in das neue `string`-Objekt zu laden.</span><span class="sxs-lookup"><span data-stu-id="405a8-114">After calling the constructor, use the <xref:System.Xml.XmlDocument.Load%2A> method to load XML data into the new <xref:System.Xml.XmlDocument> object from a <xref:System.IO.Stream>, <xref:System.IO.TextReader>, or <xref:System.Xml.XmlReader> object, as well as the `string` path to an XML file.</span></span>  
  
 <span data-ttu-id="405a8-115">Im folgenden Beispiel wird die Verwendung des Konstruktors der <xref:System.Xml.XmlDocument>-Klasse ohne Parameter und die Verwendung der <xref:System.Xml.XmlDocument.Load%2A>-Methode zum Lesen eines XML-Dokuments veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="405a8-115">The following example illustrates using the <xref:System.Xml.XmlDocument> class constructor with no parameters and the <xref:System.Xml.XmlDocument.Load%2A> method to read an XML document.</span></span>  
  
```vb  
Dim document As XmlDocument = New XmlDocument()  
document.Load("books.xml")  
```  
  
```csharp  
XmlDocument document = new XmlDocument();  
document.Load("books.xml");  
```  
  
## <a name="determining-the-encoding-of-an-xml-document"></a><span data-ttu-id="405a8-116">Bestimmen der Codierung eines XML-Dokuments</span><span class="sxs-lookup"><span data-stu-id="405a8-116">Determining the Encoding of an XML Document</span></span>  

 <span data-ttu-id="405a8-117">Ein <xref:System.Xml.XmlReader>-Objekt kann, wie in den vorangehenden Abschnitten dargestellt, zum Lesen eines XML-Dokuments und zum Erstellen eines <xref:System.Xml.XPath.XPathDocument>-Objekts und eines <xref:System.Xml.XmlDocument>-Objekts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="405a8-117">An <xref:System.Xml.XmlReader> object can be used to read an XML document and to create <xref:System.Xml.XPath.XPathDocument> and <xref:System.Xml.XmlDocument> objects as shown in the previous sections.</span></span> <span data-ttu-id="405a8-118">Ein <xref:System.Xml.XmlReader>-Objekt liest jedoch u. U. nicht codierte Daten und stellt folglich keine Codierungsinformationen bereit.</span><span class="sxs-lookup"><span data-stu-id="405a8-118">However, an <xref:System.Xml.XmlReader> object may read data that is not encoded and as a result does not provide any encoding information.</span></span>  
  
 <span data-ttu-id="405a8-119">Die <xref:System.Xml.XmlTextReader>-Klasse erbt von der <xref:System.Xml.XmlReader>-Klasse, stellt mithilfe ihrer <xref:System.Xml.XmlTextReader.Encoding%2A>-Eigenschaft Codierungsinformationen bereit und kann zum Erstellen eines <xref:System.Xml.XPath.XPathDocument>-Objekts oder eines <xref:System.Xml.XmlDocument>-Objekts verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="405a8-119">The <xref:System.Xml.XmlTextReader> class inherits from the <xref:System.Xml.XmlReader> class, provides encoding information using its <xref:System.Xml.XmlTextReader.Encoding%2A> property, and can be used to create an <xref:System.Xml.XPath.XPathDocument> object or <xref:System.Xml.XmlDocument> object.</span></span>  
  
 <span data-ttu-id="405a8-120">Weitere Informationen über die von der <xref:System.Xml.XmlTextReader>-Klasse bereitgestellten Codierungsinformationen finden Sie unter der <xref:System.Xml.XmlTextReader.Encoding%2A>-Eigenschaft in der Referenzdokumentation der <xref:System.Xml.XmlTextReader>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="405a8-120">For more information about the encoding information provided by the <xref:System.Xml.XmlTextReader> class, see the <xref:System.Xml.XmlTextReader.Encoding%2A> property in the <xref:System.Xml.XmlTextReader> class reference documentation.</span></span>  
  
## <a name="creating-xpathnavigator-objects"></a><span data-ttu-id="405a8-121">Erstellen von XPathNavigator-Objekten</span><span class="sxs-lookup"><span data-stu-id="405a8-121">Creating XPathNavigator Objects</span></span>  

 <span data-ttu-id="405a8-122">Nachdem Sie ein XML-Dokument in ein <xref:System.Xml.XPath.XPathDocument>-Objekt oder ein <xref:System.Xml.XmlDocument>-Objekt gelesen haben, können Sie ein <xref:System.Xml.XPath.XPathNavigator>-Objekt zum Auswählen, Auswerten, Navigieren und in einigen Fällen zum Bearbeiten der zugrunde liegenden XML-Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="405a8-122">After you have read an XML document into either an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object, you can create an <xref:System.Xml.XPath.XPathNavigator> object to select, evaluate, navigate, and in some cases, edit the underlying XML data.</span></span>  
  
 <span data-ttu-id="405a8-123">Zusätzlich zur <xref:System.Xml.XPath.XPathDocument>-Klasse implementieren sowohl die <xref:System.Xml.XmlDocument>-Klasse als auch die <xref:System.Xml.XmlNode>-Klasse die <xref:System.Xml.XPath.IXPathNavigable>-Schnittstelle des <xref:System.Xml.XPath?displayProperty=nameWithType>-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="405a8-123">Both the <xref:System.Xml.XPath.XPathDocument> and <xref:System.Xml.XmlDocument> classes, in addition to the <xref:System.Xml.XmlNode> class, implement the <xref:System.Xml.XPath.IXPathNavigable> interface of the <xref:System.Xml.XPath?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="405a8-124">Folglich stellen alle drei Klassen eine <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A>-Methode bereit, die ein <xref:System.Xml.XPath.XPathNavigator>-Objekt zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="405a8-124">As a result, all three classes provide a <xref:System.Xml.XPath.IXPathNavigable.CreateNavigator%2A> method that returns an <xref:System.Xml.XPath.XPathNavigator> object.</span></span>  
  
### <a name="editing-xml-documents-using-the-xpathnavigator-class"></a><span data-ttu-id="405a8-125">Bearbeiten von XML-Dokumenten mithilfe der XPathNavigator-Klasse</span><span class="sxs-lookup"><span data-stu-id="405a8-125">Editing XML Documents using the XPathNavigator Class</span></span>  

 <span data-ttu-id="405a8-126">Zusätzlich zum Auswählen, Auswerten und Navigieren von XML-Daten kann die <xref:System.Xml.XPath.XPathNavigator>-Klasse in einigen Fällen auch zum Bearbeiten eines XML-Dokuments anhand des Objekts, mit dem es erstellt wurde, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="405a8-126">In addition to selecting, evaluating, and navigating XML data, the <xref:System.Xml.XPath.XPathNavigator> class can be used to edit an XML document in some cases, based on the object that created it.</span></span>  
  
 <span data-ttu-id="405a8-127">Die <xref:System.Xml.XPath.XPathDocument>-Klasse ist schreibgeschützt, während die <xref:System.Xml.XmlDocument>-Klasse bearbeitet werden kann. Daher können <xref:System.Xml.XPath.XPathNavigator>-Objekte, die auf der Grundlage eines <xref:System.Xml.XPath.XPathDocument>-Objekts erstellt wurden, nicht zur Verarbeitung eines XML-Dokuments verwendet werden, während Objekte, die auf der Grundlage eines <xref:System.Xml.XmlDocument>-Objekts erstellt wurden, für die Verarbeitung von XML-Dokumenten eingesetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="405a8-127">The <xref:System.Xml.XPath.XPathDocument> class is read-only while the <xref:System.Xml.XmlDocument> class is editable and as a result, <xref:System.Xml.XPath.XPathNavigator> objects created from an <xref:System.Xml.XPath.XPathDocument> object cannot be used to edit an XML document while those created from an <xref:System.Xml.XmlDocument> object can.</span></span> <span data-ttu-id="405a8-128">Die <xref:System.Xml.XPath.XPathDocument>-Klasse sollte nur zum Lesen von XML-Dokumenten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="405a8-128">The <xref:System.Xml.XPath.XPathDocument> class should be used to read an XML document only.</span></span> <span data-ttu-id="405a8-129">In Fällen, bei denen Sie ein XML-Dokument bearbeiten müssen oder Zugriff auf zusätzliche Funktionen benötigen, die von der <xref:System.Xml.XmlDocument>-Klasse bereitgestellt werden (z. B. Ereignisbehandlung), sollten Sie die <xref:System.Xml.XmlDocument>-Klasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="405a8-129">In cases where you need to edit an XML document, or require access to the additional functionality provided by the <xref:System.Xml.XmlDocument> class, like event handling, the <xref:System.Xml.XmlDocument> class should be used.</span></span>  
  
 <span data-ttu-id="405a8-130">Die <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Eigenschaft der <xref:System.Xml.XPath.XPathNavigator>-Klasse gibt an, ob ein <xref:System.Xml.XPath.XPathNavigator>-Objekt XML-Daten bearbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="405a8-130">The <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property of the <xref:System.Xml.XPath.XPathNavigator> class specifies if an <xref:System.Xml.XPath.XPathNavigator> object may edit XML data.</span></span>  
  
 <span data-ttu-id="405a8-131">In der folgenden Tabelle wird der Wert der <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Eigenschaft für jede Klasse beschrieben.</span><span class="sxs-lookup"><span data-stu-id="405a8-131">The following table describes the value of the <xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> property for each class.</span></span>  
  
|<span data-ttu-id="405a8-132"><xref:System.Xml.XPath.IXPathNavigable>-Implementierung</span><span class="sxs-lookup"><span data-stu-id="405a8-132"><xref:System.Xml.XPath.IXPathNavigable> Implementation</span></span>|<span data-ttu-id="405a8-133"><xref:System.Xml.XPath.XPathNavigator.CanEdit%2A>-Wert</span><span class="sxs-lookup"><span data-stu-id="405a8-133"><xref:System.Xml.XPath.XPathNavigator.CanEdit%2A> Value</span></span>|  
|--------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|<xref:System.Xml.XPath.XPathDocument>|`false`|  
|<xref:System.Xml.XmlDocument>|`true`|  
  
## <a name="see-also"></a><span data-ttu-id="405a8-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="405a8-134">See also</span></span>

- <xref:System.Xml.XmlDocument>
- <xref:System.Xml.XPath.XPathDocument>
- <xref:System.Xml.XPath.XPathNavigator>
- [<span data-ttu-id="405a8-135">Verarbeiten von XML-Daten mithilfe des XPath-Datenmodells</span><span class="sxs-lookup"><span data-stu-id="405a8-135">Process XML Data Using the XPath Data Model</span></span>](process-xml-data-using-the-xpath-data-model.md)
- [<span data-ttu-id="405a8-136">Zugreifen auf XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="405a8-136">Accessing XML Data using XPathNavigator</span></span>](accessing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="405a8-137">Bearbeiten von XML-Daten mit XPathNavigator</span><span class="sxs-lookup"><span data-stu-id="405a8-137">Editing XML Data using XPathNavigator</span></span>](editing-xml-data-using-xpathnavigator.md)
- [<span data-ttu-id="405a8-138">Schemavalidierung mithilfe von „XPathNavigator“</span><span class="sxs-lookup"><span data-stu-id="405a8-138">Schema Validation using XPathNavigator</span></span>](schema-validation-using-xpathnavigator.md)
