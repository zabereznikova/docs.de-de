---
title: Ableiten von Elementtext
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 66dcc6a98d365f20da6c7f4c075c2fdd8ab936e2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="inferring-element-text"></a><span data-ttu-id="a8b6e-102">Ableiten von Elementtext</span><span class="sxs-lookup"><span data-stu-id="a8b6e-102">Inferring Element Text</span></span>
<span data-ttu-id="a8b6e-103">Wenn ein Element Text enthält und verfügt über keine untergeordneten Elemente wie z. B. (Elemente mit Attributen) oder sich wiederholende Elemente eine neue Spalte mit dem Namen Tabellen herzuleitende **TableName_Text** werden hinzugefügt werden, um die Tabelle, die für das Element hergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="a8b6e-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="a8b6e-104">Der in dem Element enthaltene Text wird einer Tabellenzeile hinzugefügt und in der neuen Spalte gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a8b6e-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="a8b6e-105">Die **ColumnMapping** Eigenschaft der neuen Spalte wird auf festgelegt **MappingType.SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="a8b6e-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="a8b6e-106">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="a8b6e-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="a8b6e-107">Die Herleitung wird einer Tabelle namens **Element1** mit zwei Spalten: **attr1** und **Element1_Text**.</span><span class="sxs-lookup"><span data-stu-id="a8b6e-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="a8b6e-108">Die **ColumnMapping** Eigenschaft von der **attr1** Spaltensatz zu **MappingType.Attribute**.</span><span class="sxs-lookup"><span data-stu-id="a8b6e-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="a8b6e-109">Die **ColumnMapping** Eigenschaft von der **Element1_Text** Spaltensatz zu **MappingType.SimpleContent**.</span><span class="sxs-lookup"><span data-stu-id="a8b6e-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="a8b6e-110">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a8b6e-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a8b6e-111">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="a8b6e-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a8b6e-112">attr1</span><span class="sxs-lookup"><span data-stu-id="a8b6e-112">attr1</span></span>|<span data-ttu-id="a8b6e-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="a8b6e-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="a8b6e-114">value1</span><span class="sxs-lookup"><span data-stu-id="a8b6e-114">value1</span></span>|<span data-ttu-id="a8b6e-115">Text1</span><span class="sxs-lookup"><span data-stu-id="a8b6e-115">Text1</span></span>|  
  
 <span data-ttu-id="a8b6e-116">Bei einem Element mit Text und untergeordneten Elementen, die ebenfalls Text enthalten, wird der Tabelle keine Spalte zum Speichern des Elementtexts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a8b6e-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="a8b6e-117">Der in dem Element enthaltene Text wird ignoriert, während der Text in den untergeordneten Elementen in eine Tabellenzeile eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="a8b6e-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="a8b6e-118">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="a8b6e-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="a8b6e-119">Die Herleitung wird einer Tabelle namens **Element1** mit einer Spalte mit dem Namen **ChildElement1**.</span><span class="sxs-lookup"><span data-stu-id="a8b6e-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="a8b6e-120">Der Text für die **ChildElement1** Element wird in einer Zeile in der Tabelle enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="a8b6e-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="a8b6e-121">Der restliche Text wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a8b6e-121">The other text will be ignored.</span></span> <span data-ttu-id="a8b6e-122">Die **ColumnMapping** Eigenschaft von der **ChildElement1** Spaltensatz zu **MappingType.Element**.</span><span class="sxs-lookup"><span data-stu-id="a8b6e-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="a8b6e-123">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="a8b6e-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="a8b6e-124">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="a8b6e-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="a8b6e-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="a8b6e-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="a8b6e-126">Text2</span><span class="sxs-lookup"><span data-stu-id="a8b6e-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a8b6e-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8b6e-127">See Also</span></span>  
 [<span data-ttu-id="a8b6e-128">Ableiten von relationalen DataSet-Struktur von XML</span><span class="sxs-lookup"><span data-stu-id="a8b6e-128">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="a8b6e-129">Beim Laden eines Datasets aus XML</span><span class="sxs-lookup"><span data-stu-id="a8b6e-129">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="a8b6e-130">Beim Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="a8b6e-130">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="a8b6e-131">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="a8b6e-131">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="a8b6e-132">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="a8b6e-132">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="a8b6e-133">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="a8b6e-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
