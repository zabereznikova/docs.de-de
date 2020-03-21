---
title: Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)
ms.date: 03/30/2017
ms.assetid: 8f6cd04d-6197-4bc4-9096-8c51c7e4acae
ms.openlocfilehash: d32b5cb86bc5a138f9a5f438629d8e231be4ba94
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151168"
---
# <a name="deriving-dataset-relational-structure-from-xml-schema-xsd"></a><span data-ttu-id="83217-102">Ableiten einer relationalen DataSet-Struktur aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="83217-102">Deriving DataSet Relational Structure from XML Schema (XSD)</span></span>
<span data-ttu-id="83217-103">Dieser Abschnitt enthält eine Übersicht über das Erstellen des relationalen Schemas eines `DataSet` aus einem XSD-Schemadokument (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="83217-103">This section provides an overview of how the relational schema of a `DataSet` is built from an XML Schema definition language (XSD) schema document.</span></span> <span data-ttu-id="83217-104">Im Allgemeinen wird `complexType` für jedes untergeordnete Element eines Schemaelements `DataSet`eine Tabelle im generiert.</span><span class="sxs-lookup"><span data-stu-id="83217-104">In general, for each `complexType` child element of a schema element, a table is generated in the `DataSet`.</span></span> <span data-ttu-id="83217-105">Die Tabellenstruktur wird durch die Definition des komplexen Typs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="83217-105">The table structure is determined by the definition of the complex type.</span></span> <span data-ttu-id="83217-106">Tabellen werden in `DataSet` der für Elemente der obersten Ebene im Schema erstellt.</span><span class="sxs-lookup"><span data-stu-id="83217-106">Tables are created in the `DataSet` for top-level elements in the schema.</span></span> <span data-ttu-id="83217-107">Eine Tabelle wird jedoch nur für `complexType` ein Element `complexType` der obersten Ebene `complexType` erstellt, wenn das `complexType` Element in einem `DataTable` anderen `DataSet`Element verschachtelt ist.</span><span class="sxs-lookup"><span data-stu-id="83217-107">However, a table is only created for a top-level `complexType` element when the `complexType` element is nested inside another `complexType` element, in which case the nested `complexType` element is mapped to a `DataTable` within the `DataSet`.</span></span>  
  
 <span data-ttu-id="83217-108">Weitere Informationen zum XSD finden Sie im [XML-Schema-Teil 0: Primer-Schema-Teil 0: Primer-Schema](https://www.w3.org/TR/xmlschema-0/), [im XML-Schema Teil 1: Structures-Empfehlung](https://www.w3.org/TR/xmlschema-1/)und in der [XML-Schema-Empfehlung 2: Datentypen-](https://www.w3.org/TR/xmlschema-2/)</span><span class="sxs-lookup"><span data-stu-id="83217-108">For more information about the XSD, see the World Wide Web Consortium (W3C) [XML Schema Part 0: Primer Recommendation](https://www.w3.org/TR/xmlschema-0/), the [XML Schema Part 1: Structures Recommendation](https://www.w3.org/TR/xmlschema-1/), and the [XML Schema Part 2: Datatypes Recommendation](https://www.w3.org/TR/xmlschema-2/).</span></span>  
  
 <span data-ttu-id="83217-109">Im folgenden Beispiel wird `customers` ein XML-Schema `MyDataSet` veranschaulicht, bei dem es sich um das untergeordnete Element des Elements handelt, bei dem es sich um ein **DataSet-Element** handelt.</span><span class="sxs-lookup"><span data-stu-id="83217-109">The following example demonstrates an XML Schema where `customers` is the child element of the `MyDataSet` element, which is a **DataSet** element.</span></span>  
  
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
  
 <span data-ttu-id="83217-110">Im vorherigen Beispiel ist das `customers`-Element ein Element mit komplexem Typ.</span><span class="sxs-lookup"><span data-stu-id="83217-110">In the preceding example, the element `customers` is a complex type element.</span></span> <span data-ttu-id="83217-111">Daher wird die Definition des komplexen Typs analysiert, und der Zuordnungsprozess erstellt die folgende Tabelle.</span><span class="sxs-lookup"><span data-stu-id="83217-111">Therefore, the complex type definition is parsed, and the mapping process creates the following table.</span></span>  
  
```text  
Customers (CustomerID, CompanyName, Phone)  
```  
  
 <span data-ttu-id="83217-112">Der Datentyp jeder Spalte in der Tabelle wird aus dem XML-Schematyp des entsprechenden angegebenen Elements oder Attributs abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="83217-112">The data type of each column in the table is derived from the XML Schema type of the corresponding element or attribute specified.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83217-113">Wenn das `customers` Element aus einem einfachen XML-Schema-Datentyp wie **Ganzzahl**ist, wird keine Tabelle generiert.</span><span class="sxs-lookup"><span data-stu-id="83217-113">If the element `customers` is of a simple XML Schema data type such as **integer**, no table is generated.</span></span> <span data-ttu-id="83217-114">Tabellen werden nur für Elemente auf oberster Ebene erstellt, bei denen es sich um komplexe Typen handelt.</span><span class="sxs-lookup"><span data-stu-id="83217-114">Tables are only created for the top-level elements that are complex types.</span></span>  
  
 <span data-ttu-id="83217-115">Im folgenden XML-Schema enthält das **Schemaelement** zwei untergeordnete Elementelemente `InStateCustomers` und `OutOfStateCustomers`.</span><span class="sxs-lookup"><span data-stu-id="83217-115">In the following XML Schema, the **Schema** element has two element children, `InStateCustomers` and `OutOfStateCustomers`.</span></span>  
  
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
  
 <span data-ttu-id="83217-116">Die beiden untergeordneten Elemente `InStateCustomers` und `OutOfStateCustomers` sind Elemente komplexen Typs (`customerType`).</span><span class="sxs-lookup"><span data-stu-id="83217-116">Both the `InStateCustomers` and the `OutOfStateCustomers` child elements are complex type elements (`customerType`).</span></span> <span data-ttu-id="83217-117">Daher generiert der Zuordnungsprozess die folgenden `DataSet`beiden identischen Tabellen im .</span><span class="sxs-lookup"><span data-stu-id="83217-117">Therefore, the mapping process generates the following two identical tables in the `DataSet`.</span></span>  
  
```text  
InStateCustomers (CustomerID, CompanyName, Phone)  
OutOfStateCustomers (CustomerID, CompanyName, Phone)  
```  
  
## <a name="in-this-section"></a><span data-ttu-id="83217-118">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="83217-118">In This Section</span></span>  
 [<span data-ttu-id="83217-119">Zuordnen von XML Schema (XSD)-Schlüsseleinschränkungen zu DataSet-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="83217-119">Mapping XML Schema (XSD) Constraints to DataSet Constraints</span></span>](mapping-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 <span data-ttu-id="83217-120">Beschreibt die XML-Schemaelemente, die zum Erstellen `DataSet`eindeutiger und Fremdschlüsseleinschränkungen in einem verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="83217-120">Describes the XML Schema elements used to create unique and foreign key constraints in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="83217-121">Generieren von DataSet-Beziehungen aus einem XML-Schema (XSD)</span><span class="sxs-lookup"><span data-stu-id="83217-121">Generating DataSet Relations from XML Schema (XSD)</span></span>](generating-dataset-relations-from-xml-schema-xsd.md)  
 <span data-ttu-id="83217-122">Beschreibt die XML-Schemaelemente, die zum `DataSet`Erstellen von Beziehungen zwischen Tabellenspalten in einem verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="83217-122">Describes the XML Schema elements used to create relations between table columns in a `DataSet`.</span></span>  
  
 [<span data-ttu-id="83217-123">XML-Schemaeinschränkungen und -beziehungen</span><span class="sxs-lookup"><span data-stu-id="83217-123">XML Schema Constraints and Relationships</span></span>](xml-schema-constraints-and-relationships.md)  
 <span data-ttu-id="83217-124">Beschreibt, wie Beziehungen implizit erstellt werden, wenn XML-Schemaelemente zum Erstellen von Einschränkungen in einem `DataSet`erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="83217-124">Describes how relations are created implicitly when using XML Schema elements to create constraints in a `DataSet`.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="83217-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="83217-125">Related Sections</span></span>  
 [<span data-ttu-id="83217-126">Verwenden von XML in einem "DataSet"</span><span class="sxs-lookup"><span data-stu-id="83217-126">Using XML in a DataSet</span></span>](using-xml-in-a-dataset.md)  
 <span data-ttu-id="83217-127">Beschreibt das Laden und Beibehalten der relationalen Struktur und der Daten in einem `DataSet` als XML-Daten.</span><span class="sxs-lookup"><span data-stu-id="83217-127">Describes how to load and persist the relational structure and data in a `DataSet` as XML data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83217-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="83217-128">See also</span></span>

- [<span data-ttu-id="83217-129">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="83217-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
