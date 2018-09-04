---
title: Ableiten von Tabellen
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 38709f91e01c7f85d9e8482bdd49bc0892121f09
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43528171"
---
# <a name="inferring-tables"></a><span data-ttu-id="1d067-102">Ableiten von Tabellen</span><span class="sxs-lookup"><span data-stu-id="1d067-102">Inferring Tables</span></span>
<span data-ttu-id="1d067-103">Beim Herleiten eines Schemas für ein <xref:System.Data.DataSet> aus einem XML-Dokument wird in ADO.NET zunächst bestimmt, welche XML-Elemente Tabellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="1d067-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="1d067-104">Führen Sie die folgenden XML-Strukturen in einer Tabelle für die **DataSet** Schema:</span><span class="sxs-lookup"><span data-stu-id="1d067-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="1d067-105">Elemente mit Attributen</span><span class="sxs-lookup"><span data-stu-id="1d067-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="1d067-106">Elemente mit untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="1d067-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="1d067-107">Sich wiederholende Elemente</span><span class="sxs-lookup"><span data-stu-id="1d067-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="1d067-108">Elemente mit Attributen</span><span class="sxs-lookup"><span data-stu-id="1d067-108">Elements with Attributes</span></span>  
 <span data-ttu-id="1d067-109">Elemente, in denen Attribute angegeben sind, ergeben hergeleitete Tabellen.</span><span class="sxs-lookup"><span data-stu-id="1d067-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="1d067-110">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="1d067-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="1d067-111">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="1d067-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="1d067-112">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="1d067-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="1d067-113">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="1d067-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="1d067-114">attr1</span><span class="sxs-lookup"><span data-stu-id="1d067-114">attr1</span></span>|<span data-ttu-id="1d067-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="1d067-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="1d067-116">value1</span><span class="sxs-lookup"><span data-stu-id="1d067-116">value1</span></span>||  
|<span data-ttu-id="1d067-117">value2</span><span class="sxs-lookup"><span data-stu-id="1d067-117">value2</span></span>|<span data-ttu-id="1d067-118">Text1</span><span class="sxs-lookup"><span data-stu-id="1d067-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="1d067-119">Elemente mit untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="1d067-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="1d067-120">Elemente mit untergeordneten Elementen ergeben hergeleitete Tabellen.</span><span class="sxs-lookup"><span data-stu-id="1d067-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="1d067-121">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="1d067-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="1d067-122">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="1d067-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="1d067-123">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="1d067-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="1d067-124">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="1d067-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="1d067-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="1d067-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="1d067-126">Text1</span><span class="sxs-lookup"><span data-stu-id="1d067-126">Text1</span></span>|  
  
 <span data-ttu-id="1d067-127">Das Dokument- oder Stammelement ergibt eine hergeleitete Tabelle, wenn es Attribute oder untergeordnete Elemente besitzt, die als Spalten hergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="1d067-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="1d067-128">Wenn das Dokumentelement verfügt über keine Attribute und keine untergeordneten Elemente, die als Spalten hergeleitet werden, wird das Element als abgeleitet eine **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="1d067-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="1d067-129">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="1d067-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="1d067-130">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="1d067-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="1d067-131">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="1d067-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="1d067-132">**Tabelle:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="1d067-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="1d067-133">Element1</span><span class="sxs-lookup"><span data-stu-id="1d067-133">Element1</span></span>|<span data-ttu-id="1d067-134">Element2</span><span class="sxs-lookup"><span data-stu-id="1d067-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="1d067-135">Text1</span><span class="sxs-lookup"><span data-stu-id="1d067-135">Text1</span></span>|<span data-ttu-id="1d067-136">Text2</span><span class="sxs-lookup"><span data-stu-id="1d067-136">Text2</span></span>|  
  
 <span data-ttu-id="1d067-137">Betrachten Sie alternativ dazu den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="1d067-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="1d067-138">Beim Herleiten ergibt eine **DataSet** mit dem Namen "DocumentElement", die eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="1d067-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="1d067-139">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="1d067-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="1d067-140">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="1d067-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="1d067-141">attr1</span><span class="sxs-lookup"><span data-stu-id="1d067-141">attr1</span></span>|<span data-ttu-id="1d067-142">attr2</span><span class="sxs-lookup"><span data-stu-id="1d067-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="1d067-143">value1</span><span class="sxs-lookup"><span data-stu-id="1d067-143">value1</span></span>|<span data-ttu-id="1d067-144">value2</span><span class="sxs-lookup"><span data-stu-id="1d067-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="1d067-145">Sich wiederholende Elemente</span><span class="sxs-lookup"><span data-stu-id="1d067-145">Repeating Elements</span></span>  
 <span data-ttu-id="1d067-146">Sich wiederholende Elemente ergeben eine einzige hergeleitete Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1d067-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="1d067-147">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="1d067-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="1d067-148">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="1d067-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="1d067-149">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="1d067-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="1d067-150">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="1d067-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="1d067-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="1d067-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="1d067-152">Text1</span><span class="sxs-lookup"><span data-stu-id="1d067-152">Text1</span></span>|  
|<span data-ttu-id="1d067-153">Text2</span><span class="sxs-lookup"><span data-stu-id="1d067-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1d067-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d067-154">See Also</span></span>  
 [<span data-ttu-id="1d067-155">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="1d067-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="1d067-156">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="1d067-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="1d067-157">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="1d067-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="1d067-158">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="1d067-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="1d067-159">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="1d067-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="1d067-160">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="1d067-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
