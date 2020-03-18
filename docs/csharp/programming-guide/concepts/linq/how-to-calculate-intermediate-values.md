---
title: 'Vorgehensweise: Berechnen von Zwischenwerten (C#)'
ms.date: 07/20/2015
ms.assetid: 7fd3001f-f8f9-4bce-879f-d4c7af8a04fe
ms.openlocfilehash: 3ead3bfb02f7c9192db96996c1f1e01a86a4191a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141452"
---
# <a name="how-to-calculate-intermediate-values-c"></a>Vorgehensweise: Berechnen von Zwischenwerten (C#)
In diesem Beispiel wird das Berechnen von Zwischenwerten gezeigt, die zum Sortieren, Filtern und Auswählen verwendet werden können.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel kommt die `Let`-Klausel zum Einsatz.  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> extensions =  
    from el in root.Elements("Data")  
    let extension = (decimal)el.Element("Quantity") * (decimal)el.Element("Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt. Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).  
  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Numerische Daten in einem Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<decimal> extensions =  
    from el in root.Elements(ad + "Data")  
    let extension = (decimal)el.Element(ad + "Quantity") * (decimal)el.Element(ad + "Price")  
    where extension >= 25  
    orderby extension  
    select extension;  
foreach (decimal ex in extensions)  
    Console.WriteLine(ex);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```output  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
