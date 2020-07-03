---
title: Validierung eines XML-Schemas (XSD) mit "XmlSchemaSet"
description: Informationen zum Validieren von XML-Dokumenten anhand eines XML-Schemas mithilfe der Klasse „XmlSchemaSet“ in .NET
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
ms.openlocfilehash: 995323d1882da13d45cdac516518d5b67845715a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594503"
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a><span data-ttu-id="44b8e-103">Validierung eines XML-Schemas (XSD) mit „XmlSchemaSet“</span><span class="sxs-lookup"><span data-stu-id="44b8e-103">XML schema (XSD) validation with XmlSchemaSet</span></span>

<span data-ttu-id="44b8e-104">XML-Dokumente können anhand eines XSD-Schemas (XML Schema Definition Language) in einem <xref:System.Xml.Schema.XmlSchemaSet> validiert werden.</span><span class="sxs-lookup"><span data-stu-id="44b8e-104">XML documents can be validated against an XML schema definition language (XSD) schema in an <xref:System.Xml.Schema.XmlSchemaSet>.</span></span>  
  
## <a name="validate-xml-documents"></a><span data-ttu-id="44b8e-105">Validierung von XML-Dokumenten</span><span class="sxs-lookup"><span data-stu-id="44b8e-105">Validate XML documents</span></span>  
 <span data-ttu-id="44b8e-106">XML-Dokumente werden von der <xref:System.Xml.XmlReader.Create%2A>-Methode der <xref:System.Xml.XmlReader>-Klasse validiert.</span><span class="sxs-lookup"><span data-stu-id="44b8e-106">XML documents are validated by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> class.</span></span> <span data-ttu-id="44b8e-107">Wenn Sie ein XML-Dokument validieren möchten, müssen Sie ein <xref:System.Xml.XmlReaderSettings>-Objekt erstellen, das ein XSD-Schema (XML Schema Definition) enthält, mit dem das XML-Dokument validiert wird.</span><span class="sxs-lookup"><span data-stu-id="44b8e-107">To validate an XML document, construct an <xref:System.Xml.XmlReaderSettings> object that contains an XML schema definition language (XSD) schema with which to validate the XML document.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="44b8e-108">Der <xref:System.Xml.Schema>-Namespace enthält Erweiterungsmethoden, die bei Verwendung von [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) und [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) ein einfaches Validieren einer XML-Struktur anhand einer XSD-Datei ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="44b8e-108">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XSD file when using [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md) and [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span></span> <span data-ttu-id="44b8e-109">Weitere Informationen zum Validieren von XML-Dokumenten mit LINQ to XML finden Sie unter [Vorgehensweise: Überprüfen mit XSD (LINQ to XML) (C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) und [Vorgehensweise: Überprüfen mit XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="44b8e-109">For more information on validating XML documents with LINQ to XML, see [How to validate using XSD (LINQ to XML) (C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) and [How to: Validate Using XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).</span></span>
  
 <span data-ttu-id="44b8e-110">Um einem <xref:System.Xml.Schema.XmlSchemaSet> ein einzelnes Schema oder mehrere Schemas (als <xref:System.Xml.Schema.XmlSchemaSet>) hinzuzufügen, muss eines von beiden als Parameter an die <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode des <xref:System.Xml.Schema.XmlSchemaSet> übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="44b8e-110">An individual schema or a set of schemas (as an <xref:System.Xml.Schema.XmlSchemaSet>) can be added to an <xref:System.Xml.Schema.XmlSchemaSet> by passing either one as a parameter to the <xref:System.Xml.Schema.XmlSchemaSet.Add%2A> method of <xref:System.Xml.Schema.XmlSchemaSet>.</span></span> <span data-ttu-id="44b8e-111">Beim Validieren von Dokumenten muss der Namespace des Dokuments dem Zielnamespace des Schemas im Schemasatz entsprechen.</span><span class="sxs-lookup"><span data-stu-id="44b8e-111">When validating a document the target namespace of the document must match the target namespace of the schema in the schema set.</span></span>  
  
 <span data-ttu-id="44b8e-112">Es folgt ein Beispiel für ein XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="44b8e-112">The following is an example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples #5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 <span data-ttu-id="44b8e-113">Im Folgenden wird das Schema dargestellt, das das XML-Dokument validiert.</span><span class="sxs-lookup"><span data-stu-id="44b8e-113">The following is the schema that validates the example XML document.</span></span>  
  
 [!code-xml[XSDInference Examples #6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 <span data-ttu-id="44b8e-114">Im folgenden Codebeispiel wird das oben genannte Schema der <xref:System.Xml.XmlReaderSettings.Schemas%2A>-Eigenschaft des <xref:System.Xml.XmlReaderSettings>-Objekts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="44b8e-114">In the code example that follows, the schema above is added to the <xref:System.Xml.XmlReaderSettings.Schemas%2A> property of the <xref:System.Xml.XmlReaderSettings> object.</span></span> <span data-ttu-id="44b8e-115">Das <xref:System.Xml.XmlReaderSettings>-Objekt wird als Parameter an die <xref:System.Xml.XmlReader.Create%2A>-Methode des <xref:System.Xml.XmlReader>-Objekts übergeben, das das oben genannte XML-Dokument validiert.</span><span class="sxs-lookup"><span data-stu-id="44b8e-115">The <xref:System.Xml.XmlReaderSettings> object is passed as a parameter to the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object, which validates the XML document above.</span></span>  
  
 <span data-ttu-id="44b8e-116">Die <xref:System.Xml.XmlReaderSettings.ValidationType%2A>-Eigenschaft des <xref:System.Xml.XmlReaderSettings>-Objekts wird auf `Schema` festgelegt, um die Validierung des XML-Dokuments durch die <xref:System.Xml.XmlReader.Create%2A>-Methode des <xref:System.Xml.XmlReader>-Objekts zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="44b8e-116">The <xref:System.Xml.XmlReaderSettings.ValidationType%2A> property of the <xref:System.Xml.XmlReaderSettings> object is set to `Schema` to enforce validation of the XML document by the <xref:System.Xml.XmlReader.Create%2A> method of the <xref:System.Xml.XmlReader> object.</span></span> <span data-ttu-id="44b8e-117">Dem <xref:System.Xml.Schema.ValidationEventHandler>-Objekt wird ein <xref:System.Xml.XmlReaderSettings> hinzugefügt, der alle <xref:System.Xml.Schema.XmlSeverityType.Warning>- oder <xref:System.Xml.Schema.XmlSeverityType.Error>-Ereignisse behandelt, die von während der Validierung des XML-Dokuments und des Schemas gefundenen Fehlern ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="44b8e-117">A <xref:System.Xml.Schema.ValidationEventHandler> is added to the <xref:System.Xml.XmlReaderSettings> object to handle any <xref:System.Xml.Schema.XmlSeverityType.Warning> or <xref:System.Xml.Schema.XmlSeverityType.Error> events raised by errors found during the validation process of both the XML document and the schema.</span></span>  
  
 [!code-cpp[XmlSchemaSetOverall Example #1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example #1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example #1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="44b8e-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44b8e-118">See also</span></span>

- [<span data-ttu-id="44b8e-119">„XmlSchemaSet“ zur Kompilierung von Schemas</span><span class="sxs-lookup"><span data-stu-id="44b8e-119">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="44b8e-120">Arbeiten mit XML-Schemata</span><span class="sxs-lookup"><span data-stu-id="44b8e-120">Working with XML Schemas</span></span>](working-with-xml-schemas.md)
