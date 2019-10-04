---
title: Zusammenfassung des Rückschlussprozesses von DataSet-Schemas
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 35e9b67d2d0a47aa69eabdb4b7e94f95b0b9589f
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71833980"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="a2a14-102">Zusammenfassung des Rückschlussprozesses von DataSet-Schemas</span><span class="sxs-lookup"><span data-stu-id="a2a14-102">Summary of the DataSet Schema Inference Process</span></span>
<span data-ttu-id="a2a14-103">Während des Rückschlussprozesses wird zunächst anhand des XML-Dokuments bestimmt, welche Elemente als Tabellen hergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a2a14-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="a2a14-104">Anschließend werden aus der übrigen XML die Spalten für diese Tabellen ermittelt.</span><span class="sxs-lookup"><span data-stu-id="a2a14-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="a2a14-105">Bei geschachtelten Tabellen werden beim Rückschlussprozess geschachtelte <xref:System.Data.DataRelation>-Objekte und geschachtelte <xref:System.Data.ForeignKeyConstraint>-Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="a2a14-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="a2a14-106">Im folgenden finden Sie eine kurze Zusammenfassung der Inferenz Regeln:</span><span class="sxs-lookup"><span data-stu-id="a2a14-106">The following is a brief summary of inference rules:</span></span>  
  
- <span data-ttu-id="a2a14-107">Elemente mit Attributen werden als Tabellen hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a2a14-107">Elements that have attributes are inferred as tables.</span></span>  
  
- <span data-ttu-id="a2a14-108">Elemente mit untergeordneten Elementen werden als Tabellen hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a2a14-108">Elements that have child elements are inferred as tables.</span></span>  
  
- <span data-ttu-id="a2a14-109">Sich wiederholende Elemente werden als einzelne Tabelle hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a2a14-109">Elements that repeat are inferred as a single table.</span></span>  
  
- <span data-ttu-id="a2a14-110">Ein Dokument- oder Stammelement, das keine Attribute und keine untergeordneten Elemente aufweist, die als Spalten hergeleitet würden, wird als <xref:System.Data.DataSet> hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a2a14-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="a2a14-111">Andernfalls wird das Dokumentelement als Tabelle hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a2a14-111">Otherwise, the document element is inferred as a table.</span></span>  
  
- <span data-ttu-id="a2a14-112">Attribute werden als Spalten hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a2a14-112">Attributes are inferred as columns.</span></span>  
  
- <span data-ttu-id="a2a14-113">Elemente, die keine Attribute oder untergeordnete Elemente aufweisen und sich nicht wiederholen, werden als Spalten hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="a2a14-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
- <span data-ttu-id="a2a14-114">Für Elemente, die als geschachtelte Tabellen innerhalb anderer Elemente abgeleitet werden, die auch als Tabellen abgeleitet werden, wird eine geschachtelte **DataRelations** -Beziehung zwischen den beiden Tabellen erstellt.</span><span class="sxs-lookup"><span data-stu-id="a2a14-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="a2a14-115">Eine neue Primärschlüssel Spalte mit dem Namen **TableName_Id** wird beiden Tabellen hinzugefügt und von der **DataRelations**verwendet.</span><span class="sxs-lookup"><span data-stu-id="a2a14-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="a2a14-116">Eine fremd **Schlüssel Einschränkung** wird zwischen den beiden Tabellen mithilfe der **TableName_Id** -Spalte erstellt.</span><span class="sxs-lookup"><span data-stu-id="a2a14-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
- <span data-ttu-id="a2a14-117">Für Elemente, die als Tabellen abgeleitet werden und Text enthalten, aber keine untergeordneten Elemente enthalten, wird für den Text der einzelnen Elemente eine neue Spalte mit dem Namen **TableName_Text** erstellt.</span><span class="sxs-lookup"><span data-stu-id="a2a14-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="a2a14-118">Bei einem als Tabelle hergeleiteten Element, das sowohl Text als auch untergeordnete Elemente aufweist, wird der Text ignoriert.</span><span class="sxs-lookup"><span data-stu-id="a2a14-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2a14-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2a14-119">See also</span></span>

- [<span data-ttu-id="a2a14-120">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="a2a14-120">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="a2a14-121">Laden eines DataSet aus XML</span><span class="sxs-lookup"><span data-stu-id="a2a14-121">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="a2a14-122">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="a2a14-122">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="a2a14-123">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="a2a14-123">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="a2a14-124">DataSets, DataTables und DataViews</span><span class="sxs-lookup"><span data-stu-id="a2a14-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="a2a14-125">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a2a14-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
