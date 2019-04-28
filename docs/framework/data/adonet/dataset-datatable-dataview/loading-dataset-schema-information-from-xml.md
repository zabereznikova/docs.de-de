---
title: Laden von DataSet-Schemainformationen aus XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: 06dcbbedf8c1533b3da52b447c121746ce705083
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785449"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="18133-102">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="18133-102">Loading DataSet Schema Information from XML</span></span>
<span data-ttu-id="18133-103">Das Schema der einen <xref:System.Data.DataSet> (seine Tabellen, Spalten, Beziehungen und Einschränkungen) können programmgesteuert definiert, erstellt die **füllen** oder **FillSchema** Methoden eine <xref:System.Data.Common.DataAdapter>, oder aus der geladen ein XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="18133-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="18133-104">Beim Laden **DataSet** Schemainformationen aus einer XML-Dokument, verwenden Sie entweder die **ReadXmlSchema** oder **InferXmlSchema** -Methode der der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="18133-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="18133-105">**ReadXmlSchema** ermöglicht es Ihnen, laden oder herleiten **DataSet** Schemainformationen aus dem Dokument mit Schema für XML Schema Definition Language (XSD) oder ein XML-Dokument mit Inline-XML-Schema.</span><span class="sxs-lookup"><span data-stu-id="18133-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="18133-106">**InferXmlSchema** ermöglicht das Herleiten des Schemas aus XML-Dokument und bestimmte von Ihnen angegebenen XML-Namespaces ignoriert.</span><span class="sxs-lookup"><span data-stu-id="18133-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18133-107">Tabellenreihenfolge in einem **DataSet** möglicherweise nicht beibehalten werden, wenn Sie zum Übertragen von Webdiensten oder XML-Serialisierung verwenden eine **DataSet** , mithilfe von XSD-Konstrukten (z. B. geschachtelten Beziehungen) im Arbeitsspeicher erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="18133-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="18133-108">Aus diesem Grund der Empfänger die **DataSet** dürfen nicht in diesem Fall Tabellenreihenfolge abhängen.</span><span class="sxs-lookup"><span data-stu-id="18133-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="18133-109">Allerdings Tabellenreihenfolge wird immer beibehalten, wenn das Schema der **DataSet** übertragenen gelesene aus XSD-Dateien, anstatt im Arbeitsspeicher erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="18133-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="18133-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="18133-110">ReadXmlSchema</span></span>  
 <span data-ttu-id="18133-111">Zum Laden des Schemas einer **DataSet** aus einem XML-Dokument ohne Laden von Daten, können Sie die **ReadXmlSchema** Methode der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="18133-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="18133-112">**ReadXmlSchema** erstellt **DataSet** Schema mithilfe von Schema für XML Schema Definition Language (XSD) definiert.</span><span class="sxs-lookup"><span data-stu-id="18133-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="18133-113">Die **ReadXmlSchema** Methode akzeptiert ein einzelnes Argument eines Dateinamens, einen Stream oder ein **"XmlReader"** mit dem XML-Dokument geladen werden.</span><span class="sxs-lookup"><span data-stu-id="18133-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="18133-114">Das XML-Dokument kann nur ein Schema enthalten. Es kann aber auch ein Inlineschema mit XML-Elementen besitzen, die über Daten verfügen.</span><span class="sxs-lookup"><span data-stu-id="18133-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="18133-115">Weitere Informationen zum Schreiben eines Inlineschemas als XML-Schema finden Sie unter [ableiten relationalen DataSet-Struktur von XML-Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="18133-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="18133-116">Wenn das XML-Dokument übergeben **ReadXmlSchema** enthält keine Inlineschemainformationen, **ReadXmlSchema** das Schema aus den Elementen im XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="18133-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="18133-117">Wenn die **DataSet** bereits ein Schema enthält, wird das aktuelle Schema erweitert werden, indem neue Tabellen hinzugefügt, wenn sie nicht bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="18133-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="18133-118">Vorhandenen Tabellen werden keine neuen Spalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="18133-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="18133-119">Wenn in eine Spalte hinzugefügt wird, bereits vorhanden ist die **DataSet** aber hat ein inkompatiblen Typ mit der Spalte gefunden wird, im XML wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="18133-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="18133-120">Weitere Informationen dazu, wie **ReadXmlSchema** leitet ein Schema aus einem XML-Dokument finden Sie unter [Ableiten von relationalen DataSet-Struktur von XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="18133-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="18133-121">Obwohl **ReadXmlSchema** lädt oder herleitet lediglich das Schema eine **DataSet**, die **ReadXml** -Methode der der **DataSet** lädt oder herleitet, beide Das Schema und die Daten in das XML-Dokument.</span><span class="sxs-lookup"><span data-stu-id="18133-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="18133-122">Weitere Informationen finden Sie unter [Laden eines Datasets aus XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="18133-122">For more information, see [Loading a DataSet from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="18133-123">Die folgenden Codebeispiele zeigen, wie zum Laden einer **DataSet** Schema aus einer XML-Dokument oder den Stream.</span><span class="sxs-lookup"><span data-stu-id="18133-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="18133-124">Das erste Beispiel zeigt den Namen einer XML-Schema-Datei übergeben werden, um die **ReadXmlSchema** Methode.</span><span class="sxs-lookup"><span data-stu-id="18133-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="18133-125">Im zweiten Beispiel wird eine **System.IO.StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="18133-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="18133-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="18133-126">InferXmlSchema</span></span>  
 <span data-ttu-id="18133-127">Sie können auch anweisen, die **DataSet** zum Herleiten die Schemas aus einer XML-Dokument mit den **InferXmlSchema** -Methode der der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="18133-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="18133-128">**InferXmlSchema** funktioniert genauso wie **ReadXml** mit einer **XmlReadMode** von **InferSchema** (lädt Daten sowie leitet das Schema), und **ReadXmlSchema** , wenn das gelesene Dokument kein Inlineschema enthält.</span><span class="sxs-lookup"><span data-stu-id="18133-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="18133-129">Allerdings **InferXmlSchema** bietet zusätzliche die Möglichkeit können Sie an bestimmte XML-Namespaces ignoriert werden, wenn das Schema abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="18133-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="18133-130">**InferXmlSchema** akzeptiert zwei erforderliche Argumente: den Speicherort der XML-Dokuments, angegeben durch einen Dateinamen, einen Stream oder ein **"XmlReader"**; und ein Zeichenfolgenarray von XML-Namespaces, die vom Vorgang ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="18133-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="18133-131">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="18133-131">For example, consider the following XML:</span></span>  
  
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
  
 <span data-ttu-id="18133-132">Aufgrund der Attribute, die für die Elemente in der vorhergehenden XML-Dokument, angegebene sowohl die **ReadXmlSchema** Methode und die **ReadXml** -Methode mit einem **XmlReadMode** von **InferSchema** würde Tabellen für jedes Element im Dokument zu erstellen: **Kategorien**, **CategoryID**, **"CategoryName"**, **Beschreibung**, **Produkte**, **"ProductID"**, **ReorderLevel**, und **nicht mehr unterstützte**.</span><span class="sxs-lookup"><span data-stu-id="18133-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="18133-133">(Weitere Informationen finden Sie unter [Ableiten von relationalen DataSet-Struktur von XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) Eine Struktur besser geeignet wäre jedoch nur erstellen, die **Kategorien** und **Produkte** Tabellen, und klicken Sie dann zum Erstellen **CategoryID**, **"CategoryName"** , und **Beschreibung** Spalten in der **Kategorien** Tabelle und **"ProductID"**, **ReorderLevel**, und **Discontinued** Spalten in der **Produkte** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="18133-133">(For more information, see [Inferring DataSet Relational Structure from XML](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="18133-134">Verwenden, um sicherzustellen, dass das hergeleitete Schema die in den XML-Elementen angegebenen Attribute ignoriert die **InferXmlSchema** Methode, und geben Sie die XML-Namespace für **Officedata** ignoriert werden soll, wie in dargestellt, die folgende Beispiel.</span><span class="sxs-lookup"><span data-stu-id="18133-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="18133-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="18133-135">See also</span></span>

- [<span data-ttu-id="18133-136">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="18133-136">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="18133-137">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="18133-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="18133-138">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="18133-138">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="18133-139">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="18133-139">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="18133-140">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="18133-140">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="18133-141">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="18133-141">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
