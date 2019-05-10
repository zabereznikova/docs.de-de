---
title: Ableiten von Tabellen
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 174d305688c7090c163df60a11e233aea24b8f79
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64587360"
---
# <a name="inferring-tables"></a><span data-ttu-id="923b1-102">Ableiten von Tabellen</span><span class="sxs-lookup"><span data-stu-id="923b1-102">Inferring Tables</span></span>
<span data-ttu-id="923b1-103">Beim Herleiten eines Schemas für ein <xref:System.Data.DataSet> aus einem XML-Dokument wird in ADO.NET zunächst bestimmt, welche XML-Elemente Tabellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="923b1-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="923b1-104">Führen Sie die folgenden XML-Strukturen in einer Tabelle für die **DataSet** Schema:</span><span class="sxs-lookup"><span data-stu-id="923b1-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="923b1-105">Elemente mit Attributen</span><span class="sxs-lookup"><span data-stu-id="923b1-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="923b1-106">Elemente mit untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="923b1-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="923b1-107">Sich wiederholende Elemente</span><span class="sxs-lookup"><span data-stu-id="923b1-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="923b1-108">Elemente mit Attributen</span><span class="sxs-lookup"><span data-stu-id="923b1-108">Elements with Attributes</span></span>  
 <span data-ttu-id="923b1-109">Elemente, in denen Attribute angegeben sind, ergeben hergeleitete Tabellen.</span><span class="sxs-lookup"><span data-stu-id="923b1-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="923b1-110">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="923b1-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="923b1-111">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="923b1-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="923b1-112">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="923b1-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="923b1-113">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="923b1-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="923b1-114">attr1</span><span class="sxs-lookup"><span data-stu-id="923b1-114">attr1</span></span>|<span data-ttu-id="923b1-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="923b1-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="923b1-116">value1</span><span class="sxs-lookup"><span data-stu-id="923b1-116">value1</span></span>||  
|<span data-ttu-id="923b1-117">value2</span><span class="sxs-lookup"><span data-stu-id="923b1-117">value2</span></span>|<span data-ttu-id="923b1-118">Text1</span><span class="sxs-lookup"><span data-stu-id="923b1-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="923b1-119">Elemente mit untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="923b1-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="923b1-120">Elemente mit untergeordneten Elementen ergeben hergeleitete Tabellen.</span><span class="sxs-lookup"><span data-stu-id="923b1-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="923b1-121">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="923b1-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="923b1-122">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="923b1-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="923b1-123">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="923b1-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="923b1-124">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="923b1-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="923b1-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="923b1-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="923b1-126">Text1</span><span class="sxs-lookup"><span data-stu-id="923b1-126">Text1</span></span>|  
  
 <span data-ttu-id="923b1-127">Das Dokument- oder Stammelement ergibt eine hergeleitete Tabelle, wenn es Attribute oder untergeordnete Elemente besitzt, die als Spalten hergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="923b1-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="923b1-128">Wenn das Dokumentelement verfügt über keine Attribute und keine untergeordneten Elemente, die als Spalten hergeleitet werden, wird das Element als abgeleitet eine **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="923b1-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="923b1-129">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="923b1-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="923b1-130">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="923b1-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="923b1-131">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="923b1-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="923b1-132">**Tabelle:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="923b1-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="923b1-133">Element1</span><span class="sxs-lookup"><span data-stu-id="923b1-133">Element1</span></span>|<span data-ttu-id="923b1-134">Element2</span><span class="sxs-lookup"><span data-stu-id="923b1-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="923b1-135">Text1</span><span class="sxs-lookup"><span data-stu-id="923b1-135">Text1</span></span>|<span data-ttu-id="923b1-136">Text2</span><span class="sxs-lookup"><span data-stu-id="923b1-136">Text2</span></span>|  
  
 <span data-ttu-id="923b1-137">Betrachten Sie alternativ dazu den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="923b1-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="923b1-138">Beim Herleiten ergibt eine **DataSet** mit dem Namen "DocumentElement", die eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="923b1-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="923b1-139">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="923b1-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="923b1-140">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="923b1-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="923b1-141">attr1</span><span class="sxs-lookup"><span data-stu-id="923b1-141">attr1</span></span>|<span data-ttu-id="923b1-142">attr2</span><span class="sxs-lookup"><span data-stu-id="923b1-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="923b1-143">value1</span><span class="sxs-lookup"><span data-stu-id="923b1-143">value1</span></span>|<span data-ttu-id="923b1-144">value2</span><span class="sxs-lookup"><span data-stu-id="923b1-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="923b1-145">Sich wiederholende Elemente</span><span class="sxs-lookup"><span data-stu-id="923b1-145">Repeating Elements</span></span>  
 <span data-ttu-id="923b1-146">Sich wiederholende Elemente ergeben eine einzige hergeleitete Tabelle.</span><span class="sxs-lookup"><span data-stu-id="923b1-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="923b1-147">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="923b1-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="923b1-148">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="923b1-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="923b1-149">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="923b1-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="923b1-150">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="923b1-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="923b1-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="923b1-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="923b1-152">Text1</span><span class="sxs-lookup"><span data-stu-id="923b1-152">Text1</span></span>|  
|<span data-ttu-id="923b1-153">Text2</span><span class="sxs-lookup"><span data-stu-id="923b1-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="923b1-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="923b1-154">See also</span></span>

- [<span data-ttu-id="923b1-155">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="923b1-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="923b1-156">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="923b1-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [<span data-ttu-id="923b1-157">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="923b1-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="923b1-158">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="923b1-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [<span data-ttu-id="923b1-159">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="923b1-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="923b1-160">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="923b1-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
