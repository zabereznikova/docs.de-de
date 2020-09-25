---
title: Schreiben von DataSet-Inhalten als XML-Daten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd15f8a5-3b4c-46d0-a561-4559ab2a4705
ms.openlocfilehash: c8a5c747e4ec60fcb97edf631aa3a0ae184ffec5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173717"
---
# <a name="writing-dataset-contents-as-xml-data"></a><span data-ttu-id="71bd3-102">Schreiben von DataSet-Inhalten als XML-Daten</span><span class="sxs-lookup"><span data-stu-id="71bd3-102">Writing DataSet Contents as XML Data</span></span>

<span data-ttu-id="71bd3-103">Sie können in ADO.NET die XML-Darstellung eines <xref:System.Data.DataSet> mit oder ohne dessen Schema schreiben.</span><span class="sxs-lookup"><span data-stu-id="71bd3-103">In ADO.NET you can write an XML representation of a <xref:System.Data.DataSet>, with or without its schema.</span></span> <span data-ttu-id="71bd3-104">Wenn das XML-Dokument Inlineschemainformationen enthält, werden diese mit XSD (XML Schema Definition Language) geschrieben.</span><span class="sxs-lookup"><span data-stu-id="71bd3-104">If schema information is included inline with the XML, it is written using the XML Schema definition language (XSD).</span></span> <span data-ttu-id="71bd3-105">Das Schema enthält die Tabellendefinitionen des <xref:System.Data.DataSet> sowie die Beziehungs- und Einschränkungsdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="71bd3-105">The schema contains the table definitions of the <xref:System.Data.DataSet> as well as the relation and constraint definitions.</span></span>  
  
 <span data-ttu-id="71bd3-106">Beim Schreiben eines <xref:System.Data.DataSet> als XML-Daten werden die aktuellen Versionen der Zeilen im <xref:System.Data.DataSet> geschrieben.</span><span class="sxs-lookup"><span data-stu-id="71bd3-106">When a <xref:System.Data.DataSet> is written as XML data, the rows in the <xref:System.Data.DataSet> are written in their current versions.</span></span> <span data-ttu-id="71bd3-107">Das <xref:System.Data.DataSet> kann jedoch auch als DiffGram geschrieben werden, sodass die aktuellen und die ursprünglichen Werte der Zeilen aufgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="71bd3-107">However, the <xref:System.Data.DataSet> can also be written as a DiffGram so that both the current and the original values of the rows will be included.</span></span>  
  
 <span data-ttu-id="71bd3-108">Die XML-Darstellung der <xref:System.Data.DataSet> kann in eine Datei, einen Stream, einen **XmlWriter**oder eine Zeichenfolge geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="71bd3-108">The XML representation of the <xref:System.Data.DataSet> can be written to a file, a stream, an **XmlWriter**, or a string.</span></span> <span data-ttu-id="71bd3-109">Durch diese Auswahl sind Sie äußerst flexibel bei der Übertragung der XML-Darstellung des <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="71bd3-109">These choices provide great flexibility for how you transport the XML representation of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="71bd3-110">Um die XML-Darstellung des <xref:System.Data.DataSet> als Zeichenfolge zu erhalten, verwenden Sie die **GetXml** -Methode, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="71bd3-110">To obtain the XML representation of the <xref:System.Data.DataSet> as a string, use the **GetXml** method as shown in the following example.</span></span>  
  
```vb  
Dim xmlDS As String = custDS.GetXml()  
```  
  
```csharp  
string xmlDS = custDS.GetXml();  
```  
  
 <span data-ttu-id="71bd3-111">**GetXml** gibt die XML-Darstellung der <xref:System.Data.DataSet> ohne Schema Informationen zurück.</span><span class="sxs-lookup"><span data-stu-id="71bd3-111">**GetXml** returns the XML representation of the <xref:System.Data.DataSet> without schema information.</span></span> <span data-ttu-id="71bd3-112"><xref:System.Data.DataSet>Verwenden Sie **GetXmlSchema**, um die Schema Informationen aus dem (als XML-Schema) in eine Zeichenfolge zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="71bd3-112">To write the schema information from the <xref:System.Data.DataSet> (as XML Schema) to a string, use **GetXmlSchema**.</span></span>  
  
 <span data-ttu-id="71bd3-113">Um einen <xref:System.Data.DataSet> in eine Datei, einen Stream oder einen **XmlWriter**zu schreiben, verwenden Sie die Methode " **Write texml** ".</span><span class="sxs-lookup"><span data-stu-id="71bd3-113">To write a <xref:System.Data.DataSet> to a file, stream, or **XmlWriter**, use the **WriteXml** method.</span></span> <span data-ttu-id="71bd3-114">Der erste Parameter, den Sie an " **Write texml** " übergeben, ist das Ziel der XML-Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="71bd3-114">The first parameter you pass to **WriteXml** is the destination of the XML output.</span></span> <span data-ttu-id="71bd3-115">Übergeben Sie z. b. eine Zeichenfolge mit einem Dateinamen, einem **System. IO. TextWriter** -Objekt usw.</span><span class="sxs-lookup"><span data-stu-id="71bd3-115">For example, pass a string containing a file name, a **System.IO.TextWriter** object, and so on.</span></span> <span data-ttu-id="71bd3-116">Sie können einen optionalen zweiten Parameter eines **xmlschreitemode** -Parameters übergeben, um anzugeben, wie die XML-Ausgabe geschrieben werden soll.</span><span class="sxs-lookup"><span data-stu-id="71bd3-116">You can pass an optional second parameter of an **XmlWriteMode** to specify how the XML output is to be written.</span></span>  
  
 <span data-ttu-id="71bd3-117">In der folgenden Tabelle sind die Optionen für **xmlschreitemode**aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="71bd3-117">The following table shows the options for **XmlWriteMode**.</span></span>  
  
|<span data-ttu-id="71bd3-118">"XmlWriteMode"-Option</span><span class="sxs-lookup"><span data-stu-id="71bd3-118">XmlWriteMode option</span></span>|<span data-ttu-id="71bd3-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71bd3-119">Description</span></span>|  
|-------------------------|-----------------|  
|<span data-ttu-id="71bd3-120">**IgnoreSchema**</span><span class="sxs-lookup"><span data-stu-id="71bd3-120">**IgnoreSchema**</span></span>|<span data-ttu-id="71bd3-121">Schreibt den aktuellen Inhalt des <xref:System.Data.DataSet> ohne XML-Schema als XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="71bd3-121">Writes the current contents of the <xref:System.Data.DataSet> as XML data, without an XML Schema.</span></span> <span data-ttu-id="71bd3-122">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="71bd3-122">This is the default.</span></span>|  
|<span data-ttu-id="71bd3-123">**WriteSchema**</span><span class="sxs-lookup"><span data-stu-id="71bd3-123">**WriteSchema**</span></span>|<span data-ttu-id="71bd3-124">Schreibt den aktuellen Inhalt des <xref:System.Data.DataSet> als XML-Daten mit der relationalen Struktur als XML-Inlineschema.</span><span class="sxs-lookup"><span data-stu-id="71bd3-124">Writes the current contents of the <xref:System.Data.DataSet> as XML data with the relational structure as inline XML Schema.</span></span>|  
|<span data-ttu-id="71bd3-125">**DiffGram**</span><span class="sxs-lookup"><span data-stu-id="71bd3-125">**DiffGram**</span></span>|<span data-ttu-id="71bd3-126">Schreibt das gesamte <xref:System.Data.DataSet> als DiffGram, einschließlich der ursprünglichen und aktuellen Werte.</span><span class="sxs-lookup"><span data-stu-id="71bd3-126">Writes the entire <xref:System.Data.DataSet> as a DiffGram, including original and current values.</span></span> <span data-ttu-id="71bd3-127">Weitere Informationen finden Sie unter [DiffGrams](diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="71bd3-127">For more information, see [DiffGrams](diffgrams.md).</span></span>|  
  
 <span data-ttu-id="71bd3-128">Beim Schreiben einer XML-Darstellung eines-Objekts <xref:System.Data.DataSet> , das **DataRelations** -Objekte enthält, möchten Sie wahrscheinlich, dass der resultierende XML-Code die untergeordneten Zeilen jeder Beziehung innerhalb der zugehörigen übergeordneten Elemente geschachtelt hat.</span><span class="sxs-lookup"><span data-stu-id="71bd3-128">When writing an XML representation of a <xref:System.Data.DataSet> that contains **DataRelation** objects, you will most likely want the resulting XML to have the child rows of each relation nested within their related parent elements.</span></span> <span data-ttu-id="71bd3-129">Um dies zu erreichen, legen Sie die **-Eigenschaft der** Eigenschaft " **DataRelations** " auf " **true** " fest, wenn Sie die **DataRelations** -Eigenschaft hinzufügen <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="71bd3-129">To accomplish this, set the **Nested** property of the **DataRelation** to **true** when you add the **DataRelation** to the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="71bd3-130">Weitere Informationen finden Sie unter Schachteln von [DataRelations](nesting-datarelations.md)-Elementen.</span><span class="sxs-lookup"><span data-stu-id="71bd3-130">For more information, see [Nesting DataRelations](nesting-datarelations.md).</span></span>  
  
 <span data-ttu-id="71bd3-131">Im folgenden finden Sie zwei Beispiele für das Schreiben der XML-Darstellung eines <xref:System.Data.DataSet> in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="71bd3-131">The following are two examples of how to write the XML representation of a <xref:System.Data.DataSet> to a file.</span></span> <span data-ttu-id="71bd3-132">Im ersten Beispiel wird der Dateiname für den resultierenden XML-Code als Zeichenfolge an " **Write texml**" weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="71bd3-132">The first example passes the file name for the resulting XML as a string to **WriteXml**.</span></span> <span data-ttu-id="71bd3-133">Im zweiten Beispiel wird ein **System. IO. StreamWriter** -Objekt weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="71bd3-133">The second example passes a **System.IO.StreamWriter** object.</span></span>
  
```vb  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema)  
```  
  
```csharp  
custDS.WriteXml("Customers.xml", XmlWriteMode.WriteSchema);  
```  
  
```vb  
Dim xmlSW As System.IO.StreamWriter = New System.IO.StreamWriter("Customers.xml")  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema)  
xmlSW.Close()  
```  
  
```csharp  
System.IO.StreamWriter xmlSW = new System.IO.StreamWriter("Customers.xml");  
custDS.WriteXml(xmlSW, XmlWriteMode.WriteSchema);  
xmlSW.Close();  
```  
  
## <a name="mapping-columns-to-xml-elements-attributes-and-text"></a><span data-ttu-id="71bd3-134">Zuordnen von Spalten zu XML-Elementen, -Attributen und -Text</span><span class="sxs-lookup"><span data-stu-id="71bd3-134">Mapping Columns to XML Elements, Attributes, and Text</span></span>  

 <span data-ttu-id="71bd3-135">Mithilfe der **ColumnMapping** -Eigenschaft des **datacolenn** -Objekts können Sie angeben, wie eine Spalte einer Tabelle in XML dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="71bd3-135">You can specify how a column of a table is represented in XML using the **ColumnMapping** property of the **DataColumn** object.</span></span> <span data-ttu-id="71bd3-136">In der folgenden Tabelle werden die verschiedenen **MappingType** -Werte für die **ColumnMapping** -Eigenschaft einer Tabellenspalte und die resultierende XML-Datei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="71bd3-136">The following table shows the different **MappingType** values for the **ColumnMapping** property of a table column, and the resulting XML.</span></span>  
  
|<span data-ttu-id="71bd3-137">"MappingType"-Wert</span><span class="sxs-lookup"><span data-stu-id="71bd3-137">MappingType value</span></span>|<span data-ttu-id="71bd3-138">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71bd3-138">Description</span></span>|  
|-----------------------|-----------------|  
|<span data-ttu-id="71bd3-139">**Element**</span><span class="sxs-lookup"><span data-stu-id="71bd3-139">**Element**</span></span>|<span data-ttu-id="71bd3-140">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="71bd3-140">This is the default.</span></span> <span data-ttu-id="71bd3-141">Die Spalte wird als XML-Element geschrieben, wobei ColumnName der Name des Elements ist und der Inhalt der Spalte als Text des Elements geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="71bd3-141">The column is written as an XML element where the ColumnName is the name of the element and the contents of the column are written as the text of the element.</span></span> <span data-ttu-id="71bd3-142">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="71bd3-142">For example:</span></span><br /><br /> `<ColumnName>Column Contents</ColumnName>`|  
|<span data-ttu-id="71bd3-143">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="71bd3-143">**Attribute**</span></span>|<span data-ttu-id="71bd3-144">Die Spalte wird als XML-Attribut des XML-Elements für die aktuelle Zeile geschrieben, wobei ColumnName der Name des Attributs ist und der Inhalt der Spalte als Wert des Attributs geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="71bd3-144">The column is written as an XML attribute of the XML element for the current row where the ColumnName is the name of the attribute and the contents of the column are written as the value of the attribute.</span></span> <span data-ttu-id="71bd3-145">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="71bd3-145">For example:</span></span><br /><br /> `<RowElement ColumnName="Column Contents" />`|  
|<span data-ttu-id="71bd3-146">**SimpleContent**</span><span class="sxs-lookup"><span data-stu-id="71bd3-146">**SimpleContent**</span></span>|<span data-ttu-id="71bd3-147">Der Inhalt der Spalte wird für die aktuelle Zeile als Text in das XML-Element geschrieben.</span><span class="sxs-lookup"><span data-stu-id="71bd3-147">The contents of the column are written as text in the XML element for the current row.</span></span> <span data-ttu-id="71bd3-148">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="71bd3-148">For example:</span></span><br /><br /> `<RowElement>Column Contents</RowElement>`<br /><br /> <span data-ttu-id="71bd3-149">Beachten Sie, dass " **simpleContent** " nicht für eine Spalte einer Tabelle festgelegt werden kann, die über **Element** Spalten oder Beziehungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="71bd3-149">Note that **SimpleContent** cannot be set for a column of a table that has **Element** columns or nested relations.</span></span>|  
|<span data-ttu-id="71bd3-150">**Hidden**</span><span class="sxs-lookup"><span data-stu-id="71bd3-150">**Hidden**</span></span>|<span data-ttu-id="71bd3-151">Die Spalte wird in der XML-Ausgabe nicht geschrieben.</span><span class="sxs-lookup"><span data-stu-id="71bd3-151">The column is not written in the XML output.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71bd3-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71bd3-152">See also</span></span>

- [<span data-ttu-id="71bd3-153">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="71bd3-153">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="71bd3-154">DiffGrams</span><span class="sxs-lookup"><span data-stu-id="71bd3-154">DiffGrams</span></span>](diffgrams.md)
- [<span data-ttu-id="71bd3-155">Verschachteln von "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="71bd3-155">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="71bd3-156">Schreiben von DataSet-Schemainformationen als XSD</span><span class="sxs-lookup"><span data-stu-id="71bd3-156">Writing DataSet Schema Information as XSD</span></span>](writing-dataset-schema-information-as-xsd.md)
- [<span data-ttu-id="71bd3-157">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="71bd3-157">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="71bd3-158">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="71bd3-158">ADO.NET Overview</span></span>](../ado-net-overview.md)
