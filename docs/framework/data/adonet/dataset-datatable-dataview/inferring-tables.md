---
title: Ableiten von Tabellen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 2c00dd11d4d93e5d3b0e2f1c3b75765056a10cab
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="inferring-tables"></a><span data-ttu-id="be12f-102">Ableiten von Tabellen</span><span class="sxs-lookup"><span data-stu-id="be12f-102">Inferring Tables</span></span>
<span data-ttu-id="be12f-103">Beim Herleiten eines Schemas für ein <xref:System.Data.DataSet> aus einem XML-Dokument wird in ADO.NET zunächst bestimmt, welche XML-Elemente Tabellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="be12f-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="be12f-104">Die folgenden XML-Strukturen ergeben eine Tabelle für die **DataSet** Schema:</span><span class="sxs-lookup"><span data-stu-id="be12f-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
-   <span data-ttu-id="be12f-105">Elemente mit Attributen</span><span class="sxs-lookup"><span data-stu-id="be12f-105">Elements with attributes</span></span>  
  
-   <span data-ttu-id="be12f-106">Elemente mit untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="be12f-106">Elements with child elements</span></span>  
  
-   <span data-ttu-id="be12f-107">Sich wiederholende Elemente</span><span class="sxs-lookup"><span data-stu-id="be12f-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="be12f-108">Elemente mit Attributen</span><span class="sxs-lookup"><span data-stu-id="be12f-108">Elements with Attributes</span></span>  
 <span data-ttu-id="be12f-109">Elemente, in denen Attribute angegeben sind, ergeben hergeleitete Tabellen.</span><span class="sxs-lookup"><span data-stu-id="be12f-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="be12f-110">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="be12f-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="be12f-111">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="be12f-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="be12f-112">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="be12f-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="be12f-113">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="be12f-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="be12f-114">attr1</span><span class="sxs-lookup"><span data-stu-id="be12f-114">attr1</span></span>|<span data-ttu-id="be12f-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="be12f-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="be12f-116">value1</span><span class="sxs-lookup"><span data-stu-id="be12f-116">value1</span></span>||  
|<span data-ttu-id="be12f-117">value2</span><span class="sxs-lookup"><span data-stu-id="be12f-117">value2</span></span>|<span data-ttu-id="be12f-118">Text1</span><span class="sxs-lookup"><span data-stu-id="be12f-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="be12f-119">Elemente mit untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="be12f-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="be12f-120">Elemente mit untergeordneten Elementen ergeben hergeleitete Tabellen.</span><span class="sxs-lookup"><span data-stu-id="be12f-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="be12f-121">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="be12f-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="be12f-122">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="be12f-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="be12f-123">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="be12f-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="be12f-124">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="be12f-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="be12f-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="be12f-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="be12f-126">Text1</span><span class="sxs-lookup"><span data-stu-id="be12f-126">Text1</span></span>|  
  
 <span data-ttu-id="be12f-127">Das Dokument- oder Stammelement ergibt eine hergeleitete Tabelle, wenn es Attribute oder untergeordnete Elemente besitzt, die als Spalten hergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="be12f-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="be12f-128">Wenn das Dokumentelement verfügt über keine Attribute und keine untergeordneten Elemente, die als Spalten hergeleitet würden, als das Element hergeleitet eine **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="be12f-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="be12f-129">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="be12f-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="be12f-130">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="be12f-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="be12f-131">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="be12f-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="be12f-132">**Table:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="be12f-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="be12f-133">Element1</span><span class="sxs-lookup"><span data-stu-id="be12f-133">Element1</span></span>|<span data-ttu-id="be12f-134">Element2</span><span class="sxs-lookup"><span data-stu-id="be12f-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="be12f-135">Text1</span><span class="sxs-lookup"><span data-stu-id="be12f-135">Text1</span></span>|<span data-ttu-id="be12f-136">Text2</span><span class="sxs-lookup"><span data-stu-id="be12f-136">Text2</span></span>|  
  
 <span data-ttu-id="be12f-137">Betrachten Sie alternativ dazu den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="be12f-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="be12f-138">Beim Herleiten ergibt eine **DataSet** mit dem Namen "DocumentElement", die eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="be12f-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="be12f-139">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="be12f-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="be12f-140">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="be12f-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="be12f-141">attr1</span><span class="sxs-lookup"><span data-stu-id="be12f-141">attr1</span></span>|<span data-ttu-id="be12f-142">attr2</span><span class="sxs-lookup"><span data-stu-id="be12f-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="be12f-143">value1</span><span class="sxs-lookup"><span data-stu-id="be12f-143">value1</span></span>|<span data-ttu-id="be12f-144">value2</span><span class="sxs-lookup"><span data-stu-id="be12f-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="be12f-145">Sich wiederholende Elemente</span><span class="sxs-lookup"><span data-stu-id="be12f-145">Repeating Elements</span></span>  
 <span data-ttu-id="be12f-146">Sich wiederholende Elemente ergeben eine einzige hergeleitete Tabelle.</span><span class="sxs-lookup"><span data-stu-id="be12f-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="be12f-147">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="be12f-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="be12f-148">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="be12f-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="be12f-149">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="be12f-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="be12f-150">**Table:** Element1</span><span class="sxs-lookup"><span data-stu-id="be12f-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="be12f-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="be12f-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="be12f-152">Text1</span><span class="sxs-lookup"><span data-stu-id="be12f-152">Text1</span></span>|  
|<span data-ttu-id="be12f-153">Text2</span><span class="sxs-lookup"><span data-stu-id="be12f-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be12f-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be12f-154">See Also</span></span>  
 [<span data-ttu-id="be12f-155">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="be12f-155">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="be12f-156">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="be12f-156">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="be12f-157">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="be12f-157">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="be12f-158">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="be12f-158">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="be12f-159">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="be12f-159">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="be12f-160">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="be12f-160">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
