---
title: 'Beispiel-XSD-Datei: Kunden und Bestellungen'
description: Diese XSD-Datei wird in verschiedenen Beispielen in der LINQ to XML-Dokumentation verwendet. Sie ist eine Schemadefinition für eine XML-Beispieldatei mit Kunden und Bestellungen.
ms.date: 07/20/2015
ms.assetid: ef9911a3-7ac4-44fd-b36e-a0c0ad0a157d
ms.openlocfilehash: 2fd4ce6ebc4c9b5d222ac86fe8dc6746d9126da0
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302424"
---
# <a name="sample-xsd-file-customers-and-orders"></a><span data-ttu-id="42bab-104">XSD-Beispieldatei: Kunden und Bestellungen</span><span class="sxs-lookup"><span data-stu-id="42bab-104">Sample XSD File: Customers and Orders</span></span>
<span data-ttu-id="42bab-105">Die folgende XSD-Datei wird in verschiedenen Beispielen in der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Dokumentation verwendet.</span><span class="sxs-lookup"><span data-stu-id="42bab-105">The following XSD file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="42bab-106">Diese Datei enthält eine Schemadefinition für die [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="42bab-106">This file contains a schema definition for the [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span> <span data-ttu-id="42bab-107">Das Schema verwendet die XSD-Funktionen `xs:key` und `xs:keyref`, um festzulegen, dass das `CustomerID`-Attribut des `Customer`-Elements ein Schlüssel ist, und um eine Beziehung zwischen dem `CustomerID`-Element in jedem `Order`-Element und dem `CustomerID`-Attribut in jedem `Customer`-Element einzurichten.</span><span class="sxs-lookup"><span data-stu-id="42bab-107">The schema uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>  
  
 <span data-ttu-id="42bab-108">Ein Beispiel für das Schreiben von LINQ-Abfragen mit der `Join`-Klausel, die von dieser Beziehung profitieren, finden Sie unter [Vorgehensweise: Verknüpfen von zwei Auflistungen (LINQ to XML) (C#)](./how-to-join-two-collections-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="42bab-108">For an example of writing LINQ queries that take advantage of this relationship using the `Join` clause, see [How to join two collections (LINQ to XML) (C#)](./how-to-join-two-collections-linq-to-xml.md).</span></span>  
  
## <a name="customersordersxsd"></a><span data-ttu-id="42bab-109">CustomersOrders.xsd</span><span class="sxs-lookup"><span data-stu-id="42bab-109">CustomersOrders.xsd</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<xs:schema xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name='Root'>  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name='Customers'>  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name='Customer' type='CustomerType' minOccurs='0' maxOccurs='unbounded' />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name='Orders'>  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name='Order' type='OrderType' minOccurs='0' maxOccurs='unbounded' />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:sequence>  
    </xs:complexType>  
    <xs:key name='CustomerIDKey'>  
      <xs:selector xpath='Customers/Customer'/>  
      <xs:field xpath='@CustomerID'/>  
    </xs:key>  
    <xs:keyref name='CustomerIDKeyRef' refer='CustomerIDKey'>  
      <xs:selector xpath='Orders/Order'/>  
      <xs:field xpath='CustomerID'/>  
    </xs:keyref>  
  </xs:element>  
  <xs:complexType name='CustomerType'>  
    <xs:sequence>  
      <xs:element name='CompanyName' type='xs:string'/>  
      <xs:element name='ContactName' type='xs:string'/>  
      <xs:element name='ContactTitle' type='xs:string'/>  
      <xs:element name='Phone' type='xs:string'/>  
      <xs:element name='Fax' minOccurs='0' type='xs:string'/>  
      <xs:element name='FullAddress' type='AddressType'/>  
    </xs:sequence>  
    <xs:attribute name='CustomerID' type='xs:token'/>  
  </xs:complexType>  
  <xs:complexType name='AddressType'>  
    <xs:sequence>  
      <xs:element name='Address' type='xs:string'/>  
      <xs:element name='City' type='xs:string'/>  
      <xs:element name='Region' type='xs:string'/>  
      <xs:element name='PostalCode' type='xs:string' />  
      <xs:element name='Country' type='xs:string'/>  
    </xs:sequence>  
    <xs:attribute name='CustomerID' type='xs:token'/>  
  </xs:complexType>  
  <xs:complexType name='OrderType'>  
    <xs:sequence>  
      <xs:element name='CustomerID' type='xs:token'/>  
      <xs:element name='EmployeeID' type='xs:token'/>  
      <xs:element name='OrderDate' type='xs:dateTime'/>  
      <xs:element name='RequiredDate' type='xs:dateTime'/>  
      <xs:element name='ShipInfo' type='ShipInfoType'/>  
    </xs:sequence>  
  </xs:complexType>  
  <xs:complexType name='ShipInfoType'>  
    <xs:sequence>  
      <xs:element name='ShipVia' type='xs:integer'/>  
      <xs:element name='Freight' type='xs:decimal'/>  
      <xs:element name='ShipName' type='xs:string'/>  
      <xs:element name='ShipAddress' type='xs:string'/>  
      <xs:element name='ShipCity' type='xs:string'/>  
      <xs:element name='ShipRegion' type='xs:string'/>  
      <xs:element name='ShipPostalCode' type='xs:string'/>  
      <xs:element name='ShipCountry' type='xs:string'/>  
    </xs:sequence>  
    <xs:attribute name='ShippedDate' type='xs:dateTime'/>  
  </xs:complexType>  
</xs:schema>  
```  
