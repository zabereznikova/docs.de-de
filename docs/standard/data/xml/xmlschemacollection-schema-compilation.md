---
title: Schemakompilierung mit "XmlSchemaCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 901c3fdc8fdc80cc7c3bf13170646de857a5e009
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="xmlschemacollection-schema-compilation"></a><span data-ttu-id="f4651-102">Schemakompilierung mit "XmlSchemaCollection"</span><span class="sxs-lookup"><span data-stu-id="f4651-102">XmlSchemaCollection Schema Compilation</span></span>
<span data-ttu-id="f4651-103">Die **"XmlSchemaCollection"** ist ein Cache oder die Bibliothek, wo Schemas für XML-Data Reduced (XDR) und XML Schema Definition Language (XSD) gespeichert und validiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f4651-103">The **XmlSchemaCollection** is a cache or library where XML-Data Reduced (XDR) and XML Schema definition language (XSD) schemas can be stored and validated.</span></span> <span data-ttu-id="f4651-104">**Das XmlSchemaCollection-Objekt** verbessert die Leistung durch Zwischenspeichern der Schemata im Arbeitsspeicher anstatt aus einer Datei oder eine URL auf Sie zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f4651-104">**XmlSchemaCollection** improves performance by caching schemas in memory instead of accessing them from a file or URL.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4651-105">Obwohl die **"XmlSchemaCollection"** Klasse speichert XDR-Schemas und XML-Schemas, jede Methode oder Eigenschaft, die akzeptiert bzw. zurückgibt ein **XmlSchema** Objekt unterstützt nur die XML-Schemas.</span><span class="sxs-lookup"><span data-stu-id="f4651-105">Although the **XmlSchemaCollection** class stores both XDR schemas and XML Schemas, any method and property that takes or returns an **XmlSchema** object supports XML Schemas only.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f4651-106">Die <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse ist veraltet und wurde durch die <xref:System.Xml.Schema.XmlSchemaSet>-Klasse ersetzt.</span><span class="sxs-lookup"><span data-stu-id="f4651-106">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="f4651-107">Weitere Informationen zu den <xref:System.Xml.Schema.XmlSchemaSet> Klasse finden Sie unter ["XmlSchemaSet" zur Kompilierung von Schemata](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="f4651-107">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span></span>  
  
## <a name="add-schemas-to-the-collection"></a><span data-ttu-id="f4651-108">Hinzufügen von Schemata zur Auflistung</span><span class="sxs-lookup"><span data-stu-id="f4651-108">Add Schemas to the Collection</span></span>  
 <span data-ttu-id="f4651-109">Schemas werden geladen, um die Auflistung mit den **hinzufügen** Methode **"XmlSchemaCollection"**, zu diesem Zeitpunkt das Schema einem Namespace-URI zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f4651-109">Schemas are loaded to the collection using the **Add** method of **XmlSchemaCollection**, at which time the schema is associated with a namespace URI.</span></span> <span data-ttu-id="f4651-110">Bei XML-Schemata ist der Namespace-URI normalerweise der Zielnamespace des Schemas.</span><span class="sxs-lookup"><span data-stu-id="f4651-110">For XML Schemas, the namespace URI will typically be the target namespace for the schema.</span></span> <span data-ttu-id="f4651-111">Bei XDR-Schemata ist der Namespace-URI der Namespace, der angegeben wird, wenn ein Schema der Auflistung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="f4651-111">For XDR schemas, the namespace URI is the namespace specified when the schema was added to the collection.</span></span>  
  
## <a name="check-for-a-schema-in-the-collection"></a><span data-ttu-id="f4651-112">Suche nach einem Schema in der Auflistung</span><span class="sxs-lookup"><span data-stu-id="f4651-112">Check for a Schema in the Collection</span></span>  
 <span data-ttu-id="f4651-113">Sie können überprüfen, um festzustellen, ob ein Schema in der Auflistung, mithilfe befindet der **Contains** Methode.</span><span class="sxs-lookup"><span data-stu-id="f4651-113">You can check to see if a schema is in the collection by using the **Contains** method.</span></span> <span data-ttu-id="f4651-114">Die **Contains** -Methode übernimmt entweder ein **XmlSchema** Objekts (nur XML-Schemas) oder eine Zeichenfolge, die den Namespace-URI repräsentiert (bei XML- und XDR-Schemas) Schema zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f4651-114">The **Contains** method takes either an **XmlSchema** object (for XML Schemas only) or a string representing the namespace URI associated with the schema (for XML Schemas and XDR schemas).</span></span>  
  
## <a name="retrieve-a-schema-from-the-collection"></a><span data-ttu-id="f4651-115">Abrufen eines Schemas aus der Auflistung</span><span class="sxs-lookup"><span data-stu-id="f4651-115">Retrieve a Schema from the Collection</span></span>  
 <span data-ttu-id="f4651-116">Sie können ein Schema aus der Auflistung abrufen, indem Sie mit der **Element** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f4651-116">You can retrieve a schema from the collection by using the **Item** property.</span></span> <span data-ttu-id="f4651-117">Die **Element** Eigenschaft nimmt eine Zeichenfolge, die den Namespace-URI-Schema, normalerweise den Zielnamespace zugeordnet darstellt, und gibt eine **XmlSchema** Objekt.</span><span class="sxs-lookup"><span data-stu-id="f4651-117">The **Item** property takes a string representing the namespace URI associated with the schema, typically its target namespace, and returns an **XmlSchema** object.</span></span> <span data-ttu-id="f4651-118">Die **Element** Eigenschaft gilt nur für XML-Schemas.</span><span class="sxs-lookup"><span data-stu-id="f4651-118">The **Item** property applies to XML Schemas only.</span></span> <span data-ttu-id="f4651-119">Der Rückgabewert ist bei XDR-Schemata immer ein NULL-Verweis, da diese kein Objektmodell zur Verfügung haben.</span><span class="sxs-lookup"><span data-stu-id="f4651-119">The return value is always a null reference for XDR schemas because they do not have an object model available.</span></span>  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a><span data-ttu-id="f4651-120">Validieren von XML-Dokumenten mit "XmlSchemaCollection"</span><span class="sxs-lookup"><span data-stu-id="f4651-120">Validate XML Documents Using XmlSchemaCollection</span></span>  
 <span data-ttu-id="f4651-121">Können Sie überprüfen, ein XML-Instanzdokument wird mithilfe einer **"XmlSchemaCollection"** durch das Erstellen der **"XmlSchemaCollection"** Objekt, Ihre Schemas zur Auflistung hinzufügen und Festlegen der **Schemas**  Eigenschaft auf die **XmlValidatingReader** um die erstellte **"XmlSchemaCollection"** auf die **XmlValidatingReader**.</span><span class="sxs-lookup"><span data-stu-id="f4651-121">You can validate an XML instance document using an **XmlSchemaCollection** by creating the **XmlSchemaCollection** object, adding your schemas to the collection, and setting the **Schemas** property on the **XmlValidatingReader** to assign the created **XmlSchemaCollection** to the **XmlValidatingReader**.</span></span>  
  
### <a name="improved-performance"></a><span data-ttu-id="f4651-122">Leistungssteigerung</span><span class="sxs-lookup"><span data-stu-id="f4651-122">Improved Performance</span></span>  
 <span data-ttu-id="f4651-123">Es wird empfohlen, wenn Sie mehr als ein Dokument anhand desselben Schemas überprüfen, verwenden Sie die **"XmlSchemaCollection"** , da es sich um eine bessere Leistung bietet, indem Schemata im Arbeitsspeicher zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="f4651-123">It is recommended, if you are validating more than one document against the same schema, that you use the **XmlSchemaCollection** because it provides better performance by caching schemas in memory.</span></span>  
  
 <span data-ttu-id="f4651-124">Das folgende Codebeispiel erstellt die **"XmlSchemaCollection"** Objekt, fügt der Auflistung Schemas hinzu und legt sie fest der **Schemas** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f4651-124">The following code example creates the **XmlSchemaCollection** object, adds schemas to the collection, and sets the **Schemas** property.</span></span>  
  
```vb  
Dim tr as XmlTextReader = new XmlTextReader("Books.xml")  
Dim vr as XmlValidatingReader = new XmlValidatingReader(tr)  
Dim xsc as XmlSchemaCollection = new XmlSchemaCollection  
xsc.Add("urn:bookstore-schema", "Books.xsd")  
vr.Schemas.Add(xsc)  
```  
  
```csharp  
XmlTextReader tr = new XmlTextReader("Books.xml");  
XmlValidatingReader vr = new XmlValidatingReader(tr);  
XmlSchemaCollection xsc = new XmlSchemaCollection();  
xsc.Add("urn:bookstore-schema", "Books.xsd");    
vr.Schemas.Add(xsc);  
```  
  
## <a name="see-also"></a><span data-ttu-id="f4651-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f4651-125">See Also</span></span>  
 [<span data-ttu-id="f4651-126">XDR-Validierung mit "XmlSchemaCollection"</span><span class="sxs-lookup"><span data-stu-id="f4651-126">XDR Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)  
 [<span data-ttu-id="f4651-127">Validierung von XML-Schemas (XSD) mit "XmlSchemaCollection"</span><span class="sxs-lookup"><span data-stu-id="f4651-127">XML Schema (XSD) Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
