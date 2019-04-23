---
title: Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: a1690e99aeaeb7ed9c85fd28697ae22d34bb2018
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115647"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="e2291-102">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e2291-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="e2291-103">Die XSD-Sprache (XML Schema Definition Language) ermöglicht Einschränkungen, die Sie für die Elemente und Attribute angeben können, die durch XSD definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e2291-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="e2291-104">Beim Zuordnen von XML-Schema zu relationalen Schema in ein <xref:System.Data.DataSet>, entsprechenden relationalen Einschränkungen in den Tabellen und Spalten in XML-schemaeinschränkungen zugeordnet sind die **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e2291-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="e2291-105">In diesem Abschnitt wird die Zuordnung der folgenden XML-Schemaeinschränkungen behandelt:</span><span class="sxs-lookup"><span data-stu-id="e2291-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
-   <span data-ttu-id="e2291-106">Die Unique-Einschränkung angegeben wird, mit der **eindeutige** Element.</span><span class="sxs-lookup"><span data-stu-id="e2291-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
-   <span data-ttu-id="e2291-107">Die Key-Einschränkung angegeben wird, mit der **Schlüssel** Element.</span><span class="sxs-lookup"><span data-stu-id="e2291-107">The key constraint specified using the **key** element.</span></span>  
  
-   <span data-ttu-id="e2291-108">Die Keyref-Einschränkung angegeben wird, mit der **Keyref** Element.</span><span class="sxs-lookup"><span data-stu-id="e2291-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="e2291-109">Mit einer Einschränkung für ein Element oder Attribut geben Sie bestimmte Beschränkungen für den Wert des Elements in einer beliebigen Instanz des Dokuments an.</span><span class="sxs-lookup"><span data-stu-id="e2291-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="e2291-110">Z. B. eine schlüsseleinschränkung für ein **"CustomerID"** untergeordnetes Element des eine **Kunden** Elements im Schema gibt an, dass die Werte der **"CustomerID"** untergeordnetes Element muss in jeder Dokumentinstanz eindeutig und, dass null-Werte nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="e2291-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="e2291-111">Einschränkungen können auch zwischen Elementen und Attributen in einem Dokument angegeben werden, um eine Beziehung innerhalb des Dokuments zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2291-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="e2291-112">Die key-Einschränkung und die keyref-Einschränkung werden im Schema verwendet, um Einschränkungen innerhalb des Dokuments anzugeben, die zu einer Beziehung zwischen Dokumentelementen und Attributen führen.</span><span class="sxs-lookup"><span data-stu-id="e2291-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="e2291-113">Der Zuordnungsprozess konvertiert diese schemaeinschränkungen in die entsprechenden Einschränkungen für die Tabellen erstellt, die innerhalb der **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e2291-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2291-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e2291-114">In This Section</span></span>  
 [<span data-ttu-id="e2291-115">Zuordnen von eindeutigen XML Schema-Einschränkungen (XSD)zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e2291-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="e2291-116">Beschreibt die XML-Schema-Elemente, die zum Erstellen von unique-Einschränkungen in einer **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e2291-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="e2291-117">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e2291-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="e2291-118">Beschreibt die XML-Schema-Elemente, die zum Erstellen von Key-Einschränkungen (unique-Einschränkungen, in denen null-Werte sind nicht zulässig) in einem **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e2291-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="e2291-119">Zuordnen von keyref-XML Schema-Einschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e2291-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="e2291-120">Beschreibt die XML-Schema-Elemente, die zum Erstellen von Keyref-Einschränkungen (Fremdschlüssel) in einem **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e2291-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e2291-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e2291-121">Related Sections</span></span>  
 [<span data-ttu-id="e2291-122">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="e2291-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="e2291-123">Beschreibt die relationale Struktur bzw. das Schema, der eine **DataSet** , die aus XSD-Schema erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="e2291-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="e2291-124">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="e2291-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="e2291-125">Beschreibt die XML-Schema-Elemente, die zum Erstellen von Beziehungen zwischen Tabellenspalten in einer **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e2291-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2291-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2291-126">See also</span></span>

- [<span data-ttu-id="e2291-127">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="e2291-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
