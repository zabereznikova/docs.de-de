---
title: "Zusammenfassung des Rückschlussprozesses von DataSet-Schemas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 15469e917129db7668df17f22fb71b166993d4fc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="fcc0b-102">Zusammenfassung des Rückschlussprozesses von DataSet-Schemas</span><span class="sxs-lookup"><span data-stu-id="fcc0b-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="fcc0b-103">Während des Rückschlussprozesses wird zunächst anhand des XML-Dokuments bestimmt, welche Elemente als Tabellen hergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="fcc0b-104">Anschließend werden aus der übrigen XML die Spalten für diese Tabellen ermittelt.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="fcc0b-105">Bei geschachtelten Tabellen werden beim Rückschlussprozess geschachtelte <xref:System.Data.DataRelation>-Objekte und geschachtelte <xref:System.Data.ForeignKeyConstraint>-Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="fcc0b-106">Im Folgenden finden Sie eine kurze Zusammenfassung der Rückschlussregeln:</span><span class="sxs-lookup"><span data-stu-id="fcc0b-106">Following is a brief summary of inference rules:</span></span>  
  
-   <span data-ttu-id="fcc0b-107">Elemente mit Attributen werden als Tabellen hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-107">Elements that have attributes are inferred as tables.</span></span>  
  
-   <span data-ttu-id="fcc0b-108">Elemente mit untergeordneten Elementen werden als Tabellen hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-108">Elements that have child elements are inferred as tables.</span></span>  
  
-   <span data-ttu-id="fcc0b-109">Sich wiederholende Elemente werden als einzelne Tabelle hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-109">Elements that repeat are inferred as a single table.</span></span>  
  
-   <span data-ttu-id="fcc0b-110">Ein Dokument- oder Stammelement, das keine Attribute und keine untergeordneten Elemente aufweist, die als Spalten hergeleitet würden, wird als <xref:System.Data.DataSet> hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="fcc0b-111">Andernfalls wird das Dokumentelement als Tabelle hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-111">Otherwise, the document element is inferred as a table.</span></span>  
  
-   <span data-ttu-id="fcc0b-112">Attribute werden als Spalten hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-112">Attributes are inferred as columns.</span></span>  
  
-   <span data-ttu-id="fcc0b-113">Elemente, die keine Attribute oder untergeordnete Elemente aufweisen und sich nicht wiederholen, werden als Spalten hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
-   <span data-ttu-id="fcc0b-114">Für Elemente, die als geschachtelte Tabellen innerhalb von anderen Elementen abgeleitet werden, die auch abgeleitet werden als Tabellen, eine geschachtelte **DataRelation** wird zwischen den beiden Tabellen erstellt.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="fcc0b-115">Eine neue Primärschlüsselspalte mit dem Namen **TableName_Id** für beide Tabellen hinzugefügt und verwendet werden, indem Sie die **DataRelation**.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="fcc0b-116">Ein **ForeignKeyConstraint** wird erstellt, zwischen den beiden Tabellen mithilfe der **TableName_Id** Spalte.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
-   <span data-ttu-id="fcc0b-117">Für Elemente, die als Tabellen hergeleitet werden, und, die Text enthalten, aber keine untergeordneten Elemente besitzen, eine neue Spalte mit dem Namen **TableName_Text** wird für den Text aller Elemente erstellt.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="fcc0b-118">Bei einem als Tabelle hergeleiteten Element, das sowohl Text als auch untergeordnete Elemente aufweist, wird der Text ignoriert.</span><span class="sxs-lookup"><span data-stu-id="fcc0b-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fcc0b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcc0b-119">See Also</span></span>  
 [<span data-ttu-id="fcc0b-120">Ableiten von relationalen DataSet-Struktur von XML</span><span class="sxs-lookup"><span data-stu-id="fcc0b-120">Inferring DataSet Relational Structure from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)  
 [<span data-ttu-id="fcc0b-121">Beim Laden eines Datasets aus XML</span><span class="sxs-lookup"><span data-stu-id="fcc0b-121">Loading a DataSet from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)  
 [<span data-ttu-id="fcc0b-122">Beim Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="fcc0b-122">Loading DataSet Schema Information from XML</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)  
 [<span data-ttu-id="fcc0b-123">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="fcc0b-123">Using XML in a DataSet</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)  
 [<span data-ttu-id="fcc0b-124">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="fcc0b-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="fcc0b-125">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="fcc0b-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
