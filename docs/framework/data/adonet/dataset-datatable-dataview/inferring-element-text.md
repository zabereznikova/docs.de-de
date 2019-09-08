---
title: Ableiten von Elementtext
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 3fdd110a14ddfd6065ed552171a8d76ef64e2fb5
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784543"
---
# <a name="inferring-element-text"></a><span data-ttu-id="73ee8-102">Ableiten von Elementtext</span><span class="sxs-lookup"><span data-stu-id="73ee8-102">Inferring Element Text</span></span>
<span data-ttu-id="73ee8-103">Wenn ein Element Text enthält und keine untergeordneten Elemente als Tabellen abgeleitet werden sollen (z. b. Elemente mit Attributen oder wiederholten Elementen), wird der Tabelle eine neue Spalte mit dem Namen **TableName_Text** hinzugefügt, die für das Element abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="73ee8-103">If an element contains text and has no child elements to be inferred as tables (such as elements with attributes or repeated elements), a new column with the name **TableName_Text** will be added to the table that is inferred for the element.</span></span> <span data-ttu-id="73ee8-104">Der in dem Element enthaltene Text wird einer Tabellenzeile hinzugefügt und in der neuen Spalte gespeichert.</span><span class="sxs-lookup"><span data-stu-id="73ee8-104">The text contained in the element will be added to a row in the table and stored in the new column.</span></span> <span data-ttu-id="73ee8-105">Die **ColumnMapping** -Eigenschaft der neuen Spalte wird auf **MappingType. SimpleContent**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="73ee8-105">The **ColumnMapping** property of the new column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="73ee8-106">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="73ee8-106">For example, consider the following XML.</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="73ee8-107">Der Rückschluss Prozess erzeugt eine Tabelle mit dem Namen **Element1** mit zwei Spalten: **attr1** und **Element1_Text**.</span><span class="sxs-lookup"><span data-stu-id="73ee8-107">The inference process will produce a table named **Element1** with two columns: **attr1** and **Element1_Text**.</span></span> <span data-ttu-id="73ee8-108">Die **ColumnMapping** -Eigenschaft der **attr1** -Spalte wird auf **MappingType. Attribute**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="73ee8-108">The **ColumnMapping** property of the **attr1** column will be set to **MappingType.Attribute**.</span></span> <span data-ttu-id="73ee8-109">Die **ColumnMapping** -Eigenschaft der **Element1_Text** -Spalte wird auf **MappingType. SimpleContent**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="73ee8-109">The **ColumnMapping** property of the **Element1_Text** column will be set to **MappingType.SimpleContent**.</span></span>  
  
 <span data-ttu-id="73ee8-110">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="73ee8-110">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="73ee8-111">**Glaub** Element1</span><span class="sxs-lookup"><span data-stu-id="73ee8-111">**Table:** Element1</span></span>  
  
|<span data-ttu-id="73ee8-112">attr1</span><span class="sxs-lookup"><span data-stu-id="73ee8-112">attr1</span></span>|<span data-ttu-id="73ee8-113">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="73ee8-113">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="73ee8-114">value1</span><span class="sxs-lookup"><span data-stu-id="73ee8-114">value1</span></span>|<span data-ttu-id="73ee8-115">Text1</span><span class="sxs-lookup"><span data-stu-id="73ee8-115">Text1</span></span>|  
  
 <span data-ttu-id="73ee8-116">Bei einem Element mit Text und untergeordneten Elementen, die ebenfalls Text enthalten, wird der Tabelle keine Spalte zum Speichern des Elementtexts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="73ee8-116">If an element contains text, but also has child elements that contain text, a column will not be added to the table to store the text contained in the element.</span></span> <span data-ttu-id="73ee8-117">Der in dem Element enthaltene Text wird ignoriert, während der Text in den untergeordneten Elementen in eine Tabellenzeile eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="73ee8-117">The text contained in the element will be ignored, while the text in the child elements is included in a row in the table.</span></span> <span data-ttu-id="73ee8-118">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="73ee8-118">For example, consider the following XML.</span></span>  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 <span data-ttu-id="73ee8-119">Der Rückschluss Prozess erzeugt eine Tabelle mit dem Namen " **Element1** " mit einer Spalte mit dem Namen " **ChildElement1**".</span><span class="sxs-lookup"><span data-stu-id="73ee8-119">The inference process will produce a table named **Element1** with one column named **ChildElement1**.</span></span> <span data-ttu-id="73ee8-120">Der Text für das **ChildElement1** -Element wird in eine Zeile in der Tabelle eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="73ee8-120">The text for the **ChildElement1** element will be included in a row in the table.</span></span> <span data-ttu-id="73ee8-121">Der restliche Text wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="73ee8-121">The other text will be ignored.</span></span> <span data-ttu-id="73ee8-122">Die **ColumnMapping** -Eigenschaft der **ChildElement1** -Spalte wird auf **MappingType. Element**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="73ee8-122">The **ColumnMapping** property of the **ChildElement1** column will be set to **MappingType.Element**.</span></span>  
  
 <span data-ttu-id="73ee8-123">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="73ee8-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="73ee8-124">**Glaub** Element1</span><span class="sxs-lookup"><span data-stu-id="73ee8-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="73ee8-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="73ee8-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="73ee8-126">Text2</span><span class="sxs-lookup"><span data-stu-id="73ee8-126">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="73ee8-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73ee8-127">See also</span></span>

- [<span data-ttu-id="73ee8-128">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="73ee8-128">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="73ee8-129">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="73ee8-129">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="73ee8-130">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="73ee8-130">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="73ee8-131">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="73ee8-131">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="73ee8-132">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="73ee8-132">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="73ee8-133">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="73ee8-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
