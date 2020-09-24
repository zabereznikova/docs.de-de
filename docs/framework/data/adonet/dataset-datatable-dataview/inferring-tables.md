---
title: Ableiten von Tabellen
ms.date: 03/30/2017
ms.assetid: 74a288d4-b8e9-4f1a-b2cd-10df92c1ed1f
ms.openlocfilehash: 4a3d7b239dbc405cf2acae967b5be401dc772e38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177552"
---
# <a name="inferring-tables"></a><span data-ttu-id="8db43-102">Ableiten von Tabellen</span><span class="sxs-lookup"><span data-stu-id="8db43-102">Inferring Tables</span></span>

<span data-ttu-id="8db43-103">Beim Herleiten eines Schemas für ein <xref:System.Data.DataSet> aus einem XML-Dokument wird in ADO.NET zunächst bestimmt, welche XML-Elemente Tabellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="8db43-103">When inferring a schema for a <xref:System.Data.DataSet> from an XML document, ADO.NET first determines which XML elements represent tables.</span></span> <span data-ttu-id="8db43-104">Die folgenden XML-Strukturen führen zu einer Tabelle für das **DataSet** -Schema:</span><span class="sxs-lookup"><span data-stu-id="8db43-104">The following XML structures result in a table for the **DataSet** schema:</span></span>  
  
- <span data-ttu-id="8db43-105">Elemente mit Attributen</span><span class="sxs-lookup"><span data-stu-id="8db43-105">Elements with attributes</span></span>  
  
- <span data-ttu-id="8db43-106">Elemente mit untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="8db43-106">Elements with child elements</span></span>  
  
- <span data-ttu-id="8db43-107">Sich wiederholende Elemente</span><span class="sxs-lookup"><span data-stu-id="8db43-107">Repeating elements</span></span>  
  
## <a name="elements-with-attributes"></a><span data-ttu-id="8db43-108">Elemente mit Attributen</span><span class="sxs-lookup"><span data-stu-id="8db43-108">Elements with Attributes</span></span>  

 <span data-ttu-id="8db43-109">Elemente, in denen Attribute angegeben sind, ergeben hergeleitete Tabellen.</span><span class="sxs-lookup"><span data-stu-id="8db43-109">Elements that have attributes specified in them result in inferred tables.</span></span> <span data-ttu-id="8db43-110">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="8db43-110">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1"/>  
  <Element1 attr1="value2">Text1</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="8db43-111">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="8db43-111">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="8db43-112">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="8db43-112">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="8db43-113">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="8db43-113">**Table:** Element1</span></span>  
  
|<span data-ttu-id="8db43-114">attr1</span><span class="sxs-lookup"><span data-stu-id="8db43-114">attr1</span></span>|<span data-ttu-id="8db43-115">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="8db43-115">Element1_Text</span></span>|  
|-----------|--------------------|  
|<span data-ttu-id="8db43-116">value1</span><span class="sxs-lookup"><span data-stu-id="8db43-116">value1</span></span>||  
|<span data-ttu-id="8db43-117">value2</span><span class="sxs-lookup"><span data-stu-id="8db43-117">value2</span></span>|<span data-ttu-id="8db43-118">Text1</span><span class="sxs-lookup"><span data-stu-id="8db43-118">Text1</span></span>|  
  
## <a name="elements-with-child-elements"></a><span data-ttu-id="8db43-119">Elemente mit untergeordneten Elementen</span><span class="sxs-lookup"><span data-stu-id="8db43-119">Elements with Child Elements</span></span>  

 <span data-ttu-id="8db43-120">Elemente mit untergeordneten Elementen ergeben hergeleitete Tabellen.</span><span class="sxs-lookup"><span data-stu-id="8db43-120">Elements that have child elements result in inferred tables.</span></span> <span data-ttu-id="8db43-121">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="8db43-121">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1>Text1</ChildElement1>  
  </Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="8db43-122">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="8db43-122">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="8db43-123">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="8db43-123">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="8db43-124">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="8db43-124">**Table:** Element1</span></span>  
  
|<span data-ttu-id="8db43-125">ChildElement1</span><span class="sxs-lookup"><span data-stu-id="8db43-125">ChildElement1</span></span>|  
|-------------------|  
|<span data-ttu-id="8db43-126">Text1</span><span class="sxs-lookup"><span data-stu-id="8db43-126">Text1</span></span>|  
  
 <span data-ttu-id="8db43-127">Das Dokument- oder Stammelement ergibt eine hergeleitete Tabelle, wenn es Attribute oder untergeordnete Elemente besitzt, die als Spalten hergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="8db43-127">The document, or root, element result in an inferred table if it has attributes or child elements that are inferred as columns.</span></span> <span data-ttu-id="8db43-128">Wenn das Document-Element keine Attribute und keine untergeordneten Elemente aufweist, die als Spalten abgeleitet werden, wird das Element als **DataSet**abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="8db43-128">If the document element has no attributes and no child elements that would be inferred as columns, the element is inferred as a **DataSet**.</span></span> <span data-ttu-id="8db43-129">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="8db43-129">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element2>Text2</Element2>  
</DocumentElement>  
```  
  
 <span data-ttu-id="8db43-130">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "DocumentElement".</span><span class="sxs-lookup"><span data-stu-id="8db43-130">The inference process produces a table named "DocumentElement."</span></span>  
  
 <span data-ttu-id="8db43-131">**DataSet:** NewDataSet</span><span class="sxs-lookup"><span data-stu-id="8db43-131">**DataSet:** NewDataSet</span></span>  
  
 <span data-ttu-id="8db43-132">**Tabelle:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="8db43-132">**Table:** DocumentElement</span></span>  
  
|<span data-ttu-id="8db43-133">Element1</span><span class="sxs-lookup"><span data-stu-id="8db43-133">Element1</span></span>|<span data-ttu-id="8db43-134">Element2</span><span class="sxs-lookup"><span data-stu-id="8db43-134">Element2</span></span>|  
|--------------|--------------|  
|<span data-ttu-id="8db43-135">Text1</span><span class="sxs-lookup"><span data-stu-id="8db43-135">Text1</span></span>|<span data-ttu-id="8db43-136">Text2</span><span class="sxs-lookup"><span data-stu-id="8db43-136">Text2</span></span>|  
  
 <span data-ttu-id="8db43-137">Betrachten Sie alternativ dazu den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="8db43-137">Alternatively, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1" attr2="value2"/>  
</DocumentElement>  
```  
  
 <span data-ttu-id="8db43-138">Der Rückschluss Prozess erzeugt ein **DataSet** mit dem Namen "DocumentElement", das eine Tabelle mit dem Namen "Element1" enthält.</span><span class="sxs-lookup"><span data-stu-id="8db43-138">The inference process produces a **DataSet** named "DocumentElement" that contains a table named "Element1."</span></span>  
  
 <span data-ttu-id="8db43-139">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="8db43-139">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="8db43-140">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="8db43-140">**Table:** Element1</span></span>  
  
|<span data-ttu-id="8db43-141">attr1</span><span class="sxs-lookup"><span data-stu-id="8db43-141">attr1</span></span>|<span data-ttu-id="8db43-142">attr2</span><span class="sxs-lookup"><span data-stu-id="8db43-142">attr2</span></span>|  
|-----------|-----------|  
|<span data-ttu-id="8db43-143">value1</span><span class="sxs-lookup"><span data-stu-id="8db43-143">value1</span></span>|<span data-ttu-id="8db43-144">value2</span><span class="sxs-lookup"><span data-stu-id="8db43-144">value2</span></span>|  
  
## <a name="repeating-elements"></a><span data-ttu-id="8db43-145">Sich wiederholende Elemente</span><span class="sxs-lookup"><span data-stu-id="8db43-145">Repeating Elements</span></span>  

 <span data-ttu-id="8db43-146">Sich wiederholende Elemente ergeben eine einzige hergeleitete Tabelle.</span><span class="sxs-lookup"><span data-stu-id="8db43-146">Elements that repeat result in a single inferred table.</span></span> <span data-ttu-id="8db43-147">Betrachten Sie beispielsweise den folgenden XML-Code:</span><span class="sxs-lookup"><span data-stu-id="8db43-147">For example, consider the following XML:</span></span>  
  
```xml  
<DocumentElement>  
  <Element1>Text1</Element1>  
  <Element1>Text2</Element1>  
</DocumentElement>  
```  
  
 <span data-ttu-id="8db43-148">Beim Herleiten ergibt sich eine Tabelle mit dem Namen "Element1".</span><span class="sxs-lookup"><span data-stu-id="8db43-148">The inference process produces a table named "Element1."</span></span>  
  
 <span data-ttu-id="8db43-149">**DataSet:** DocumentElement</span><span class="sxs-lookup"><span data-stu-id="8db43-149">**DataSet:** DocumentElement</span></span>  
  
 <span data-ttu-id="8db43-150">**Tabelle:** Element1</span><span class="sxs-lookup"><span data-stu-id="8db43-150">**Table:** Element1</span></span>  
  
|<span data-ttu-id="8db43-151">Element1_Text</span><span class="sxs-lookup"><span data-stu-id="8db43-151">Element1_Text</span></span>|  
|--------------------|  
|<span data-ttu-id="8db43-152">Text1</span><span class="sxs-lookup"><span data-stu-id="8db43-152">Text1</span></span>|  
|<span data-ttu-id="8db43-153">Text2</span><span class="sxs-lookup"><span data-stu-id="8db43-153">Text2</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8db43-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8db43-154">See also</span></span>

- [<span data-ttu-id="8db43-155">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="8db43-155">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="8db43-156">Laden eines "DataSets" aus XML</span><span class="sxs-lookup"><span data-stu-id="8db43-156">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="8db43-157">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="8db43-157">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="8db43-158">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="8db43-158">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="8db43-159">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="8db43-159">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="8db43-160">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="8db43-160">ADO.NET Overview</span></span>](../ado-net-overview.md)
