---
title: Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: 878e39af575328fb0abba096c327d36203a52231
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164804"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="e29b7-102">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="e29b7-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>

<span data-ttu-id="e29b7-103">Dieser Abschnitt enthält eine Übersicht über das Erstellen des relationalen Schemas eines `DataSet` aus einem XSD-Schemadokument (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="e29b7-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="e29b7-104">Im Allgemeinen wird für jedes untergeordnete `complexType` Element eines Schema Elements eine Tabelle in generiert `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="e29b7-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="e29b7-105">Die Tabellenstruktur wird durch die Definition des komplexen Typs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e29b7-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="e29b7-106">Tabellen werden in `DataSet` für Elemente der obersten Ebene im Schema erstellt.</span><span class="sxs-lookup"><span data-stu-id="e29b7-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="e29b7-107">Allerdings wird eine Tabelle nur für ein Element der obersten Ebene erstellt `complexType` , wenn das `complexType` Element in einem anderen Element geschachtelt ist `complexType` . in diesem Fall wird das geschachtelte `complexType` Element einem in `DataTable` der zugeordnet `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="e29b7-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="e29b7-108">Weitere Informationen zu XSD finden Sie in der Empfehlung zum XML- [Schema Part 0: Primer](https://www.w3.org/TR/xmlschema-0/)(World Wide Web Consortium (W3C), der Empfehlung zu [XML-Schema Teil 1: Strukturen](https://www.w3.org/TR/xmlschema-1/)und der [Empfehlung XML Schema Part 2: Datatypes](https://www.w3.org/TR/xmlschema-2/).</span><span class="sxs-lookup"><span data-stu-id="e29b7-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="e29b7-109">Im folgenden Beispiel wird ein XML-Schema veranschaulicht `customers` , wobei das untergeordnete Element des- `MyDataSet` Elements ist, bei dem es sich um ein **DataSet** -Element handelt.</span><span class="sxs-lookup"><span data-stu-id="e29b7-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
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
  
 <span data-ttu-id="e29b7-110">Im vorherigen Beispiel ist das `customers`-Element ein Element mit komplexem Typ.</span><span class="sxs-lookup"><span data-stu-id="e29b7-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="e29b7-111">Daher wird die Definition des komplexen Typs analysiert, und der Zuordnungsprozess erstellt die folgende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e29b7-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="e29b7-112">Der Datentyp jeder Spalte in der Tabelle wird aus dem XML-Schematyp des entsprechenden angegebenen Elements oder Attributs abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="e29b7-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e29b7-113">Wenn das Element `customers` einen einfachen XML-Schema Datentyp wie " **Integer**" hat, wird keine Tabelle generiert.</span><span class="sxs-lookup"><span data-stu-id="e29b7-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="e29b7-114">Tabellen werden nur für Elemente auf oberster Ebene erstellt, bei denen es sich um komplexe Typen handelt.</span><span class="sxs-lookup"><span data-stu-id="e29b7-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="e29b7-115">Im folgenden XML-Schema verfügt das **Schema** Element über zwei untergeordnete Elemente, `InStateCustomers` und `OutOfStateCustomers` .</span><span class="sxs-lookup"><span data-stu-id="e29b7-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
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
  
 <span data-ttu-id="e29b7-116">Die beiden untergeordneten Elemente `InStateCustomers` und `OutOfStateCustomers` sind Elemente komplexen Typs (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="e29b7-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="e29b7-117">Aus diesem Grund generiert der Mapping-Prozess die folgenden beiden identischen Tabellen in `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="e29b7-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="e29b7-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e29b7-118">In This Section</span></span>  

 [<span data-ttu-id="e29b7-119">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e29b7-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="e29b7-120">Beschreibt die XML-Schema Elemente, die zum Erstellen von Unique-und FOREIGN KEY-Einschränkungen in einer verwendet werden `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="e29b7-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="e29b7-121">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="e29b7-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="e29b7-122">Beschreibt die XML-Schema Elemente, die zum Erstellen von Beziehungen zwischen Tabellen Spalten in einem verwendet werden `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="e29b7-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="e29b7-123">XML-Schemaeinschränkungen und -beziehungen</span><span class="sxs-lookup"><span data-stu-id="e29b7-123">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="e29b7-124">Beschreibt, wie Beziehungen implizit erstellt werden, wenn XML-Schema Elemente zum Erstellen von Einschränkungen in verwendet werden `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="e29b7-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e29b7-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="e29b7-125">Related Sections</span></span>  

 [<span data-ttu-id="e29b7-126">Using XML in a DataSet (Verwenden von XML in einem DataSet)</span><span class="sxs-lookup"><span data-stu-id="e29b7-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="e29b7-127">Beschreibt, wie die relationale Struktur und die Daten in als XML-Daten geladen und persistent gespeichert werden `DataSet` .</span><span class="sxs-lookup"><span data-stu-id="e29b7-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e29b7-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e29b7-128">See also</span></span>

- [<span data-ttu-id="e29b7-129">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e29b7-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
