---
title: Lesen und Schreiben von XML-Schemata
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: b5757c4a-ea59-467e-ac62-be2bfe24eb77
ms.openlocfilehash: 889c5f85a2ea3fc08dadefda5509de0fcfab76ec
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710413"
---
# <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="8ff40-102">Lesen und Schreiben von XML-Schemata</span><span class="sxs-lookup"><span data-stu-id="8ff40-102">Reading and Writing XML Schemas</span></span>
<span data-ttu-id="8ff40-103">Mit der SOM-API (Schema Object Model) können XSD-Schemata (XML Schema Definition Language) aus Dateien und anderen Quellen gelesen und geschrieben werden. Außerdem können mithilfe der Klassen im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace speicherintern XML-Schemata erstellt werden, die den Strukturen entsprechen, die in der XML-Schemaempfehlung des W3C (World Wide Web Consortium) festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="8ff40-103">The Schema Object Model (SOM) API can be used to read and write XML Schema definition language (XSD) schemas from files or other sources and build XML schemas in-memory using the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation.</span></span>  
  
## <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="8ff40-104">Lesen und Schreiben von XML-Schemata</span><span class="sxs-lookup"><span data-stu-id="8ff40-104">Reading and Writing XML Schemas</span></span>  
 <span data-ttu-id="8ff40-105">Die <xref:System.Xml.Schema.XmlSchema>-Klasse stellt die <xref:System.Xml.Schema.XmlSchema.Read%2A>-Methode und die <xref:System.Xml.Schema.XmlSchema.Write%2A>-Methode bereit, mit denen XML-Schemata gelesen bzw. geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8ff40-105">The <xref:System.Xml.Schema.XmlSchema> class provides the <xref:System.Xml.Schema.XmlSchema.Read%2A> and <xref:System.Xml.Schema.XmlSchema.Write%2A> methods to read and write XML schemas.</span></span> <span data-ttu-id="8ff40-106">Mit der <xref:System.Xml.Schema.XmlSchema.Read%2A>-Methode wird ein <xref:System.Xml.Schema.XmlSchema>-Objekt zurückgegeben, das das XML-Schema darstellt, und einen optionalen <xref:System.Xml.Schema.ValidationEventHandler> als Parameter annimmt, um Schemavalidierungswarnungen und Fehler zu behandeln, die beim Lesen eines XML-Schemas auftreten.</span><span class="sxs-lookup"><span data-stu-id="8ff40-106">The <xref:System.Xml.Schema.XmlSchema.Read%2A> method returns an <xref:System.Xml.Schema.XmlSchema> object representing the XML schema and takes an optional <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to handle schema validation warnings and errors encountered while reading an XML schema.</span></span>  
  
 <span data-ttu-id="8ff40-107">Mit der <xref:System.Xml.Schema.XmlSchema.Write%2A>-Methode werden XML-Schemata in die Objekte <xref:System.IO.Stream>, <xref:System.IO.TextWriter> und <xref:System.Xml.XmlWriter> geschrieben, und ein optionales <xref:System.Xml.XmlNamespaceManager>-Objekt kann als Parameter angenommen werden.</span><span class="sxs-lookup"><span data-stu-id="8ff40-107">The <xref:System.Xml.Schema.XmlSchema.Write%2A> method writes XML schemas to <xref:System.IO.Stream>, <xref:System.IO.TextWriter> and <xref:System.Xml.XmlWriter> objects and can take an optional <xref:System.Xml.XmlNamespaceManager> object as a parameter.</span></span> <span data-ttu-id="8ff40-108">Mit einem <xref:System.Xml.XmlNamespaceManager> werden in einem XML-Schema gefundene Namespaces behandelt.</span><span class="sxs-lookup"><span data-stu-id="8ff40-108">An <xref:System.Xml.XmlNamespaceManager> is used to handle namespaces encountered in an XML schema.</span></span> <span data-ttu-id="8ff40-109">Weitere Informationen zur <xref:System.Xml.XmlNamespaceManager>-Klasse finden Sie unter [Verwalten von Namespaces in einem XML-Dokument](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="8ff40-109">For more information about the <xref:System.Xml.XmlNamespaceManager> class, see [Managing Namespaces in an XML Document](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md).</span></span>  
  
 <span data-ttu-id="8ff40-110">Im folgenden Codebeispiel werden das Lesen und Schreiben von XML-Schemata in eine bzw. aus einer Datei veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8ff40-110">The following code example illustrates reading and writing XML schemas from and to a file.</span></span> <span data-ttu-id="8ff40-111">Im Codebeispiel wird die Datei `example.xsd` verwendet und mithilfe der <xref:System.Xml.Schema.XmlSchema>`static`-Methode in ein <xref:System.Xml.Schema.XmlSchema.Read%2A>-Objekt eingelesen. Anschließend wird die Datei in die Konsole und eine neue Datei `new.xsd` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="8ff40-111">The code example takes the `example.xsd` file, reads it into an <xref:System.Xml.Schema.XmlSchema> object using the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method, and then writes the file to the console and a new `new.xsd` file.</span></span> <span data-ttu-id="8ff40-112">Im Codebeispiel wird außerdem ein <xref:System.Xml.Schema.ValidationEventHandler> als Parameter für die `static`<xref:System.Xml.Schema.XmlSchema.Read%2A>-Methode bereitgestellt, mit dem alle Schemavalidierungswarnungen und Fehler behandelt werden, die beim Lesen des XML-Schemas auftreten.</span><span class="sxs-lookup"><span data-stu-id="8ff40-112">The code example also provides a <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method to handle any schema validation warnings or errors encountered while reading the XML schema.</span></span> <span data-ttu-id="8ff40-113">Wenn der <xref:System.Xml.Schema.ValidationEventHandler> nicht angegeben ist (bzw. `null` ist), werden keine Warnungen oder Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="8ff40-113">If the <xref:System.Xml.Schema.ValidationEventHandler> is not specified (`null`), no warnings or errors are reported.</span></span>  
  
 [!code-cpp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaReadWriteExample/CPP/XmlSchemaReadWriteExample.cpp#1)]
 [!code-csharp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaReadWriteExample/CS/XmlSchemaReadWriteExample.cs#1)]
 [!code-vb[XmlSchemaReadWriteExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaReadWriteExample/VB/XmlSchemaReadWriteExample.vb#1)]  
  
 <span data-ttu-id="8ff40-114">In diesem Beispiel wird `example.xsd` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="8ff40-114">The example takes the `example.xsd` as input.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<xs:schema id="play" targetNamespace="http://tempuri.org/play.xsd" elementFormDefault="qualified" xmlns="http://tempuri.org/play.xsd" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name='myShoeSize'>  
        <xs:complexType>  
            <xs:simpleContent>  
                <xs:extension base='xs:decimal'>  
                    <xs:attribute name='sizing' type='xs:string' />  
                </xs:extension>  
            </xs:simpleContent>  
        </xs:complexType>  
    </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ff40-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ff40-115">See also</span></span>

- [<span data-ttu-id="8ff40-116">Übersicht über das XML-Schemaobjektmodell (SOM)</span><span class="sxs-lookup"><span data-stu-id="8ff40-116">XML Schema Object Model Overview</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-overview.md)
- [<span data-ttu-id="8ff40-117">Erstellen von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="8ff40-117">Building XML Schemas</span></span>](../../../../docs/standard/data/xml/building-xml-schemas.md)
- [<span data-ttu-id="8ff40-118">Durchlaufen von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="8ff40-118">Traversing XML Schemas</span></span>](../../../../docs/standard/data/xml/traversing-xml-schemas.md)
- [<span data-ttu-id="8ff40-119">Bearbeiten von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="8ff40-119">Editing XML Schemas</span></span>](../../../../docs/standard/data/xml/editing-xml-schemas.md)
- [<span data-ttu-id="8ff40-120">Einfügen oder Importieren von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="8ff40-120">Including or Importing XML Schemas</span></span>](../../../../docs/standard/data/xml/including-or-importing-xml-schemas.md)
- [<span data-ttu-id="8ff40-121">„XmlSchemaSet“ zur Kompilierung von Schemas</span><span class="sxs-lookup"><span data-stu-id="8ff40-121">XmlSchemaSet for Schema Compilation</span></span>](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="8ff40-122">Post-Schema-Compilation-Infoset</span><span class="sxs-lookup"><span data-stu-id="8ff40-122">Post-Schema Compilation Infoset</span></span>](../../../../docs/standard/data/xml/post-schema-compilation-infoset.md)
- [<span data-ttu-id="8ff40-123">Managing Namespaces in an XML Document (Verwalten von Namespaces in einem XML-Dokument)</span><span class="sxs-lookup"><span data-stu-id="8ff40-123">Managing Namespaces in an XML Document</span></span>](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)
