---
title: Ableiten von Beziehungen
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: ee691eee95c34afdb6374cdd7448d4b44ece3055
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177565"
---
# <a name="inferring-relationships"></a><span data-ttu-id="4a11a-102">Ableiten von Beziehungen</span><span class="sxs-lookup"><span data-stu-id="4a11a-102">Inferring Relationships</span></span>

<span data-ttu-id="4a11a-103">Wenn ein als Tabelle hergeleitetes Element ein ebenfalls als Tabelle hergeleitetes untergeordnetes Element aufweist, wird zwischen den beiden Tabellen eine <xref:System.Data.DataRelation> erstellt.</span><span class="sxs-lookup"><span data-stu-id="4a11a-103">If an element that is inferred as a table has a child element that is also inferred as a table, a <xref:System.Data.DataRelation> will be created between the two tables.</span></span> <span data-ttu-id="4a11a-104">Eine neue Spalte mit dem Namen **ParentTableName_Id** wird sowohl der für das übergeordnete Element erstellten Tabelle als auch der Tabelle hinzugefügt, die für das untergeordnete Element erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4a11a-104">A new column with a name of **ParentTableName_Id** will be added to both the table created for the parent element, and the table created for the child element.</span></span> <span data-ttu-id="4a11a-105">Die **ColumnMapping** -Eigenschaft dieser Identitäts Spalte wird auf **MappingType. Hidden**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4a11a-105">The **ColumnMapping** property of this identity column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="4a11a-106">Bei der Spalte handelt es sich um einen automatisch inkrementierenden Primärschlüssel für die übergeordnete Tabelle, der für die **DataRelations** -Beziehung zwischen den beiden Tabellen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4a11a-106">The column will be an auto-incrementing primary key for the parent table, and will be used for the **DataRelation** between the two tables.</span></span> <span data-ttu-id="4a11a-107">Der Datentyp der hinzugefügten Identitäts Spalte ist **System. Int32**, anders als beim Datentyp aller anderen abgelegten Spalten, d. h. **System. String**.</span><span class="sxs-lookup"><span data-stu-id="4a11a-107">The data type of the added identity column will be **System.Int32**, unlike the data type of all other inferred columns, which is **System.String**.</span></span> <span data-ttu-id="4a11a-108"><xref:System.Data.ForeignKeyConstraint> **DeleteRule**  =  Mithilfe der neuen Spalte in der übergeordneten und der untergeordneten Tabelle wird auch ein mit DeleteRule**Cascade** erstellt.</span><span class="sxs-lookup"><span data-stu-id="4a11a-108">A <xref:System.Data.ForeignKeyConstraint> with **DeleteRule** = **Cascade** will also be created using the new column in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="4a11a-109">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="4a11a-109">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="4a11a-110">Der Rückschluss Prozess erzeugt zwei Tabellen: **Element1** und **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="4a11a-110">The inference process will produce two tables: **Element1** and **ChildElement1**.</span></span>  
  
 <span data-ttu-id="4a11a-111">Die **Element1** -Tabelle enthält zwei Spalten: **Element1_Id** und **ChildElement2**.</span><span class="sxs-lookup"><span data-stu-id="4a11a-111">The **Element1** table will have two columns: **Element1_Id** and **ChildElement2**.</span></span> <span data-ttu-id="4a11a-112">Die **ColumnMapping** -Eigenschaft der **Element1_Id** -Spalte wird auf **MappingType. Hidden**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4a11a-112">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span> <span data-ttu-id="4a11a-113">Die **ColumnMapping** -Eigenschaft der **ChildElement2** -Spalte wird auf **MappingType. Element**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4a11a-113">The **ColumnMapping** property of the **ChildElement2** column will be set to **MappingType.Element**.</span></span> <span data-ttu-id="4a11a-114">Die **Element1_Id** Spalte wird als Primärschlüssel der **Element1** -Tabelle festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4a11a-114">The **Element1_Id** column will be set as the primary key of the **Element1** table.</span></span>  
  
 <span data-ttu-id="4a11a-115">Die **ChildElement1** -Tabelle enthält drei Spalten: **attr1**, **attr2** und **Element1_Id**.</span><span class="sxs-lookup"><span data-stu-id="4a11a-115">The **ChildElement1** table will have three columns: **attr1**, **attr2** and **Element1_Id**.</span></span> <span data-ttu-id="4a11a-116">Die **ColumnMapping** -Eigenschaft für die Spalten **attr1** und **attr2** wird auf **MappingType. Attribute**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4a11a-116">The **ColumnMapping** property for the **attr1** and **attr2** columns will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="4a11a-117">Die **ColumnMapping** -Eigenschaft der **Element1_Id** -Spalte wird auf **MappingType. Hidden**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4a11a-117">The **ColumnMapping** property of the **Element1_Id** column will be set to **MappingType.Hidden**.</span></span>  
  
 <span data-ttu-id="4a11a-118">Eine **DataRelations** -und eine fremd **Schlüssel Einschränkung** werden mithilfe der **Element1_Id** Spalten aus beiden Tabellen erstellt.</span><span class="sxs-lookup"><span data-stu-id="4a11a-118">A **DataRelation** and **ForeignKeyConstraint** will be created using the **Element1_Id** columns from both tables.</span></span>  
  
 <span data-ttu-id="4a11a-119">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="4a11a-119">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="4a11a-120">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="4a11a-120">**Table:** Element1</span></span>  
  
|<span data-ttu-id="4a11a-121">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="4a11a-121">Element1_Id</span></span>|<span data-ttu-id="4a11a-122">ChildElement2</span><span class="sxs-lookup"><span data-stu-id="4a11a-122">ChildElement2</span></span>|  
|------------------|-------------------|  
|<span data-ttu-id="4a11a-123">0</span><span class="sxs-lookup"><span data-stu-id="4a11a-123">0</span></span>|<span data-ttu-id="4a11a-124">Text2</span><span class="sxs-lookup"><span data-stu-id="4a11a-124">Text2</span></span>|  
  
 <span data-ttu-id="4a11a-125">**Tabelle:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="4a11a-125">**Table:** ChildElement1</span></span>  
  
|<span data-ttu-id="4a11a-126">attr1</span><span class="sxs-lookup"><span data-stu-id="4a11a-126">attr1</span></span>|<span data-ttu-id="4a11a-127">attr2</span><span class="sxs-lookup"><span data-stu-id="4a11a-127">attr2</span></span>|<span data-ttu-id="4a11a-128">Element1_Id</span><span class="sxs-lookup"><span data-stu-id="4a11a-128">Element1_Id</span></span>|  
|-----------|-----------|------------------|  
|<span data-ttu-id="4a11a-129">value1</span><span class="sxs-lookup"><span data-stu-id="4a11a-129">value1</span></span>|<span data-ttu-id="4a11a-130">value2</span><span class="sxs-lookup"><span data-stu-id="4a11a-130">value2</span></span>|<span data-ttu-id="4a11a-131">0</span><span class="sxs-lookup"><span data-stu-id="4a11a-131">0</span></span>|  
  
 <span data-ttu-id="4a11a-132">**DataRelations:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="4a11a-132">**DataRelation:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="4a11a-133">**Parametritable:** Element1</span><span class="sxs-lookup"><span data-stu-id="4a11a-133">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="4a11a-134">Element **Column:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="4a11a-134">**ParentColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="4a11a-135">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="4a11a-135">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="4a11a-136">**ChildColumn:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="4a11a-136">**ChildColumn:** Element1_Id</span></span>  
  
 <span data-ttu-id="4a11a-137">In der folgenden Liste **:** Fall</span><span class="sxs-lookup"><span data-stu-id="4a11a-137">**Nested:** True</span></span>  
  
 <span data-ttu-id="4a11a-138">Fremd **Schlüssel Einschränkung:** Element1_ChildElement1</span><span class="sxs-lookup"><span data-stu-id="4a11a-138">**ForeignKeyConstraint:** Element1_ChildElement1</span></span>  
  
 <span data-ttu-id="4a11a-139">**Spalte:** Element1_Id</span><span class="sxs-lookup"><span data-stu-id="4a11a-139">**Column:** Element1_Id</span></span>  
  
 <span data-ttu-id="4a11a-140">**Parametritable:** Element1</span><span class="sxs-lookup"><span data-stu-id="4a11a-140">**ParentTable:** Element1</span></span>  
  
 <span data-ttu-id="4a11a-141">**ChildTable:** ChildElement1</span><span class="sxs-lookup"><span data-stu-id="4a11a-141">**ChildTable:** ChildElement1</span></span>  
  
 <span data-ttu-id="4a11a-142">**DeleteRule:** Mix</span><span class="sxs-lookup"><span data-stu-id="4a11a-142">**DeleteRule:** Cascade</span></span>  
  
 <span data-ttu-id="4a11a-143">**Akzeptrejectrule:** Gar</span><span class="sxs-lookup"><span data-stu-id="4a11a-143">**AcceptRejectRule:** None</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a11a-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a11a-144">See also</span></span>

- [<span data-ttu-id="4a11a-145">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="4a11a-145">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="4a11a-146">Laden eines "DataSets" aus XML</span><span class="sxs-lookup"><span data-stu-id="4a11a-146">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="4a11a-147">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="4a11a-147">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="4a11a-148">Verschachteln von "DataRelations"</span><span class="sxs-lookup"><span data-stu-id="4a11a-148">Nesting DataRelations</span></span>](nesting-datarelations.md)
- [<span data-ttu-id="4a11a-149">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="4a11a-149">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="4a11a-150">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="4a11a-150">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="4a11a-151">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="4a11a-151">ADO.NET Overview</span></span>](../ado-net-overview.md)
