---
title: Ableiten von Beziehungen
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: 9833966fa5a16bef70a6ae2b9ca618fde0e05fbb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="inferring-relationships"></a><span data-ttu-id="07d52-102">Ableiten von Beziehungen</span><span class="sxs-lookup"><span data-stu-id="07d52-102">Inferring Relationships</span></span>
<span data-ttu-id="07d52-103">Wenn ein als Tabelle hergeleitetes Element ein ebenfalls als Tabelle hergeleitetes untergeordnetes Element aufweist, wird zwischen den beiden Tabellen eine <xref:System.Data.DataRelation> erstellt.</span><span class="sxs-lookup"><span data-stu-id="07d52-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="07d52-104">Eine neue Spalte mit dem Namen **ParentTableName_Id** wird für das übergeordnete Element erstellten Tabelle, und für das untergeordnete Element erstellten Tabelle hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="07d52-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="07d52-105">Die **ColumnMapping** -Eigenschaft dieser Identitätsspalte wird auf festgelegt **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="07d52-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="07d52-106">Die Spalte wird automatisch erhöhenden Primärschlüssel für die übergeordnete Tabelle und verwendet werden, für die **DataRelation** zwischen den beiden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="07d52-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="07d52-107">Der Datentyp der hinzugefügten Identitätsspalte **System. Int32**, im Gegensatz zum Datentyp aller anderen hergeleiteten Spalten **System.String**.</span><span class="sxs-lookup"><span data-stu-id="07d52-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="07d52-108">Ein <xref:System.Data.ForeignKeyConstraint> mit **DeleteRule** = **Cascade** wird auch mit der neuen Spalte in der über- und untergeordneten Tabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="07d52-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="07d52-109">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="07d52-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="07d52-110">Die Herleitung wird zwei Tabellen: **Element1** und **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="07d52-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="07d52-111">Die **Element1** Tabelle weist zwei Spalten: **Element1_Id** und **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="07d52-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="07d52-112">Die **ColumnMapping** Eigenschaft von der **Element1_Id** Spaltensatz zu **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="07d52-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="07d52-113">Die **ColumnMapping** Eigenschaft von der **ChildElement2** Spaltensatz zu **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="07d52-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="07d52-114">Die **Element1_Id** Spaltensatz wird als Primärschlüssel von der **Element1** Tabelle.</span><span class="sxs-lookup"><span data-stu-id="07d52-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="07d52-115">Die **ChildElement1** Tabelle weist drei Spalten: **attr1**, **attr2** und **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="07d52-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="07d52-116">Die **ColumnMapping** -Eigenschaft für die **attr1** und **attr2** Spalten festgelegt, um **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="07d52-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="07d52-117">Die **ColumnMapping** Eigenschaft von der **Element1_Id** Spaltensatz zu **MappingType.Hidden**.</span><span class="sxs-lookup"><span data-stu-id="07d52-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="07d52-118">Ein **DataRelation** und **ForeignKeyConstraint** mithilfe erstellt die **Element1_Id** Spalten aus beiden Tabellen.</span><span class="sxs-lookup"><span data-stu-id="07d52-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="07d52-119">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="07d52-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="07d52-120">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="07d52-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="07d52-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="07d52-121">Element1_Id</span></span>|<span data-ttu-id="07d52-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="07d52-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="07d52-123">0</span><span class="sxs-lookup"><span data-stu-id="07d52-123">0</span></span>|<span data-ttu-id="07d52-124">Text2</span><span class="sxs-lookup"><span data-stu-id="07d52-124">Text2</span></span>|  
  
 <span data-ttu-id="07d52-125">**Table:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="07d52-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="07d52-126">attr1</span><span class="sxs-lookup"><span data-stu-id="07d52-126">attr1</span></span>|<span data-ttu-id="07d52-127">attr2</span><span class="sxs-lookup"><span data-stu-id="07d52-127">attr2</span></span>|<span data-ttu-id="07d52-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="07d52-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="07d52-129">value1</span><span class="sxs-lookup"><span data-stu-id="07d52-129">value1</span></span>|<span data-ttu-id="07d52-130">value2</span><span class="sxs-lookup"><span data-stu-id="07d52-130">value2</span></span>|<span data-ttu-id="07d52-131">0</span><span class="sxs-lookup"><span data-stu-id="07d52-131">0</span></span>|  
  
 <span data-ttu-id="07d52-132">**DataRelation:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="07d52-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="07d52-133">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="07d52-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="07d52-134">**ParentColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="07d52-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="07d52-135">**UntergeordneteTabelle:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="07d52-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="07d52-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="07d52-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="07d52-137">**Geschachtelte:** "true"</span><span class="sxs-lookup"><span data-stu-id="07d52-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="07d52-138">**ForeignKeyConstraint:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="07d52-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="07d52-139">**Spalte:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="07d52-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="07d52-140">**ParentTable:** Element1</span><span class="sxs-lookup"><span data-stu-id="07d52-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="07d52-141">**UntergeordneteTabelle:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="07d52-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="07d52-142">**DeleteRule:** Cascade</span><span class="sxs-lookup"><span data-stu-id="07d52-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="07d52-143">**AcceptRejectRule:** None</span><span class="sxs-lookup"><span data-stu-id="07d52-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07d52-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07d52-144">See Also</span></span>  
 [<span data-ttu-id="07d52-145">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="07d52-145">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="07d52-146">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="07d52-146">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="07d52-147">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="07d52-147">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="07d52-148">Schachteln von DataRelations</span><span class="sxs-lookup"><span data-stu-id="07d52-148">Nesting DataRelations</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)  
 [<span data-ttu-id="07d52-149">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="07d52-149">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="07d52-150">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="07d52-150">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="07d52-151">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="07d52-151">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
