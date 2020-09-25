---
title: Zusammenfassung des Rückschlussprozesses von DataSet-Schemas
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 8d517487b96aa7f204ea9f25d326500db7df413a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198508"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a><span data-ttu-id="61815-102">Zusammenfassung des Rückschlussprozesses von DataSet-Schemas</span><span class="sxs-lookup"><span data-stu-id="61815-102">Summary of the DataSet Schema Inference Process</span></span>

<span data-ttu-id="61815-103">Während des Rückschlussprozesses wird zunächst anhand des XML-Dokuments bestimmt, welche Elemente als Tabellen hergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="61815-103">The inference process first determines, from the XML document, which elements will be inferred as tables.</span></span> <span data-ttu-id="61815-104">Anschließend werden aus der übrigen XML die Spalten für diese Tabellen ermittelt.</span><span class="sxs-lookup"><span data-stu-id="61815-104">From the remaining XML, the inference process determines the columns for those tables.</span></span> <span data-ttu-id="61815-105">Bei geschachtelten Tabellen werden beim Rückschlussprozess geschachtelte <xref:System.Data.DataRelation>-Objekte und geschachtelte <xref:System.Data.ForeignKeyConstraint>-Objekte erstellt.</span><span class="sxs-lookup"><span data-stu-id="61815-105">For nested tables, the inference process generates nested <xref:System.Data.DataRelation> and <xref:System.Data.ForeignKeyConstraint> objects.</span></span>  
  
 <span data-ttu-id="61815-106">Im folgenden finden Sie eine kurze Zusammenfassung der Inferenz Regeln:</span><span class="sxs-lookup"><span data-stu-id="61815-106">The following is a brief summary of inference rules:</span></span>  
  
- <span data-ttu-id="61815-107">Elemente mit Attributen werden als Tabellen hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="61815-107">Elements that have attributes are inferred as tables.</span></span>  
  
- <span data-ttu-id="61815-108">Elemente mit untergeordneten Elementen werden als Tabellen hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="61815-108">Elements that have child elements are inferred as tables.</span></span>  
  
- <span data-ttu-id="61815-109">Sich wiederholende Elemente werden als einzelne Tabelle hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="61815-109">Elements that repeat are inferred as a single table.</span></span>  
  
- <span data-ttu-id="61815-110">Ein Dokument- oder Stammelement, das keine Attribute und keine untergeordneten Elemente aufweist, die als Spalten hergeleitet würden, wird als <xref:System.Data.DataSet> hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="61815-110">If the document, or root, element has no attributes, and no child elements that would be inferred as columns, it is inferred as a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="61815-111">Andernfalls wird das Dokumentelement als Tabelle hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="61815-111">Otherwise, the document element is inferred as a table.</span></span>  
  
- <span data-ttu-id="61815-112">Attribute werden als Spalten hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="61815-112">Attributes are inferred as columns.</span></span>  
  
- <span data-ttu-id="61815-113">Elemente, die keine Attribute oder untergeordnete Elemente aufweisen und sich nicht wiederholen, werden als Spalten hergeleitet.</span><span class="sxs-lookup"><span data-stu-id="61815-113">Elements that have no attributes or child elements, and that do not repeat, are inferred as columns.</span></span>  
  
- <span data-ttu-id="61815-114">Für Elemente, die als geschachtelte Tabellen innerhalb anderer Elemente abgeleitet werden, die auch als Tabellen abgeleitet werden, wird eine geschachtelte **DataRelations** -Beziehung zwischen den beiden Tabellen erstellt.</span><span class="sxs-lookup"><span data-stu-id="61815-114">For elements that are inferred as nested tables within other elements that are also inferred as tables, a nested **DataRelation** is created between the two tables.</span></span> <span data-ttu-id="61815-115">Eine neue Primärschlüssel Spalte mit dem Namen **TableName_Id** wird beiden Tabellen hinzugefügt und von der **DataRelations**verwendet.</span><span class="sxs-lookup"><span data-stu-id="61815-115">A new, primary key column named **TableName_Id** is added to both tables and used by the **DataRelation**.</span></span> <span data-ttu-id="61815-116">Eine fremd **Schlüssel Einschränkung** wird zwischen den beiden Tabellen mithilfe der **TableName_Id** Spalte erstellt.</span><span class="sxs-lookup"><span data-stu-id="61815-116">A **ForeignKeyConstraint** is created between the two tables using the **TableName_Id** column.</span></span>  
  
- <span data-ttu-id="61815-117">Für Elemente, die als Tabellen abgeleitet werden und Text enthalten, aber keine untergeordneten Elemente enthalten, wird eine neue Spalte mit dem Namen **TableName_Text** für den Text der einzelnen Elemente erstellt.</span><span class="sxs-lookup"><span data-stu-id="61815-117">For elements that are inferred as tables and that contain text but have no child elements, a new column named **TableName_Text** is created for the text of each of the elements.</span></span> <span data-ttu-id="61815-118">Bei einem als Tabelle hergeleiteten Element, das sowohl Text als auch untergeordnete Elemente aufweist, wird der Text ignoriert.</span><span class="sxs-lookup"><span data-stu-id="61815-118">If an element is inferred as a table and has text, but also has child elements, the text is ignored.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61815-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61815-119">See also</span></span>

- [<span data-ttu-id="61815-120">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema</span><span class="sxs-lookup"><span data-stu-id="61815-120">Inferring DataSet Relational Structure from XML</span></span>](inferring-dataset-relational-structure-from-xml.md)
- [<span data-ttu-id="61815-121">Laden eines "DataSets" aus XML</span><span class="sxs-lookup"><span data-stu-id="61815-121">Loading a DataSet from XML</span></span>](loading-a-dataset-from-xml.md)
- [<span data-ttu-id="61815-122">Laden von DataSet-Schemainformationen aus XML</span><span class="sxs-lookup"><span data-stu-id="61815-122">Loading DataSet Schema Information from XML</span></span>](loading-dataset-schema-information-from-xml.md)
- [<span data-ttu-id="61815-123">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="61815-123">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)
- [<span data-ttu-id="61815-124">"DataSets", "DataTables" und "DataViews"</span><span class="sxs-lookup"><span data-stu-id="61815-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="61815-125">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="61815-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
