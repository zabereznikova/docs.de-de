---
title: "Übersicht über die XDocument-Klasse (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 45cb7e71-196a-47da-bfe9-7a5589db1eed
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 3f51808a64d51fb354159df1a7323ad2fc26eedc
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="xdocument-class-overview-visual-basic"></a><span data-ttu-id="815d0-102">Übersicht über die XDocument-Klasse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="815d0-102">XDocument Class Overview (Visual Basic)</span></span>
<span data-ttu-id="815d0-103">In diesem Abschnitt wird die <xref:System.Xml.Linq.XDocument>Klasse.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="815d0-103">This topic introduces the <xref:System.Xml.Linq.XDocument> class.</span></span>  
  
## <a name="overview-of-the-xdocument-class"></a><span data-ttu-id="815d0-104">Allgemeines</span><span class="sxs-lookup"><span data-stu-id="815d0-104">Overview of the XDocument class</span></span>  
 <span data-ttu-id="815d0-105">Die <xref:System.Xml.Linq.XDocument>-Klasse enthält die notwendigen Informationen für ein gültiges XML-Dokument.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="815d0-105">The <xref:System.Xml.Linq.XDocument> class contains the information necessary for a valid XML document.</span></span> <span data-ttu-id="815d0-106">Dazu gehören eine XML-Deklaration, Verarbeitungsanweisungen und Kommentare.</span><span class="sxs-lookup"><span data-stu-id="815d0-106">This includes an XML declaration, processing instructions, and comments.</span></span>  
  
 <span data-ttu-id="815d0-107">Beachten Sie, dass Sie nur erstellen, <xref:System.Xml.Linq.XDocument>Objekte, wenn Sie die spezifische Funktionalität benötigen von der <xref:System.Xml.Linq.XDocument>-Klasse</xref:System.Xml.Linq.XDocument> bereitgestellt müssen</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="815d0-107">Note that you only have to create <xref:System.Xml.Linq.XDocument> objects if you require the specific functionality provided by the <xref:System.Xml.Linq.XDocument> class.</span></span> <span data-ttu-id="815d0-108">In vielen Fällen können Sie arbeiten direkt mit <xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="815d0-108">In many circumstances, you can work directly with <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="815d0-109">Direktes Arbeiten mit <xref:System.Xml.Linq.XElement>ist ein einfacheres Programmiermodell.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="815d0-109">Working directly with <xref:System.Xml.Linq.XElement> is a simpler programming model.</span></span>  
  
 <span data-ttu-id="815d0-110"><xref:System.Xml.Linq.XDocument><xref:System.Xml.Linq.XContainer>.</xref:System.Xml.Linq.XContainer> abgeleitet ist.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="815d0-110"><xref:System.Xml.Linq.XDocument> derives from <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="815d0-111">Deshalb kann es untergeordnete Knoten enthalten.</span><span class="sxs-lookup"><span data-stu-id="815d0-111">Therefore, it can contain child nodes.</span></span> <span data-ttu-id="815d0-112">Allerdings <xref:System.Xml.Linq.XDocument>können nur ein untergeordnetes Element besitzen <xref:System.Xml.Linq.XElement>Knoten.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="815d0-112">However, <xref:System.Xml.Linq.XDocument> objects can have only one child <xref:System.Xml.Linq.XElement> node.</span></span> <span data-ttu-id="815d0-113">Dies spiegelt den XML-Standard wider, demzufolge in einem XML-Dokument nur ein Stammelement vorhanden sein darf.</span><span class="sxs-lookup"><span data-stu-id="815d0-113">This reflects the XML standard that there can be only one root element in an XML document.</span></span>  
  
## <a name="components-of-xdocument"></a><span data-ttu-id="815d0-114">Komponenten von "XDocument"</span><span class="sxs-lookup"><span data-stu-id="815d0-114">Components of XDocument</span></span>  
 <span data-ttu-id="815d0-115">Ein <xref:System.Xml.Linq.XDocument>kann die folgenden Elemente enthalten:</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="815d0-115">An <xref:System.Xml.Linq.XDocument> can contain the following elements:</span></span>  
  
-   <span data-ttu-id="815d0-116">Ein <xref:System.Xml.Linq.XDeclaration>Objekt.</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="815d0-116">One <xref:System.Xml.Linq.XDeclaration> object.</span></span> <span data-ttu-id="815d0-117"><xref:System.Xml.Linq.XDeclaration>ermöglicht es Ihnen, die wichtigen Teile einer XML-Deklaration angeben: die XML-Version, die Codierung des Dokuments, und gibt an, ob das XML-Dokument eigenständig ist.</xref:System.Xml.Linq.XDeclaration></span><span class="sxs-lookup"><span data-stu-id="815d0-117"><xref:System.Xml.Linq.XDeclaration> enables you to specify the pertinent parts of an XML declaration: the XML version, the encoding of the document, and whether the XML document is stand-alone.</span></span>  
  
-   <span data-ttu-id="815d0-118">Ein <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="815d0-118">One <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="815d0-119">Dies ist der Stammknoten des XML-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="815d0-119">This is the root node of the XML document.</span></span>  
  
-   <span data-ttu-id="815d0-120">Eine beliebige Anzahl von <xref:System.Xml.Linq.XProcessingInstruction>Objekte.</xref:System.Xml.Linq.XProcessingInstruction></span><span class="sxs-lookup"><span data-stu-id="815d0-120">Any number of <xref:System.Xml.Linq.XProcessingInstruction> objects.</span></span> <span data-ttu-id="815d0-121">Eine Verarbeitungsanweisung stellt der Anwendung, die das XML-Dokument verarbeitet, entsprechende Informationen zur Verarbeitung bereit.</span><span class="sxs-lookup"><span data-stu-id="815d0-121">A processing instruction communicates information to an application that processes the XML.</span></span>  
  
-   <span data-ttu-id="815d0-122">Eine beliebige Anzahl von <xref:System.Xml.Linq.XComment>Objekte.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="815d0-122">Any number of <xref:System.Xml.Linq.XComment> objects.</span></span> <span data-ttu-id="815d0-123">Die Kommentare sind dem Stammelement nebengeordnet.</span><span class="sxs-lookup"><span data-stu-id="815d0-123">The comments will be siblings to the root element.</span></span> <span data-ttu-id="815d0-124">Das <xref:System.Xml.Linq.XComment>Objekt darf nicht das erste Argument in der Liste sein, da nicht für ein XML-Dokument mit einem Kommentar beginnen darf.</xref:System.Xml.Linq.XComment></span><span class="sxs-lookup"><span data-stu-id="815d0-124">The <xref:System.Xml.Linq.XComment> object cannot be the first argument in the list, because it is not valid for an XML document to start with a comment.</span></span>  
  
-   <span data-ttu-id="815d0-125">Eine <xref:System.Xml.Linq.XDocumentType>für die DTD.</xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="815d0-125">One <xref:System.Xml.Linq.XDocumentType> for the DTD.</span></span>  
  
 <span data-ttu-id="815d0-126">Beim Serialisieren einer <xref:System.Xml.Linq.XDocument>, selbst wenn `XDocument.Declaration` ist `null`, haben die Ausgabe eine XML-Deklaration, wenn der Writer `Writer.Settings.OmitXmlDeclaration` festgelegt `false` (Standard).</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="815d0-126">When you serialize an <xref:System.Xml.Linq.XDocument>, even if `XDocument.Declaration` is `null`, the output will have an XML declaration if the writer has `Writer.Settings.OmitXmlDeclaration` set to `false` (the default).</span></span>  
  
 <span data-ttu-id="815d0-127">Standardmäßig legt [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] die Version auf "1.0" und die Codierung auf "utf-8" fest.</span><span class="sxs-lookup"><span data-stu-id="815d0-127">By default, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] sets the version to "1.0", and sets the encoding to "utf-8".</span></span>  
  
## <a name="using-xelement-without-xdocument"></a><span data-ttu-id="815d0-128">Verwenden von "XElement" ohne "XDocument"</span><span class="sxs-lookup"><span data-stu-id="815d0-128">Using XElement without XDocument</span></span>  
 <span data-ttu-id="815d0-129">Wie bereits erwähnt, die <xref:System.Xml.Linq.XElement>-Klasse ist die Hauptklasse in der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] Programmierschnittstelle.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="815d0-129">As previously mentioned, the <xref:System.Xml.Linq.XElement> class is the main class in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] programming interface.</span></span> <span data-ttu-id="815d0-130">In vielen Fällen wird es für Ihre Anwendung nicht notwendig sein, ein Dokument zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="815d0-130">In many cases, your application will not require that you create a document.</span></span> <span data-ttu-id="815d0-131">Mithilfe der <xref:System.Xml.Linq.XElement>-Klasse, Sie können eine XML-Struktur andere XML-Strukturen hinzufügen, ändern und die XML-Struktur und it. speichern</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="815d0-131">By using the <xref:System.Xml.Linq.XElement> class, you can create an XML tree, add other XML trees to it, modify the XML tree, and save it.</span></span>  
  
## <a name="using-xdocument"></a><span data-ttu-id="815d0-132">Verwenden von "XDocument"</span><span class="sxs-lookup"><span data-stu-id="815d0-132">Using XDocument</span></span>  
 <span data-ttu-id="815d0-133">Erstellt eine <xref:System.Xml.Linq.XDocument>, die funktionale Konstruktion wie zum Konstruieren verwenden <xref:System.Xml.Linq.XElement>Objekte.</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="815d0-133">To construct an <xref:System.Xml.Linq.XDocument>, use functional construction, just like you do to construct <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="815d0-134">Der folgende Code erstellt ein <xref:System.Xml.Linq.XDocument>-Objekt und die zugehörigen enthaltenen Objekte.</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="815d0-134">The following code creates an <xref:System.Xml.Linq.XDocument> object and its associated contained objects.</span></span>  
  
```vb  
Dim doc As XDocument = <?xml version="1.0" encoding="utf-8"?>  
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
doc.Save("test.xml")  
```  
  
 <span data-ttu-id="815d0-135">Wenn Sie sich die Datei <legacyBold>test.xml</legacyBold> ansehen, erhalten Sie die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="815d0-135">When you examine the file test.xml, you get the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="815d0-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="815d0-136">See Also</span></span>  
 [<span data-ttu-id="815d0-137">LINQ to XML-Programmierung (Übersicht) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="815d0-137">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
