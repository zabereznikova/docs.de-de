---
title: Schreiben von DataSet-Schemainformationen als XSD
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4e530831-695e-49ff-8f0b-e5b0c526b8eb
ms.openlocfilehash: 7634dfc8415b6f73fc60f2ebe59c92a0c31f83a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173730"
---
# <a name="writing-dataset-schema-information-as-xsd"></a><span data-ttu-id="6891a-102">Schreiben von DataSet-Schemainformationen als XSD</span><span class="sxs-lookup"><span data-stu-id="6891a-102">Writing DataSet Schema Information as XSD</span></span>

<span data-ttu-id="6891a-103">Sie können das Schema eines <xref:System.Data.DataSet> als XSD-Schema (XML Schema Definition Language) schreiben, sodass Sie es mit oder ohne zugehörige Daten in ein XML-Dokument übertragen können.</span><span class="sxs-lookup"><span data-stu-id="6891a-103">You can write the schema of a <xref:System.Data.DataSet> as XML Schema definition language (XSD) schema, so that you can transport it, with or without related data, in an XML document.</span></span> <span data-ttu-id="6891a-104">Das XML-Schema kann in eine Datei, einen Stream, einen <xref:System.Xml.XmlWriter> oder eine Zeichenfolge geschrieben werden. es ist nützlich, um ein stark typisiertes **DataSet**zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="6891a-104">XML Schema can be written to a file, a stream, an <xref:System.Xml.XmlWriter>, or a string; it is useful for generating a strongly typed **DataSet**.</span></span> <span data-ttu-id="6891a-105">Weitere Informationen zu stark typisierten **DataSet** -Objekten finden Sie unter [typisierte Datasets](typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="6891a-105">For more information about strongly typed **DataSet** objects, see [Typed DataSets](typed-datasets.md).</span></span>  
  
 <span data-ttu-id="6891a-106">Mithilfe der **ColumnMapping** -Eigenschaft des-Objekts können Sie angeben, wie eine Spalte einer Tabelle im XML-Schema dargestellt wird <xref:System.Data.DataColumn> .</span><span class="sxs-lookup"><span data-stu-id="6891a-106">You can specify how a column of a table is represented in XML Schema using the **ColumnMapping** property of the <xref:System.Data.DataColumn> object.</span></span> <span data-ttu-id="6891a-107">Weitere Informationen finden Sie unter "Mapping von Spalten zu XML-Elementen,-Attributen und-Text" unter [Schreiben von DataSet-Inhalten als XML-Daten](writing-dataset-contents-as-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="6891a-107">For more information, see "Mapping Columns to XML Elements, Attributes, and Text" in [Writing DataSet Contents as XML Data](writing-dataset-contents-as-xml-data.md).</span></span>  
  
 <span data-ttu-id="6891a-108">Um das Schema eines **DataSets** als XML-Schema in eine Datei, einen Stream oder einen **XmlWriter**zu schreiben, verwenden Sie die Schreib **texmlschema** -Methode des **DataSets**.</span><span class="sxs-lookup"><span data-stu-id="6891a-108">To write the schema of a **DataSet** as XML Schema, to a file, stream, or **XmlWriter**, use the **WriteXmlSchema** method of the **DataSet**.</span></span> <span data-ttu-id="6891a-109">" **Write texmlschema** " nimmt einen Parameter an, der das Ziel des resultierenden XML-Schemas angibt.</span><span class="sxs-lookup"><span data-stu-id="6891a-109">**WriteXmlSchema** takes one parameter that specifies the destination of the resulting XML Schema.</span></span> <span data-ttu-id="6891a-110">Die folgenden Codebeispiele veranschaulichen, wie das XML-Schema eines **DataSets** in eine Datei geschrieben wird, indem eine Zeichenfolge mit einem Dateinamen und einem-Objekt übergeben wird <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="6891a-110">The following code examples demonstrate how to write the XML Schema of a **DataSet** to a file by passing a string containing a file name and a <xref:System.IO.StreamWriter> object.</span></span>  
  
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
  
 <span data-ttu-id="6891a-111">Wenn Sie das Schema eines **DataSets** abrufen und als XML-Schema Zeichenfolge schreiben möchten, verwenden Sie die **GetXmlSchema** -Methode, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6891a-111">To obtain the schema of a **DataSet** and write it as an XML Schema string, use the **GetXmlSchema** method, as shown in the following example.</span></span>  
  
```vb  
Dim schemaString As String = dataSet.GetXmlSchema()  
```  
  
```csharp  
string schemaString = dataSet.GetXmlSchema();  
```  
  
## <a name="see-also"></a><span data-ttu-id="6891a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6891a-112">See also</span></span>

- [<span data-ttu-id="6891a-113">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="6891a-113">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="6891a-114">Schreiben von DataSet-Inhalten als XML-Daten</span><span class="sxs-lookup"><span data-stu-id="6891a-114">Writing DataSet Contents as XML Data</span></span>](writing-dataset-contents-as-xml-data.md)
- [<span data-ttu-id="6891a-115">Typisierte "DataSets"</span><span class="sxs-lookup"><span data-stu-id="6891a-115">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="6891a-116">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="6891a-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="6891a-117">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="6891a-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
