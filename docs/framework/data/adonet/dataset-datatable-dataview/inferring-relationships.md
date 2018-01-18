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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 79f79c1dbc74b98cff10de81c2bd7bd32d7d286b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-relationships"></a><span data-ttu-id="faa7d-102">Ableiten von Beziehungen</span><span class="sxs-lookup"><span data-stu-id="faa7d-102">Inferring Relationships</span></span>
<span data-ttu-id="faa7d-103">Wenn ein als Tabelle hergeleitetes Element ein ebenfalls als Tabelle hergeleitetes untergeordnetes Element aufweist, wird zwischen den beiden Tabellen eine <xref:System.Data.DataRelation> erstellt.</span><span class="sxs-lookup"><span data-stu-id="faa7d-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="faa7d-104">Eine neue Spalte mit dem Namen **ParentTableName_Id** wird für das übergeordnete Element erstellten Tabelle, und für das untergeordnete Element erstellten Tabelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="faa7d-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="faa7d-105">Die **ColumnMapping** -Eigenschaft dieser Identitätsspalte wird auf festgelegt **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="faa7d-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="faa7d-106">Die Spalte wird automatisch erhöhenden Primärschlüssel für die übergeordnete Tabelle und verwendet werden, für die **DataRelation** zwischen den beiden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="faa7d-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="faa7d-107">Der Datentyp der hinzugefügten Identitätsspalte **System. Int32**, im Gegensatz zum Datentyp aller anderen hergeleiteten Spalten **System.String**.</span><span class="sxs-lookup"><span data-stu-id="faa7d-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="faa7d-108">Ein <xref:System.Data.ForeignKeyConstraint> mit **DeleteRule** = **Cascade** wird auch mit der neuen Spalte in der über- und untergeordneten Tabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="faa7d-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="faa7d-109">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="faa7d-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="faa7d-110">Die Herleitung wird zwei Tabellen: **Element1** und **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="faa7d-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="faa7d-111">Die **Element1** Tabelle weist zwei Spalten: **Element1_Id** und **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="faa7d-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="faa7d-112">Die **ColumnMapping** Eigenschaft von der **Element1_Id** Spaltensatz zu **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="faa7d-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="faa7d-113">Die **ColumnMapping** Eigenschaft von der **ChildElement2** Spaltensatz zu **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="faa7d-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="faa7d-114">Die **Element1_Id** Spaltensatz wird als Primärschlüssel von der **Element1** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="faa7d-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="faa7d-115">Die **ChildElement1** Tabelle weist drei Spalten: **attr1**, **attr2** und **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="faa7d-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="faa7d-116">Die **ColumnMapping** -Eigenschaft für die **attr1** und **attr2** Spalten festgelegt, um **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="faa7d-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="faa7d-117">Die **ColumnMapping** Eigenschaft von der **Element1_Id** Spaltensatz zu **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="faa7d-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="faa7d-118">Ein **DataRelation** und **ForeignKeyConstraint** mithilfe erstellt die **Element1_Id** Spalten aus beiden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="faa7d-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="faa7d-119">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="faa7d-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="faa7d-120">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="faa7d-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="faa7d-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="faa7d-121">Element1_Id</span></span>|<span data-ttu-id="faa7d-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="faa7d-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="faa7d-123">0</span><span class="sxs-lookup"><span data-stu-id="faa7d-123">0</span></span>|<span data-ttu-id="faa7d-124">Text2</span><span class="sxs-lookup"><span data-stu-id="faa7d-124">Text2</span></span>|  
  
 <span data-ttu-id="faa7d-125">**Table:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="faa7d-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="faa7d-126">attr1</span><span class="sxs-lookup"><span data-stu-id="faa7d-126">attr1</span></span>|<span data-ttu-id="faa7d-127">attr2</span><span class="sxs-lookup"><span data-stu-id="faa7d-127">attr2</span></span>|<span data-ttu-id="faa7d-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="faa7d-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="faa7d-129">value1</span><span class="sxs-lookup"><span data-stu-id="faa7d-129">value1</span></span>|<span data-ttu-id="faa7d-130">value2</span><span class="sxs-lookup"><span data-stu-id="faa7d-130">value2</span></span>|<span data-ttu-id="faa7d-131">0</span><span class="sxs-lookup"><span data-stu-id="faa7d-131">0</span></span>|  
  
 <span data-ttu-id="faa7d-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="faa7d-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="faa7d-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="faa7d-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="faa7d-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="faa7d-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="faa7d-135">**UntergeordneteTabelle:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="faa7d-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="faa7d-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="faa7d-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="faa7d-137">**Geschachtelte:** "true"</span><span class="sxs-lookup"><span data-stu-id="faa7d-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="faa7d-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="faa7d-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="faa7d-139">**Spalte:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="faa7d-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="faa7d-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="faa7d-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="faa7d-141">**UntergeordneteTabelle:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="faa7d-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="faa7d-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="faa7d-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="faa7d-143">**AcceptRejectRule:** None</span><span class="sxs-lookup"><span data-stu-id="faa7d-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faa7d-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="faa7d-144">See Also</span></span>  
 [<span data-ttu-id="faa7d-145">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="faa7d-145">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="faa7d-146">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="faa7d-146">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="faa7d-147">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="faa7d-147">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="faa7d-148">Schachteln von DataRelations</span><span class="sxs-lookup"><span data-stu-id="faa7d-148">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [<span data-ttu-id="faa7d-149">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="faa7d-149">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="faa7d-150">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="faa7d-150">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="faa7d-151">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="faa7d-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
