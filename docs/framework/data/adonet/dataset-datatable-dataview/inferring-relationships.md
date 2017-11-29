---
title: Ableiten von Beziehungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 41c73ac31105cdae0a23c2367211747dee8d44f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-relationships"></a><span data-ttu-id="fc353-102">Ableiten von Beziehungen</span><span class="sxs-lookup"><span data-stu-id="fc353-102">Inferring Relationships</span></span>
<span data-ttu-id="fc353-103">Wenn ein als Tabelle hergeleitetes Element ein ebenfalls als Tabelle hergeleitetes untergeordnetes Element aufweist, wird zwischen den beiden Tabellen eine <xref:System.Data.DataRelation> erstellt.</span><span class="sxs-lookup"><span data-stu-id="fc353-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="fc353-104">Eine neue Spalte mit dem Namen **ParentTableName_Id** wird für das übergeordnete Element erstellten Tabelle, und für das untergeordnete Element erstellten Tabelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="fc353-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="fc353-105">Die **ColumnMapping** -Eigenschaft dieser Identitätsspalte wird auf festgelegt **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="fc353-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="fc353-106">Die Spalte wird automatisch erhöhenden Primärschlüssel für die übergeordnete Tabelle und verwendet werden, für die **DataRelation** zwischen den beiden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="fc353-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="fc353-107">Der Datentyp der hinzugefügten Identitätsspalte **System. Int32**, im Gegensatz zum Datentyp aller anderen hergeleiteten Spalten **System.String**.</span><span class="sxs-lookup"><span data-stu-id="fc353-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="fc353-108">Ein <xref:System.Data.ForeignKeyConstraint> mit **DeleteRule** = **Cascade** wird auch mit der neuen Spalte in der über- und untergeordneten Tabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="fc353-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="fc353-109">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="fc353-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="fc353-110">Die Herleitung wird zwei Tabellen: **Element1** und **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="fc353-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="fc353-111">Die **Element1** Tabelle weist zwei Spalten: **Element1_Id** und **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="fc353-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="fc353-112">Die **ColumnMapping** Eigenschaft von der **Element1_Id** Spaltensatz zu **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="fc353-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="fc353-113">Die **ColumnMapping** Eigenschaft von der **ChildElement2** Spaltensatz zu **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="fc353-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="fc353-114">Die **Element1_Id** Spaltensatz wird als Primärschlüssel von der **Element1** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="fc353-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="fc353-115">Die **ChildElement1** Tabelle weist drei Spalten: **attr1**, **attr2** und **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="fc353-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="fc353-116">Die **ColumnMapping** -Eigenschaft für die **attr1** und **attr2** Spalten festgelegt, um **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="fc353-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="fc353-117">Die **ColumnMapping** Eigenschaft von der **Element1_Id** Spaltensatz zu **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="fc353-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="fc353-118">Ein **DataRelation** und **ForeignKeyConstraint** mithilfe erstellt die **Element1_Id** Spalten aus beiden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="fc353-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="fc353-119">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="fc353-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="fc353-120">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="fc353-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="fc353-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="fc353-121">Element1_Id</span></span>|<span data-ttu-id="fc353-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="fc353-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="fc353-123">0</span><span class="sxs-lookup"><span data-stu-id="fc353-123">0</span></span>|<span data-ttu-id="fc353-124">Text2</span><span class="sxs-lookup"><span data-stu-id="fc353-124">Text2</span></span>|  
  
 <span data-ttu-id="fc353-125">**Table:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="fc353-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="fc353-126">attr1</span><span class="sxs-lookup"><span data-stu-id="fc353-126">attr1</span></span>|<span data-ttu-id="fc353-127">attr2</span><span class="sxs-lookup"><span data-stu-id="fc353-127">attr2</span></span>|<span data-ttu-id="fc353-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="fc353-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="fc353-129">value1</span><span class="sxs-lookup"><span data-stu-id="fc353-129">value1</span></span>|<span data-ttu-id="fc353-130">value2</span><span class="sxs-lookup"><span data-stu-id="fc353-130">value2</span></span>|<span data-ttu-id="fc353-131">0</span><span class="sxs-lookup"><span data-stu-id="fc353-131">0</span></span>|  
  
 <span data-ttu-id="fc353-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="fc353-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="fc353-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="fc353-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="fc353-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="fc353-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="fc353-135">**UntergeordneteTabelle:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="fc353-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="fc353-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="fc353-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="fc353-137">**Geschachtelte:** "true"</span><span class="sxs-lookup"><span data-stu-id="fc353-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="fc353-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="fc353-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="fc353-139">**Spalte:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="fc353-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="fc353-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="fc353-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="fc353-141">**UntergeordneteTabelle:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="fc353-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="fc353-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="fc353-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="fc353-143">**AcceptRejectRule:** None</span><span class="sxs-lookup"><span data-stu-id="fc353-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc353-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc353-144">See Also</span></span>  
 [<span data-ttu-id="fc353-145">Ableiten von relationalen DataSet-Struktur von XML</span><span class="sxs-lookup"><span data-stu-id="fc353-145">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="fc353-146">Beim Laden eines Datasets aus XML</span><span class="sxs-lookup"><span data-stu-id="fc353-146">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="fc353-147">Beim Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="fc353-147">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="fc353-148">Verschachteln von "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="fc353-148">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [<span data-ttu-id="fc353-149">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="fc353-149">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="fc353-150">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="fc353-150">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="fc353-151">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="fc353-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
