---
title: Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: b0082b534b8df10ac5277cf2f5aa5b2d2e40c11b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204624"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a><span data-ttu-id="a74fe-102">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a74fe-102">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>
<span data-ttu-id="a74fe-103">Die XSD-Sprache (XML Schema Definition Language) ermöglicht Einschränkungen, die Sie für die Elemente und Attribute angeben können, die durch XSD definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a74fe-103">The XML Schema definition language (XSD) allows constraints to be specified on the elements and attributes it defines.</span></span> <span data-ttu-id="a74fe-104">Beim Zuordnen eines XML-Schemas zu einem relationalen Schema in einem <xref:System.Data.DataSet>werden XML-Schema Einschränkungen den entsprechenden relationalen Einschränkungen für die Tabellen und Spalten im **DataSet**zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a74fe-104">When mapping an XML Schema to relational schema in a <xref:System.Data.DataSet>, XML Schema constraints are mapped to appropriate relational constraints on the tables and columns within the **DataSet**.</span></span>  
  
 <span data-ttu-id="a74fe-105">In diesem Abschnitt wird die Zuordnung der folgenden XML-Schemaeinschränkungen behandelt:</span><span class="sxs-lookup"><span data-stu-id="a74fe-105">This section discusses the mapping of the following XML Schema constraints:</span></span>  
  
- <span data-ttu-id="a74fe-106">Die Eindeutigkeits Einschränkung, die mit dem **Unique** -Element angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a74fe-106">The uniqueness constraint specified using the **unique** element.</span></span>  
  
- <span data-ttu-id="a74fe-107">Die Schlüssel Einschränkung, die mit dem **Key** -Element angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a74fe-107">The key constraint specified using the **key** element.</span></span>  
  
- <span data-ttu-id="a74fe-108">Die keyref-Einschränkung, die mit dem **keyref** -Element angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a74fe-108">The keyref constraint specified using the **keyref** element.</span></span>  
  
 <span data-ttu-id="a74fe-109">Mit einer Einschränkung für ein Element oder Attribut geben Sie bestimmte Beschränkungen für den Wert des Elements in einer beliebigen Instanz des Dokuments an.</span><span class="sxs-lookup"><span data-stu-id="a74fe-109">By using a constraint on an element or attribute, you specify certain restrictions on the values of the element in any instance of the document.</span></span> <span data-ttu-id="a74fe-110">Eine Schlüssel Einschränkung für ein untergeordnetes **CustomerID-** Element eines **Customer** -Elements im Schema gibt beispielsweise an, dass die Werte des untergeordneten **CustomerID-** Elements in jeder Dokument Instanz eindeutig sein müssen und dass NULL-Werte nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="a74fe-110">For example, a key constraint on a **CustomerID** child element of a **Customer** element in the schema indicates that the values of the **CustomerID** child element must be unique in any document instance, and that null values are not allowed.</span></span>  
  
 <span data-ttu-id="a74fe-111">Einschränkungen können auch zwischen Elementen und Attributen in einem Dokument angegeben werden, um eine Beziehung innerhalb des Dokuments zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a74fe-111">Constraints can also be specified between elements and attributes in a document, in order to establish a relationship within the document.</span></span> <span data-ttu-id="a74fe-112">Die key-Einschränkung und die keyref-Einschränkung werden im Schema verwendet, um Einschränkungen innerhalb des Dokuments anzugeben, die zu einer Beziehung zwischen Dokumentelementen und Attributen führen.</span><span class="sxs-lookup"><span data-stu-id="a74fe-112">The key and keyref constraints are used in the schema to specify the constraints within the document, resulting in a relationship between document elements and attributes.</span></span>  
  
 <span data-ttu-id="a74fe-113">Der Zuordnungsprozess konvertiert diese Schema Einschränkungen in entsprechende Einschränkungen für die Tabellen, die innerhalb des **DataSets**erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a74fe-113">The mapping process converts these schema constraints into appropriate constraints on the tables created within the **DataSet**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a74fe-114">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a74fe-114">In This Section</span></span>  
 [<span data-ttu-id="a74fe-115">Zuordnen von eindeutigen XML Schema-Einschränkungen (XSD)zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a74fe-115">Map unique XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="a74fe-116">Beschreibt die XML-Schema Elemente, die verwendet werden, um UNIQUE-Einschränkungen in einem **DataSet**zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a74fe-116">Describes the XML Schema elements used to create unique constraints in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="a74fe-117">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a74fe-117">Map key XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="a74fe-118">Beschreibt die XML-Schema Elemente, mit denen Schlüssel Einschränkungen (Unique-Einschränkungen, bei denen NULL-Werte nicht zulässig sind) in einem **DataSet**erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a74fe-118">Describes the XML Schema elements used to create key constraints (unique constraints where null values are not allowed) in a **DataSet**.</span></span>  
  
 [<span data-ttu-id="a74fe-119">Zuordnen von keyref-XML Schema-Einschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="a74fe-119">Map keyref XML Schema (XSD) Constraints to DataSet Constraints</span></span>](map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="a74fe-120">Beschreibt die XML-Schema Elemente, die verwendet werden, um keyref-Einschränkungen (Foreign Key) in einem **DataSet**zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a74fe-120">Describes the XML Schema elements used to create keyref (foreign key) constraints in a **DataSet**.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a74fe-121">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a74fe-121">Related Sections</span></span>  
 [<span data-ttu-id="a74fe-122">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="a74fe-122">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 <span data-ttu-id="a74fe-123">Beschreibt die relationale Struktur bzw. das Schema eines **DataSets** , das aus einem XSD-Schema erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a74fe-123">Describes the relational structure, or schema, of a **DataSet** that is created from XSD schema.</span></span>  
  
 [<span data-ttu-id="a74fe-124">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="a74fe-124">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="a74fe-125">Beschreibt die XML-Schema Elemente, die verwendet werden, um Beziehungen zwischen Tabellen Spalten in einem **DataSet**zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a74fe-125">Describes the XML Schema elements used to create relations between table columns in a **DataSet**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a74fe-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a74fe-126">See also</span></span>

- [<span data-ttu-id="a74fe-127">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="a74fe-127">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
