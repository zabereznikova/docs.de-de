---
title: Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d15aa02b41b9a34b00298aeb32d2e3998de8feba
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786333"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="7a7a6-102">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="7a7a6-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="7a7a6-103">Dieser Abschnitt enthält eine Übersicht über das Erstellen des relationalen Schemas eines `DataSet` aus einem XSD-Schemadokument (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="7a7a6-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="7a7a6-104">Im Allgemeinen wird für jedes `complexType` untergeordnete Element eines Schema Elements eine Tabelle `DataSet`in generiert.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="7a7a6-105">Die Tabellenstruktur wird durch die Definition des komplexen Typs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="7a7a6-106">Tabellen werden in `DataSet` für Elemente der obersten Ebene im Schema erstellt.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="7a7a6-107">Allerdings wird eine Tabelle nur für ein Element der obersten Ebene `complexType` erstellt, wenn `complexType` das `complexType` Element in einem anderen `complexType` Element geschachtelt ist. in diesem Fall wird das geschachtelte `DataTable` Element einem `DataSet`in der zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="7a7a6-108">Weitere Informationen zu XSD finden Sie in der World Wide Web Consortium (W3C) [XML Schema Part 0: Empfehlung](https://www.w3.org/TR/xmlschema-0/)für das [XML-Schema Teil 1: Struktur Empfehlung](https://www.w3.org/TR/xmlschema-1/)und das [XML-Schema Teil 2: Empfehlungen zu Datentypen](https://www.w3.org/TR/xmlschema-2/).</span><span class="sxs-lookup"><span data-stu-id="7a7a6-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="7a7a6-109">Im folgenden Beispiel wird ein XML-Schema `customers` veranschaulicht, wobei das untergeordnete `MyDataSet` Element des-Elements ist, bei dem es sich um ein **DataSet** -Element handelt.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element name="customers" >   
           <xs:complexType >  
             <xs:sequence>  
               <xs:element name="CustomerID" type="xs:integer"   
                            minOccurs="0" />  
               <xs:element name="CompanyName" type="xs:string"   
                            minOccurs="0" />  
               <xs:element name="Phone" type="xs:string" />  
             </xs:sequence>  
           </xs:complexType>  
          </xs:element>  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="7a7a6-110">Im vorherigen Beispiel ist das `customers`-Element ein Element mit komplexem Typ.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="7a7a6-111">Daher wird die Definition des komplexen Typs analysiert, und der Zuordnungsprozess erstellt die folgende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```  
Customers (CustomerID , CompanyName, Phone)  
```  
  
 <span data-ttu-id="7a7a6-112">Der Datentyp jeder Spalte in der Tabelle wird aus dem XML-Schematyp des entsprechenden angegebenen Elements oder Attributs abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a7a6-113">Wenn das Element `customers` einen einfachen XML-Schema Datentyp wie " **Integer**" hat, wird keine Tabelle generiert.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="7a7a6-114">Tabellen werden nur für Elemente auf oberster Ebene erstellt, bei denen es sich um komplexe Typen handelt.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="7a7a6-115">Im folgenden XML-Schema verfügt das **Schema** Element über zwei untergeordnete Elemente `InStateCustomers` , `OutOfStateCustomers`und.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
```xml  
<xs:schema id="SomeID"   
            xmlns=""   
            xmlns:xs="http://www.w3.org/2001/XMLSchema"   
            xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
   <xs:element name="InStateCustomers" type="customerType" />  
   <xs:element name="OutOfStateCustomers" type="customerType" />  
    <xs:complexType name="customerType" >  
  
     </xs:complexType>  
  
   <xs:element name="MyDataSet" msdata:IsDataSet="true">  
     <xs:complexType>  
       <xs:choice maxOccurs="unbounded">  
         <xs:element ref="customers" />  
       </xs:choice>  
     </xs:complexType>  
   </xs:element>  
 </xs:schema>  
```  
  
 <span data-ttu-id="7a7a6-116">Die beiden untergeordneten Elemente `InStateCustomers` und `OutOfStateCustomers` sind Elemente komplexen Typs (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="7a7a6-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="7a7a6-117">Aus diesem Grund generiert der Mapping-Prozess die folgenden beiden identischen Tabellen `DataSet`in.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```  
InStateCustomers (CustomerID , CompanyName, Phone)  
OutOfStateCustomers (CustomerID , CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="7a7a6-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7a7a6-118">In This Section</span></span>  
 [<span data-ttu-id="7a7a6-119">Zuordnen von XML Schema-Schlüsseleinschränkungen (XSD) zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7a7a6-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="7a7a6-120">Beschreibt die XML-Schema Elemente, die zum Erstellen von Unique-und Foreign `DataSet`Key-Einschränkungen in einer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="7a7a6-121">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="7a7a6-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="7a7a6-122">Beschreibt die XML-Schema Elemente, die zum Erstellen von Beziehungen zwischen Tabellen `DataSet`Spalten in einem verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="7a7a6-123">XML-Schemaeinschränkungen und -beziehungen</span><span class="sxs-lookup"><span data-stu-id="7a7a6-123">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="7a7a6-124">Beschreibt, wie Beziehungen implizit erstellt werden, wenn XML-Schema Elemente zum Erstellen von `DataSet`Einschränkungen in verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7a7a6-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="7a7a6-125">Related Sections</span></span>  
 [<span data-ttu-id="7a7a6-126">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="7a7a6-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="7a7a6-127">Beschreibt, wie die relationale Struktur und die Daten in `DataSet` als XML-Daten geladen und persistent gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="7a7a6-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a7a6-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a7a6-128">See also</span></span>

- [<span data-ttu-id="7a7a6-129">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="7a7a6-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
