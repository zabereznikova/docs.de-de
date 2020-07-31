---
title: 'Vorgehensweise: Abfragen von LINQ to XML mit XPath (C#)'
description: Sie können in C# Erweiterungsmethoden verwenden, um einen XML-Baum mithilfe von XPath abzufragen. Im Allgemeinen wird die Verwendung von XPath mit LINQ to XML nicht empfohlen.
ms.date: 07/20/2015
ms.assetid: ee5af263-4ab1-45e5-b792-33a3221b426d
ms.openlocfilehash: fff45a93380b5af85aa640fc690783cc95e6298b
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104340"
---
# <a name="how-to-query-linq-to-xml-using-xpath-c"></a>Vorgehensweise: Abfragen von LINQ to XML mit XPath (C#)
Dieses Thema führt Sie in die Erweiterungsmethoden ein, mit denen Sie zum Abfragen einer XML-Struktur XPath verwenden können. Ausführliche Informationen zum Verwenden dieser Erweiterungsmethoden finden Sie unter <xref:System.Xml.XPath.Extensions?displayProperty=nameWithType>.  
  
 Sofern Sie keinen besonderen Grund dafür haben, Abfragen mit XPath zu schreiben, z. B. weil in großem Maße Legacy-Code verwendet wird, wird die Verwendung von XPath mit LINQ to XML nicht empfohlen. XPath-Abfragen sind nicht so leistungsfähig wie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine kleine XML-Struktur und verwendet zum Auswählen eines Satzes von Elementen <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A>.  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", 1),  
    new XElement("Child1", 2),  
    new XElement("Child1", 3),  
    new XElement("Child2", 4),  
    new XElement("Child2", 5),  
    new XElement("Child2", 6)  
);  
IEnumerable<XElement> list = root.XPathSelectElements("./Child2");  
foreach (XElement el in list)  
    Console.WriteLine(el);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Child2>4</Child2>  
<Child2>5</Child2>  
<Child2>6</Child2>  
```  
  