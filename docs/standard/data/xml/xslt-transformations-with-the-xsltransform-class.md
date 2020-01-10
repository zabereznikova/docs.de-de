---
title: XSLT-Transformationen mit der XslTransform-Klasse
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 500335af-f9b5-413b-968a-e6d9a824478c
ms.openlocfilehash: 5f670fa5e83d1802496c0cc6972a7e3af7cae374
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709646"
---
# <a name="xslt-transformations-with-the-xsltransform-class"></a><span data-ttu-id="2ed5e-102">XSLT-Transformationen mit der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="2ed5e-102">XSLT Transformations with the XslTransform Class</span></span>

> [!NOTE]
> <span data-ttu-id="2ed5e-103">Die <xref:System.Xml.Xsl.XslTransform>-Klasse ist in .NET Framework 2.0 veraltet.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-103">The <xref:System.Xml.Xsl.XslTransform> class is obsolete in the .NET Framework 2.0.</span></span> <span data-ttu-id="2ed5e-104">Mithilfe der <xref:System.Xml.Xsl.XslCompiledTransform>-Klasse können Sie XSLT-Transformationen (Extensible Stylesheet Language for Transformations) vornehmen.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-104">You can perform Extensible Stylesheet Language for Transformations (XSLT) transformations using the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span> <span data-ttu-id="2ed5e-105">Weitere Informationen finden Sie unter [Verwenden der XslCompiledTransform-Klasse](using-the-xslcompiledtransform-class.md) und [Migrieren von der XslTransform-Klasse](migrating-from-the-xsltransform-class.md).</span><span class="sxs-lookup"><span data-stu-id="2ed5e-105">See [Using the XslCompiledTransform Class](using-the-xslcompiledtransform-class.md) and [Migrating From the XslTransform Class](migrating-from-the-xsltransform-class.md) for more information.</span></span>

<span data-ttu-id="2ed5e-106">Zweck der XSLT ist es, den Inhalt eines XML-Quelldokuments in ein anderes Dokument zu transformieren, das ein anderes Format oder eine andere Struktur aufweist (beispielsweise kann XML für die Verwendung in einer Website in HTML transformiert werden, oder aber in ein Dokument, das nur die Felder enthält, die von einer Anwendung benötigt werden).</span><span class="sxs-lookup"><span data-stu-id="2ed5e-106">The goal of the XSLT is to transform the content of a source XML document into another document that is different in format or structure (for example, to transform XML into HTML for use on a Web site or to transform it into a document that contains only the fields required by an application).</span></span> <span data-ttu-id="2ed5e-107">Dieser Transformationsprozess wird in der W3C-Empfehlung (W3C = World Wide Web Consortium) zur [XSLT-Version 1.0](https://www.w3.org/TR/1999/REC-xslt-19991116) angegeben.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-107">This transformation process is specified by the World Wide Web Consortium (W3C)[XSLT version 1.0 recommendation](https://www.w3.org/TR/1999/REC-xslt-19991116).</span></span> <span data-ttu-id="2ed5e-108">In .NET Framework ist die <xref:System.Xml.Xsl.XslTransform>-Klasse im <xref:System.Xml.Xsl>-Namespace der XSLT-Prozessor, der die Funktionen dieser Spezifikation implementiert.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-108">In the .NET Framework, the <xref:System.Xml.Xsl.XslTransform> class, found in the <xref:System.Xml.Xsl> namespace, is the XSLT processor that implements the functionality of this specification.</span></span> <span data-ttu-id="2ed5e-109">Einige wenige Funktionen aus der Empfehlung des W3C zu XSLT, Version 1.0, die nicht implementiert wurden, sind in [Ausgaben aus XslTransform](outputs-from-an-xsltransform.md) aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-109">There are a small number of features that have not been implemented from the W3C XSLT 1.0 recommendation, listed in [Outputs from an XslTransform](outputs-from-an-xsltransform.md).</span></span> <span data-ttu-id="2ed5e-110">In der folgenden Abbildung ist die Transformationsarchitektur von .NET Framework dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-110">The following figure shows the transformation architecture of the .NET Framework.</span></span>

## <a name="overview"></a><span data-ttu-id="2ed5e-111">Übersicht über</span><span class="sxs-lookup"><span data-stu-id="2ed5e-111">Overview</span></span>

![Diagramm der XSLT-Transformationsarchitektur](./media/xslt-transformations-with-the-xsltransform-class/xslt-transformation-architecture.gif) 

<span data-ttu-id="2ed5e-113">Die XSLT-Empfehlung verwendet XPath (XML Path Language) zum Auswählen von Teilen eines XML-Dokuments, wobei XPath eine Abfragesprache ist, die zum Navigieren in Knoten einer Dokumentstruktur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-113">The XSLT recommendation uses XML Path Language (XPath) to select parts of an XML document, where XPath is a query language used to navigate nodes of a document tree.</span></span> <span data-ttu-id="2ed5e-114">Wie in der Abbildung gezeigt, wird die .NET Framework-Implementierung von XPath zum Auswählen von XML-Teilen verwendet, die in mehreren Klassen gespeichert sind, z. B. <xref:System.Xml.XmlDocument>, <xref:System.Xml.XmlDataDocument> und <xref:System.Xml.XPath.XPathDocument>.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-114">As shown in the diagram, the .NET Framework implementation of XPath is used to select parts of XML stored in several classes, such as an <xref:System.Xml.XmlDocument>, an <xref:System.Xml.XmlDataDocument>, and an <xref:System.Xml.XPath.XPathDocument>.</span></span> <span data-ttu-id="2ed5e-115">Ein <xref:System.Xml.XPath.XPathDocument> ist ein optimierter XSLT-Datenspeicher, der bei Verwendung zusammen mit <xref:System.Xml.Xsl.XslTransform> leistungsfähige XSLT-Transformationen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-115">An <xref:System.Xml.XPath.XPathDocument> is an optimized XSLT data store, and when used with <xref:System.Xml.Xsl.XslTransform>, it provides XSLT transformations with good performance.</span></span>

<span data-ttu-id="2ed5e-116">In der folgenden Tabelle werden Klassen aufgelistet, die beim Arbeiten mit <xref:System.Xml.Xsl.XslTransform> und XPath und deren Funktionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-116">The following table list commonly uses classes when working with <xref:System.Xml.Xsl.XslTransform> and XPath and their function.</span></span>

|<span data-ttu-id="2ed5e-117">Klasse oder Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ed5e-117">Class or Interface</span></span>|<span data-ttu-id="2ed5e-118">Funktion</span><span class="sxs-lookup"><span data-stu-id="2ed5e-118">Function</span></span>|
|------------------------|--------------|
|<xref:System.Xml.XPath.XPathNavigator>|<span data-ttu-id="2ed5e-119">Eine API, die ein Cursormodell für die Navigation in einem Speicher bereitstellt und XPath-Abfragen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-119">It is an API that provides a cursor style model for navigating over a store, along with XPath query support.</span></span> <span data-ttu-id="2ed5e-120">Sie ermöglicht keine Bearbeitung des zugrunde liegenden Speichers.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-120">It does not provide editing of the underlying store.</span></span> <span data-ttu-id="2ed5e-121">Verwenden Sie zum Bearbeiten die <xref:System.Xml.XmlDocument>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-121">For editing, use the <xref:System.Xml.XmlDocument> class.</span></span>|
|<xref:System.Xml.XPath.IXPathNavigable>|<span data-ttu-id="2ed5e-122">Eine Schnittstelle, die einem `CreateNavigator` für den Speicher eine <xref:System.Xml.XPath.XPathNavigator>-Methode bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-122">It is an interface that provides a `CreateNavigator` method to an <xref:System.Xml.XPath.XPathNavigator> for the store.</span></span>|
|<xref:System.Xml.XmlDocument>|<span data-ttu-id="2ed5e-123">Ermöglicht die Bearbeitung dieses Dokuments.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-123">It enables editing of this document.</span></span> <span data-ttu-id="2ed5e-124">Implementiert <xref:System.Xml.XPath.IXPathNavigable> und ermöglicht so Dokumentbearbeitungen, bei denen nachfolgend XSLT-Transformationen benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-124">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing document-editing scenarios where XSLT transformations are subsequently required.</span></span> <span data-ttu-id="2ed5e-125">Weitere Informationen finden Sie unter [XmlDocument-Eingaben in XslTransform](xmldocument-input-to-xsltransform.md).</span><span class="sxs-lookup"><span data-stu-id="2ed5e-125">For more information, see [XmlDocument Input to XslTransform](xmldocument-input-to-xsltransform.md).</span></span>|
|<xref:System.Xml.XmlDataDocument>|<span data-ttu-id="2ed5e-126">Wird aus dem <xref:System.Xml.XmlDocument> abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-126">It is derived from the <xref:System.Xml.XmlDocument>.</span></span> <span data-ttu-id="2ed5e-127">Stellt eine Brücke zwischen XML und den relationalen Daten her. Dazu wird ein <xref:System.Data.DataSet> verwendet, um die Speicherung von strukturierten Daten innerhalb des XML-Dokuments gemäß festgelegten Zuordnungen für das <xref:System.Data.DataSet> zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-127">It bridges the relational and XML worlds by using a <xref:System.Data.DataSet> to optimize storage of structured data within the XML document according to specified mappings on the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="2ed5e-128">Implementiert <xref:System.Xml.XPath.IXPathNavigable>, sodass XSLT-Transformationen über relationale Daten ausgeführt werden können, die aus einer Datenbank abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-128">It implements <xref:System.Xml.XPath.IXPathNavigable>, allowing scenarios where XSLT transformations can be performed over relational data retrieved from a database.</span></span> <span data-ttu-id="2ed5e-129">Weitere Informationen finden Sie unter [XML-Integration mit relationalen Daten und ADO.NET](xml-integration-with-relational-data-and-adonet.md).</span><span class="sxs-lookup"><span data-stu-id="2ed5e-129">For more information, see [XML Integration with Relational Data and ADO.NET](xml-integration-with-relational-data-and-adonet.md).</span></span>|
|<xref:System.Xml.XPath.XPathDocument>|<span data-ttu-id="2ed5e-130">Diese Klasse ist für die <xref:System.Xml.Xsl.XslTransform>-Verarbeitung und für XPath-Abfragen optimiert. Sie stellt einen sehr leistungsfähigen schreibgeschützten Zwischenspeicher bereit.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-130">This class is optimized for <xref:System.Xml.Xsl.XslTransform> processing and XPath queries, and it provides a read-only high performance cache.</span></span> <span data-ttu-id="2ed5e-131">Implementiert <xref:System.Xml.XPath.IXPathNavigable> und ist der bevorzugte Speicher für XSLT-Transformationen.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-131">It implements <xref:System.Xml.XPath.IXPathNavigable> and is the preferred store to use for XSLT transformations.</span></span>|
|<xref:System.Xml.XPath.XPathNodeIterator>|<span data-ttu-id="2ed5e-132">Ermöglicht Navigation über XPath-Knotengruppen.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-132">It provides navigation over XPath node sets.</span></span> <span data-ttu-id="2ed5e-133">Alle XPath-Auswahlmethoden für den <xref:System.Xml.XPath.XPathNavigator> geben einen <xref:System.Xml.XPath.XPathNodeIterator> zurück.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-133">All XPath selection methods on the <xref:System.Xml.XPath.XPathNavigator> return an <xref:System.Xml.XPath.XPathNodeIterator>.</span></span> <span data-ttu-id="2ed5e-134">Mehrere <xref:System.Xml.XPath.XPathNodeIterator>-Objekte können für den gleichen Speicher erstellt werden, wobei jedes eine ausgewählte Knotengruppe darstellt.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-134">Multiple <xref:System.Xml.XPath.XPathNodeIterator> objects can be created over the same store, each representing a selected set of nodes.</span></span>|

## <a name="msxml-xslt-extensions"></a><span data-ttu-id="2ed5e-135">MSXML-XSLT-Erweiterungen</span><span class="sxs-lookup"><span data-stu-id="2ed5e-135">MSXML XSLT Extensions</span></span>

<span data-ttu-id="2ed5e-136">Die Funktionen `msxsl:script` und `msxsl:node-set` sind die einzigen XSLT-Erweiterungen von MSXML (Microsoft XML Core Services), die von der <xref:System.Xml.Xsl.XslTransform>-Klasse unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-136">The `msxsl:script` and `msxsl:node-set` functions are the only Microsoft XML Core Services (MSXML) XSLT extensions supported by the <xref:System.Xml.Xsl.XslTransform> class.</span></span>

## <a name="example"></a><span data-ttu-id="2ed5e-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2ed5e-137">Example</span></span>

<span data-ttu-id="2ed5e-138">Das folgende Codebeispiel lädt ein XSLT-Stylesheet, liest eine Datei mit dem Namen mydata.xml in ein <xref:System.Xml.XPath.XPathDocument> ein und transformiert die Daten für eine fiktive Datei mit dem Namen myStyleSheet.xsl, wobei die formatierte Ausgabe an die Konsole gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ed5e-138">The following code example loads an XSLT style sheet, reads a file called mydata.xml into an <xref:System.Xml.XPath.XPathDocument>, and performs a transformation on the data on a fictitious file called myStyleSheet.xsl, sending the formatted output to the console.</span></span>

```vb
Imports System.IO
Imports System.Xml
Imports System.Xml.XPath
Imports System.Xml.Xsl

Public Class Sample
    Private filename As [String] = "mydata.xml"
    Private stylesheet As [String] = "myStyleSheet.xsl"

    Public Shared Sub Main()
        Dim xslt As New XslTransform()
        xslt.Load(stylesheet)
        Dim xpathdocument As New XPathDocument(filename)
        Dim writer As New XmlTextWriter(Console.Out)
        writer.Formatting = Formatting.Indented

        xslt.Transform(xpathdocument, Nothing, writer, Nothing)
    End Sub 'Main
End Class 'Sample
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.XPath;
using System.Xml.Xsl;

public class Sample 
{
    private const String filename = "mydata.xml";
    private const String stylesheet = "myStyleSheet.xsl";

    public static void Main()
    {
        XslTransform xslt = new XslTransform();
        xslt.Load(stylesheet);
        XPathDocument xpathdocument = new XPathDocument(filename);
        XmlTextWriter writer = new XmlTextWriter(Console.Out);
        writer.Formatting = Formatting.Indented;

        xslt.Transform(xpathdocument, null, writer, null);
    }
}
```

## <a name="see-also"></a><span data-ttu-id="2ed5e-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ed5e-139">See also</span></span>

- <xref:System.Xml.Xsl.XslTransform>
- [<span data-ttu-id="2ed5e-140">Implementierung des XSLT-Prozessors durch die XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="2ed5e-140">XslTransform Class Implements the XSLT Processor</span></span>](xsltransform-class-implements-the-xslt-processor.md)
- [<span data-ttu-id="2ed5e-141">Implementierung von freigegebenen Verhaltensweisen in der XslTransform-Klasse</span><span class="sxs-lookup"><span data-stu-id="2ed5e-141">Implementation of Discretionary Behaviors in the XslTransform Class</span></span>](implementation-of-discretionary-behaviors-in-the-xsltransform-class.md)
- [<span data-ttu-id="2ed5e-142">„XPathNavigator“ in Transformationen</span><span class="sxs-lookup"><span data-stu-id="2ed5e-142">XPathNavigator in Transformations</span></span>](xpathnavigator-in-transformations.md)
- [<span data-ttu-id="2ed5e-143">„XPathNodeIterator“ in Transformationen</span><span class="sxs-lookup"><span data-stu-id="2ed5e-143">XPathNodeIterator in Transformations</span></span>](xpathnodeiterator-in-transformations.md)
- [<span data-ttu-id="2ed5e-144">XPathDocument-Eingaben in XslTransform</span><span class="sxs-lookup"><span data-stu-id="2ed5e-144">XPathDocument Input to XslTransform</span></span>](xpathdocument-input-to-xsltransform.md)
- [<span data-ttu-id="2ed5e-145">XmlDataDocument-Eingaben in „XslTransform“</span><span class="sxs-lookup"><span data-stu-id="2ed5e-145">XmlDataDocument Input to XslTransform</span></span>](xmldatadocument-input-to-xsltransform.md)
- [<span data-ttu-id="2ed5e-146">XmlDocument-Eingaben in „XslTransform“</span><span class="sxs-lookup"><span data-stu-id="2ed5e-146">XmlDocument Input to XslTransform</span></span>](xmldocument-input-to-xsltransform.md)
