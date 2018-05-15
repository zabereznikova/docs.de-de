---
title: Laden von DataSet-Schemainformationen aus XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 4b212a7233e6eec93cdce3e521b58e08745e35e0
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="bf132-102">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="bf132-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="bf132-103">Das Schema der eine <xref:System.Data.DataSet> (seine Tabellen, Spalten, Beziehungen und Einschränkungen) können programmgesteuert definiert, erstellt, indem die **füllen** oder **FillSchema** Methoden eine <xref:System.Data.Common.DataAdapter>, oder aus geladen ein XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="bf132-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="bf132-104">Beim Laden **DataSet** Schemainformationen aus einem XML-Dokument verwenden Sie entweder die **ReadXmlSchema** oder **InferXmlSchema** Methode der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="bf132-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="bf132-105">**ReadXmlSchema** können Sie zum Laden oder herleiten **DataSet** Schemainformationen aus dem Dokument, das Schema für XML Schema Definition Language (XSD) oder ein XML-Dokument mit Inline-XML-Schema enthält.</span><span class="sxs-lookup"><span data-stu-id="bf132-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="bf132-106">**InferXmlSchema** ermöglicht das Herleiten des Schemas aus der XML-Dokument während bestimmte von Ihnen angegebenen XML-Namespaces ignoriert.</span><span class="sxs-lookup"><span data-stu-id="bf132-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bf132-107">Tabellenreihenfolge in einem **DataSet** möglicherweise nicht beibehalten, wenn Sie zum Übertragen von Webdiensten oder XML-Serialisierung verwenden eine **DataSet** , mithilfe von XSD-Konstrukten (z. B. geschachtelten Beziehungen) im Arbeitsspeicher erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bf132-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="bf132-108">Aus diesem Grund für den Empfänger des der **DataSet** sollten Tabellenreihenfolge in diesem Fall nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bf132-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="bf132-109">Allerdings Tabellenreihenfolge wird immer beibehalten, wenn das Schema der **DataSet** übertragenen gelesene aus XSD-Dateien, anstatt im Arbeitsspeicher erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="bf132-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="bf132-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="bf132-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="bf132-111">Zum Laden des Schemas ein **DataSet** aus einem XML-Dokument ohne Daten zu laden, können Sie die **ReadXmlSchema** Methode der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="bf132-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="bf132-112">**ReadXmlSchema** erstellt **DataSet** Schema mithilfe von Schemas für XML Schema Definition Language (XSD) definiert.</span><span class="sxs-lookup"><span data-stu-id="bf132-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="bf132-113">Die **ReadXmlSchema** Methode akzeptiert ein einzelnes Argument eines Dateinamens, einen Stream oder eine **XmlReader** mit dem XML-Dokument geladen werden.</span><span class="sxs-lookup"><span data-stu-id="bf132-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="bf132-114">Das XML-Dokument kann nur ein Schema enthalten. Es kann aber auch ein Inlineschema mit XML-Elementen besitzen, die über Daten verfügen.</span><span class="sxs-lookup"><span data-stu-id="bf132-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="bf132-115">Informationen über das Schreiben von Inlineschema als XML-Schema finden Sie unter [ableiten relationalen DataSet-Struktur von XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="bf132-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="bf132-116">Wenn das XML-Dokument übergeben **ReadXmlSchema** keine Inlineschemainformationen enthält **ReadXmlSchema** das Schema aus den Elementen im XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="bf132-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="bf132-117">Wenn die **DataSet** bereits ein Schema enthält, das aktuelle Schema erweitert, indem neue Tabellen hinzugefügt werden, wenn sie nicht bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="bf132-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="bf132-118">Vorhandenen Tabellen werden keine neuen Spalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="bf132-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="bf132-119">Ggf. eine hinzuzufügende Spalte bereits in der **DataSet** aber hat ein inkompatiblen Typ mit der Spalte gefunden, in der XML-Code wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="bf132-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="bf132-120">Weitere Informationen dazu, wie **ReadXmlSchema** leitet ein Schema aus einem XML-Dokument, finden Sie unter [Ableiten von relationalen DataSet-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bf132-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="bf132-121">Obwohl **ReadXmlSchema** lädt oder herleitet nur das Schema des eine **DataSet**, die **ReadXml** Methode der **DataSet** lädt oder herleitet, beide Das Schema und die Daten in das XML-Dokument enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="bf132-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="bf132-122">Weitere Informationen finden Sie unter [beim Laden eines Datasets aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bf132-122">For more information, see [Loading a DataSet from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="bf132-123">Die folgenden Codebeispiele zeigen, wie beim Laden einer **DataSet** Schema aus einem XML-Dokument oder den Stream.</span><span class="sxs-lookup"><span data-stu-id="bf132-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="bf132-124">Im ersten Beispiel wird ein XML-Schema-Dateiname übergeben werden, um die **ReadXmlSchema** Methode.</span><span class="sxs-lookup"><span data-stu-id="bf132-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="bf132-125">Im zweiten Beispiel wird eine **System.IO.StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="bf132-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As System.IO.StreamReader = New System.IO.StreamReader ("schema.xsd");  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema(xmlStream)  
xmlStream.Close()  
```  
  
```csharp  
System.IO.StreamReader xmlStream = new System.IO.StreamReader("schema.xsd");  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema(xmlStream);  
xmlStream.Close();  
```  
  
## <a name="inferxmlschema"></a><span data-ttu-id="bf132-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="bf132-126">InferXmlSchema</span></span>  
 <span data-ttu-id="bf132-127">Sie können auch festlegen, dass die **DataSet** Ableiten von dessen Schema aus einer XML-Dokuments mithilfe der **InferXmlSchema** Methode der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="bf132-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="bf132-128">**InferXmlSchema** funktioniert genauso wie **ReadXml** mit einem **XmlReadMode** von **InferSchema** (lädt Daten sowie leitet das Schema ab), und **ReadXmlSchema** , wenn das gelesene Dokument kein Inlineschema enthält.</span><span class="sxs-lookup"><span data-stu-id="bf132-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="bf132-129">Allerdings **InferXmlSchema** zusätzlich die Möglichkeit Möglichkeit an bestimmte XML-Namespaces ignoriert werden, wenn das Schema abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="bf132-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="bf132-130">**InferXmlSchema** hat zwei erforderliche Argumente: den Speicherort der XML-Dokuments, angegeben durch einen Dateinamen, einen Stream oder eine **XmlReader**; und ein Zeichenfolgenarray mit XML-Namespaces, die vom Vorgang ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="bf132-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="bf132-131">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="bf132-131">For example, consider the following XML:</span></span>  
  
```xml  
<NewDataSet xmlns:od="urn:schemas-microsoft-com:officedata">  
<Categories>  
  <CategoryID od:adotype="3">1</CategoryID>   
  <CategoryName od:maxLength="15" od:adotype="130">Beverages</CategoryName>   
  <Description od:adotype="203">Soft drinks and teas</Description>   
</Categories>  
<Products>  
  <ProductID od:adotype="20">1</ProductID>   
  <ReorderLevel od:adotype="3">10</ReorderLevel>   
  <Discontinued od:adotype="11">0</Discontinued>   
</Products>  
</NewDataSet>  
```  
  
 <span data-ttu-id="bf132-132">Aufgrund der Attribute für die Elemente in der vorhergehenden XML-Dokument sowohl die **ReadXmlSchema** Methode und die **ReadXml** Methode mit einer **XmlReadMode** von **InferSchema** würde Erstellen von Tabellen für jedes Element im Dokument: **Kategorien**, **CategoryID**, **CategoryName**, **Beschreibung**, **Produkte**, **"ProductID"**, **ReorderLevel**, und **nicht mehr unterstützte**.</span><span class="sxs-lookup"><span data-stu-id="bf132-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="bf132-133">(Weitere Informationen finden Sie unter [Ableiten von relationalen DataSet-Struktur aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) Eine besser geeignete Struktur wäre jedoch nur für Erstellung der **Kategorien** und **Produkte** Tabellen, und klicken Sie dann auf Erstellen **CategoryID**, **CategoryName** , und **Beschreibung** Spalten in der **Kategorien** Tabelle und **"ProductID"**, **ReorderLevel**, und **Discontinued** Spalten in der **Produkte** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bf132-133">(For more information, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="bf132-134">Verwenden, um sicherzustellen, dass das hergeleitete Schema die in der XML-Elementen angegebenen Attribute ignoriert die **InferXmlSchema** Methode, und geben Sie den XML-Namespace für **Officedata** ignoriert werden soll, wie in dargestellt, die folgende.</span><span class="sxs-lookup"><span data-stu-id="bf132-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf132-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf132-135">See Also</span></span>  
 [<span data-ttu-id="bf132-136">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="bf132-136">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="bf132-137">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="bf132-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 [<span data-ttu-id="bf132-138">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="bf132-138">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="bf132-139">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="bf132-139">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="bf132-140">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="bf132-140">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="bf132-141">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="bf132-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
