---
title: 'Beispiel-XML-Datei: Typische Bestellung in einem Namespace'
description: Diese XML-Datei wird in verschiedenen Beispielen in der LINQ to XML-Dokumentation verwendet. Bei der Datei handelt es sich um einen typischen Auftrag. Der XML-Code befindet sich in einem Namespace.
ms.date: 07/20/2015
ms.assetid: 84dc3339-ea32-4ccc-9af6-ab38ddfecced
ms.openlocfilehash: 698fb8711ad86e2739f1d8485747d3c56eb71d46
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302450"
---
# <a name="sample-xml-file-typical-purchase-order-in-a-namespace"></a><span data-ttu-id="16e66-105">Beispiel-XML-Datei: Typische Bestellung in einem Namespace</span><span class="sxs-lookup"><span data-stu-id="16e66-105">Sample XML File: Typical Purchase Order in a Namespace</span></span>
<span data-ttu-id="16e66-106">Die folgende XML-Datei wird in verschiedenen Beispielen in der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Dokumentation verwendet.</span><span class="sxs-lookup"><span data-stu-id="16e66-106">The following XML file is used in various examples in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] documentation.</span></span> <span data-ttu-id="16e66-107">Dabei handelt es sich um einen typischen Auftrag.</span><span class="sxs-lookup"><span data-stu-id="16e66-107">This file is a typical purchase order.</span></span> <span data-ttu-id="16e66-108">Der XML-Code befindet sich in einem Namespace.</span><span class="sxs-lookup"><span data-stu-id="16e66-108">The XML is in a namespace.</span></span>  
  
## <a name="purchaseorderinnamespacexml"></a><span data-ttu-id="16e66-109">PurchaseOrderInNamespace.xml</span><span class="sxs-lookup"><span data-stu-id="16e66-109">PurchaseOrderInNamespace.xml</span></span>  
  
```xml  
<?xml version="1.0"?>  
<aw:PurchaseOrder  
    aw:PurchaseOrderNumber="99503"  
    aw:OrderDate="1999-10-20"  
    xmlns:aw="http://www.adventure-works.com">  
  <aw:Address aw:Type="Shipping">  
    <aw:Name>Ellen Adams</aw:Name>  
    <aw:Street>123 Maple Street</aw:Street>  
    <aw:City>Mill Valley</aw:City>  
    <aw:State>CA</aw:State>  
    <aw:Zip>10999</aw:Zip>  
    <aw:Country>USA</aw:Country>  
  </aw:Address>  
  <aw:Address aw:Type="Billing">  
    <aw:Name>Tai Yee</aw:Name>  
    <aw:Street>8 Oak Avenue</aw:Street>  
    <aw:City>Old Town</aw:City>  
    <aw:State>PA</aw:State>  
    <aw:Zip>95819</aw:Zip>  
    <aw:Country>USA</aw:Country>  
  </aw:Address>  
  <aw:DeliveryNotes>Please leave packages in shed by driveway.</aw:DeliveryNotes>  
  <aw:Items>  
    <aw:Item aw:PartNumber="872-AA">  
      <aw:ProductName>Lawnmower</aw:ProductName>  
      <aw:Quantity>1</aw:Quantity>  
      <aw:USPrice>148.95</aw:USPrice>  
      <aw:Comment>Confirm this is electric</aw:Comment>  
    </aw:Item>  
    <aw:Item aw:PartNumber="926-AA">  
      <aw:ProductName>Baby Monitor</aw:ProductName>  
      <aw:Quantity>2</aw:Quantity>  
      <aw:USPrice>39.98</aw:USPrice>  
      <aw:ShipDate>1999-05-21</aw:ShipDate>  
    </aw:Item>  
  </aw:Items>  
</aw:PurchaseOrder>  
```  
