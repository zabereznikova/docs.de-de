---
title: Schreiben von DataSet-Schemainformationen als XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 8403f9d9be88f34e473fd3512f5499193245d227
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59099442"
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="112e1-102">Schreiben von DataSet-Schemainformationen als XSD</span><span class="sxs-lookup"><span data-stu-id="112e1-102">Writing DataSet Schema Information as XSD</span></span>
<span data-ttu-id="112e1-103">Sie können das Schema eines <xref:System.Data.DataSet> als XSD-Schema (XML Schema Definition Language) schreiben, sodass Sie es mit oder ohne zugehörige Daten in ein XML-Dokument übertragen können.</span><span class="sxs-lookup"><span data-stu-id="112e1-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="112e1-104">XML-Schema in eine Datei, einen Stream geschrieben werden kann. ein <xref:System.Xml.XmlWriter>, oder eine Zeichenfolge ist nützlich für das Generieren einer stark typisierten **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="112e1-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="112e1-105">Weitere Informationen zu stark typisierte **DataSet** Objekten finden Sie [typisierter DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="112e1-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>  
  
 <span data-ttu-id="112e1-106">Können Sie angeben, wie eine Spalte einer Tabelle im XML-Schema dargestellt wird mithilfe der **ColumnMapping** Eigenschaft der <xref:System.Data.DataColumn> Objekt.</span><span class="sxs-lookup"><span data-stu-id="112e1-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="112e1-107">Weitere Informationen finden Sie unter "Zuordnen von Spalten zu XML-Elemente, Attribute und Text" in [Schreiben von DataSet-Inhalten als XML-Daten](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="112e1-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="112e1-108">Schreiben Sie das Schema der einen **DataSet** als XML-Schema, in eine Datei, Stream oder **"XmlWriter"**, verwenden die **WriteXmlSchema** -Methode der der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="112e1-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="112e1-109">**WriteXmlSchema** nimmt einen Parameter an, die das Ziel des resultierenden XML-Schemas angibt.</span><span class="sxs-lookup"><span data-stu-id="112e1-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="112e1-110">Die folgenden Codebeispiele veranschaulichen, wie zum Schreiben der XML-Schema eine **DataSet** in eine Datei durch die Übergabe einer Zeichenfolge mit einem Dateinamen und einen <xref:System.IO.StreamWriter> Objekt.</span><span class="sxs-lookup"><span data-stu-id="112e1-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
```vb  
dataSet.WriteXmlSchema("Customers.xsd")  
```  
  
```csharp  
dataSet.WriteXmlSchema("Customers.xsd");  
```  
  
```vb  
Dim writer As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xsd")  
dataSet.WriteXmlSchema(writer)  
writer.Close()  
```  
  
```csharp  
System.IO.StreamWriter writer = new System.IO.StreamWriter("Customers.xsd");  
dataSet.WriteXmlSchema(writer);  
writer.Close();  
```  
  
 <span data-ttu-id="112e1-111">Das Schema der abzurufenden eine **DataSet** und als XML-Schemazeichenfolge zu schreiben, verwenden Sie die **GetXmlSchema** Methode, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="112e1-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="112e1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="112e1-112">See also</span></span>

- [<span data-ttu-id="112e1-113">Verwenden von XML in einem "DataSet"</span><span class="sxs-lookup"><span data-stu-id="112e1-113">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="112e1-114">Schreiben von DataSet-Inhalten als XML-Daten</span><span class="sxs-lookup"><span data-stu-id="112e1-114">Writing DataSet Contents as XML Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/writing-dataset-contents-as-xml-data.md)
- [<span data-ttu-id="112e1-115">Typisierte "DataSets"</span><span class="sxs-lookup"><span data-stu-id="112e1-115">Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)
- [<span data-ttu-id="112e1-116">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="112e1-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="112e1-117">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="112e1-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
