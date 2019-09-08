---
title: Ableiten von Tabellen
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 52ffd3fe90eb491dd01acf8538276cc828fdb309
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784492"
---
# <a name="inferring-tables"></a><span data-ttu-id="b2b64-102">Ableiten von Tabellen</span><span class="sxs-lookup"><span data-stu-id="b2b64-102">Inferring Tables</span></span>
<span data-ttu-id="b2b64-103">Beim Herleiten eines Schemas für ein <xref:System.Data.DataSet> aus einem XML-Dokument wird in ADO.NET zunächst bestimmt, welche XML-Elemente Tabellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="b2b64-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="b2b64-104">Die folgenden XML-Strukturen führen zu einer Tabelle für das **DataSet** -Schema:</span><span class="sxs-lookup"><span data-stu-id="b2b64-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="b2b64-105">Elemente mit Attributen</span><span class="sxs-lookup"><span data-stu-id="b2b64-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="b2b64-106">Elemente mit untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="b2b64-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="b2b64-107">Sich wiederholende Elemente</span><span class="sxs-lookup"><span data-stu-id="b2b64-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="b2b64-108">Elemente mit Attributen</span><span class="sxs-lookup"><span data-stu-id="b2b64-108">Elements with Attributes</span></span>  
 <span data-ttu-id="b2b64-109">Elemente, in denen Attribute angegeben sind, ergeben hergeleitete Tabellen.</span><span class="sxs-lookup"><span data-stu-id="b2b64-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="b2b64-110">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="b2b64-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b2b64-111">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="b2b64-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="b2b64-112">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b2b64-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="b2b64-113">**Glaub** Element1</span><span class="sxs-lookup"><span data-stu-id="b2b64-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="b2b64-114">attr1</span><span class="sxs-lookup"><span data-stu-id="b2b64-114">attr1</span></span>|<span data-ttu-id="b2b64-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="b2b64-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="b2b64-116">value1</span><span class="sxs-lookup"><span data-stu-id="b2b64-116">value1</span></span>||  
|<span data-ttu-id="b2b64-117">value2</span><span class="sxs-lookup"><span data-stu-id="b2b64-117">value2</span></span>|<span data-ttu-id="b2b64-118">Text1</span><span class="sxs-lookup"><span data-stu-id="b2b64-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="b2b64-119">Elemente mit untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="b2b64-119">Elements with Child Elements</span></span>  
 <span data-ttu-id="b2b64-120">Elemente mit untergeordneten Elementen ergeben hergeleitete Tabellen.</span><span class="sxs-lookup"><span data-stu-id="b2b64-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="b2b64-121">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="b2b64-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b2b64-122">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="b2b64-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="b2b64-123">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b2b64-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="b2b64-124">**Glaub** Element1</span><span class="sxs-lookup"><span data-stu-id="b2b64-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="b2b64-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="b2b64-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="b2b64-126">Text1</span><span class="sxs-lookup"><span data-stu-id="b2b64-126">Text1</span></span>|  
  
 <span data-ttu-id="b2b64-127">Das Dokument- oder Stammelement ergibt eine hergeleitete Tabelle, wenn es Attribute oder untergeordnete Elemente besitzt, die als Spalten hergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="b2b64-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="b2b64-128">Wenn das Document-Element keine Attribute und keine untergeordneten Elemente aufweist, die als Spalten abgeleitet werden, wird das Element als **DataSet**abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="b2b64-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="b2b64-129">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="b2b64-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b2b64-130">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="b2b64-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="b2b64-131">**DataSet** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="b2b64-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="b2b64-132">**Glaub** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b2b64-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="b2b64-133">Element1</span><span class="sxs-lookup"><span data-stu-id="b2b64-133">Element1</span></span>|<span data-ttu-id="b2b64-134">Element2</span><span class="sxs-lookup"><span data-stu-id="b2b64-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="b2b64-135">Text1</span><span class="sxs-lookup"><span data-stu-id="b2b64-135">Text1</span></span>|<span data-ttu-id="b2b64-136">Text2</span><span class="sxs-lookup"><span data-stu-id="b2b64-136">Text2</span></span>|  
  
 <span data-ttu-id="b2b64-137">Betrachten Sie alternativ dazu den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="b2b64-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b2b64-138">Der Rückschluss Prozess erzeugt ein **DataSet** mit dem Namen "DocumentElement", das eine Tabelle mit dem Namen "Element1" enthält.</span><span class="sxs-lookup"><span data-stu-id="b2b64-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="b2b64-139">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b2b64-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="b2b64-140">**Glaub** Element1</span><span class="sxs-lookup"><span data-stu-id="b2b64-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="b2b64-141">attr1</span><span class="sxs-lookup"><span data-stu-id="b2b64-141">attr1</span></span>|<span data-ttu-id="b2b64-142">attr2</span><span class="sxs-lookup"><span data-stu-id="b2b64-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="b2b64-143">value1</span><span class="sxs-lookup"><span data-stu-id="b2b64-143">value1</span></span>|<span data-ttu-id="b2b64-144">value2</span><span class="sxs-lookup"><span data-stu-id="b2b64-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="b2b64-145">Sich wiederholende Elemente</span><span class="sxs-lookup"><span data-stu-id="b2b64-145">Repeating Elements</span></span>  
 <span data-ttu-id="b2b64-146">Sich wiederholende Elemente ergeben eine einzige hergeleitete Tabelle.</span><span class="sxs-lookup"><span data-stu-id="b2b64-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="b2b64-147">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="b2b64-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="b2b64-148">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="b2b64-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="b2b64-149">**DataSet** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="b2b64-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="b2b64-150">**Glaub** Element1</span><span class="sxs-lookup"><span data-stu-id="b2b64-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="b2b64-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="b2b64-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="b2b64-152">Text1</span><span class="sxs-lookup"><span data-stu-id="b2b64-152">Text1</span></span>|  
|<span data-ttu-id="b2b64-153">Text2</span><span class="sxs-lookup"><span data-stu-id="b2b64-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b2b64-154">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2b64-154">See also</span></span>

- [<span data-ttu-id="b2b64-155">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="b2b64-155">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="b2b64-156">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="b2b64-156">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="b2b64-157">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="b2b64-157">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="b2b64-158">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="b2b64-158">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="b2b64-159">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="b2b64-159">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b2b64-160">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b2b64-160">ADO.NET Overview</span></span>](../ado-net-overview.md)
