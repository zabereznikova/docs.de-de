---
title: Ableiten von Spalten
ms.date: 03/30/2017
ms.assetid: 0e022699-c922-454c-93e2-957dd7e7247a
ms.openlocfilehash: 56de4b4d6cf704473ec46957625ad1c376f595c2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43671409"
---
# <a name="inferring-columns"></a><span data-ttu-id="d4edf-102">Ableiten von Spalten</span><span class="sxs-lookup"><span data-stu-id="d4edf-102">Inferring Columns</span></span>
<span data-ttu-id="d4edf-103">Nachdem von ADO.NET anhand eines XML-Dokuments ermittelt wurde, welche Elemente als Tabellen für ein <xref:System.Data.DataSet>-Objekt abgeleitet werden sollen, werden die Spalten für diese Tabellen abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="d4edf-103">After ADO.NET has determined from an XML document which elements to infer as tables for a <xref:System.Data.DataSet>, it then infers the columns for those tables.</span></span> <span data-ttu-id="d4edf-104">Neu in ADO.NET 2.0 eingeführt, eine neues Schema Rückschluss-Engine, die einen stark typisierten Datentyp für jede herleitet **SimpleType** Element.</span><span class="sxs-lookup"><span data-stu-id="d4edf-104">ADO.NET 2.0 introduced a new schema inference engine that infers a strongly typed data type for each **simpleType** element.</span></span> <span data-ttu-id="d4edf-105">In früheren Versionen der Datentyp eines hergeleiteten **SimpleType** Element wurde immer **xsd: String**.</span><span class="sxs-lookup"><span data-stu-id="d4edf-105">In previous versions, the data type of an inferred **simpleType** element was always **xsd:string**.</span></span>  
  
## <a name="migration-and-backward-compatibility"></a><span data-ttu-id="d4edf-106">Migration und Abwärtskompatibilität</span><span class="sxs-lookup"><span data-stu-id="d4edf-106">Migration and Backward Compatibility</span></span>  
 <span data-ttu-id="d4edf-107">Die **ReadXml** Methode akzeptiert ein Argument des Typs **InferSchema**.</span><span class="sxs-lookup"><span data-stu-id="d4edf-107">The **ReadXml** method takes an argument of type **InferSchema**.</span></span> <span data-ttu-id="d4edf-108">Mit diesem Argument können Sie das mit vorherigen Versionen kompatible Herleitungsverhalten angeben.</span><span class="sxs-lookup"><span data-stu-id="d4edf-108">This argument allows you to specify inference behavior compatible with previous versions.</span></span> <span data-ttu-id="d4edf-109">Die verfügbaren Werte für die **InferSchema** Enumeration in der folgenden Tabelle dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d4edf-109">The available values for the **InferSchema** enumeration are shown in the following table.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferSchema>  
 <span data-ttu-id="d4edf-110">Stellt Abwärtskompatibilität bereit, indem immer ein einfacher Typ als <xref:System.String> hergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="d4edf-110">Provides backward compatibility by always inferring a simple type as <xref:System.String>.</span></span>  
  
 <xref:System.Data.XmlReadMode.InferTypedSchema>  
 <span data-ttu-id="d4edf-111">Leitet einen Datentyp mit strikter Typbindung her.</span><span class="sxs-lookup"><span data-stu-id="d4edf-111">Infers a strongly typed data type.</span></span> <span data-ttu-id="d4edf-112">Löst bei der Verwendung mit einer <xref:System.Data.DataTable> eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="d4edf-112">Throws an exception if used with a <xref:System.Data.DataTable>.</span></span>  
  
 <xref:System.Data.XmlReadMode.IgnoreSchema>  
 <span data-ttu-id="d4edf-113">Ignoriert alle Inlineschemata und liest Daten in das vorhandene <xref:System.Data.DataSet>-Schema ein.</span><span class="sxs-lookup"><span data-stu-id="d4edf-113">Ignores any inline schema and reads data into the existing <xref:System.Data.DataSet> schema.</span></span>  
  
## <a name="attributes"></a><span data-ttu-id="d4edf-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="d4edf-114">Attributes</span></span>  
 <span data-ttu-id="d4edf-115">Gemäß [Herleiten von Tabellen](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), wird ein Element mit Attributen als Tabelle hergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="d4edf-115">As defined in [Inferring Tables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-tables.md), an element with attributes will be inferred as a table.</span></span> <span data-ttu-id="d4edf-116">Die Attribute dieses Elements werden anschließend als Spalten für die entsprechende Tabelle hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d4edf-116">The attributes of that element will then be inferred as columns for the table.</span></span> <span data-ttu-id="d4edf-117">Die **ColumnMapping** -Eigenschaft der Spalten auf festgelegt **MappingType.Attribute**, um sicherzustellen, dass die Spaltennamen werden als Attribute geschrieben werden, wenn das Schema in XML zurückgeschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="d4edf-117">The **ColumnMapping** property of the columns will be set to **MappingType.Attribute**, to ensure that the column names will be written as attributes if the schema is written back to XML.</span></span> <span data-ttu-id="d4edf-118">Die Werte der Attribute werden in einer Tabellenzeile gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d4edf-118">The values of the attributes are stored in a row in the table.</span></span> <span data-ttu-id="d4edf-119">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="d4edf-119">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d4edf-120">Die Herleitung wird einer Tabelle namens **Element1** mit zwei Spalten, **attr1** und **attr2**.</span><span class="sxs-lookup"><span data-stu-id="d4edf-120">The inference process will produce a table named **Element1** with two columns, **attr1** and **attr2**.</span></span> <span data-ttu-id="d4edf-121">Die **ColumnMapping** -Eigenschaft der beiden Spalten wird festgelegt **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="d4edf-121">The **ColumnMapping** property of both columns will be set to **MappingType.Attribute**.</span></span>  
  
 <span data-ttu-id="d4edf-122">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d4edf-122">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d4edf-123">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="d4edf-123">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d4edf-124">attr1</span><span class="sxs-lookup"><span data-stu-id="d4edf-124">attr1</span></span>|<span data-ttu-id="d4edf-125">attr2</span><span class="sxs-lookup"><span data-stu-id="d4edf-125">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="d4edf-126">value1</span><span class="sxs-lookup"><span data-stu-id="d4edf-126">value1</span></span>|<span data-ttu-id="d4edf-127">value2</span><span class="sxs-lookup"><span data-stu-id="d4edf-127">value2</span></span>|  
  
## <a name="elements-without-attributes-or-child-elements"></a><span data-ttu-id="d4edf-128">Elemente ohne Attribute oder untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d4edf-128">Elements Without Attributes or Child Elements</span></span>  
 <span data-ttu-id="d4edf-129">Ein Element ohne untergeordnete Elemente oder Attribute wird als Spalte hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="d4edf-129">If an element has no child elements or attributes, it will be inferred as a column.</span></span> <span data-ttu-id="d4edf-130">Die **ColumnMapping** -Eigenschaft der Spalte auf festgelegt **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="d4edf-130">The **ColumnMapping** property of the column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="d4edf-131">Der Text der untergeordneten Elemente wird in einer Tabellenzeile gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d4edf-131">The text for child elements is stored in a row in the table.</span></span> <span data-ttu-id="d4edf-132">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="d4edf-132">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="d4edf-133">Die Herleitung wird einer Tabelle namens **Element1** mit zwei Spalten, **ChildElement1** und **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="d4edf-133">The inference process will produce a table named **Element1** with two columns, **ChildElement1** and **ChildElement2**.</span></span> <span data-ttu-id="d4edf-134">Die **ColumnMapping** -Eigenschaft der beiden Spalten wird festgelegt **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="d4edf-134">The **ColumnMapping** property of both columns will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="d4edf-135">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="d4edf-135">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="d4edf-136">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="d4edf-136">**Table:** Element1</span></span>  
  
|<span data-ttu-id="d4edf-137">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="d4edf-137">ChildElement1</span></span>|<span data-ttu-id="d4edf-138">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="d4edf-138">ChildElement2</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="d4edf-139">Text1</span><span class="sxs-lookup"><span data-stu-id="d4edf-139">Text1</span></span>|<span data-ttu-id="d4edf-140">Text2</span><span class="sxs-lookup"><span data-stu-id="d4edf-140">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d4edf-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4edf-141">See Also</span></span>  
 [<span data-ttu-id="d4edf-142">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="d4edf-142">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="d4edf-143">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="d4edf-143">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="d4edf-144">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="d4edf-144">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="d4edf-145">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="d4edf-145">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="d4edf-146">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="d4edf-146">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="d4edf-147">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="d4edf-147">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
