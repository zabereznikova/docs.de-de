---
title: 'Vorgehensweise: Erstellen einer Hierarchie mittels Gruppierung (C#)'
description: Erfahren Sie, wie Sie Daten gruppieren und dann eine neue XML-Datei generieren, wobei die XML-Hierarchie die Gruppierung reflektiert.
ms.date: 07/20/2015
ms.assetid: 0213d59e-5f76-438c-9cab-4bf11f7b971d
ms.openlocfilehash: d9470ce9b9b7702cf9b835cb2143b6a36f3a254f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302918"
---
# <a name="how-to-create-hierarchy-using-grouping-c"></a><span data-ttu-id="dd389-103">Vorgehensweise: Erstellen einer Hierarchie mittels Gruppierung (C#)</span><span class="sxs-lookup"><span data-stu-id="dd389-103">How to create hierarchy using grouping (C#)</span></span>
<span data-ttu-id="dd389-104">Dieses Beispiel zeigt, wie Sie Daten gruppieren und anschließend anhand der Gruppierung XML generieren können.</span><span class="sxs-lookup"><span data-stu-id="dd389-104">This example shows how to group data, and then generate XML based on the grouping.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dd389-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd389-105">Example</span></span>  
 <span data-ttu-id="dd389-106">Dieses Beispiel gruppiert die Daten zuerst nach einer Kategorie, woraufhin eine neue XML-Datei generiert wird, in der die XML-Hierarchie die Gruppierung widerspiegelt.</span><span class="sxs-lookup"><span data-stu-id="dd389-106">This example first groups data by a category, then generates a new XML file in which the XML hierarchy reflects the grouping.</span></span>  
  
 <span data-ttu-id="dd389-107">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="dd389-107">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement doc = XElement.Load("Data.xml");  
var newData =  
    new XElement("Root",  
        from data in doc.Elements("Data")  
        group data by (string)data.Element("Category") into groupedData  
        select new XElement("Group",  
            new XAttribute("ID", groupedData.Key),  
            from g in groupedData  
            select new XElement("Data",  
                g.Element("Quantity"),  
                g.Element("Price")  
            )  
        )  
    );  
Console.WriteLine(newData);  
```  
  
 <span data-ttu-id="dd389-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="dd389-108">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Group ID="A">  
    <Data>  
      <Quantity>3</Quantity>  
      <Price>24.50</Price>  
    </Data>  
    <Data>  
      <Quantity>5</Quantity>  
      <Price>4.95</Price>  
    </Data>  
    <Data>  
      <Quantity>3</Quantity>  
      <Price>66.00</Price>  
    </Data>  
    <Data>  
      <Quantity>15</Quantity>  
      <Price>29.00</Price>  
    </Data>  
  </Group>  
  <Group ID="B">  
    <Data>  
      <Quantity>1</Quantity>  
      <Price>89.99</Price>  
    </Data>  
    <Data>  
      <Quantity>10</Quantity>  
      <Price>.99</Price>  
    </Data>  
    <Data>  
      <Quantity>8</Quantity>  
      <Price>6.99</Price>  
    </Data>  
  </Group>  
</Root>  
```  
