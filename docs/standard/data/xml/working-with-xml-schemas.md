---
title: Arbeiten mit XML-Schemata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbbcc70c-bf9a-4f6a-af72-1bab5384a187
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e21d402dce02ecb332d041f0cda651df911979ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="working-with-xml-schemas"></a><span data-ttu-id="db857-102">Arbeiten mit XML-Schemata</span><span class="sxs-lookup"><span data-stu-id="db857-102">Working with XML Schemas</span></span>
<span data-ttu-id="db857-103">Um die Struktur eines XML-Dokuments sowie dessen Elementbeziehungen, Datentypen und Inhaltseinschränkungen anzugeben, verwenden Sie eine DTD (Document Type Definition) oder ein XSD-Schema (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="db857-103">To define the structure of an XML document, as well as its element relationships, data types, and content constraints, you use a document type definition (DTD) or XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="db857-104">Obwohl ein XML-Dokument als wohlgeformt angesehen wird, wenn es alle syntaktischen Anforderungen erfüllt, die in der W3C-Empfehlung (World Wide Web Consortium) "Extensible Markup Language (XML) 1.0" definiert sind, ist es nur dann gültig, wenn es sowohl wohlgeformt ist als auch den Einschränkungen der DTD oder des Schemas entspricht.</span><span class="sxs-lookup"><span data-stu-id="db857-104">Although an XML document is considered to be well-formed if it meets all the syntactical requirements defined by the World Wide Web Consortium (W3C) Extensible Markup Language (XML) 1.0 Recommendation, it is not considered valid unless it is both well-formed and conforms to the constraints defined by its DTD or schema.</span></span> <span data-ttu-id="db857-105">Das heißt, dass alle gültigen XML-Dokumente wohlgeformt sind, jedoch nicht alle wohlgeformten XML-Dokumente gültig sein müssen.</span><span class="sxs-lookup"><span data-stu-id="db857-105">Therefore, although all valid XML documents are well-formed, not all well-formed XML documents are valid.</span></span>  
  
 <span data-ttu-id="db857-106">Weitere Informationen zu XML finden Sie unter der [W3C XML 1.0-Empfehlung](http://go.microsoft.com/fwlink/?linkid=7269).</span><span class="sxs-lookup"><span data-stu-id="db857-106">For more information about XML, see the [W3C XML 1.0 Recommendation](http://go.microsoft.com/fwlink/?linkid=7269).</span></span> <span data-ttu-id="db857-107">Weitere Informationen zum XML-Schema finden Sie unter der [W3C XML Schema Part 1: Strukturempfehlung](http://go.microsoft.com/fwlink/?linkid=48881) und [W3C XML Schema Part 2: Datatypes Recommendation](http://go.microsoft.com/fwlink/?linkid=17392) Empfehlungen.</span><span class="sxs-lookup"><span data-stu-id="db857-107">For more information about XML Schema, see the [W3C XML Schema Part 1: Structures Recommendation](http://go.microsoft.com/fwlink/?linkid=48881) and the [W3C XML Schema Part 2: Datatypes Recommendation](http://go.microsoft.com/fwlink/?linkid=17392) recommendations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db857-108">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="db857-108">In This Section</span></span>  
 [<span data-ttu-id="db857-109">XML Schema Object Model (SOM) (XML-Schemaobjektmodell (SOM))</span><span class="sxs-lookup"><span data-stu-id="db857-109">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 <span data-ttu-id="db857-110">In diesem Abschnitt wird das Schema Object Model (SOM) im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace beschrieben, das eine Reihe von Klassen zur Verfügung stellt, mit denen Sie ein XSD-Schema aus einer Datei lesen oder programmgesteuert im Speicher ein Schema erstellen können.</span><span class="sxs-lookup"><span data-stu-id="db857-110">Discusses the Schema Object Model (SOM) in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that provides a set of classes that allows you to read a Schema definition language (XSD) schema from a file or programmatically create a schema in-memory.</span></span>  
  
 [<span data-ttu-id="db857-111">"XmlSchemaSet" zur Kompilierung von Schemata</span><span class="sxs-lookup"><span data-stu-id="db857-111">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)  
 <span data-ttu-id="db857-112">In diesem Abschnitt wird die <xref:System.Xml.Schema.XmlSchemaSet>-Klasse beschrieben, die als Cache fungiert, in dem XSD-Schemata gespeichert und validiert werden können.</span><span class="sxs-lookup"><span data-stu-id="db857-112">Discusses the <xref:System.Xml.Schema.XmlSchemaSet> class that is a cache where XSD schemas can be stored and validated.</span></span>  
  
 [<span data-ttu-id="db857-113">Pushbasierte Validierung</span><span class="sxs-lookup"><span data-stu-id="db857-113">XmlSchemaValidator Push-Based Validation</span></span>](../../../../docs/standard/data/xml/xmlschemavalidator-push-based-validation.md)  
 <span data-ttu-id="db857-114">In diesem Abschnitt wird die <xref:System.Xml.Schema.XmlSchemaValidator>-Klasse beschrieben, die eine effiziente leistungsstarke Methode zum Validieren von XML-Daten anhand von XSD-Schemata in einem Push-Verfahren bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="db857-114">Discusses the <xref:System.Xml.Schema.XmlSchemaValidator> class that provides an efficient, high-performance mechanism to validate XML data against XSD schemas in a push-based manner.</span></span>  
  
 [<span data-ttu-id="db857-115">Herleiten eines XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="db857-115">Inferring an XML Schema</span></span>](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)  
 <span data-ttu-id="db857-116">In diesem Abschnitt wird das Verwenden der <xref:System.Xml.Schema.XmlSchemaInference>-Klasse zum Herleiten eines XSD-Schemas aus der Struktur eines XML-Dokuments beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db857-116">Discusses how to use the <xref:System.Xml.Schema.XmlSchemaInference> class to infer an XSD schema from the structure of an XML document.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="db857-117">Verweis</span><span class="sxs-lookup"><span data-stu-id="db857-117">Reference</span></span>  
 <span data-ttu-id="db857-118"><xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="db857-118"><xref:System.Xml.Schema.XmlSchemaSet> &#124; <xref:System.Xml.Schema.XmlSchemaInference> &#124; <xref:System.Xml.XmlReader></span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="db857-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="db857-119">Related Sections</span></span>  
 [<span data-ttu-id="db857-120">Validieren eines XML-Dokuments im DOKUMENTOBJEKTMODELL</span><span class="sxs-lookup"><span data-stu-id="db857-120">Validating an XML Document in the DOM</span></span>](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
 <span data-ttu-id="db857-121">In diesem Abschnitt wird das Validieren von XML im DOM (Document Object Model) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db857-121">Discusses how to validate the XML in the Document Object Model (DOM).</span></span> <span data-ttu-id="db857-122">Sie können das XML beim Laden in das DOM validieren, oder Sie validieren ein zuvor nicht validiertes XML-Dokument im DOM.</span><span class="sxs-lookup"><span data-stu-id="db857-122">You can validate the XML as it is loaded into the DOM, or validate a previously unvalidated XML document in the DOM.</span></span>  
  
 [<span data-ttu-id="db857-123">Schema-Validierung mit "XPathNavigator"</span><span class="sxs-lookup"><span data-stu-id="db857-123">Schema Validation using XPathNavigator</span></span>](../../../../docs/standard/data/xml/schema-validation-using-xpathnavigator.md)  
 <span data-ttu-id="db857-124">In diesem Abschnitt wird das Validieren von XML beschrieben, das mithilfe der <xref:System.Xml.XPath.XPathNavigator>-Klasse durchsucht und bearbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="db857-124">Discusses how to validate XML being navigated and edited using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>
