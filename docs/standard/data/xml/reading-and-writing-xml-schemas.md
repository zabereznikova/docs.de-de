---
title: Lesen und Schreiben von XML-Schemata
description: Lesen und schreiben Sie in .NET Schemas in der Sprache der XML-Schemadefinition (XSD) für Dateien oder andere Quellen mit der SOM-API (Schemaobjektmodell).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
ms.assetid: b5757c4a-ea59-467e-ac62-be2bfe24eb77
ms.openlocfilehash: 7ba736272579451cf30c5e78026ffaa4186e03c9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95686851"
---
# <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="8e359-103">Lesen und Schreiben von XML-Schemata</span><span class="sxs-lookup"><span data-stu-id="8e359-103">Reading and Writing XML Schemas</span></span>

<span data-ttu-id="8e359-104">Mit der SOM-API (Schema Object Model) können XSD-Schemata (XML Schema Definition Language) aus Dateien und anderen Quellen gelesen und geschrieben werden. Außerdem können mithilfe der Klassen im <xref:System.Xml.Schema?displayProperty=nameWithType>-Namespace speicherintern XML-Schemata erstellt werden, die den Strukturen entsprechen, die in der XML-Schemaempfehlung des W3C (World Wide Web Consortium) festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="8e359-104">The Schema Object Model (SOM) API can be used to read and write XML Schema definition language (XSD) schemas from files or other sources and build XML schemas in-memory using the classes in the <xref:System.Xml.Schema?displayProperty=nameWithType> namespace that map to the structures defined in the World Wide Web Consortium (W3C) XML Schema Recommendation.</span></span>  
  
## <a name="reading-and-writing-xml-schemas"></a><span data-ttu-id="8e359-105">Lesen und Schreiben von XML-Schemata</span><span class="sxs-lookup"><span data-stu-id="8e359-105">Reading and Writing XML Schemas</span></span>  

 <span data-ttu-id="8e359-106">Die <xref:System.Xml.Schema.XmlSchema>-Klasse stellt die <xref:System.Xml.Schema.XmlSchema.Read%2A>-Methode und die <xref:System.Xml.Schema.XmlSchema.Write%2A>-Methode bereit, mit denen XML-Schemata gelesen bzw. geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8e359-106">The <xref:System.Xml.Schema.XmlSchema> class provides the <xref:System.Xml.Schema.XmlSchema.Read%2A> and <xref:System.Xml.Schema.XmlSchema.Write%2A> methods to read and write XML schemas.</span></span> <span data-ttu-id="8e359-107">Mit der <xref:System.Xml.Schema.XmlSchema.Read%2A>-Methode wird ein <xref:System.Xml.Schema.XmlSchema>-Objekt zurückgegeben, das das XML-Schema darstellt, und einen optionalen <xref:System.Xml.Schema.ValidationEventHandler> als Parameter annimmt, um Schemavalidierungswarnungen und Fehler zu behandeln, die beim Lesen eines XML-Schemas auftreten.</span><span class="sxs-lookup"><span data-stu-id="8e359-107">The <xref:System.Xml.Schema.XmlSchema.Read%2A> method returns an <xref:System.Xml.Schema.XmlSchema> object representing the XML schema and takes an optional <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to handle schema validation warnings and errors encountered while reading an XML schema.</span></span>  
  
 <span data-ttu-id="8e359-108">Mit der <xref:System.Xml.Schema.XmlSchema.Write%2A>-Methode werden XML-Schemata in die Objekte <xref:System.IO.Stream>, <xref:System.IO.TextWriter> und <xref:System.Xml.XmlWriter> geschrieben, und ein optionales <xref:System.Xml.XmlNamespaceManager>-Objekt kann als Parameter angenommen werden.</span><span class="sxs-lookup"><span data-stu-id="8e359-108">The <xref:System.Xml.Schema.XmlSchema.Write%2A> method writes XML schemas to <xref:System.IO.Stream>, <xref:System.IO.TextWriter> and <xref:System.Xml.XmlWriter> objects and can take an optional <xref:System.Xml.XmlNamespaceManager> object as a parameter.</span></span> <span data-ttu-id="8e359-109">Mit einem <xref:System.Xml.XmlNamespaceManager> werden in einem XML-Schema gefundene Namespaces behandelt.</span><span class="sxs-lookup"><span data-stu-id="8e359-109">An <xref:System.Xml.XmlNamespaceManager> is used to handle namespaces encountered in an XML schema.</span></span> <span data-ttu-id="8e359-110">Weitere Informationen zur <xref:System.Xml.XmlNamespaceManager>-Klasse finden Sie unter [Verwalten von Namespaces in einem XML-Dokument](managing-namespaces-in-an-xml-document.md).</span><span class="sxs-lookup"><span data-stu-id="8e359-110">For more information about the <xref:System.Xml.XmlNamespaceManager> class, see [Managing Namespaces in an XML Document](managing-namespaces-in-an-xml-document.md).</span></span>  
  
 <span data-ttu-id="8e359-111">Im folgenden Codebeispiel werden das Lesen und Schreiben von XML-Schemata in eine bzw. aus einer Datei veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="8e359-111">The following code example illustrates reading and writing XML schemas from and to a file.</span></span> <span data-ttu-id="8e359-112">Im Codebeispiel wird die Datei `example.xsd` verwendet und mithilfe der <xref:System.Xml.Schema.XmlSchema>`static`-Methode in ein <xref:System.Xml.Schema.XmlSchema.Read%2A>-Objekt eingelesen. Anschließend wird die Datei in die Konsole und eine neue Datei `new.xsd` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="8e359-112">The code example takes the `example.xsd` file, reads it into an <xref:System.Xml.Schema.XmlSchema> object using the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method, and then writes the file to the console and a new `new.xsd` file.</span></span> <span data-ttu-id="8e359-113">Im Codebeispiel wird außerdem ein <xref:System.Xml.Schema.ValidationEventHandler> als Parameter für die `static`<xref:System.Xml.Schema.XmlSchema.Read%2A>-Methode bereitgestellt, mit dem alle Schemavalidierungswarnungen und Fehler behandelt werden, die beim Lesen des XML-Schemas auftreten.</span><span class="sxs-lookup"><span data-stu-id="8e359-113">The code example also provides a <xref:System.Xml.Schema.ValidationEventHandler> as a parameter to the `static`<xref:System.Xml.Schema.XmlSchema.Read%2A> method to handle any schema validation warnings or errors encountered while reading the XML schema.</span></span> <span data-ttu-id="8e359-114">Wenn der <xref:System.Xml.Schema.ValidationEventHandler> nicht angegeben ist (bzw. `null` ist), werden keine Warnungen oder Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="8e359-114">If the <xref:System.Xml.Schema.ValidationEventHandler> is not specified (`null`), no warnings or errors are reported.</span></span>  
  
 [!code-cpp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaReadWriteExample/CPP/XmlSchemaReadWriteExample.cpp#1)]
 [!code-csharp[XmlSchemaReadWriteExample#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaReadWriteExample/CS/XmlSchemaReadWriteExample.cs#1)]
 [!code-vb[XmlSchemaReadWriteExample#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaReadWriteExample/VB/XmlSchemaReadWriteExample.vb#1)]  
  
 <span data-ttu-id="8e359-115">In diesem Beispiel wird `example.xsd` als Eingabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e359-115">The example takes the `example.xsd` as input.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8e359-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e359-116">See also</span></span>

- [<span data-ttu-id="8e359-117">Übersicht über das XML-Schemaobjektmodell (SOM)</span><span class="sxs-lookup"><span data-stu-id="8e359-117">XML Schema Object Model Overview</span></span>](xml-schema-object-model-overview.md)
- [<span data-ttu-id="8e359-118">Erstellen von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="8e359-118">Building XML Schemas</span></span>](building-xml-schemas.md)
- [<span data-ttu-id="8e359-119">Durchlaufen von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="8e359-119">Traversing XML Schemas</span></span>](traversing-xml-schemas.md)
- [<span data-ttu-id="8e359-120">Bearbeiten von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="8e359-120">Editing XML Schemas</span></span>](editing-xml-schemas.md)
- [<span data-ttu-id="8e359-121">Einfügen oder Importieren von XML-Schemas</span><span class="sxs-lookup"><span data-stu-id="8e359-121">Including or Importing XML Schemas</span></span>](including-or-importing-xml-schemas.md)
- [<span data-ttu-id="8e359-122">„XmlSchemaSet“ zur Kompilierung von Schemas</span><span class="sxs-lookup"><span data-stu-id="8e359-122">XmlSchemaSet for Schema Compilation</span></span>](xmlschemaset-for-schema-compilation.md)
- [<span data-ttu-id="8e359-123">Post-Schema-Compilation-Infoset</span><span class="sxs-lookup"><span data-stu-id="8e359-123">Post-Schema Compilation Infoset</span></span>](post-schema-compilation-infoset.md)
- [<span data-ttu-id="8e359-124">Managing Namespaces in an XML Document (Verwalten von Namespaces in einem XML-Dokument)</span><span class="sxs-lookup"><span data-stu-id="8e359-124">Managing Namespaces in an XML Document</span></span>](managing-namespaces-in-an-xml-document.md)
