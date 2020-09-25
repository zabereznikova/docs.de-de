---
title: Laden von DataSet-Schemainformationen aus XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 43dfb23b-5cef-46f2-8d87-78f0fba1eb8c
ms.openlocfilehash: b084590d7158024227a9f12da759b56ae2031373
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201342"
---
# <a name="loading-dataset-schema-information-from-xml"></a><span data-ttu-id="c28a1-102">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="c28a1-102">Loading DataSet Schema Information from XML</span></span>

<span data-ttu-id="c28a1-103">Das Schema von a <xref:System.Data.DataSet> (Tabellen, Spalten, Beziehungen und Einschränkungen) kann Programm gesteuert definiert, durch die **Fill** -Methode oder die **FillSchema** -Methode eines erstellt <xref:System.Data.Common.DataAdapter> oder aus einem XML-Dokument geladen werden.</span><span class="sxs-lookup"><span data-stu-id="c28a1-103">The schema of a <xref:System.Data.DataSet> (its tables, columns, relations, and constraints) can be defined programmatically, created by the **Fill** or **FillSchema** methods of a <xref:System.Data.Common.DataAdapter>, or loaded from an XML document.</span></span> <span data-ttu-id="c28a1-104">Zum Laden von **DataSet** -Schema Informationen aus einem XML-Dokument können Sie entweder die " **infoxmlschema** "-Methode oder die **InferXmlSchema** -Methode des **DataSets**verwenden.</span><span class="sxs-lookup"><span data-stu-id="c28a1-104">To load **DataSet** schema information from an XML document, you can use either the **ReadXmlSchema** or the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="c28a1-105">Mit " **infoxmlschema** " können Sie **DataSet** -Schema Informationen aus dem Dokument, das das XSD-Schema (XML Schema Definition Language) enthält, oder ein XML-Dokument mit Inline-XML-Schema laden bzw. daraus ableiten.</span><span class="sxs-lookup"><span data-stu-id="c28a1-105">**ReadXmlSchema** allows you to load or infer **DataSet** schema information from the document containing XML Schema definition language (XSD) schema, or an XML document with inline XML Schema.</span></span> <span data-ttu-id="c28a1-106">Mit **InferXmlSchema** können Sie das Schema aus dem XML-Dokument ableiten, während bestimmte von Ihnen angegebene XML-Namespaces ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="c28a1-106">**InferXmlSchema** allows you to infer the schema from the XML document while ignoring certain XML namespaces that you specify.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c28a1-107">Die Tabellen Anordnung in einem **DataSet** wird möglicherweise nicht beibehalten, wenn Sie Webdienste oder XML-Serialisierung verwenden, um ein **DataSet** zu übertragen, das in-Memory mithilfe von XSD-Konstrukten (z. b. gruppierte Beziehungen) erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c28a1-107">Table ordering in a **DataSet** might not be preserved when you use Web services or XML serialization to transfer a **DataSet** that was created in-memory by using XSD constructs (such as nested relations).</span></span> <span data-ttu-id="c28a1-108">Daher sollte der Empfänger des **DataSets** in diesem Fall nicht von der Tabellen Anordnung abhängen.</span><span class="sxs-lookup"><span data-stu-id="c28a1-108">Therefore, the recipient of the **DataSet** should not depend on table ordering in this case.</span></span> <span data-ttu-id="c28a1-109">Die Tabellen Anordnung wird jedoch immer beibehalten, wenn das Schema des übertragenen **DataSets** aus XSD-Dateien gelesen wurde und nicht im Arbeitsspeicher erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="c28a1-109">However, table ordering is always preserved if the schema of the **DataSet** being transferred was read from XSD files, instead of being created in-memory.</span></span>  
  
## <a name="readxmlschema"></a><span data-ttu-id="c28a1-110">ReadXmlSchema</span><span class="sxs-lookup"><span data-stu-id="c28a1-110">ReadXmlSchema</span></span>  

 <span data-ttu-id="c28a1-111">Wenn Sie das Schema eines **DataSets** aus einem XML-Dokument ohne das Laden von Daten laden möchten, können Sie die Methode "read **XmlSchema** " des **DataSets**verwenden.</span><span class="sxs-lookup"><span data-stu-id="c28a1-111">To load the schema of a **DataSet** from an XML document without loading any data, you can use the **ReadXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="c28a1-112">Das mit dem XSD-Schema (XML Schema Definition Language) definierte **DataSet** -Schema wird von "read **XmlSchema** " erstellt.</span><span class="sxs-lookup"><span data-stu-id="c28a1-112">**ReadXmlSchema** creates **DataSet** schema defined using XML Schema definition language (XSD) schema.</span></span>  
  
 <span data-ttu-id="c28a1-113">Die Methode "read **XmlSchema** " nimmt ein einzelnes Argument eines Datei namens, eines Streams oder eines **XmlReader** , der das zu ladende XML-Dokument enthält.</span><span class="sxs-lookup"><span data-stu-id="c28a1-113">The **ReadXmlSchema** method takes a single argument of a file name, a stream, or an **XmlReader** containing the XML document to be loaded.</span></span> <span data-ttu-id="c28a1-114">Das XML-Dokument kann nur ein Schema enthalten. Es kann aber auch ein Inlineschema mit XML-Elementen besitzen, die über Daten verfügen.</span><span class="sxs-lookup"><span data-stu-id="c28a1-114">The XML document can contain only schema, or can contain schema inline with XML elements containing data.</span></span> <span data-ttu-id="c28a1-115">Ausführliche Informationen zum Schreiben eines Inline Schemas als XML-Schema finden Sie unter [Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span><span class="sxs-lookup"><span data-stu-id="c28a1-115">For details about writing inline schema as XML Schema, see [Deriving DataSet Relational Structure from XML Schema (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md).</span></span>  
  
 <span data-ttu-id="c28a1-116">Wenn das an " **infoxmlschema** " übergebenen XML-Dokument keine Inline Schema Informationen enthält, leitet " **infoxmlschema** " das Schema aus den Elementen im XML-Dokument ab.</span><span class="sxs-lookup"><span data-stu-id="c28a1-116">If the XML document passed to **ReadXmlSchema** contains no inline schema information, **ReadXmlSchema** will infer the schema from the elements in the XML document.</span></span> <span data-ttu-id="c28a1-117">Wenn das **DataSet** bereits ein Schema enthält, wird das aktuelle Schema erweitert, indem neue Tabellen hinzugefügt werden, sofern diese nicht bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c28a1-117">If the **DataSet** already contains a schema, the current schema will be extended by adding new tables if they do not already exist.</span></span> <span data-ttu-id="c28a1-118">Vorhandenen Tabellen werden keine neuen Spalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c28a1-118">New columns will not be added to added to existing tables.</span></span> <span data-ttu-id="c28a1-119">Wenn eine hinzugefügte Spalte bereits im **DataSet** vorhanden ist, aber einen nicht kompatiblen Typ mit der im XML gefundenen Spalte aufweist, wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="c28a1-119">If a column being added already exists in the **DataSet** but has an incompatible type with the column found in the XML, an exception is thrown.</span></span> <span data-ttu-id="c28a1-120">Ausführliche Informationen dazu, wie " **infoxmlschema** " ein Schema aus einem XML-Dokument ableitet, finden Sie unter [ableiten der relationalen DataSet-Struktur aus XML](inferring-dataset-relational-structure-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c28a1-120">For details about how **ReadXmlSchema** infers a schema from an XML document, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).</span></span>  
  
 <span data-ttu-id="c28a1-121">Obwohl das Schema eines **DataSets**von " **infoxmlschema** " geladen oder abgerufen wird, werden sowohl das Schema als auch die Daten, die im XML-Dokument enthalten sind, von der "read **XML** "-Methode des **DataSets** geladen oder abgerufen.</span><span class="sxs-lookup"><span data-stu-id="c28a1-121">Although **ReadXmlSchema** loads or infers only the schema of a **DataSet**, the **ReadXml** method of the **DataSet** loads or infers both the schema and the data contained in the XML document.</span></span> <span data-ttu-id="c28a1-122">Weitere Informationen finden Sie unter [Laden eines Datasets aus XML](loading-a-dataset-from-xml.md).</span><span class="sxs-lookup"><span data-stu-id="c28a1-122">For more information, see [Loading a DataSet from XML](loading-a-dataset-from-xml.md).</span></span>  
  
 <span data-ttu-id="c28a1-123">In den folgenden Codebeispielen wird gezeigt, wie ein **DataSet** -Schema aus einem XML-Dokument oder-Stream geladen wird.</span><span class="sxs-lookup"><span data-stu-id="c28a1-123">The following code examples show how to load a **DataSet** schema from an XML document or stream.</span></span> <span data-ttu-id="c28a1-124">Im ersten Beispiel wird gezeigt, wie ein XML-Schema Dateiname an die Methode "read **XmlSchema** " übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="c28a1-124">The first example shows an XML Schema file name being passed to the **ReadXmlSchema** method.</span></span> <span data-ttu-id="c28a1-125">Das zweite Beispiel zeigt einen **System. IO. StreamReader**.</span><span class="sxs-lookup"><span data-stu-id="c28a1-125">The second example shows a **System.IO.StreamReader**.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.ReadXmlSchema("schema.xsd")  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.ReadXmlSchema("schema.xsd");  
```  
  
```vb  
Dim xmlStream As New System.IO.StreamReader("schema.xsd")
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
  
## <a name="inferxmlschema"></a><span data-ttu-id="c28a1-126">InferXmlSchema</span><span class="sxs-lookup"><span data-stu-id="c28a1-126">InferXmlSchema</span></span>  

 <span data-ttu-id="c28a1-127">Sie können das **DataSet** auch anweisen, sein Schema mithilfe der **InferXmlSchema** -Methode des **DataSets**von einem XML-Dokument abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="c28a1-127">You can also instruct the **DataSet** to infer its schema from an XML document using the **InferXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="c28a1-128">**InferXmlSchema** funktioniert genauso wie "read **XML** " mit einem **xmllesemode** " **InferSchema** " (lädt sowohl Daten als auch ein ausgabenschema) und "leadxmlschema", wenn das gelesene Dokument kein Inline Schema enthält. **ReadXmlSchema**</span><span class="sxs-lookup"><span data-stu-id="c28a1-128">**InferXmlSchema** functions the same as do both **ReadXml** with an **XmlReadMode** of **InferSchema** (loads data as well as infers schema), and **ReadXmlSchema** if the document being read contains no inline schema.</span></span> <span data-ttu-id="c28a1-129">**InferXmlSchema** bietet jedoch die zusätzliche Möglichkeit, bestimmte XML-Namespaces anzugeben, die beim Ableiten des Schemas ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="c28a1-129">However, **InferXmlSchema** provides the additional capability of allowing you to specify particular XML namespaces to be ignored when the schema is inferred.</span></span> <span data-ttu-id="c28a1-130">**InferXmlSchema** erfordert zwei erforderliche Argumente: den Speicherort des XML-Dokuments, das durch einen Dateinamen, einen Stream oder einen **XmlReader**angegeben wird. und ein Zeichen folgen Array von XML-Namespaces, die vom Vorgang ignoriert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c28a1-130">**InferXmlSchema** takes two required arguments: the location of the XML document, specified by a file name, a stream, or an **XmlReader**; and a string array of XML namespaces to be ignored by the operation.</span></span>  
  
 <span data-ttu-id="c28a1-131">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="c28a1-131">For example, consider the following XML:</span></span>  
  
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
  
 <span data-ttu-id="c28a1-132">Aufgrund der Attribute, die für die Elemente im vorangehenden XML-Dokument angegeben sind, würden sowohl die "read **XmlSchema** "-Methode als auch die "read **Discontinued** **CategoryName** **Description** **XML** "-Methode mit einem " **xmllesemode** " von " **CategoryID** **InferSchema** " Tabellen für jedes Element im Dokument erstellen **Products** **:** **ProductID** **ReorderLevel**</span><span class="sxs-lookup"><span data-stu-id="c28a1-132">Because of the attributes specified for the elements in the preceding XML document, both the **ReadXmlSchema** method and the **ReadXml** method with an **XmlReadMode** of **InferSchema** would create tables for every element in the document: **Categories**, **CategoryID**, **CategoryName**, **Description**, **Products**, **ProductID**, **ReorderLevel**, and **Discontinued**.</span></span> <span data-ttu-id="c28a1-133">(Weitere Informationen finden Sie unter [ableiten der relationalen DataSet-Struktur aus XML](inferring-dataset-relational-structure-from-xml.md).) Eine geeignetere Struktur wäre jedoch, nur die Tabellen **Categories** und **Products** zu erstellen und dann die Spalten **CategoryID**, **CategoryName**und **Description** in der Tabelle **Categories** sowie die Spalten **ProductID**, **ReorderLevel**und nicht mehr unter **stützte Spalten in** der Tabelle **Products** zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c28a1-133">(For more information, see [Inferring DataSet Relational Structure from XML](inferring-dataset-relational-structure-from-xml.md).) However, a more appropriate structure would be to create only the **Categories** and **Products** tables, and then to create **CategoryID**, **CategoryName**, and **Description** columns in the **Categories** table, and **ProductID**, **ReorderLevel**, and **Discontinued** columns in the **Products** table.</span></span> <span data-ttu-id="c28a1-134">Um sicherzustellen, dass das abzurufende Schema die in den XML-Elementen angegebenen Attribute ignoriert, verwenden Sie die **InferXmlSchema** -Methode, und geben Sie den XML-Namespace für **officedata** an, der ignoriert werden soll, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c28a1-134">To ensure that the inferred schema ignores the attributes specified in the XML elements, use the **InferXmlSchema** method and specify the XML namespace for **officedata** to be ignored, as shown in the following example.</span></span>  
  
```vb  
Dim dataSet As DataSet = New DataSet  
dataSet.InferXmlSchema("input_od.xml", New String() {"urn:schemas-microsoft-com:officedata"})  
```  
  
```csharp  
DataSet dataSet = new DataSet();  
dataSet.InferXmlSchema("input_od.xml", new string[] "urn:schemas-microsoft-com:officedata");  
```  
  
## <a name="see-also"></a><span data-ttu-id="c28a1-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c28a1-135">See also</span></span>

- [<span data-ttu-id="c28a1-136">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="c28a1-136">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="c28a1-137">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="c28a1-137">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)
- [<span data-ttu-id="c28a1-138">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="c28a1-138">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="c28a1-139">Laden eines "DataSets" aus XML</span><span class="sxs-lookup"><span data-stu-id="c28a1-139">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="c28a1-140">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="c28a1-140">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="c28a1-141">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c28a1-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
