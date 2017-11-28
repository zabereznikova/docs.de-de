---
title: "Übersicht über die XDocument-Klasse (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 63305603-ab54-49fc-84e4-f76eecc59549
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 5dcb221dadcae934c382d20a2a93149af9541db9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xdocument-class-overview-c"></a><span data-ttu-id="92464-102">Übersicht über die XDocument-Klasse (C#)</span><span class="sxs-lookup"><span data-stu-id="92464-102">XDocument Class Overview (C#)</span></span>
<span data-ttu-id="92464-103">Dieses Thema enthält eine Einführung in die <xref:System.Xml.Linq.XDocument>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="92464-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="92464-104">Allgemeines</span><span class="sxs-lookup"><span data-stu-id="92464-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="92464-105">Die <xref:System.Xml.Linq.XDocument>-Klasse enthält die für ein gültiges XML-Dokument erforderlichen Informationen.</span><span class="sxs-lookup"><span data-stu-id="92464-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="92464-106">Dazu gehören eine XML-Deklaration, Verarbeitungsanweisungen und Kommentare.</span><span class="sxs-lookup"><span data-stu-id="92464-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="92464-107">Beachten Sie, dass Sie <xref:System.Xml.Linq.XDocument>-Objekte nur erstellen müssen, wenn Sie die spezifische Funktionalität benötigen, die von der <xref:System.Xml.Linq.XDocument>-Klasse bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="92464-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="92464-108">In vielen Fällen können Sie direkt mit <xref:System.Xml.Linq.XElement> arbeiten.</span><span class="sxs-lookup"><span data-stu-id="92464-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="92464-109">Das direkte Arbeiten mit <xref:System.Xml.Linq.XElement> ist ein einfacheres Programmiermodell.</span><span class="sxs-lookup"><span data-stu-id="92464-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="92464-110"><xref:System.Xml.Linq.XDocument> wird von <xref:System.Xml.Linq.XContainer> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="92464-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="92464-111">Deshalb kann es untergeordnete Knoten enthalten.</span><span class="sxs-lookup"><span data-stu-id="92464-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="92464-112"><xref:System.Xml.Linq.XDocument>-Objekte können aber nur einen untergeordneten <xref:System.Xml.Linq.XElement>-Knoten besitzen.</span><span class="sxs-lookup"><span data-stu-id="92464-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="92464-113">Dies spiegelt den XML-Standard wider, demzufolge in einem XML-Dokument nur ein Stammelement vorhanden sein darf.</span><span class="sxs-lookup"><span data-stu-id="92464-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="92464-114">Komponenten von "XDocument"</span><span class="sxs-lookup"><span data-stu-id="92464-114">Components of XDocument</span></span>  
 <span data-ttu-id="92464-115">Ein <xref:System.Xml.Linq.XDocument> kann die folgenden Elemente enthalten:</span><span class="sxs-lookup"><span data-stu-id="92464-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
-   <span data-ttu-id="92464-116">genau ein <xref:System.Xml.Linq.XDeclaration>-Objekt:</span><span class="sxs-lookup"><span data-stu-id="92464-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="92464-117">Mit <xref:System.Xml.Linq.XDeclaration> können Sie die wichtigen Teile einer XML-Deklaration angeben: die XML-Version, die Codierung des Dokuments und die Angabe, ob das XML-Dokument eigenständig ist.</span><span class="sxs-lookup"><span data-stu-id="92464-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
-   <span data-ttu-id="92464-118">genau ein <xref:System.Xml.Linq.XElement>-Objekt:</span><span class="sxs-lookup"><span data-stu-id="92464-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="92464-119">Dies ist der Stammknoten des XML-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="92464-119">This is the root node of the XML document.</span></span>  
  
-   <span data-ttu-id="92464-120">eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction>-Objekten:</span><span class="sxs-lookup"><span data-stu-id="92464-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="92464-121">Eine Verarbeitungsanweisung stellt der Anwendung, die das XML-Dokument verarbeitet, entsprechende Informationen zur Verarbeitung bereit.</span><span class="sxs-lookup"><span data-stu-id="92464-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
-   <span data-ttu-id="92464-122">eine beliebige Anzahl von <xref:System.Xml.Linq.XComment>-Objekten:</span><span class="sxs-lookup"><span data-stu-id="92464-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="92464-123">Die Kommentare sind dem Stammelement nebengeordnet.</span><span class="sxs-lookup"><span data-stu-id="92464-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="92464-124">Das <xref:System.Xml.Linq.XComment>-Objekt kann nicht das erste Argument in der Liste sein, da ein XML-Dokument nicht mit einem Kommentar beginnen darf.</span><span class="sxs-lookup"><span data-stu-id="92464-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
-   <span data-ttu-id="92464-125">genau ein <xref:System.Xml.Linq.XDocumentType> für die DTD</span><span class="sxs-lookup"><span data-stu-id="92464-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="92464-126">Beim Serialisieren eines <xref:System.Xml.Linq.XDocument>-Objekts enthält die Ausgabe eine XML-Deklaration. Dies gilt auch dann, wenn `XDocument.Declaration` auf `null` gesetzt ist, solange der Writer für `Writer.Settings.OmitXmlDeclaration` den Standardwert `false` festgelegt hat.</span><span class="sxs-lookup"><span data-stu-id="92464-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="92464-127">Standardmäßig legt [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] die Version auf "1.0" und die Codierung auf "utf-8" fest.</span><span class="sxs-lookup"><span data-stu-id="92464-127">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="92464-128">Verwenden von "XElement" ohne "XDocument"</span><span class="sxs-lookup"><span data-stu-id="92464-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="92464-129">Wie bereits erwähnt, ist die <xref:System.Xml.Linq.XElement>-Klasse die Hauptklasse in der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Programmierschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="92464-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface.</span></span> <span data-ttu-id="92464-130">In vielen Fällen wird es für Ihre Anwendung nicht notwendig sein, ein Dokument zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="92464-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="92464-131">Dank der <xref:System.Xml.Linq.XElement>-Klasse können Sie eine XML-Struktur erstellen, dieser Struktur andere XML-Strukturen hinzufügen, die XML-Struktur ändern und die XML-Struktur speichern.</span><span class="sxs-lookup"><span data-stu-id="92464-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="92464-132">Verwenden von "XDocument"</span><span class="sxs-lookup"><span data-stu-id="92464-132">Using XDocument</span></span>  
 <span data-ttu-id="92464-133">Zum Konstruieren eines <xref:System.Xml.Linq.XDocument> können Sie genauso die funktionale Konstruktion verwenden wie zum Konstruieren von <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="92464-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="92464-134">Der folgende Code erstellt ein <xref:System.Xml.Linq.XDocument>-Objekt und die zugehörigen in ihm enthaltenen Objekte.</span><span class="sxs-lookup"><span data-stu-id="92464-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```csharp  
XDocument d = new XDocument(  
    new XComment("This is a comment."),  
    new XProcessingInstruction("xml-stylesheet",  
        "href='mystyle.css' title='Compact' type='text/css'"),  
    new XElement("Pubs",  
        new XElement("Book",  
            new XElement("Title", "Artifacts of Roman Civilization"),  
            new XElement("Author", "Moreno, Jordao")  
        ),  
        new XElement("Book",  
            new XElement("Title", "Midieval Tools and Implements"),  
            new XElement("Author", "Gazit, Inbar")  
        )  
    ),  
    new XComment("This is another comment.")  
);  
d.Declaration = new XDeclaration("1.0", "utf-8", "true");  
Console.WriteLine(d);  
  
d.Save("test.xml");  
```  
  
 <span data-ttu-id="92464-135">Wenn Sie sich die Datei <legacyBold>test.xml</legacyBold> ansehen, erhalten Sie die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="92464-135">When you examine the file test.xml, you get the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<!--This is a comment.-->  
<?xml-stylesheet href='mystyle.css' title='Compact' type='text/css'?>  
<Pubs>  
  <Book>  
    <Title>Artifacts of Roman Civilization</Title>  
    <Author>Moreno, Jordao</Author>  
  </Book>  
  <Book>  
    <Title>Midieval Tools and Implements</Title>  
    <Author>Gazit, Inbar</Author>  
  </Book>  
</Pubs>  
<!--This is another comment.-->  
```  
  
## <a name="see-also"></a><span data-ttu-id="92464-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92464-136">See Also</span></span>  
 [<span data-ttu-id="92464-137">LINQ to XML Programming Overview (C#) (Übersicht der LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="92464-137">LINQ to XML Programming Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
