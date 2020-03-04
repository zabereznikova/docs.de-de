---
title: Schemakompilierung mit "XmlSchemaCollection"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 76f28770-7126-428f-9ed5-7b5ae8bad5ee
ms.openlocfilehash: af6df3729f1bd926e9a47cc5b9d9bf460c8e1225
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159285"
---
# <a name="xmlschemacollection-schema-compilation"></a><span data-ttu-id="bada5-102">Schemakompilierung mit "XmlSchemaCollection"</span><span class="sxs-lookup"><span data-stu-id="bada5-102">XmlSchemaCollection Schema Compilation</span></span>
<span data-ttu-id="bada5-103">Bei **XmlSchemaCollection** handelt es sich um einen Cache oder eine Bibliothek, worin XDR-Schemata (XML-Data Reduced) und XSD-Schemata (XML Schema Definition Language) gespeichert und validiert werden können.</span><span class="sxs-lookup"><span data-stu-id="bada5-103">The **XmlSchemaCollection** is a cache or library where XML-Data Reduced (XDR) and XML Schema definition language (XSD) schemas can be stored and validated.</span></span> <span data-ttu-id="bada5-104">**XmlSchemaCollection** erhöht die Leistungsfähigkeit, indem Schemata im Arbeitsspeicher zwischengespeichert werden, anstatt über eine Datei oder eine URL auf sie zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="bada5-104">**XmlSchemaCollection** improves performance by caching schemas in memory instead of accessing them from a file or URL.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bada5-105">Obwohl in der **XmlSchemaCollection** sowohl XML-Schemata als auch XDR-Schemata gespeichert werden, unterstützt jede Methode oder Eigenschaft, die ein **XmlSchema**-Objekt akzeptiert bzw. zurückgibt, nur XML-Schemata.</span><span class="sxs-lookup"><span data-stu-id="bada5-105">Although the **XmlSchemaCollection** class stores both XDR schemas and XML Schemas, any method and property that takes or returns an **XmlSchema** object supports XML Schemas only.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bada5-106">Die <xref:System.Xml.Schema.XmlSchemaCollection>-Klasse ist veraltet und wurde durch die <xref:System.Xml.Schema.XmlSchemaSet>-Klasse ersetzt.</span><span class="sxs-lookup"><span data-stu-id="bada5-106">The <xref:System.Xml.Schema.XmlSchemaCollection> class is now obsolete and has been replaced with the <xref:System.Xml.Schema.XmlSchemaSet> class.</span></span> <span data-ttu-id="bada5-107">Weitere Informationen zur <xref:System.Xml.Schema.XmlSchemaSet>-Klasse finden Sie unter [„XmlSchemaSet“ zur Kompilierung von Schemata](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span><span class="sxs-lookup"><span data-stu-id="bada5-107">For more information about the <xref:System.Xml.Schema.XmlSchemaSet> class see, [XmlSchemaSet for Schema Compilation](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md).</span></span>  
  
## <a name="add-schemas-to-the-collection"></a><span data-ttu-id="bada5-108">Hinzufügen von Schemata zur Auflistung</span><span class="sxs-lookup"><span data-stu-id="bada5-108">Add Schemas to the Collection</span></span>  
 <span data-ttu-id="bada5-109">Durch die **Add**-Methode von **XmlSchemaCollection** werden Schemata in die Auflistung geladen, sobald das Schema einem Namespace-URI zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="bada5-109">Schemas are loaded to the collection using the **Add** method of **XmlSchemaCollection**, at which time the schema is associated with a namespace URI.</span></span> <span data-ttu-id="bada5-110">Bei XML-Schemata ist der Namespace-URI normalerweise der Zielnamespace des Schemas.</span><span class="sxs-lookup"><span data-stu-id="bada5-110">For XML Schemas, the namespace URI will typically be the target namespace for the schema.</span></span> <span data-ttu-id="bada5-111">Bei XDR-Schemata ist der Namespace-URI der Namespace, der angegeben wird, wenn ein Schema der Auflistung hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="bada5-111">For XDR schemas, the namespace URI is the namespace specified when the schema was added to the collection.</span></span>  
  
## <a name="check-for-a-schema-in-the-collection"></a><span data-ttu-id="bada5-112">Suche nach einem Schema in der Auflistung</span><span class="sxs-lookup"><span data-stu-id="bada5-112">Check for a Schema in the Collection</span></span>  
 <span data-ttu-id="bada5-113">Mit der **Contains**-Methode können Sie überprüfen, ob ein Schema in der Auflistung enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="bada5-113">You can check to see if a schema is in the collection by using the **Contains** method.</span></span> <span data-ttu-id="bada5-114">Die **Contains**-Methode übernimmt entweder ein **XmlSchema**-Objekt (nur bei XML-Schemata) oder eine Zeichenfolge, die den dem Schema zugeordneten Namespace-URI repräsentiert (bei XML- und XDR-Schemata).</span><span class="sxs-lookup"><span data-stu-id="bada5-114">The **Contains** method takes either an **XmlSchema** object (for XML Schemas only) or a string representing the namespace URI associated with the schema (for XML Schemas and XDR schemas).</span></span>  
  
## <a name="retrieve-a-schema-from-the-collection"></a><span data-ttu-id="bada5-115">Abrufen eines Schemas aus der Auflistung</span><span class="sxs-lookup"><span data-stu-id="bada5-115">Retrieve a Schema from the Collection</span></span>  
 <span data-ttu-id="bada5-116">Mit der **Item**-Eigenschaft kann ein Schema aus der Auflistung abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="bada5-116">You can retrieve a schema from the collection by using the **Item** property.</span></span> <span data-ttu-id="bada5-117">Die **Item**-Eigenschaft übernimmt eine Zeichenfolge, die den dem Schema zugeordneten Namespace-URI repräsentiert (normalerweise den Zielnamespace des Schemas), und gibt ein **XmlSchema**-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="bada5-117">The **Item** property takes a string representing the namespace URI associated with the schema, typically its target namespace, and returns an **XmlSchema** object.</span></span> <span data-ttu-id="bada5-118">Die **Item**-Eigenschaft wird nur bei XML-Schemata angewendet.</span><span class="sxs-lookup"><span data-stu-id="bada5-118">The **Item** property applies to XML Schemas only.</span></span> <span data-ttu-id="bada5-119">Der Rückgabewert ist bei XDR-Schemata immer ein NULL-Verweis, da diese kein Objektmodell zur Verfügung haben.</span><span class="sxs-lookup"><span data-stu-id="bada5-119">The return value is always a null reference for XDR schemas because they do not have an object model available.</span></span>  
  
## <a name="validate-xml-documents-using-xmlschemacollection"></a><span data-ttu-id="bada5-120">Validieren von XML-Dokumenten mit "XmlSchemaCollection"</span><span class="sxs-lookup"><span data-stu-id="bada5-120">Validate XML Documents Using XmlSchemaCollection</span></span>  
 <span data-ttu-id="bada5-121">Ein XML-Instanzdokument wird mithilfe von **XmlSchemaCollection** folgendermaßen validiert: Ein **XmlSchemaCollection**-Objekt wird erstellt, und die jeweiligen Schemata werden der Auflistung hinzugefügt. Anschließend wird die **Schemas**-Eigenschaft von **XmlValidatingReader** festgelegt, um die erstellte **XmlSchemaCollection** dem **XmlValidatingReader** zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="bada5-121">You can validate an XML instance document using an **XmlSchemaCollection** by creating the **XmlSchemaCollection** object, adding your schemas to the collection, and setting the **Schemas** property on the **XmlValidatingReader** to assign the created **XmlSchemaCollection** to the **XmlValidatingReader**.</span></span>  
  
### <a name="improved-performance"></a><span data-ttu-id="bada5-122">Leistungssteigerung</span><span class="sxs-lookup"><span data-stu-id="bada5-122">Improved Performance</span></span>  
 <span data-ttu-id="bada5-123">Wird mehr als ein Dokument anhand desselben Schemas validiert, ist es ratsam, **XmlSchemaCollection** zu verwenden. Die Leistung wird durch Zwischenspeichern der Schemata im Arbeitsspeicher gesteigert.</span><span class="sxs-lookup"><span data-stu-id="bada5-123">It is recommended, if you are validating more than one document against the same schema, that you use the **XmlSchemaCollection** because it provides better performance by caching schemas in memory.</span></span>  
  
 <span data-ttu-id="bada5-124">Im folgenden Codebeispiel wird das **XmlSchemaCollection**-Objekt erstellt, und die Schemata werden der Auflistung hinzugefügt. Anschließend wird die **Schemas**-Eigenschaft festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bada5-124">The following code example creates the **XmlSchemaCollection** object, adds schemas to the collection, and sets the **Schemas** property.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bada5-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bada5-125">See also</span></span>

- [<span data-ttu-id="bada5-126">XDR-Validierung mit „XmlSchemaCollection“</span><span class="sxs-lookup"><span data-stu-id="bada5-126">XDR Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xdr-validation-with-xmlschemacollection.md)
- [<span data-ttu-id="bada5-127">XSD-Validierung (XML Schema) mit „XmlSchemaCollection“</span><span class="sxs-lookup"><span data-stu-id="bada5-127">XML Schema (XSD) Validation with XmlSchemaCollection</span></span>](../../../../docs/standard/data/xml/xml-schema-xsd-validation-with-xmlschemacollection.md)
