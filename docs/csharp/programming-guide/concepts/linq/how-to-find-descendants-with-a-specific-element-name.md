---
title: 'Vorgehensweise: Suchen nach Nachfolgern mit einem bestimmten Elementnamen (C#)'
ms.date: 07/20/2015
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
ms.openlocfilehash: b3200a2fdf75dbf52079a2b3d27aa1a88d313406
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141080"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a>Vorgehensweise: Suchen nach Nachfolgern mit einem bestimmten Elementnamen (C#)
Es kann vorkommen, dass Sie alle Nachfolgerelemente mit einem bestimmten Namen ermitteln möchten. Dazu könnten Sie Code schreiben, der alle Nachfolgerelemente durchläuft, einfacher ist es aber, die <xref:System.Xml.Linq.XContainer.Descendants%2A>-Achse zu verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie Sie Nachfolgerelemente anhand des Elementnamens ermitteln können:  
  
```csharp  
XElement root = XElement.Parse(@"<root>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
IEnumerable<string> textSegs =  
    from seg in root.Descendants("t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```output  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird dieselbe Abfrage für XML in einem Namespace gezeigt. Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).  
  
```csharp  
XElement root = XElement.Parse(@"<root xmlns='http://www.adatum.com'>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<string> textSegs =  
    from seg in root.Descendants(ad + "t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```output  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Xml.Linq.XContainer.Descendants%2A>
