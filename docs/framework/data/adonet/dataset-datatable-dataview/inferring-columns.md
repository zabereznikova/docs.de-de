---
title: Ableiten von Spalten
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 45d27b78b5d83d333c16192e172e7b7e3dd88c10
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164700"
---
# <a name="inferring-columns"></a><span data-ttu-id="26aa6-102">Ableiten von Spalten</span><span class="sxs-lookup"><span data-stu-id="26aa6-102">Inferring Columns</span></span>

<span data-ttu-id="26aa6-103">Nachdem von ADO.NET anhand eines XML-Dokuments ermittelt wurde, welche Elemente als Tabellen für ein <xref:System.Data.DataSet>-Objekt abgeleitet werden sollen, werden die Spalten für diese Tabellen abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="26aa6-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="26aa6-104">ADO.NET 2,0 hat eine neue Rückschluss-Engine eingeführt, die einen stark typisierten Datentyp für jedes **simpleType** -Element ableitet.</span><span class="sxs-lookup"><span data-stu-id="26aa6-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="26aa6-105">In früheren Versionen war der Datentyp eines abgeleitet **simpleType** -Elements immer " **xsd: String**".</span><span class="sxs-lookup"><span data-stu-id="26aa6-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="26aa6-106">Migration und Abwärtskompatibilität</span><span class="sxs-lookup"><span data-stu-id="26aa6-106">Migration and Backward Compatibility</span></span>  

 <span data-ttu-id="26aa6-107">Die "read **XML** "-Methode nimmt ein Argument vom Typ " **InferSchema**" an.</span><span class="sxs-lookup"><span data-stu-id="26aa6-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="26aa6-108">Mit diesem Argument können Sie das mit vorherigen Versionen kompatible Herleitungsverhalten angeben.</span><span class="sxs-lookup"><span data-stu-id="26aa6-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="26aa6-109">In der folgenden Tabelle sind die verfügbaren Werte für die **InferSchema** -Enumeration aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="26aa6-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="26aa6-110">Stellt Abwärtskompatibilität bereit, indem immer ein einfacher Typ als <xref:System.String> hergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="26aa6-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="26aa6-111">Leitet einen Datentyp mit strikter Typbindung her.</span><span class="sxs-lookup"><span data-stu-id="26aa6-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="26aa6-112">Löst bei der Verwendung mit einer <xref:System.Data.DataTable> eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="26aa6-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="26aa6-113">Ignoriert alle Inlineschemata und liest Daten in das vorhandene <xref:System.Data.DataSet>-Schema ein.</span><span class="sxs-lookup"><span data-stu-id="26aa6-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="26aa6-114">Attributes</span><span class="sxs-lookup"><span data-stu-id="26aa6-114">Attributes</span></span>  

 <span data-ttu-id="26aa6-115">Wie in [ableiten von Tabellen](inferring-tables.md)definiert, wird ein Element mit Attributen als Tabelle abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="26aa6-115">As defined in [Inferring Tables](inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="26aa6-116">Die Attribute dieses Elements werden anschließend als Spalten für die entsprechende Tabelle hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="26aa6-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="26aa6-117">Die **ColumnMapping** -Eigenschaft der Spalten wird auf **MappingType. Attribute**festgelegt, um sicherzustellen, dass die Spaltennamen als Attribute geschrieben werden, wenn das Schema in XML zurückgeschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="26aa6-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="26aa6-118">Die Werte der Attribute werden in einer Tabellenzeile gespeichert.</span><span class="sxs-lookup"><span data-stu-id="26aa6-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="26aa6-119">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="26aa6-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="26aa6-120">Der Rückschluss Prozess erzeugt eine Tabelle mit dem Namen **Element1** mit zwei Spalten: **attr1** und **attr2**.</span><span class="sxs-lookup"><span data-stu-id="26aa6-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="26aa6-121">Die **ColumnMapping** -Eigenschaft der beiden Spalten wird auf **MappingType. Attribute**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="26aa6-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="26aa6-122">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="26aa6-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="26aa6-123">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="26aa6-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="26aa6-124">attr1</span><span class="sxs-lookup"><span data-stu-id="26aa6-124">attr1</span></span>|<span data-ttu-id="26aa6-125">attr2</span><span class="sxs-lookup"><span data-stu-id="26aa6-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="26aa6-126">value1</span><span class="sxs-lookup"><span data-stu-id="26aa6-126">value1</span></span>|<span data-ttu-id="26aa6-127">value2</span><span class="sxs-lookup"><span data-stu-id="26aa6-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="26aa6-128">Elemente ohne Attribute oder untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26aa6-128">Elements Without Attributes or Child Elements</span></span>  

 <span data-ttu-id="26aa6-129">Ein Element ohne untergeordnete Elemente oder Attribute wird als Spalte hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="26aa6-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="26aa6-130">Die **ColumnMapping** -Eigenschaft der Spalte wird auf **MappingType. Element**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="26aa6-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="26aa6-131">Der Text der untergeordneten Elemente wird in einer Tabellenzeile gespeichert.</span><span class="sxs-lookup"><span data-stu-id="26aa6-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="26aa6-132">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="26aa6-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="26aa6-133">Der Rückschluss Prozess erzeugt eine Tabelle mit dem Namen **Element1** mit zwei Spalten: **ChildElement1** und **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="26aa6-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="26aa6-134">Die **ColumnMapping** -Eigenschaft der beiden Spalten wird auf **MappingType. Element**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="26aa6-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="26aa6-135">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="26aa6-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="26aa6-136">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="26aa6-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="26aa6-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="26aa6-137">ChildElement1</span></span>|<span data-ttu-id="26aa6-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="26aa6-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="26aa6-139">Text1</span><span class="sxs-lookup"><span data-stu-id="26aa6-139">Text1</span></span>|<span data-ttu-id="26aa6-140">Text2</span><span class="sxs-lookup"><span data-stu-id="26aa6-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="26aa6-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26aa6-141">See also</span></span>

- [<span data-ttu-id="26aa6-142">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="26aa6-142">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="26aa6-143">Laden eines "DataSets" aus XML</span><span class="sxs-lookup"><span data-stu-id="26aa6-143">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="26aa6-144">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="26aa6-144">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="26aa6-145">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="26aa6-145">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="26aa6-146">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="26aa6-146">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="26aa6-147">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="26aa6-147">ADO.NET Overview</span></span>](../ado-net-overview.md)
